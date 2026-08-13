# Qase Test Suites

## Overview

Qase.io is used as the test management platform for the RESTful Booker API testing project.

The test cases are organized into suites based on the API modules and their respective endpoints. Each suite contains functional, validation, negative, authentication, response validation, and end-to-end test scenarios according to the scope of each module.

The Qase test suites are aligned with the test case documentation stored in the repository under:

`test-design/03-test-cases/`

---

## Test Suite Summary

| Suite | Module | HTTP Method | Endpoint | Test Cases |
|-------|--------|-------------|----------|-----------:|
| Health Check | Health Check | GET | `/ping` | 5 |
| Authentication | Authentication | POST | `/auth` | 15 |
| Get Booking | Booking Retrieval | GET | `/booking` / `/booking/{id}` | 12 |
| Create Booking | Booking Creation | POST | `/booking` | 22 |
| Update Booking | Full Booking Update | PUT | `/booking/{id}` | 18 |
| Partial Update Booking | Partial Booking Update | PATCH | `/booking/{id}` | 15 |
| Delete Booking | Booking Deletion | DELETE | `/booking/{id}` | 10 |
| **Total** | | | | **97** |

---

# 1. Health Check

### Suite Information

| Field | Value |
|-------|-------|
| Suite | Health Check |
| Module | Health Check |
| HTTP Method | GET |
| Endpoint | `/ping` |
| Authentication | Not Required |
| Test Cases | 5 |

### Coverage

The Health Check suite verifies that the API service is available, responsive, and returns the expected response.

Coverage includes:

- Endpoint availability
- HTTP status code validation
- Response body validation
- Response time observation
- Response consistency

### Test Cases

| Test Case ID | Description |
|--------------|-------------|
| TC-PING-001 | Verify Health Check endpoint accessibility |
| TC-PING-002 | Verify Health Check HTTP status code |
| TC-PING-003 | Verify Health Check response body |
| TC-PING-004 | Verify Health Check response time |
| TC-PING-005 | Verify Health Check response consistency |

Repository test case documentation:

`test-design/03-test-cases/health-check/health-check-test-cases.md`

---

# 2. Authentication

### Suite Information

| Field | Value |
|-------|-------|
| Suite | Authentication |
| Module | Authentication |
| HTTP Method | POST |
| Endpoint | `/auth` |
| Authentication | Not Required |
| Test Cases | 15 |

### Coverage

The Authentication suite verifies authentication behavior and token generation.

Coverage includes:

- Valid authentication credentials
- Invalid username
- Invalid password
- Missing credentials
- Empty credentials
- Invalid credential combinations
- Authentication response validation
- Token generation
- Authentication error handling

### Test Cases

The suite contains **15 test cases** covering authentication and token-generation scenarios.

Repository test case documentation:

`test-design/03-test-cases/authentication/auth-test-cases.md`

---

# 3. Get Booking

### Suite Information

| Field | Value |
|-------|-------|
| Suite | Get Booking |
| Module | Booking Retrieval |
| HTTP Method | GET |
| Endpoint | `/booking` / `/booking/{id}` |
| Authentication | Not Required |
| Test Cases | 12 |

### Coverage

The Get Booking suite verifies that booking information can be retrieved correctly.

Coverage includes:

- Retrieve booking using a valid Booking ID
- Retrieve multiple existing bookings
- Non-existing Booking ID
- Invalid Booking ID format
- Response status code validation
- Response body validation
- Response schema validation
- Response data type validation
- Response header validation
- Booking data accuracy

The test case documentation defines the Get Booking module as covering booking retrieval using `/booking` and `/booking/{id}`. :contentReference[oaicite:2]{index=2}

### Test Cases

| Test Case ID | Description |
|--------------|-------------|
| TC-BOOK-GET-001 | Verify booking retrieval using a valid Booking ID |
| TC-BOOK-GET-002 | Verify retrieval of another existing booking |
| TC-BOOK-GET-003 | Verify behavior for a non-existing Booking ID |
| ... | Additional Get Booking validation and response test cases |
| **Total** | **12** |

Repository test case documentation:

`test-design/03-test-cases/booking/get-booking.md`

---

# 4. Create Booking

### Suite Information

| Field | Value |
|-------|-------|
| Suite | Create Booking |
| Module | Booking Creation |
| HTTP Method | POST |
| Endpoint | `/booking` |
| Authentication | Not Required |
| Test Cases | 22 |

### Coverage

The Create Booking suite verifies booking creation using valid and invalid request payloads.

Coverage includes:

- Valid booking creation
- Required field validation
- Missing fields
- Empty values
- Missing request objects
- Empty JSON request
- Invalid numeric values
- Invalid data types
- Invalid date formats
- Invalid booking date logic
- Boundary values
- Unexpected properties
- Null values
- Content-Type validation
- Malformed JSON

### Test Cases

| Test Case ID | Description |
|--------------|-------------|
| TC-BOOK-CREATE-001 to TC-BOOK-CREATE-022 | Booking creation, validation, negative, boundary, and request validation scenarios |
| **Total** | **22** |

The project currently documents six Create Booking defects related to missing fields, empty JSON, invalid Content-Type, null values, and missing booking dates. :contentReference[oaicite:3]{index=3}

Repository test case documentation:

`test-design/03-test-cases/booking/create-booking.md`

---

# 5. Update Booking

### Suite Information

| Field | Value |
|-------|-------|
| Suite | Update Booking |
| Module | Full Booking Update |
| HTTP Method | PUT |
| Endpoint | `/booking/{id}` |
| Authentication | Required |
| Test Cases | 18 |

### Coverage

The Update Booking suite verifies full booking resource updates.

Coverage includes:

