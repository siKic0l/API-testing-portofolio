# BUG-BOOK-004 — Invalid Content-Type Header Is Accepted During Booking Creation

## Bug Information

| Field | Value |
|------|--------|
| Bug ID | BUG-BOOK-004 |
| Module | Create Booking |
| Endpoint | POST /booking |
| Severity | Medium |
| Priority | Medium |
| Status | Open |
| Reported By | Nurrohmi Zaki |
| Report Date | August 7, 2026 |
| Related Test Case | TC-BOOK-CREATE-019 |

---

# Summary

The Create Booking endpoint accepts requests with an invalid `Content-Type` header (`text/plain`) and still processes the booking successfully.

The API does not enforce Content-Type validation, allowing unsupported media types to be processed.

---

# Environment

| Item | Value |
|------|--------|
| Environment | Public Demo |
| Base URL | https://restful-booker.herokuapp.com |
| Method | POST |
| Endpoint | /booking |
| Tool | Postman |

---

# Preconditions

- RESTful Booker API is accessible.
- Internet connection is stable.

---

# Steps to Reproduce

1. Open Postman.
2. Create a **POST** request to `/booking`.
3. Set the request header:

```
Content-Type: text/plain
```

4. Send a valid booking payload.
5. Observe the API response.

---

# Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 150,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-08-01",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "Breakfast"
}
```

---

# Expected Result

- API rejects requests using an unsupported `Content-Type`.
- The request is not processed.
- An appropriate client error response (such as **415 Unsupported Media Type** or another validation response defined by the API) is returned.

---

# Actual Result

- API accepted the request even though the `Content-Type` header was set to `text/plain`.
- The booking was successfully created.
- No validation error related to the unsupported media type was returned.

---

# Impact

Clients can submit requests using unsupported media types, resulting in inconsistent API behavior and making request validation less reliable.

---

# Evidence

`projects/restful-booker/evidence/manual-testing/booking/create-booking/TC_BOOK_CREATE_019_FAIL.png`

---

# Suggested Fix

- Validate the `Content-Type` header before processing the request.
- Reject unsupported media types with an appropriate client error response (for example, **415 Unsupported Media Type**).
- Ensure only supported content types (such as `application/json`) are accepted for booking creation.
