# Phase 4: Delete a Booking

## Execution details

- **Request method:** `DELETE`
- **Request URL:** `https://restful-booker.herokuapp.com/booking/913`
- **Observed status:** `201 Created`
- **Execution date:** 2026-11-01
- **Tool:** Postman

## Test objective

Delete the fresh booking created for this workflow and verify that it can no longer be retrieved.

## Preconditions

- A fresh booking was created with booking ID `913`.
- Authentication succeeded and returned a token.
- The token was sent in the request cookie.

## Delete request

The request used the documented token cookie format:

```text
Cookie: token=[REDACTED]
```

No request body was required.

## Verification request

After the DELETE request, a GET request was sent to:

```text
https://restful-booker.herokuapp.com/booking/913
```

The verification request returned `404 Not Found`, confirming that booking `913` was no longer available.

## Result

The booking deletion was verified successfully:

- DELETE request: `201 Created`
- Follow-up GET request: `404 Not Found`

The authentication token is intentionally not recorded.

## Reproduction

1. Create a fresh booking and record its returned booking ID.
2. Obtain an authentication token using the documented demo credentials.
3. Send `DELETE /booking/{bookingId}` with the token cookie.
4. Record the actual DELETE response.
5. Send `GET /booking/{bookingId}`.
6. Confirm and document the actual verification response.
