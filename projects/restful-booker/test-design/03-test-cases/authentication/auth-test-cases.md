# Authentication Test Cases

## Overview

This document contains detailed manual test cases for the **Authentication** endpoint of the RESTful Booker API.

The objective of these test cases is to verify that the authentication endpoint correctly validates user credentials, generates authentication tokens, rejects invalid requests, and handles malformed input appropriately.

These test cases will be executed manually using **Postman**, managed in **Qase.io**, and later automated using **Postman Test Scripts** and **Newman**.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/auth` |
| HTTP Method | POST |
| Authentication Required | No |
| Content-Type | application/json |
| Expected Success Status | 200 OK |

---

# Positive Testing

---

## TC-AUTH-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-001 |
| Test Scenario | SC-AUTH-001 |
| Priority | High |
| Testing Type | Positive |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify that a valid authentication token is generated when valid credentials are submitted.

---

### Preconditions

- RESTful Booker API is accessible.
- Postman is installed.
- Base URL has been configured.

---

### Test Data

| Field | Value |
|------|--------|
| Username | admin |
| Password | password123 |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "admin",
  "password": "password123"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a new **POST** request. |
| 3 | Enter the `/auth` endpoint. |
| 4 | Add the `Content-Type: application/json` header. |
| 5 | Enter valid credentials in the request body. |
| 6 | Click **Send**. |
| 7 | Verify the API response. |

---

### Expected Result

- Status Code is **200 OK**.
- Response body is returned in JSON format.
- Authentication token is generated.
- Token value is not empty.

---

### Notes

N/A

---

# Negative Testing

---

## TC-AUTH-002

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-002 |
| Test Scenario | SC-AUTH-002 |
| Priority | High |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify that authentication fails when an invalid username is provided.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | invaliduser |
| Password | password123 |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "invaliduser",
  "password": "password123"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Enter an invalid username. |
| 4 | Enter a valid password. |
| 5 | Click **Send**. |
| 6 | Verify the API response. |

---

### Expected Result

- Status Code is **200 OK**.
- Response contains:

```json
{
  "reason": "Bad credentials"
}
```

- Authentication token is **not** generated.

---

### Notes

N/A

---

## TC-AUTH-003

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-003 |
| Test Scenario | SC-AUTH-003 |
| Priority | High |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify that authentication fails when an invalid password is provided.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | admin |
| Password | wrongpassword |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "admin",
  "password": "wrongpassword"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Enter a valid username. |
| 4 | Enter an invalid password. |
| 5 | Click **Send**. |
| 6 | Verify the API response. |

---

### Expected Result

- Status Code is **200 OK**.
- Response contains:

```json
{
  "reason": "Bad credentials"
}
```

- Authentication token is **not** generated.

---

### Notes

N/A

---

## TC-AUTH-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-004 |
| Test Scenario | SC-AUTH-004 |
| Priority | High |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify that authentication fails when both username and password are invalid.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | wronguser |
| Password | wrongpassword |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "wronguser",
  "password": "wrongpassword"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Enter an invalid username. |
| 4 | Enter an invalid password. |
| 5 | Click **Send**. |
| 6 | Verify the API response. |

---

### Expected Result

- Status Code is **200 OK**.
- Response contains **Bad credentials**.
- Authentication token is **not** generated.

---

### Notes

N/A

---

## TC-AUTH-005

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-005 |
| Test Scenario | SC-AUTH-005 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify authentication behavior when the username is empty.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | *(empty)* |
| Password | password123 |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "",
  "password": "password123"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Leave the username empty. |
| 4 | Enter a valid password. |
| 5 | Click **Send**. |
| 6 | Verify the API response. |

---

### Expected Result

- Authentication is rejected.
- No authentication token is generated.
- Appropriate response message is returned.

---

### Notes

N/A

---

## TC-AUTH-006

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-006 |
| Test Scenario | SC-AUTH-006 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify authentication behavior when the password is empty.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | admin |
| Password | *(empty)* |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "admin",
  "password": ""
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Enter a valid username. |
| 4 | Leave the password empty. |
| 5 | Click **Send**. |
| 6 | Verify the API response. |

---

### Expected Result

- Authentication is rejected.
- Authentication token is not generated.
- Appropriate response message is returned.

---

### Notes

N/A

---

## TC-AUTH-007

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-007 |
| Test Scenario | SC-AUTH-007 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify authentication behavior when both username and password are empty.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | *(empty)* |
| Password | *(empty)* |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "",
  "password": ""
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Leave both username and password empty. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- Authentication is rejected.
- Authentication token is not generated.
- Appropriate response message is returned.

---

### Notes

N/A

---

## TC-AUTH-008

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-008 |
| Test Scenario | SC-AUTH-008 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify API behavior when the username field is omitted from the request body.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | Missing |
| Password | password123 |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "password": "password123"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Remove the `username` field from the request body. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- Authentication is rejected.
- Token is not generated.
- API returns an appropriate validation response.

---

### Notes

Observe whether the API validates missing required fields correctly.

---

## TC-AUTH-009

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-009 |
| Test Scenario | SC-AUTH-009 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify API behavior when the password field is omitted from the request body.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | admin |
| Password | Missing |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "admin"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Remove the `password` field from the request body. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- Authentication is rejected.
- Token is not generated.
- API returns an appropriate validation response.

---

### Notes

Observe how the API handles missing required properties.

---

## TC-AUTH-010

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-010 |
| Test Scenario | SC-AUTH-010 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify API behavior when an empty request body is submitted.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

No request data.

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Send an empty JSON object as the request body. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- Authentication is rejected.
- Authentication token is not generated.
- API returns an appropriate validation response.

---

### Notes

Observe whether the API distinguishes between an empty request body and missing fields.

---

## TC-AUTH-011

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-011 |
| Test Scenario | SC-AUTH-011 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify API behavior when the request body contains malformed JSON.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

Malformed JSON payload.

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "admin",
  "password":
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Enter malformed JSON in the request body. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- API rejects the malformed request.
- Authentication token is not generated.
- Appropriate error message is returned.

---

### Notes

Observe the returned HTTP status code and error message.

---

## TC-AUTH-012

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-012 |
| Test Scenario | SC-AUTH-012 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify API behavior when an invalid Content-Type header is used.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Header | Value |
|--------|--------|
| Content-Type | text/plain |

---

### Request Headers

```http
Content-Type: text/plain
```

### Request Body

```text
username=admin&password=password123
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Change the Content-Type header to `text/plain`. |
| 4 | Send the request. |
| 5 | Verify the API response. |

