# BUG-CREATE-003 — Internal Server Error When an Empty JSON Object Is Submitted

## Bug Information

| Field | Value |
|------|--------|
| Bug ID | BUG-CREATE-003 |
| Module | Create Booking |
| Endpoint | POST /booking |
| Severity | High |
| Priority | High |
| Status | Open |
| Reported By | Nurrohmi Zaki |
| Report Date | August 7, 2026 |
| Related Test Case | TC-BOOK-CREATE-010 |

---

# Summary

The API returns an **Internal Server Error (500)** when an empty JSON object (`{}`) is submitted to the Create Booking endpoint.

Instead of validating the request payload and returning an appropriate client error, the server fails during request processing.

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
3. Set the request body to an empty JSON object (`{}`).
4. Send the request.
5. Observe the API response.

---

# Request Body

```json
{}
```

---

# Expected Result

- API rejects or handles the request consistently.
- No unexpected server error occurs.
- The API returns an appropriate validation response.

---

# Actual Result

- API returns **500 Internal Server Error**.
- The empty request payload is not handled gracefully.
- No meaningful validation message is returned.

---

# Impact

Clients receive a server-side error instead of a validation response for an invalid request payload.

This behavior reduces API reliability and makes it difficult for API consumers to distinguish between client-side input errors and server-side failures.

---

# Evidence

`projects/restful-booker/evidence/manual-testing/booking/create-booking/TC_BOOK_CREATE_010_FAIL.png`

---

# Suggested Fix

- Validate the request body before processing the booking creation.
- Reject empty JSON payloads with an appropriate client error response (such as **400 Bad Request**) instead of returning **500 Internal Server Error**.
- Return a descriptive validation message indicating that required booking fields are missing.
