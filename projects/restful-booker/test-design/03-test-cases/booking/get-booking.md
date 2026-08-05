# Get Booking Test Cases

## Overview

This document contains manual test cases for the **Get Booking** endpoint of the RESTful Booker API.

The objective of these test cases is to verify that booking information can be retrieved correctly using a booking ID, validate API behavior for invalid and non-existent booking IDs, and ensure the API returns accurate response data, status codes, and headers.

These test cases will be executed manually using **Postman**, managed in **Qase.io**, and later automated using **Postman Test Scripts** and **Newman**.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/booking/{id}` |
| HTTP Method | GET |
| Authentication | Not Required |
| Content-Type | application/json |
| Expected Success Status | 200 OK |

---

# Shared Preconditions

The following preconditions apply to all test cases unless otherwise stated.

- RESTful Booker API is accessible.
- Postman is installed and configured.
- Base URL has been configured.
- At least one booking record already exists.
- A valid Booking ID is available.

---

# Positive Testing

## TC-BOOK-GET-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-001 |
| Test Scenario | SC-BOOK-GET-001 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that booking information can be successfully retrieved using a valid Booking ID.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a GET request to `/booking/{id}`. |
| 3 | Replace `{id}` with a valid Booking ID. |
| 4 | Click **Send**. |
| 5 | Verify the response. |

---

### Expected Result

- Status Code is **200 OK**.
- Response body is returned in JSON format.
- Booking information is displayed.
- Returned data matches the selected Booking ID.

---

### Notes

Record the Booking ID used for future update and delete testing.

---

## TC-BOOK-GET-002

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-002 |
| Test Scenario | SC-BOOK-GET-002 |
| Priority | Medium |
| Testing Type | Positive |

---

### Objective

Verify that multiple existing booking records can be retrieved successfully.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Another Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a GET request to `/booking/{id}`. |
| 3 | Enter another valid Booking ID. |
| 4 | Click **Send**. |
| 5 | Verify the response. |

---

### Expected Result

- Status Code is **200 OK**.
- Correct booking information is returned.
- Response structure remains consistent.

---

### Notes

Compare the response structure with TC-BOOK-GET-001.

---

# Negative Testing

## TC-BOOK-GET-003

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-003 |
| Test Scenario | SC-BOOK-GET-003 |
| Priority | High |
| Testing Type | Negative |

---

### Objective

Verify API behavior when requesting a non-existing Booking ID.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | 99999999 |

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a GET request. |
| 3 | Enter a Booking ID that does not exist. |
| 4 | Click **Send**. |
| 5 | Verify the response. |

---

### Expected Result

- API returns an appropriate error response.
- No unexpected server error occurs.
- Response behavior is consistent.

---

### Notes

Actual response will be confirmed during execution.

---

## TC-BOOK-GET-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-004 |
| Test Scenario | SC-BOOK-GET-004 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when the Booking ID is a negative number.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | -1 |

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a GET request. |
| 3 | Replace the Booking ID with `-1`. |
| 4 | Click **Send**. |
| 5 | Verify the response. |

---

### Expected Result

- API handles invalid numeric values correctly.
- No unexpected server error occurs.

---

### Notes

Observe the returned HTTP status code.

---

# Boundary Testing

## TC-BOOK-GET-005

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-005 |
| Test Scenario | SC-BOOK-GET-005 |
| Priority | Medium |
| Testing Type | Boundary |

---

### Objective

Verify API behavior when the Booking ID is `0`.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | 0 |

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a GET request. |
| 3 | Replace the Booking ID with `0`. |
| 4 | Click **Send**. |
| 5 | Verify the response. |

---

### Expected Result

- API processes the request consistently.
- Appropriate response is returned.
- No unexpected server error occurs.

---

### Notes

Observe whether Booking ID `0` is considered valid.

---

# Validation Testing

## TC-BOOK-GET-006

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-006 |
| Test Scenario | SC-BOOK-GET-006 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the Booking ID contains decimal values.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | 1.5 |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request to `/booking/{id}`.|
|3|Replace the Booking ID with `1.5`.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API validates the Booking ID format.
- Appropriate response is returned.
- No unexpected server error occurs.

---

### Notes

Observe whether decimal values are accepted or rejected.

---

## TC-BOOK-GET-007

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-007 |
| Test Scenario | SC-BOOK-GET-007 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the Booking ID contains alphabetic characters.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | abc |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request.|
|3|Replace the Booking ID with `abc`.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API validates the Booking ID format.
- Response remains consistent.
- No unexpected server error occurs.

---

### Notes

Observe how the endpoint handles non-numeric path parameters.

---

## TC-BOOK-GET-008

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-008 |
| Test Scenario | SC-BOOK-GET-008 |
| Priority | Low |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the Booking ID contains special characters.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | @#$% |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request.|
|3|Replace the Booking ID with special characters.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API validates invalid path values correctly.
- Appropriate response is returned.
- No unexpected server error occurs.

---

### Notes

Observe how URL encoding affects the request.

---

# Negative Testing

## TC-BOOK-GET-009

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-009 |
| Test Scenario | SC-BOOK-GET-009 |
| Priority | High |
| Testing Type | Negative |

---

### Objective

Verify API behavior when no Booking ID is provided.

---

### Test Data

N/A

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request to `/booking/`.|
|3|Do not specify a Booking ID.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API returns an appropriate response.
- No unexpected server error occurs.
- Response behavior is consistent.

---

### Notes

Observe whether the endpoint redirects or returns an error.

---

# Boundary Testing

## TC-BOOK-GET-010

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-010 |
| Test Scenario | SC-BOOK-GET-010 |
| Priority | Low |
| Testing Type | Boundary |

---

### Objective

Verify API behavior when an extremely large Booking ID is requested.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | 999999999999 |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request.|
|3|Replace the Booking ID with a very large numeric value.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API handles large numeric values safely.
- No unexpected server error occurs.
- Appropriate response is returned.

---

### Notes

Observe whether integer overflow or parsing issues occur.

---

# Response Validation

## TC-BOOK-GET-011

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-011 |
| Test Scenario | SC-BOOK-GET-011 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify that the response body contains the expected JSON schema for a successful booking retrieval.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Click **Send**.|
|5|Inspect the response body.|

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
- Data types match the API specification.

---

### Notes

This test validates the response structure instead of the response values.

---

## TC-BOOK-GET-012

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-GET-012 |
| Test Scenario | SC-BOOK-GET-012 |
| Priority | Low |
| Testing Type | Validation |

---

### Objective

Verify that the API returns the correct HTTP response headers.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Click **Send**.|
|5|Inspect the response headers.|

---

### Expected Result

- Status Code is **200 OK**.
- Response contains the `Content-Type` header.
- `Content-Type` is `application/json`.
- Response headers are returned successfully.

---

### Notes

Additional response headers may also be verified if required.

---

# Test Case Summary

| Category | Total |
|----------|------:|
| Positive Testing | 2 |
| Negative Testing | 3 |
| Validation Testing | 5 |
| Boundary Testing | 2 |
| **Total Test Cases** | **12** |

---

# Coverage Summary

| Coverage | Status |
|----------|:------:|
| Valid Booking Retrieval | Yes |
| Invalid Booking ID Validation | Yes |
| Non-existing Booking Validation | Yes |
| Boundary Value Validation | Yes |
| Response Schema Validation | Yes |
| Response Header Validation | Yes |
| HTTP Status Code Validation | Yes |

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
| 1.0 | Initial Get Booking Test Cases |
| 1.1 | Added response validation, boundary testing, and comprehensive negative test cases |
