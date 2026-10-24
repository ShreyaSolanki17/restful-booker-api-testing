# Phase 4: Obtain an Authentication Token

## Execution details

- **Request method:** `POST`
- **Request URL:** `https://restful-booker.herokuapp.com/auth`
- **Observed status:** `200 OK`
- **Observed response time:** `283.32 ms`
- **Execution date:** 2026-10-24
- **Tool:** Postman

## Request body

```json
{
  "username": "admin",
  "password": "password123"
}
```

These are the documented Restful Booker demo credentials. They are not personal credentials.

## Observed response body

The response contained a token. The token value is intentionally not recorded:

```json
{
  "token": "[REDACTED]"
}
```

The post-response script saved the token in the collection variable `authToken` for later authenticated requests.

## Postman test result

Both assertions passed:

- `Response is valid JSON`
- `Response contains a token`

The token itself must not be committed to the repository or included in screenshots.

## Reproduction

1. Send a `POST` request to `https://restful-booker.herokuapp.com/auth`.
2. Use the documented demo credentials in the JSON request body.
3. Confirm that the response contains a non-empty token.
4. Save the token to the Postman collection variable `authToken`.
5. Record the new execution date, response time, status, and assertion results without recording the token value.
