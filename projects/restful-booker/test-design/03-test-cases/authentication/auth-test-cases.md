# Authentication Test Cases

## Overview

This document contains all test cases related to the **Authentication** endpoint of the RESTful Booker API.

The purpose of these test cases is to verify that the authentication mechanism correctly validates user credentials, generates authentication tokens, handles invalid requests, and returns appropriate HTTP status codes.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/auth` |
| Method | POST |
| Authentication | Not Required |
| Expected Success Status | 200 OK |

---

# Test Cases

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
| Endpoint | `/auth` |

### Objective

Verify that a valid authentication token is generated when correct credentials are provided.

### Preconditions

- RESTful Booker API is accessible.

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

### Test Steps

1. Send a POST request to `/auth`.
2. Provide valid username and password.
3. Submit the request.

### Expected Result

- Status Code is **200 OK**
- Response contains a valid authentication token.
- Response body is returned in JSON format.

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
| Endpoint | `/auth` |

### Objective

Verify that authentication fails when an invalid username is provided.

### Preconditions

- RESTful Booker API is accessible.

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

### Test Steps

1. Send a POST request to `/auth`.
2. Enter an invalid username.
3. Submit the request.

### Expected Result

- Status Code is **200 OK**
- Response contains

```json
{
  "reason": "Bad credentials"
}
```

- No authentication token is generated.

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
| Endpoint | `/auth` |

### Objective

Verify that authentication fails when an invalid password is provided.

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

### Test Steps

1. Send a POST request.
2. Enter an invalid password.
3. Submit the request.

### Expected Result

- Status Code is **200 OK**
- Response contains

```json
{
  "reason": "Bad credentials"
}
```

- No authentication token is generated.

---

## TC-AUTH-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-AUTH-004 |
| Test Scenario | SC-AUTH-004 |
| Priority | Medium |
| Testing Type | Negative |
| HTTP Method | POST |
| Endpoint | `/auth` |

### Objective

Verify the API response when both username and password are empty.

### Request Body

```json
{
  "username": "",
  "password": ""
}
```

### Test Steps

1. Send a POST request.
2. Leave username empty.
3. Leave password empty.
4. Submit the request.

### Expected Result

- Status Code is **200 OK**
- Authentication is rejected.
- No authentication token is generated.

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
| Endpoint | `/auth` |

### Objective

Verify API behavior when the request body contains malformed JSON.

### Request Body

```json
{
  "username": "admin",
  "password":
}
```

### Test Steps

1. Send a malformed JSON request.
2. Submit the request.

### Expected Result

- Status Code indicates an invalid request.
- Authentication token is not generated.
- Appropriate error response is returned.

---

# Test Case Summary

| ID | Scenario | Priority | Type |
|----|----------|----------|------|
| TC-AUTH-001 | Valid Authentication | High | Positive |
| TC-AUTH-002 | Invalid Username | High | Negative |
| TC-AUTH-003 | Invalid Password | High | Negative |
| TC-AUTH-004 | Empty Credentials | Medium | Negative |
| TC-AUTH-005 | Malformed JSON | Medium | Negative |

---

# Related Documents

- Test Plan
- Test Scenarios
- Test Data
- Endpoint Analysis
- Postman Collection
- Qase Test Cases

---

# Update History

| Version | Description |
|----------|-------------|
| 1.0 | Initial Authentication Test Cases |
