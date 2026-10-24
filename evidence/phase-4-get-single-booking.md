# Phase 4: Retrieve One Booking

## Execution details

- **Request method:** `GET`
- **Request URL:** `https://restful-booker.herokuapp.com/booking/1`
- **Observed status:** `200 OK`
- **Observed response time:** `814.75 ms`
- **Execution date:** 2026-10-24
- **Tool:** Postman

## Observed response

```json
{
  "firstname": "Susan",
  "lastname": "Wilson",
  "totalprice": 849,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2017-03-21",
    "checkout": "2019-01-05"
  },
  "additionalneeds": "Breakfast"
}
```

The response contains one booking object with the expected booking details, including nested `bookingdates`.

## Postman test result

The existing test named `Booking count is available` failed with:

```text
AssertionError: expected { firstname: 'Susan', …(5) } to be an array
```

This is a test-script mismatch, not evidence that the API request failed. The script was written for `GET /booking`, whose response is a collection. `GET /booking/1` returns one object, so an array-count assertion is not appropriate for this endpoint.

The Postman Console also reported:

```text
Total booking objects: undefined
```

That output is consistent with the same mismatch: the script attempted to count an object as if it were an array.

## Reproduction

1. Open Postman.
2. Send a `GET` request to `https://restful-booker.herokuapp.com/booking/1`.
3. Confirm the status and inspect the single booking object.
4. Use assertions appropriate for an object response, such as checking required fields and the nested `bookingdates` object.
5. Record the new execution date, response time, status, response body, and assertion results. The public demo data may change.