---

### Expected Result

- API handles the invalid Content-Type appropriately.
- Authentication token is not generated.
- Appropriate response is returned.

---

### Notes

Observe whether the API validates the request header.

---

## TC-AUTH-013

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-013 |
| Test Scenario | SC-AUTH-013 |
| Priority | Low |
| Testing Type | Negative |
| HTTP Method | GET |
| Endpoint | /auth |

---

### Objective

Verify that unsupported HTTP methods are rejected.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

N/A

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a GET request to `/auth`. |
| 3 | Click **Send**. |
| 4 | Verify the API response. |

---

### Expected Result

- API rejects unsupported HTTP methods.
- Appropriate HTTP status code is returned.

---

### Notes

Common responses include **404 Not Found** or **405 Method Not Allowed**, depending on the API implementation.

---

## TC-AUTH-014

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-014 |
| Test Scenario | SC-AUTH-014 |
| Priority | Low |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify API behavior when unexpected fields are included in the request body.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | admin |
| Password | password123 |
| Role | administrator |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "admin",
  "password": "password123",
  "role": "administrator"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Add an unexpected field to the request body. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- API ignores or safely handles unexpected fields.
- Authentication process remains stable.
- No unexpected server error occurs.

---

### Notes

Observe whether unexpected fields affect the authentication process.

---

# Boundary Testing

---

## TC-AUTH-015

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-015 |
| Test Scenario | SC-AUTH-015 |
| Priority | Low |
| Testing Type | Boundary |
| HTTP Method | POST |
| Endpoint | /auth |

---

### Objective

Verify API behavior when extremely long username and password values are submitted.

---

### Preconditions

- RESTful Booker API is accessible.

---

### Test Data

| Field | Value |
|------|--------|
| Username | 256+ characters |
| Password | 256+ characters |

---

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
  "username": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "password": "bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb"
}
```

---

### Test Steps

| Step | Action |
|------|--------|
| 1 | Open Postman. |
| 2 | Create a POST request to `/auth`. |
| 3 | Enter extremely long username and password values. |
| 4 | Click **Send**. |
| 5 | Verify the API response. |

---

### Expected Result

- Authentication is rejected.
- API remains stable.
- No server crash or unexpected error occurs.

---

### Notes

This test verifies the endpoint's resilience against excessively long input values.

---

# Test Case Summary

| Category | Total |
|----------|------:|
| Positive Testing | 1 |
| Negative Testing | 13 |
| Boundary Testing | 1 |

**Total Test Cases: 15**

---

# Coverage Summary

| Coverage | Status |
|----------|:------:|
| Positive Testing | Yes |
| Negative Testing | Yes |
| Required Field Validation | Yes |
| Authentication Validation | Yes |
| Request Validation | Yes |
| Header Validation | Yes |
| HTTP Method Validation | Yes |
| Boundary Testing | Yes |

---

# Related Documents

- Test Plan
- Test Scenarios
- Test Data
- API Documentation
- Postman Collection
- Qase Test Cases

---

# Update History

| Version | Description |
|----------|-------------|
| 1.0 | Initial Authentication Test Cases |
| 1.1 | Expanded authentication coverage with comprehensive positive, negative, validation, and boundary test cases |