- Successful full booking update
- Required field validation
- Invalid data types
- Negative numeric values
- Invalid date formats
- Invalid booking date logic
- Invalid Booking IDs
- Authentication validation
- Response validation
- Data persistence
- End-to-end PUT followed by GET verification

The project identified four Update Booking defects involving `totalprice` data types, negative values, invalid `checkin` formats, and invalid checkout/checkin date logic. :contentReference[oaicite:4]{index=4}

### Test Cases

| Test Case ID | Description |
|--------------|-------------|
| TC-BOOK-UPDATE-001 to TC-BOOK-UPDATE-018 | Full booking update and validation scenarios |
| **Total** | **18** |

Repository test case documentation:

`test-design/03-test-cases/booking/update-booking.md`

---

# 6. Partial Update Booking

### Suite Information

| Field | Value |
|-------|-------|
| Suite | Partial Update Booking |
| Module | Partial Booking Update |
| HTTP Method | PATCH |
| Endpoint | `/booking/{id}` |
| Authentication | Required |
| Test Cases | 15 |

### Coverage

The Partial Update Booking suite verifies that individual booking fields can be updated without unintentionally modifying other booking data.

Coverage includes:

- Individual field updates
- Multiple field updates
- Empty values
- Invalid data types
- Invalid date formats
- Null values
- Non-existing Booking IDs
- Invalid Booking ID formats
- Authentication validation
- Invalid authentication token
- Response schema validation
- Data persistence
- End-to-end PATCH followed by GET verification

The project records 15 Partial Update Booking test cases, with 13 passed and 2 blocked during manual execution. The blocked scenarios involved non-existing and invalid Booking IDs. :contentReference[oaicite:5]{index=5}

### Test Cases

| Test Case ID | Description |
|--------------|-------------|
| TC-BOOK-PATCH-001 to TC-BOOK-PATCH-015 | Partial booking update and validation scenarios |
| **Total** | **15** |

Repository test case documentation:

`test-design/03-test-cases/booking/partial-update-booking.md`

---

# 7. Delete Booking

### Suite Information

| Field | Value |
|-------|-------|
| Suite | Delete Booking |
| Module | Booking Deletion |
| HTTP Method | DELETE |
| Endpoint | `/booking/{id}` |
| Authentication | Required |
| Test Cases | 10 |

### Coverage

The Delete Booking suite verifies that booking records can be deleted correctly and that deleted resources are no longer accessible.

Coverage includes:

- Successful booking deletion
- Authentication requirements
- Missing authentication
- Invalid authentication
- Invalid Booking IDs
- Non-existing Booking IDs
- Repeated deletion
- Deleted resource retrieval
- Data integrity of unrelated bookings
- End-to-end DELETE followed by GET verification

The Delete Booking module contains 10 executed test cases, all of which passed during the documented manual execution. :contentReference[oaicite:6]{index=6}

### Test Cases

| Test Case ID | Description |
|--------------|-------------|
| TC-BOOK-DELETE-001 to TC-BOOK-DELETE-010 | Booking deletion, authentication, validation, and data integrity scenarios |
| **Total** | **10** |

Repository test case documentation:

`test-design/03-test-cases/booking/delete-booking.md`

---

# Overall Test Suite Summary

| Suite | Test Cases | Repository Documentation |
|-------|-----------:|---------------------------|
| Health Check | 5 | `health-check/health-check-test-cases.md` |
| Authentication | 15 | `authentication/auth-test-cases.md` |
| Get Booking | 12 | `booking/get-booking.md` |
| Create Booking | 22 | `booking/create-booking.md` |
| Update Booking | 18 | `booking/update-booking.md` |
| Partial Update Booking | 15 | `booking/partial-update-booking.md` |
| Delete Booking | 10 | `booking/delete-booking.md` |
| **Total** | **97** | |

---

# Qase Organization

The Qase project is organized according to the API modules defined in the test design.

```text
Qase Project
│
├── Health Check
│   └── 5 Test Cases
│
├── Authentication
│   └── 15 Test Cases
│
└── Booking
    │
    ├── Get Booking
    │   └── 12 Test Cases
    │
    ├── Create Booking
    │   └── 22 Test Cases
    │
    ├── Update Booking
    │   └── 18 Test Cases
    │
    ├── Partial Update Booking
    │   └── 15 Test Cases
    │
    └── Delete Booking
        └── 10 Test Cases
```
Total: 97 Test Cases

# Traceability

The Qase test suites are intended to maintain traceability between:
```
API Documentation
       ↓
API Analysis
       ↓
Test Scenarios
       ↓
Test Cases
       ↓
Qase Test Suites
       ↓
Qase Test Runs
       ↓
Manual Test Execution
       ↓
Evidence
       ↓
Defect Reports
       ↓
Automation
       ↓
Final Test Report
```
The repository follows this same QA workflow, including Qase Test Execution before API automation and Newman execution.

# Test Case Distribution

| Module                 | Test Cases | Percentage |
| ---------------------- | ---------: | ---------: |
| Create Booking         |         22 |     22.68% |
| Update Booking         |         18 |     18.56% |
| Authentication         |         15 |     15.46% |
| Partial Update Booking |         15 |     15.46% |
| Get Booking            |         12 |     12.37% |
| Delete Booking         |         10 |     10.31% |
| Health Check           |          5 |      5.15% |
| **Total**              |     **97** |   **100%** |

# Notes

- Test case IDs and test case details are maintained in the Qase test management project.
- Detailed test case definitions are maintained separately under test-design/03-test-cases/.
- Manual execution results are maintained under test-executions/manual-testing/.
- Evidence is maintained under evidence/manual-testing/.
- Defects are documented under bug-reports/.
- Qase is used to maintain traceability between test scenarios, test cases, execution results, and defects.
