# Test Cases

## Overview

This directory contains all detailed API test cases created for the RESTful Booker API Testing project.

Each test case is derived from the approved Test Scenarios and is designed to validate specific API behaviors, expected responses, input validations, authentication requirements, and business rules.

These test cases serve as the primary reference for manual API testing, Qase.io test management, and Postman execution.

---

# Purpose

The objectives of this directory are to:

- Translate test scenarios into executable test cases.
- Provide detailed testing instructions for each API endpoint.
- Ensure complete test coverage.
- Support manual API testing.
- Support API automation development.
- Maintain consistency between documentation, Postman collections, and Qase.io.

---

# Directory Structure

```text
03-test-cases
│
├── README.md
│
├── authentication
│   └── auth-test-cases.md
│
├── booking
│   ├── create-booking.md
│   ├── get-booking.md
│   ├── update-booking.md
│   ├── partial-update-booking.md
│   ├── delete-booking.md
│   └── booking-list.md
│
└── health-check
    └── ping-test-cases.md
```

---

# Test Case Organization

The test cases are organized by API resource to improve readability and maintenance.

## Authentication

Covers authentication-related testing.

Included endpoint:

- POST `/auth`

---

## Booking

Covers all booking operations.

Included endpoints:

- GET `/booking`
- GET `/booking/{id}`
- POST `/booking`
- PUT `/booking/{id}`
- PATCH `/booking/{id}`
- DELETE `/booking/{id}`

---

## Health Check

Covers API availability verification.

Included endpoint:

- GET `/ping`

---

# Test Case Format

Each test case includes the following information:

- Test Case ID
- Test Scenario Reference
- Test Objective
- HTTP Method
- Endpoint
- Preconditions
- Request Headers
- Request Body
- Test Steps
- Expected Result
- Expected Status Code
- Priority

---

# Test Coverage

The test cases include validation for:

- Functional Testing
- Positive Testing
- Negative Testing
- Authentication Testing
- CRUD Operations
- Input Validation
- Required Field Validation
- Invalid Data Handling
- Boundary Value Testing
- Error Handling
- HTTP Status Code Validation

---

# Execution

The test cases in this directory will be executed using:

- Postman
- Qase.io
- Newman (Automation Phase)

Execution results, evidence, and bug reports are documented in the corresponding project folders.

---

# Related Documents

This directory is closely related to:

- Test Plan
- Test Scenarios
- Test Data
- API Analysis
- Endpoint Summary
- Postman Collection
- Qase.io Test Cases
- Newman Reports

---

# Update History

| Version | Description |
|----------|-------------|
| 1.0 | Initial Test Case documentation structure |
