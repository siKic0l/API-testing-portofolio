# Authentication Test Cases

## Overview

This document contains detailed test cases for the **Authentication** endpoint of the RESTful Booker API.

The objective of these test cases is to verify that the authentication endpoint correctly validates user credentials, generates authentication tokens, rejects invalid requests, and handles malformed input appropriately.

These test cases will be executed manually using Postman, managed in Qase.io, and later automated using Postman Test Scripts and Newman.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/auth` |
| Method | POST |
| Authentication Required | No |
| Content-Type | application/json |
| Expected Success Status | 200 OK |

---

# Test Cases

---

# Positive Testing

---

## TC-AUTH-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-001 |
| Scenario | SC-AUTH-001 |
| Priority | High |
| Type | Positive |

### Objective

Verify that the API successfully generates an authentication token when valid credentials are provided.

### Preconditions

- RESTful Booker API is accessible.

### Request Headers

```http
Content-Type: application/json
```

### Request Body

```json
{
    "username":"admin",
    "password":"password123"
}
```

### Expected Result

- Status Code is **200**
- Response Body contains **token**
- Token value is not empty

---

# Negative Testing

---

## TC-AUTH-002

### Objective

Verify authentication fails when an invalid username is provided.

Request

```json
{
    "username":"invaliduser",
    "password":"password123"
}
```

Expected Result

- Status Code is **200**
- Response

```json
{
    "reason":"Bad credentials"
}
```

---

## TC-AUTH-003

### Objective

Verify authentication fails when an invalid password is provided.

Request

```json
{
    "username":"admin",
    "password":"wrongpassword"
}
```

Expected Result

- Status Code is **200**
- Bad credentials returned

---

## TC-AUTH-004

### Objective

Verify authentication fails when both username and password are invalid.

Request

```json
{
    "username":"wrong",
    "password":"wrong"
}
```

Expected Result

- Bad credentials returned
- Token is not generated

---

## TC-AUTH-005

### Objective

Verify authentication fails when username is empty.

Request

```json
{
    "username":"",
    "password":"password123"
}
```

Expected Result

- Authentication rejected

---

## TC-AUTH-006

### Objective

Verify authentication fails when password is empty.

Request

```json
{
    "username":"admin",
    "password":""
}
```

Expected Result

- Authentication rejected

---

## TC-AUTH-007

### Objective

Verify authentication fails when both credentials are empty.

Request

```json
{
    "username":"",
    "password":""
}
```

Expected Result

- Authentication rejected

---

## TC-AUTH-008

### Objective

Verify API behavior when username field is missing.

Request

```json
{
    "password":"password123"
}
```

Expected Result

- Authentication rejected

---

## TC-AUTH-009

### Objective

Verify API behavior when password field is missing.

Request

```json
{
    "username":"admin"
}
```

Expected Result

- Authentication rejected

---

## TC-AUTH-010

### Objective

Verify API behavior when request body is empty.

Request

```json
{}
```

Expected Result

- Authentication rejected

---

## TC-AUTH-011

### Objective

Verify API behavior when malformed JSON is submitted.

Request

```json
{
    "username":"admin",
    "password":
}
```

Expected Result

- Invalid request is returned
- Token is not generated

---

## TC-AUTH-012

### Objective

Verify API behavior when Content-Type is incorrect.

Header

```http
Content-Type: text/plain
```

Expected Result

- API rejects unsupported content type or returns appropriate error

---

## TC-AUTH-013

### Objective

Verify endpoint rejects unsupported HTTP methods.

Method

```http
GET /auth
```

Expected Result

- Method not allowed
- Appropriate HTTP status code returned

---

## TC-AUTH-014

### Objective

Verify API ignores or rejects unexpected additional fields.

Request

```json
{
    "username":"admin",
    "password":"password123",
    "role":"administrator"
}
```

Expected Result

- Authentication still behaves correctly
- No unexpected behavior occurs

---

# Boundary Testing

---

## TC-AUTH-015

### Objective

Verify API behavior when extremely long username and password values are submitted.

Request

```json
{
    "username":"aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "password":"bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb"
}
```

Expected Result

- Authentication rejected
- API remains stable
- No server error occurs

---

# Test Case Summary

| ID | Category | Priority |
|----|----------|----------|
| TC-AUTH-001 | Valid Authentication | High |
| TC-AUTH-002 | Invalid Username | High |
| TC-AUTH-003 | Invalid Password | High |
| TC-AUTH-004 | Invalid Credentials | High |
| TC-AUTH-005 | Empty Username | Medium |
| TC-AUTH-006 | Empty Password | Medium |
| TC-AUTH-007 | Empty Credentials | Medium |
| TC-AUTH-008 | Missing Username | Medium |
| TC-AUTH-009 | Missing Password | Medium |
| TC-AUTH-010 | Empty Request Body | Medium |
| TC-AUTH-011 | Malformed JSON | Medium |
| TC-AUTH-012 | Invalid Content-Type | Medium |
| TC-AUTH-013 | Unsupported HTTP Method | Low |
| TC-AUTH-014 | Unexpected Fields | Low |
| TC-AUTH-015 | Boundary Input Length | Low |

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
| Boundary Value Testing | Yes |

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
