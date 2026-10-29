# Phase 4: Update Booking with PUT

## Execution details

- **Request method:** `PUT`
- **Request URL:** `https://restful-booker.herokuapp.com/booking/{bookingId}`
- **Execution date:** 2026-10-29
- **Tool:** Postman
- **Observed result:** `403 Forbidden`

## Test objective

Change the booking's `additionalneeds` value from `Breakfast` to `Lunch`.

## Request body

```json
{
  "firstname": "Phase",
  "lastname": "Four",
  "totalprice": 250,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-11-01",
    "checkout": "2026-11-05"
  },
  "additionalneeds": "Lunch"
}
```

## Investigation performed

- A fresh booking was created and successfully retrieved with `GET` before the update attempt.
- Authentication returned `200 OK` and a token.
- The PUT request used the documented token cookie format:

```text
Cookie: token=[REDACTED]
```

- The Postman Console was checked to confirm that the cookie header was sent.
- Stored cookies for the Restful Booker domain were cleared and the PUT request was retried.
- The PUT request continued to return `403 Forbidden`.

## Result

The update could not be verified. The test is marked **Blocked / Not verifiable**. This evidence does not establish that the API has a permanent defect; the service is a shared public demo environment and may have authentication or environment limitations.

The booking ID and token are not recorded as permanent project data.
