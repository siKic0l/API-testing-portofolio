# BUG-BOOK-001 — Internal Server Error When `firstname` Field Is Missing

## Bug Information

| Field | Value |
|------|--------|
| Bug ID | BUG-BOOK-001 |
| Module | Create Booking |
| Endpoint | POST /booking |
| Severity | High |
| Priority | High |
| Status | Open |
| Reported By | Nurrohmi Zaki |
| Report Date | August 7, 2026 |
| Related Test Case | TC-BOOK-CREATE-002 |

---

# Summary

The API returns an **Internal Server Error (500)** when the `firstname` field is omitted from the booking request body.

Instead of handling the missing required field gracefully, the server fails during request processing.

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
- Request uses `Content-Type: application/json`.

---

# Steps to Reproduce

1. Open Postman.
2. Create a **POST** request to `/booking`.
3. Remove the `firstname` field from the request body.
4. Send the request.
5. Observe the API response.

---

# Request Body

```json
{
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

- API handles the missing required field appropriately.
- No unexpected server error occurs.
- Response behavior remains consistent.

---

# Actual Result

- API returns **500 Internal Server Error**.
- The request is not handled gracefully.
- No meaningful validation response is returned.

---

# Impact

Clients cannot determine whether the request failed because of invalid input or because of a server-side issue.

Returning an Internal Server Error for client input validation may also expose weaknesses in server-side validation and reduce API reliability.

---

# Evidence

`projects/restful-booker/evidence/manual-testing/booking/create-booking/TC_BOOK_CREATE_002_FAIL.png`

---

# Suggested Fix

- Validate required request fields before processing the booking.
- Return an appropriate client error response (such as **400 Bad Request**) with a clear validation message instead of returning **500 Internal Server Error**.
