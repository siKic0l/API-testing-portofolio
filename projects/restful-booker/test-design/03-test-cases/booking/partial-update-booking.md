# Partial Update Booking Test Cases

## Overview

This document contains manual test cases for the **Partial Update Booking** endpoint of the RESTful Booker API.

The objective of these test cases is to verify that specific booking fields can be updated without affecting other existing data, validate request payloads, verify authentication requirements, and ensure the API correctly processes partial updates.

These test cases will be executed manually using **Postman**, managed in **Qase.io**, and later automated using **Postman Test Scripts** and **Newman**.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/booking/{id}` |
| HTTP Method | PATCH |
| Authentication | Required |
| Content-Type | application/json |

---

# Shared Preconditions

The following preconditions apply to all test cases unless otherwise stated.

- RESTful Booker API is accessible.
- Postman is installed and configured.
- Base URL has been configured.
- A valid authentication token has been generated.
- At least one booking record already exists.
- A valid Booking ID is available.

---

# Shared Request Headers

| Header | Value |
|--------|--------|
| Content-Type | application/json |
| Cookie | token={{auth_token}} |

---

# Positive Testing

## TC-BOOK-PATCH-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-001 |
| Test Scenario | SC-BOOK-PATCH-001 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that only the `firstname` field can be updated successfully.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |
| firstname | Michael |

---

### Request Body

```json
{
    "firstname": "Michael"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Add a valid authentication token.|
|5|Enter the request body containing only `firstname`.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- Status Code is **200 OK**.
- Only `firstname` is updated.
- Other booking fields remain unchanged.

---

### Notes

This test verifies partial resource modification.

---

## TC-BOOK-PATCH-002

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-002 |
| Test Scenario | SC-BOOK-PATCH-002 |
| Priority | Medium |
| Testing Type | Positive |

---

### Objective

Verify that only the `lastname` field can be updated successfully.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |
| lastname | Halpert |

---

### Request Body

```json
{
    "lastname": "Halpert"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Add a valid authentication token.|
|5|Enter the request body containing only `lastname`.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- Status Code is **200 OK**.
- Only `lastname` is updated.
- All other fields remain unchanged.

---

### Notes

Verify unchanged fields using a subsequent GET request.

---

## TC-BOOK-PATCH-003

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-003 |
| Test Scenario | SC-BOOK-PATCH-003 |
| Priority | Medium |
| Testing Type | Positive |

---

### Objective

Verify that only the `additionalneeds` field can be updated successfully.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |
| additionalneeds | Dinner |

---

### Request Body

```json
{
    "additionalneeds": "Dinner"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Enter the request body containing only `additionalneeds`.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- Status Code is **200 OK**.
- Only `additionalneeds` is updated.
- Remaining booking data is preserved.

---

### Notes

This verifies that optional fields can be updated independently.

---

## TC-BOOK-PATCH-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-004 |
| Test Scenario | SC-BOOK-PATCH-004 |
| Priority | Medium |
| Testing Type | Positive |

---

### Objective

Verify that only the `depositpaid` field can be updated successfully.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |
| depositpaid | false |

---

### Request Body

```json
{
    "depositpaid": false
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Update only `depositpaid`.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- Status Code is **200 OK**.
- Only `depositpaid` is updated.
- Remaining fields remain unchanged.

---

### Notes

Verify the updated value using GET Booking.

---

## TC-BOOK-PATCH-005

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-005 |
| Test Scenario | SC-BOOK-PATCH-005 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that multiple selected fields can be updated simultaneously.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | Jim |
| lastname | Halpert |
| additionalneeds | Breakfast |

---

### Request Body

```json
{
    "firstname": "Jim",
    "lastname": "Halpert",
    "additionalneeds": "Breakfast"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Update multiple selected fields.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- Status Code is **200 OK**.
- Selected fields are updated successfully.
- Fields not included in the request remain unchanged.

---

### Notes

This test confirms that PATCH updates only submitted fields without replacing the entire resource.

---

# Validation Testing

## TC-BOOK-PATCH-006

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-006 |
| Test Scenario | SC-BOOK-PATCH-006 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `firstname` is updated with an empty string.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | "" |

---

### Request Body

```json
{
    "firstname": ""
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Set `firstname` to an empty string.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- API handles empty values consistently.
- No unexpected server error occurs.
- Response behavior remains stable.

---

### Notes

Observe whether empty strings are accepted or rejected.

---

## TC-BOOK-PATCH-007

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-007 |
| Test Scenario | SC-BOOK-PATCH-007 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `totalprice` is updated with an invalid data type.

---

### Test Data

| Field | Value |
|------|--------|
| totalprice | "invalid" |

---

### Request Body

```json
{
    "totalprice": "invalid"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Set `totalprice` to a string value.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- API validates the submitted data type.
- No unexpected server error occurs.
- Response behavior remains consistent.

---

### Notes

Observe whether automatic type conversion occurs.

---

## TC-BOOK-PATCH-008

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-008 |
| Test Scenario | SC-BOOK-PATCH-008 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `bookingdates` is updated using an invalid date format.

---

### Test Data

| Field | Value |
|------|--------|
| checkin | 01/09/2026 |

---

### Request Body

```json
{
    "bookingdates": {
        "checkin": "01/09/2026",
        "checkout": "2026-09-05"
    }
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Update `bookingdates` using an invalid date format.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- API validates the submitted date format.
- No unexpected server error occurs.
- Response behavior remains stable.

---

### Notes

Expected format is `YYYY-MM-DD`.

---

## TC-BOOK-PATCH-009

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-009 |
| Test Scenario | SC-BOOK-PATCH-009 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when updating fields using `null` values.

---

### Request Body

```json
{
    "firstname": null
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Set `firstname` to `null`.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- API handles null values consistently.
- No unexpected server error occurs.
- Response behavior remains stable.

---

### Notes

Observe whether null values overwrite existing values or are rejected.

---

# Negative Testing

## TC-BOOK-PATCH-010

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-010 |
| Test Scenario | SC-BOOK-PATCH-010 |
| Priority | High |
| Testing Type | Negative |

---

### Objective

Verify API behavior when attempting to partially update a non-existing booking.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | 99999999 |

---

### Request Body

```json
{
    "firstname": "Michael"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request to `/booking/{id}`.|
|3|Replace `{id}` with a non-existing Booking ID.|
|4|Add a valid authentication token.|
|5|Send the request.|
|6|Verify the response.|

---

### Expected Result

- API returns an appropriate error response.
- No booking data is modified.
- No unexpected server error occurs.

---

### Notes

Actual status code will be confirmed during execution.

---

## TC-BOOK-PATCH-011

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-011 |
| Test Scenario | SC-BOOK-PATCH-011 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when the Booking ID contains invalid characters.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | abc |

---

### Request Body

```json
{
    "firstname": "Michael"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace the Booking ID with `abc`.|
|4|Authenticate using a valid token.|
|5|Send the request.|
|6|Verify the response.|

---

### Expected Result

- API validates the Booking ID format.
- No unexpected server error occurs.
- Appropriate response is returned.

---

### Notes

Observe the returned HTTP status code.

---

# Authentication Testing

## TC-BOOK-PATCH-012

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-012 |
| Test Scenario | SC-BOOK-PATCH-012 |
| Priority | High |
| Testing Type | Authentication |

---

### Objective

Verify API behavior when updating a booking without authentication.

---

### Test Data

No authentication token.

---

### Request Body

```json
{
    "firstname": "Michael"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Do not include the Cookie authentication header.|
|4|Send the request.|
|5|Verify the response.|

---

### Expected Result

- API rejects the request.
- Booking information is not updated.
- No unexpected server error occurs.

---

### Notes

Authentication is mandatory for this endpoint.

---

## TC-BOOK-PATCH-013

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-013 |
| Test Scenario | SC-BOOK-PATCH-013 |
| Priority | High |
| Testing Type | Authentication |

---

### Objective

Verify API behavior when an invalid authentication token is used.

---

### Test Data

| Header | Value |
|--------|--------|
| Cookie | token=invalid_token |

---

### Request Body

```json
{
    "firstname": "Michael"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request.|
|3|Replace the authentication token with an invalid token.|
|4|Send the request.|
|5|Verify the response.|

---

### Expected Result

- API rejects the request.
- Booking information is not updated.
- Appropriate authentication error is returned.

---

### Notes

Actual response will be confirmed during execution.

---

# Response Validation

## TC-BOOK-PATCH-014

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-014 |
| Test Scenario | SC-BOOK-PATCH-014 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify that the response body follows the expected JSON schema after a successful partial update.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Request Body

```json
{
    "firstname": "Michael"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PATCH request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Update the `firstname` field.|
|6|Click **Send**.|
|7|Inspect the response body.|

---

### Expected Result

- Status Code is **200 OK**.
- Response is returned in JSON format.
- Response contains the following fields:
  - firstname
  - lastname
  - totalprice
  - depositpaid
  - bookingdates
  - additionalneeds
- All returned data types match the API specification.

---

### Notes

This test validates the response structure rather than the response values.

---

# End-to-End Verification

## TC-BOOK-PATCH-015

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-PATCH-015 |
| Test Scenario | SC-BOOK-PATCH-015 |
| Priority | High |
| Testing Type | End-to-End Verification |

---

### Objective

Verify that only the submitted fields are updated while all other existing booking information remains unchanged.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |
| Updated Field | firstname |

---

### Request Body

```json
{
    "firstname": "Michael"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Send a GET request to retrieve the current booking data.|
|2|Record the original booking information.|
|3|Send a PATCH request updating only the `firstname` field.|
|4|Verify that the PATCH request returns **200 OK**.|
|5|Send another GET request using the same Booking ID.|
|6|Compare both GET responses.|
|7|Verify that only `firstname` has changed.|
|8|Verify that `lastname`, `totalprice`, `depositpaid`, `bookingdates`, and `additionalneeds` remain unchanged.|

---

### Expected Result

- PATCH request returns **200 OK**.
- Only the specified field is updated.
- All other fields retain their previous values.
- No unintended data modification occurs.
- Data consistency is maintained.

---

### Notes

This test verifies the fundamental behavior of the PATCH method by ensuring partial updates do not overwrite unaffected fields.

---

# Test Case Summary

| Category | Total |
|----------|------:|
| Positive Testing | 5 |
| Validation Testing | 5 |
| Negative Testing | 2 |
| Authentication Testing | 2 |
| End-to-End Verification | 1 |
| **Total Test Cases** | **15** |

---

# Coverage Summary

| Coverage | Status |
|----------|:------:|
| Partial Field Update | Yes |
| Field Value Validation | Yes |
| Data Type Validation | Yes |
| Date Validation | Yes |
| Authentication Validation | Yes |
| Invalid Booking Validation | Yes |
| Response Schema Validation | Yes |
| End-to-End Partial Update Verification | Yes |

---

# Related Documents

- Test Plan
- Test Scenarios
- Test Data
- Postman Collection
- Qase Test Cases
- API Documentation

---

# Update History

| Version | Description |
|----------|-------------|
| 1.0 | Initial Partial Update Booking Test Cases |
| 1.1 | Added response validation and end-to-end verification |
