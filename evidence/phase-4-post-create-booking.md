# Phase 4: Create a Booking

## Execution details

- **Request method:** `POST`
- **Request URL:** `https://restful-booker.herokuapp.com/booking`
- **Observed status:** `200 OK`
- **Observed response time:** `645 ms`
- **Execution date:** 2026-10-24
- **Tool:** Postman

## Request body

```json
{
  "firstname": "API",
  "lastname": "Tester",
  "totalprice": 100,
  "depositpaid": false,
  "bookingdates": {
    "checkin": "2026-11-01",
    "checkout": "2026-11-05"
  },
  "additionalneeds": "Breakfast"
}
```

## Observed response body

```json
{
  "bookingid": 3448,
  "booking": {
    "firstname": "API",
    "lastname": "Tester",
    "totalprice": 100,
    "depositpaid": false,
    "bookingdates": {
      "checkin": "2026-11-01",
      "checkout": "2026-11-05"
    },
    "additionalneeds": "Breakfast"
  }
}
```

The response returned booking ID `3448` and echoed the submitted booking data in the nested `booking` object.

## Postman test result

All four assertions passed:

- `Response is valid JSON`
- `Response contains a booking ID`
- `Response contains the created booking`
- `Created booking matches the request`

The script also saved the returned ID as the collection variable `createdBookingId`, so later requests can use:

```text
{{createdBookingId}}
```

The booking ID and response time are specific to this execution. A later run may return different values.

## Reproduction

1. Send the documented `POST /booking` request with the JSON body above.
2. Confirm the response status and inspect the returned `bookingid`.
3. Review the four post-response assertions.
4. Use `{{createdBookingId}}` in a later request to retrieve or update the created booking.
5. Record the metadata and response from the new execution rather than reusing this evidence.
