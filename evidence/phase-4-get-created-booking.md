# Phase 4: Retrieve the Created Booking

## Execution details

- **Request method:** `GET`
- **Request URL:** `https://restful-booker.herokuapp.com/booking/3448`
- **Observed status:** `200 OK`
- **Observed response time:** `2.34 seconds`
- **Execution date:** 2026-10-24
- **Tool:** Postman

## Postman test result

All three assertions passed:

- `Status is 200`
- `Response is a single booking object`
- `Booking has required fields`

The request used booking ID `3448`, which was returned by the earlier successful `POST /booking` execution. The request had no body, as expected for this `GET` request.

## Reproduction

1. Send a `GET` request to `https://restful-booker.herokuapp.com/booking/3448`.
2. Confirm the response status and inspect the booking object in the response body.
3. Run assertions appropriate for a single booking object.
4. Record the new execution date, response time, status, response body, and assertion results. The public demo API may reset or change its data.
