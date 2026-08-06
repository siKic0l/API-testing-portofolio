# Create Booking Test Cases

## Overview

This document contains manual test cases for the **Create Booking** endpoint of the RESTful Booker API.

The purpose of these test cases is to verify that new booking records can be created successfully, input validation is properly enforced, invalid requests are handled correctly, and the API returns consistent responses.

These test cases will be executed manually using **Postman**, managed in **Qase.io**, and later automated using **Postman Test Scripts** and **Newman**.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/booking` |
| HTTP Method | POST |
| Authentication | Not Required |
| Content-Type | application/json |
| Expected Success Status | 200 OK |

---

# Shared Preconditions

The following preconditions apply to all test cases unless otherwise stated.

- RESTful Booker API is accessible.
- Postman is installed and configured.
- Base URL has been configured.
- Internet connection is stable.

---

# Shared Request Headers

| Header | Value |
|---------|--------|
| Content-Type | application/json |

---

# Request Body Schema

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

# Positive Testing

## TC-BOOK-CREATE-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-001 |
| Test Scenario | SC-BOOK-CREATE-001 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that a booking can be successfully created using valid booking information.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | John |
| lastname | Doe |
| totalprice | 150 |
| depositpaid | true |
| checkin | 2026-08-01 |
| checkout | 2026-08-05 |
| additionalneeds | Breakfast |

---

### Request Body

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

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a new POST request. |
| 3 | Enter the `/booking` endpoint. |
| 4 | Use the default request header. |
| 5 | Enter a valid booking payload. |
| 6 | Click **Send**. |
| 7 | Verify the API response. |

---

### Expected Result

- Status Code is **200 OK**.
- Response body is returned in JSON format.
- Booking ID is generated.
- Booking object is returned.
- Response values match the submitted request.

---

### Notes

N/A

---

## TC-BOOK-CREATE-002

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-002 |
| Test Scenario | SC-BOOK-CREATE-002 |
| Priority | High |
| Testing Type | Negative |

---

### Objective

Verify API behavior when the **firstname** field is omitted.

---

### Test Data

Missing `firstname`

---

### Request Body

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

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/booking`. |
| 3 | Remove the `firstname` field from the request body. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- API handles the missing required field appropriately.
- No unexpected server error occurs.
- Response behavior is consistent.

---

### Notes

Observe whether the API accepts or rejects incomplete booking data.

---

## TC-BOOK-CREATE-003

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-003 |
| Test Scenario | SC-BOOK-CREATE-003 |
| Priority | High |
| Testing Type | Negative |

---

### Objective

Verify API behavior when the **lastname** field is omitted.

---

### Test Data

Missing `lastname`

---

### Request Body

```json
{
    "firstname": "John",
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

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/booking`. |
| 3 | Remove the `lastname` field from the request body. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- API handles the missing field correctly.
- API response remains stable.
- No unexpected server error occurs.

---

### Notes

Observe whether the API accepts or rejects the incomplete payload.

---

## TC-BOOK-CREATE-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-004 |
| Test Scenario | SC-BOOK-CREATE-004 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that a booking can be created when **depositpaid** is set to `false`.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | John |
| lastname | Doe |
| totalprice | 200 |
| depositpaid | false |
| checkin | 2026-08-01 |
| checkout | 2026-08-05 |
| additionalneeds | Lunch |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 200,
    "depositpaid": false,
    "bookingdates": {
        "checkin": "2026-08-01",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "Lunch"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/booking`. |
| 3 | Enter a valid payload with `depositpaid=false`. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- Status Code is **200 OK**.
- Booking is created successfully.
- `depositpaid` value is returned as **false**.

---

### Notes

Verify that Boolean values are stored correctly.

---

## TC-BOOK-CREATE-005

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-005 |
| Test Scenario | SC-BOOK-CREATE-005 |
| Priority | Medium |
| Testing Type | Boundary |

---

### Objective

Verify that a booking can be created when **totalprice** equals **0**.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | John |
| lastname | Doe |
| totalprice | 0 |
| depositpaid | true |
| checkin | 2026-08-01 |
| checkout | 2026-08-05 |
| additionalneeds | None |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 0,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-08-01",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "None"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/booking`. |
| 3 | Enter `0` as the total price. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- API processes the request consistently.
- Booking is created or rejected according to API validation rules.
- No unexpected server error occurs.

---

### Notes

This test validates the lower boundary of the **totalprice** field.

---

# Validation Testing

---

## TC-BOOK-CREATE-006

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-006 |
| Test Scenario | SC-BOOK-CREATE-006 |
| Priority | High |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the **firstname** field is an empty string.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | "" |
| lastname | Doe |
| totalprice | 150 |
| depositpaid | true |
| checkin | 2026-08-01 |
| checkout | 2026-08-05 |
| additionalneeds | Breakfast |

---

### Request Body

```json
{
    "firstname": "",
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

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/booking`. |
| 3 | Set `firstname` to an empty string. |
| 4 | Send the request. |
| 5 | Verify the response. |

---

### Expected Result

- API processes the request consistently.
- API either accepts or rejects the empty value according to its validation rules.
- No unexpected server error occurs.

---

### Notes

Observe how the API handles empty string values.

---

## TC-BOOK-CREATE-007

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-007 |
| Test Scenario | SC-BOOK-CREATE-007 |
| Priority | High |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the **lastname** field is an empty string.

---

### Test Data

| Field | Value |
|------|--------|
| lastname | "" |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "",
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

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request. |
| 3 | Leave `lastname` empty. |
| 4 | Send the request. |
| 5 | Verify the response. |

---

### Expected Result

- API handles the request correctly.
- No unexpected server error occurs.

---

### Notes

Observe validation behavior.

---

## TC-BOOK-CREATE-008

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-008 |
| Test Scenario | SC-BOOK-CREATE-008 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when **additionalneeds** is omitted.

---

### Test Data

additionalneeds omitted.

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 150,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-08-01",
        "checkout": "2026-08-05"
    }
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request. |
| 3 | Remove `additionalneeds`. |
| 4 | Send the request. |
| 5 | Verify the response. |

