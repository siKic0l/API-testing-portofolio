# BUG-CREATE-006 — API Accepts `null` Values for All Booking Fields

## Bug Information

| Field             | Value                                                                        |
| ----------------- | ---------------------------------------------------------------------------- |
| Bug ID            | BUG-CREATE-006                                                               |
| Module            | Create Booking                                                               |
| Endpoint          | POST /booking                                                                |
| Severity          | Medium                                                                       |
| Priority          | Medium                                                                       |
| Status            | Open                                                                         |
| Reported By       | Nurrohmi Zaki                                                                |
| Report Date       | August 7, 2026                                                               |
| Related Test Case | TC-BOOK-CREATE-009                                                           |

---

# Summary

The API accepts a booking request in which all supported booking fields are set to `null` instead of validating and rejecting the invalid input.

The request is processed successfully even though fields such as `firstname`, `lastname`, `totalprice`, `depositpaid`, and `bookingdates` contain `null` values.

---

# Environment

| Item        | Value                                                                        |
| ----------- | ---------------------------------------------------------------------------- |
| Environment | Public Demo                                                                  |
| Base URL    | [https://restful-booker.herokuapp.com](https://restful-booker.herokuapp.com) |
| Method      | POST                                                                         |
| Endpoint    | /booking                                                                     |
| Tool        | Postman                                                                      |

---

# Preconditions

- RESTful Booker API is accessible.
- Internet connection is stable.
- Request uses `Content-Type: application/json`.

---

# Steps to Reproduce

1. Open Postman.
2. Create a **POST** request to `/booking`.
3. Set all booking field values to `null`.
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

- API validates the provided null values appropriately.
- Invalid null values are rejected or handled according to the API validation rules.
- No unexpected server error occurs.
- API returns an appropriate and consistent response.

---

# Actual Result

- API accepts the request containing null values.
- The booking request is processed successfully despite all supported fields containing null.
- The API does not reject the invalid input as expected.
- The response indicates that the request was accepted instead of returning an appropriate validation error.

---

# Impact

Accepting null values for all booking fields may allow invalid or incomplete booking records to be created.

This can result in inconsistent booking data and makes it difficult for API consumers to rely on the expected data structure and validation behavior.

---

# Evidence

[View Evidence](../../evidence/manual-testing/booking/create-booking/TC_BOOK_CREATE_009_FAIL.png)

---

# Suggested Fix

- Implement server-side validation for null values in booking fields.
- Reject null values for fields that require valid non-null data.
- Return an appropriate client error response, such as 400 Bad Request, with a clear validation message.
- Ensure validation behavior is consistent with the defined API request schema.
