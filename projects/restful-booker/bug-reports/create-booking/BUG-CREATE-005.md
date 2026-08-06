# BUG-CREATE-005 — Internal Server Error When All Request Fields Are Null

## Bug Information

| Field | Value |
|------|--------|
| Bug ID | BUG-CREATE-005 |
| Module | Create Booking |
| Endpoint | POST /booking |
| Severity | High |
| Priority | High |
| Status | Open |
| Reported By | Nurrohmi Zaki |
| Report Date | August 7, 2026 |
| Related Test Case | TC-BOOK-CREATE-022 |

---

# Summary

The Create Booking endpoint returns an **Internal Server Error (500)** when all request fields are submitted with `null` values.

Instead of validating the request payload and returning an appropriate client error response, the server fails during request processing.

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
3. Replace all request field values with `null`.
4. Send the request.
5. Observe the API response.

---

# Request Body

```json
{
    "firstname": null,
    "lastname": null,
    "totalprice": null,
    "depositpaid": null,
    "bookingdates": null,
    "additionalneeds": null
}
```

---

# Expected Result

- API validates null values appropriately.
- No unexpected server error occurs.
- The API returns an appropriate validation response for invalid input.

---

# Actual Result

- API returned **500 Internal Server Error**.
- The request containing null values was not handled gracefully.
- No validation message was returned to indicate invalid input.

---

# Impact

The API fails when processing requests containing null values, making it difficult for API consumers to identify input validation issues.

Returning a server-side error for invalid client input reduces API reliability and indicates insufficient input validation.

---

# Evidence

`projects/restful-booker/evidence/manual-testing/booking/create-booking/TC_BOOK_CREATE_022_FAIL.png`

---

# Suggested Fix

- Validate all required fields before processing the request.
- Reject requests containing invalid `null` values with an appropriate client error response (such as **400 Bad Request**) instead of returning **500 Internal Server Error**.
- Return a descriptive validation message indicating which required fields cannot be null.