---

### Expected Result

- API handles optional fields correctly.
- Booking is created if the field is optional.

---

### Notes

Verify whether `additionalneeds` is required.

---

## TC-BOOK-CREATE-009

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-009 |
| Test Scenario | SC-BOOK-CREATE-009 |
| Priority | High |
| Testing Type | Validation |

---

### Objective

Verify API behavior when **bookingdates** is missing.

---

### Test Data

bookingdates omitted.

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 150,
    "depositpaid": true,
    "additionalneeds": "Breakfast"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request. |
| 3 | Remove the `bookingdates` object. |
| 4 | Send the request. |
| 5 | Verify the response. |

---

### Expected Result

- API validates missing booking dates appropriately.
- No unexpected server error occurs.

---

### Notes

Observe whether booking dates are mandatory.

---

# Negative Testing

---

## TC-BOOK-CREATE-010

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-010 |
| Test Scenario | SC-BOOK-CREATE-010 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when an empty JSON object is submitted.

---

### Test Data

Empty JSON.

---

### Request Body

```json
{}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request. |
| 3 | Send an empty JSON object. |
| 4 | Verify the response. |

---

### Expected Result

- API rejects or handles the request consistently.
- No unexpected server error occurs.

---

### Notes

Observe the returned status code and response body.

---

## TC-BOOK-CREATE-011

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-011 |
| Test Scenario | SC-BOOK-CREATE-011 |
| Priority | Medium |
| Testing Type | Negative |

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
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": -100,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-08-01",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "Breakfast"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request to `/booking`.|
|3|Set `totalprice` to `-100`.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API handles negative numeric values correctly.
- No unexpected server error occurs.
- Validation behavior is consistent.

---

### Notes

Observe whether negative values are accepted or rejected.

---

## TC-BOOK-CREATE-012

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-012 |
| Test Scenario | SC-BOOK-CREATE-012 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `totalprice` is submitted as a string.

---

### Test Data

| Field | Value |
|------|--------|
| totalprice | "one hundred" |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": "one hundred",
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-08-01",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "Breakfast"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request.|
|3|Replace `totalprice` with a string value.|
|4|Send the request.|
|5|Verify the response.|

---

### Expected Result

- API validates the incorrect data type.
- No unexpected server error occurs.

---

### Notes

Observe whether the API performs type validation.

---

## TC-BOOK-CREATE-013

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-013 |
| Test Scenario | SC-BOOK-CREATE-013 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when `depositpaid` is submitted as a string.

---

### Test Data

| Field | Value |
|------|--------|
| depositpaid | "true" |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 150,
    "depositpaid": "true",
    "bookingdates": {
        "checkin": "2026-08-01",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "Breakfast"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request.|
|3|Replace `depositpaid` with a string value.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API validates Boolean values correctly.
- Response behavior remains consistent.

---

### Notes

Observe whether implicit type conversion occurs.

---

## TC-BOOK-CREATE-014

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-014 |
| Test Scenario | SC-BOOK-CREATE-014 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the check-in date uses an invalid date format.

---

### Test Data

| Field | Value |
|------|--------|
| checkin | 01/08/2026 |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 150,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "01/08/2026",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "Breakfast"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request.|
|3|Use an invalid date format for `checkin`.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API validates the date format correctly.
- Response behavior is consistent.

---

### Notes

Expected date format is `YYYY-MM-DD`.

---

## TC-BOOK-CREATE-015

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-015 |
| Test Scenario | SC-BOOK-CREATE-015 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify API behavior when the checkout date is earlier than the check-in date.

---

### Test Data

| Field | Value |
|------|--------|
| checkin | 2026-08-10 |
| checkout | 2026-08-05 |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 150,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-08-10",
        "checkout": "2026-08-05"
    },
    "additionalneeds": "Breakfast"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request.|
|3|Set checkout date earlier than check-in date.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API validates the booking dates appropriately.
- No unexpected server error occurs.
- Response behavior remains consistent.

---

### Notes

Observe whether logical date validation is implemented.

---

## TC-BOOK-CREATE-016

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-016 |
| Test Scenario | SC-BOOK-CREATE-016 |
| Priority | Low |
| Testing Type | Boundary |

---

### Objective

Verify API behavior when `firstname` exceeds the expected character limit.

---

### Test Data

| Field | Value |
|------|--------|
| firstname | 256+ characters |

---

### Request Body

```json
{
    "firstname": "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA",
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

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request to `/booking`.|
|3|Enter a firstname longer than 255 characters.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API handles long input safely.
- No server crash occurs.
- Response remains consistent.

---

### Notes

Observe whether input length validation exists.

---

## TC-BOOK-CREATE-017

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-017 |
| Test Scenario | SC-BOOK-CREATE-017 |
| Priority | Low |
| Testing Type | Boundary |

---

### Objective

Verify API behavior when `lastname` exceeds the expected character limit.

---

### Test Data

| Field | Value |
|------|--------|
| lastname | 256+ characters |

---

### Request Body

```json
{
    "firstname": "John",
    "lastname": "BBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBB",
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

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request.|
|3|Enter a lastname longer than 255 characters.|
|4|Send the request.|
|5|Verify the response.|

---

### Expected Result

- API handles long input safely.
- No unexpected behavior occurs.

---

### Notes

Observe any truncation or validation.

---

# HTTP & Header Validation

---

## TC-BOOK-CREATE-018

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-018 |
| Test Scenario | SC-BOOK-CREATE-018 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when an unsupported HTTP method is used.

---

### Test Data

N/A

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request to `/booking`.|
|3|Click **Send**.|
|4|Verify the response.|

---

### Expected Result

- API returns the appropriate response for the GET endpoint.
- No unexpected server error occurs.

---

### Notes

This test confirms endpoint behavior for a different HTTP method. Verify that the response matches the API specification.

---

## TC-BOOK-CREATE-019

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-019 |
| Test Scenario | SC-BOOK-CREATE-019 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when the Content-Type header is invalid.

---

### Test Data

| Header | Value |
|--------|--------|
| Content-Type | text/plain |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request.|
|3|Change Content-Type to `text/plain`.|
|4|Send the request.|
|5|Verify the response.|

---

### Expected Result

- API handles the invalid Content-Type appropriately.
- Response behavior remains consistent.

---

### Notes

Observe whether Content-Type validation is enforced.

---

## TC-BOOK-CREATE-020

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-020 |
| Test Scenario | SC-BOOK-CREATE-020 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when malformed JSON is submitted.

---

### Request Body

```json
{
    "firstname":"John",
    "lastname":
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a POST request.|
|3|Enter malformed JSON.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API rejects malformed JSON.
- No unexpected server error occurs.

---

### Notes

Observe the returned HTTP status code.

---

## TC-BOOK-CREATE-021

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-021 |
| Test Scenario | SC-BOOK-CREATE-021 |
| Priority | Low |
| Testing Type | Negative |

---

### Objective

Verify API behavior when unexpected properties are included in the request body.

---

### Request Body

```json
{
    "firstname":"John",
    "lastname":"Doe",
    "totalprice":150,
    "depositpaid":true,
    "bookingdates":{
        "checkin":"2026-08-01",
        "checkout":"2026-08-05"
    },
    "additionalneeds":"Breakfast",
    "role":"Administrator"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Add an unsupported property to the request body.|
|3|Click **Send**.|
|4|Verify the response.|

---

### Expected Result

- API ignores unsupported properties or handles them safely.
- Booking creation remains stable.

---

### Notes

Observe whether additional properties affect the response.

---

## TC-BOOK-CREATE-022

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-CREATE-022 |
| Test Scenario | SC-BOOK-CREATE-022 |
| Priority | Low |
| Testing Type | Validation |

---

### Objective

Verify API behavior when all fields contain null values.

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
|2|Create a POST request.|
|3|Replace every field value with `null`.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API validates null values appropriately.
- No unexpected server error occurs.

---

### Notes

Observe how the API handles null values.

---

# Test Case Summary

| Category | Total |
|----------|------:|
| Positive Testing | 2 |
| Negative Testing | 8 |
| Validation Testing | 9 |
| Boundary Testing | 3 |
| **Total Test Cases** | **22** |

---

# Coverage Summary

| Coverage                     | Status |
| ---------------------------- | :----: |
| Valid Booking Creation       |   Yes  |
| Required Field Validation    |   Yes  |
| Optional Field Validation    |   Yes  |
| Data Type Validation         |   Yes  |
| Date Validation              |   Yes  |
| Boundary Testing             |   Yes  |
| Header Validation            |   Yes  |
| Malformed Request Validation |   Yes  |

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
| 1.0 | Initial Create Booking Test Cases |
| 1.1 | Added comprehensive positive, validation, negative, boundary, and request validation test cases |
