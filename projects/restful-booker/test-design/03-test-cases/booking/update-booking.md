# Update Booking Test Cases

## Overview

This document contains manual test cases for the **Update Booking** endpoint of the RESTful Booker API.

The objective of these test cases is to verify that an existing booking can be updated successfully, validate request payloads, verify authentication requirements, and ensure the API returns correct responses after updating booking information.

These test cases will be executed manually using **Postman**, managed in **Qase.io**, and later automated using **Postman Test Scripts** and **Newman**.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/booking/{id}` |
| HTTP Method | PUT |
| Authentication | Required |
| Content-Type | application/json |
| Expected Success Status | 200 OK |

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

## TC-BOOK-UPDATE-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-001 |
| Test Scenario | SC-BOOK-UPDATE-001 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that an existing booking can be updated successfully using valid data.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |
| Authentication | Valid Token |

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": 250,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-09-01",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PUT request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Add a valid authentication token.|
|5|Enter the request body.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- Status Code is **200 OK**.
- Updated booking information is returned.
- Response body matches the submitted request.

---

### Notes

The booking should be updated successfully.

---

## TC-BOOK-UPDATE-002

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-002 |
| Test Scenario | SC-BOOK-UPDATE-002 |
| Priority | Medium |
| Testing Type | Positive |

---

### Objective

Verify that multiple booking fields can be updated simultaneously.

---

### Test Data

Different valid booking information.

---

### Request Body

```json
{
    "firstname": "Pam",
    "lastname": "Beesly",
    "totalprice": 320,
    "depositpaid": false,
    "bookingdates": {
        "checkin": "2026-10-01",
        "checkout": "2026-10-10"
    },
    "additionalneeds": "Dinner"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Send a PUT request using another valid payload.|
|3|Verify the response.|

---

### Expected Result

- Status Code is **200 OK**.
- All submitted fields are updated successfully.

---

### Notes

Verify every updated field.

---

# Validation Testing

## TC-BOOK-UPDATE-003

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-003 |
| Test Scenario | SC-BOOK-UPDATE-003 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `firstname` is empty.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | "" |

---

### Request Body

```json
{
    "firstname": "",
    "lastname": "Scott",
    "totalprice": 250,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-09-01",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Replace firstname with an empty string.|
|3|Send the request.|
|4|Verify the response.|

---

### Expected Result

- API handles empty values consistently.
- No unexpected server error occurs.

---

### Notes

Actual validation behavior will be confirmed during execution.

---

## TC-BOOK-UPDATE-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-004 |
| Test Scenario | SC-BOOK-UPDATE-004 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `lastname` is empty.

---

### Test Data

| Field | Value |
|------|--------|
| lastname | "" |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Replace lastname with an empty string.|
|3|Send the request.|
|4|Verify the response.|

---

### Expected Result

- API handles empty values consistently.
- Response behavior remains stable.

---

### Notes

Observe validation behavior.

---

## TC-BOOK-UPDATE-005

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-005 |
| Test Scenario | SC-BOOK-UPDATE-005 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `totalprice` is submitted as a string.

---

### Test Data

| Field | Value |
|------|--------|
| totalprice | "abc" |

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": "abc",
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-09-01",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Replace totalprice with a string value.|
|2|Send the request.|
|3|Verify the response.|

---

### Expected Result

- API validates the data type correctly.
- No unexpected server error occurs.

---

### Notes

Observe whether implicit conversion occurs.

---

## TC-BOOK-UPDATE-006

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-006 |
| Test Scenario | SC-BOOK-UPDATE-006 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `totalprice` is a negative value.

---

### Test Data

| Field | Value |
|------|--------|
| totalprice | -100 |

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": -100,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-09-01",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PUT request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Set `totalprice` to `-100`.|
|5|Add a valid authentication token.|
|6|Click **Send**.|
|7|Verify the response.|

---

### Expected Result

- API handles negative numeric values consistently.
- No unexpected server error occurs.
- Response behavior remains stable.

---

### Notes

Observe whether negative values are accepted or rejected.

---

## TC-BOOK-UPDATE-007

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-007 |
| Test Scenario | SC-BOOK-UPDATE-007 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the `checkin` date uses an invalid format.

---

### Test Data

| Field | Value |
|------|--------|
| checkin | 01/09/2026 |

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": 250,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "01/09/2026",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Replace `checkin` with an invalid date format.|
|3|Send the request.|
|4|Verify the response.|

---

### Expected Result

- API validates the date format.
- Response behavior remains consistent.
- No unexpected server error occurs.

---

### Notes

Expected format is `YYYY-MM-DD`.

---

## TC-BOOK-UPDATE-008

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-008 |
| Test Scenario | SC-BOOK-UPDATE-008 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `checkout` is earlier than `checkin`.

---

### Test Data

| Field | Value |
|------|--------|
| checkin | 2026-09-10 |
| checkout | 2026-09-05 |

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": 250,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-09-10",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Modify the booking dates so checkout is earlier than checkin.|
|3|Click **Send**.|
|4|Verify the response.|

---

### Expected Result

- API validates booking dates appropriately.
- No unexpected server error occurs.

---

### Notes

Observe whether logical date validation exists.

---

## TC-BOOK-UPDATE-009

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-009 |
| Test Scenario | SC-BOOK-UPDATE-009 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the `bookingdates` object is omitted.

---

### Test Data

bookingdates omitted

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": 250,
    "depositpaid": true,
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Remove the `bookingdates` object from the request body.|
|3|Click **Send**.|
|4|Verify the response.|

---

### Expected Result

- API handles missing objects consistently.
- Appropriate response is returned.

---

### Notes

Observe whether the object is mandatory.

---

## TC-BOOK-UPDATE-010

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-010 |
| Test Scenario | SC-BOOK-UPDATE-010 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when all fields contain `null` values.

---

### Request Body

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

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Replace all values with `null`.|
|3|Click **Send**.|
|4|Verify the response.|

---

### Expected Result

- API handles null values consistently.
- No unexpected server error occurs.

---

### Notes

Observe validation behavior for null values.

---

# Negative Testing

## TC-BOOK-UPDATE-011

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-011 |
| Test Scenario | SC-BOOK-UPDATE-011 |
| Priority | High |
| Testing Type | Negative |

---

### Objective

Verify API behavior when updating a non-existing booking.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | 99999999 |
| Authentication | Valid Token |

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": 250,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-09-01",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PUT request to `/booking/{id}`.|
|3|Replace `{id}` with a non-existing Booking ID.|
|4|Add a valid authentication token.|
|5|Send the request.|
|6|Verify the response.|

---

### Expected Result

- API returns an appropriate error response.
- No unexpected server error occurs.
- Booking data is not created or modified.

---

### Notes

Actual status code will be confirmed during execution.

---

## TC-BOOK-UPDATE-012

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-012 |
| Test Scenario | SC-BOOK-UPDATE-012 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when the Booking ID format is invalid.

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
|2|Replace the Booking ID with alphabetic characters.|
|3|Send the request.|
|4|Verify the response.|

---

### Expected Result

- API validates the Booking ID format.
- No unexpected server error occurs.

---

### Notes

Observe the returned HTTP status code.

---

# Authentication Testing

## TC-BOOK-UPDATE-013

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-013 |
| Test Scenario | SC-BOOK-UPDATE-013 |
| Priority | High |
| Testing Type | Authentication |

---

### Objective

Verify API behavior when updating a booking without authentication.

---

### Test Data

No authentication token.

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PUT request.|
|3|Remove the Cookie header containing the authentication token.|
|4|Send the request.|
|5|Verify the response.|

---

### Expected Result

- API rejects the request.
- Booking data is not updated.
- No unexpected server error occurs.

---

### Notes

Authentication is required for this endpoint.

---

## TC-BOOK-UPDATE-014

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-014 |
| Test Scenario | SC-BOOK-UPDATE-014 |
| Priority | High |
| Testing Type | Authentication |

---

### Objective

Verify API behavior when using an invalid authentication token.

---

### Test Data

| Header | Value |
|--------|--------|
| Cookie | token=invalid_token |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Replace the authentication token with an invalid token.|
|3|Send the request.|
|4|Verify the response.|

---

### Expected Result

- API rejects the request.
- Booking information is not updated.
- Appropriate authentication error is returned.

---

### Notes

Actual response will be confirmed during execution.

---

# Negative Testing

## TC-BOOK-UPDATE-015

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-015 |
| Test Scenario | SC-BOOK-UPDATE-015 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when malformed JSON is submitted.

---

### Request Body

```json
{
    "firstname":"Michael",
    "lastname":
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PUT request.|
|3|Enter malformed JSON.|
|4|Send the request.|
|5|Verify the response.|

---

### Expected Result

- API rejects malformed JSON.
- No unexpected server error occurs.

---

### Notes

Observe the returned HTTP status code.

---

## TC-BOOK-UPDATE-016

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-016 |
| Test Scenario | SC-BOOK-UPDATE-016 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when an unsupported `Content-Type` header is used.

---

### Test Data

| Header | Value |
|--------|--------|
| Content-Type | text/plain |

---

### Request Body

```json
{
    "firstname": "Michael",
    "lastname": "Scott",
    "totalprice": 250,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-09-01",
        "checkout": "2026-09-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a PUT request to `/booking/{id}`.|
|3|Replace the `Content-Type` header with `text/plain`.|
|4|Add a valid authentication token.|
|5|Send the request.|
|6|Verify the response.|

---

### Expected Result

- API handles unsupported Content-Type appropriately.
- No unexpected server error occurs.
- Response behavior remains consistent.

---

### Notes

Actual response will be confirmed during execution.

---

# Response Validation

## TC-BOOK-UPDATE-017

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-017 |
| Test Scenario | SC-BOOK-UPDATE-017 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify that the response body follows the expected JSON schema after a successful update.

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
|2|Update an existing booking using valid data.|
|3|Inspect the response body.|
|4|Verify every returned field.|

---

### Expected Result

- Status Code is **200 OK**.
- Response is returned in JSON format.
- Response contains:
  - firstname
  - lastname
  - totalprice
  - depositpaid
  - bookingdates
  - additionalneeds
- Returned data types match the API specification.

---

### Notes

This test validates the response structure rather than the field values.

---

# End-to-End Verification

## TC-BOOK-UPDATE-018

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-UPDATE-018 |
| Test Scenario | SC-BOOK-UPDATE-018 |
| Priority | High |
| Testing Type | End-to-End Verification |

---

### Objective

Verify that updated booking information is successfully persisted by retrieving the same booking after the update.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Create a booking or use an existing booking.|
|2|Update the booking using the PUT endpoint.|
|3|Verify that the update request returns **200 OK**.|
|4|Send a GET request using the same Booking ID.|
|5|Compare the GET response with the data submitted in the PUT request.|
|6|Verify that every updated field matches.|

---

### Expected Result

- PUT request returns **200 OK**.
- GET request returns **200 OK**.
- All updated values are successfully persisted.
- No old values remain.
- Data consistency is maintained between PUT and GET.

---

### Notes

This test verifies complete update persistence and ensures that the API updates the stored resource correctly.

---

# Test Case Summary

| Category | Total |
|----------|------:|
| Positive Testing | 2 |
| Validation Testing | 8 |
| Negative Testing | 5 |
| Authentication Testing | 2 |
| End-to-End Verification | 1 |
| **Total Test Cases** | **18** |

---

# Coverage Summary

| Coverage | Status |
|----------|:------:|
| Valid Booking Update | Yes |
| Required Field Validation | Yes |
| Data Type Validation | Yes |
| Date Validation | Yes |
| Authentication Validation | Yes |
| Invalid Booking Validation | Yes |
| Response Schema Validation | Yes |
| End-to-End Data Verification | Yes |

---

# Related Documents

- Test Plan
- Test Scenarios
- Test Data
- Postman Collection
- Qase Test Cases
- API Documentation
