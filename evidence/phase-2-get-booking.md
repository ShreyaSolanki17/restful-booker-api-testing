# Phase 2: List Bookings GET Request

## Execution details

- **Request method:** `GET`
- **Request URL:** `https://restful-booker.herokuapp.com/booking`
- **Observed status:** `200 OK`
- **Approximate response time:** `1.1 seconds`
- **Execution date:** 2026-10-24
- **Tool:** Postman

## Postman result

The Post-response script passed the test:

> Booking count is available

The Postman Console reported:

```text
Total booking objects: 3425
```

This count is the number of booking objects returned during this execution. It is not a permanent value: Restful Booker is a shared public demo API, so its data can change or reset between executions.

## What this request demonstrates

- `GET` requests retrieve data without creating or changing a booking.
- The `200 OK` status indicates that the server successfully returned a response for this request.
- The response body contains a collection of booking references.
- The post-response script checks that a booking count is available and reports the observed count in the Postman Console.

## Reproduction

1. Open Postman.
2. Send a `GET` request to `https://restful-booker.herokuapp.com/booking`.
3. Confirm the response status and inspect the response body.
4. Open the Postman Console to view the booking count reported by the script.
5. Record the new execution date, response time, status, and observed count. Do not assume they will match this evidence.
