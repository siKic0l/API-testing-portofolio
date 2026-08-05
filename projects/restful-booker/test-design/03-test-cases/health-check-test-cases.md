# Health Check Test Cases

## Overview

This document contains manual test cases for the **Health Check** endpoint of the RESTful Booker API.

The objective of these test cases is to verify that the API service is available, responsive, and consistently returns the expected response. Health Check testing is commonly used as a quick verification before executing more comprehensive API testing.

These test cases will be executed manually using **Postman**, managed in **Qase.io**, and later automated using **Postman Test Scripts** and **Newman**.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/ping` |
| HTTP Method | GET |
| Authentication | Not Required |
| Expected Success Status | 201 Created |

---

# Shared Preconditions

The following preconditions apply to all test cases unless otherwise stated.

- RESTful Booker API is accessible.
- Postman is installed and configured.
- Base URL has been configured.
- Internet connection is stable.

---

# Positive Testing

## TC-PING-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-PING-001 |
| Test Scenario | SC-PING-001 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that the Health Check endpoint is accessible.

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a GET request to `/ping`.|
|3|Click **Send**.|
|4|Verify the response.|

---

### Expected Result

- Endpoint is accessible.
- Request completes successfully.
- No unexpected server error occurs.

---

### Notes

This test confirms basic API availability.

---

# Response Validation

## TC-PING-002

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-PING-002 |
| Test Scenario | SC-PING-002 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify that the endpoint returns the expected HTTP status code.

---

### Test Steps

| Step | Action |
|------|--------|
|1|Send a GET request to `/ping`.|
|2|Observe the returned status code.|

---

### Expected Result

- Status Code is **201 Created**.

---

### Notes

Confirms compliance with the API specification.

---

## TC-PING-003

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-PING-003 |
| Test Scenario | SC-PING-003 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify that the response body matches the expected value.

---

### Test Steps

| Step | Action |
|------|--------|
|1|Send a GET request to `/ping`.|
|2|Inspect the response body.|

---

### Expected Result

- Response Body is:

```text
Created
```

---

### Notes

Confirms that the API returns the expected response payload.

---

## TC-PING-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-PING-004 |
| Test Scenario | SC-PING-004 |
| Priority | Low |
| Testing Type | Performance Observation |

---

### Objective

Verify that the endpoint responds within an acceptable response time.

---

### Test Steps

| Step | Action |
|------|--------|
|1|Send a GET request to `/ping`.|
|2|Observe the response time displayed in Postman.|

---

### Expected Result

- Request completes successfully.
- Response time is acceptable (for example, less than 1000 ms).

---

### Notes

This is an observation only and is not a formal performance test.

---

# Reliability Testing

## TC-PING-005

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-PING-005 |
| Test Scenario | SC-PING-005 |
| Priority | Medium |
| Testing Type | Reliability |

---

### Objective

Verify that repeated requests return consistent responses.

---

### Test Steps

| Step | Action |
|------|--------|
|1|Send the GET request to `/ping` multiple times consecutively (at least 5).|
|2|Observe every response.|

---

### Expected Result

- Every request returns **201 Created**.
- Every response body is **Created**.
- No intermittent failures occur.

---

### Notes

This verifies the consistency of the Health Check endpoint.

---

# Test Case Summary

| Category | Total |
|----------|------:|
| Positive Testing | 1 |
| Validation Testing | 2 |
| Performance Observation | 1 |
| Reliability Testing | 1 |
| **Total Test Cases** | **5** |

---

# Coverage Summary

| Coverage | Status |
|----------|:------:|
| Endpoint Availability | Covered |
| Status Code Validation | Covered |
| Response Body Validation | Covered |
| Response Time Observation | Covered |
| Response Consistency | Covered |

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
| 1.0 | Initial Health Check Test Cases |
