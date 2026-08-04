# API Test Strategy

## Overview

This document describes the testing strategy used for the Restful Booker API project.

The objective is to define the overall testing approach, scope, priorities, test levels, and testing techniques before creating test scenarios and executing API tests.

This strategy serves as the foundation for manual testing, Postman automation, Newman execution, and future CI/CD integration.

---

# Test Objectives

The primary objectives of this API testing project are:

- Verify all API endpoints function correctly.
- Validate request and response structures.
- Verify authentication and authorization behavior.
- Ensure data validation rules are enforced.
- Verify CRUD operations.
- Identify functional defects.
- Build reusable Postman collections for automation.

---

# Testing Scope

## In Scope

The following endpoints will be tested:

| Endpoint | Method |
|-----------|--------|
| /ping | GET |
| /auth | POST |
| /booking | GET |
| /booking/{id} | GET |
| /booking | POST |
| /booking/{id} | PUT |
| /booking/{id} | PATCH |
| /booking/{id} | DELETE |

Testing activities include:

- Endpoint validation
- Request validation
- Response validation
- Authentication testing
- CRUD testing
- Schema validation
- Status code validation
- Header validation
- Response time validation
- Manual execution
- Postman automation
- Newman execution

---

## Out of Scope

The following areas are not included in this project:

- UI Testing
- Mobile Testing
- Load Testing
- Stress Testing
- Security Penetration Testing
- Database Verification
- Source Code Review

---

# Test Levels

The project focuses on API-level testing.

Testing includes:

- Endpoint Testing
- Integration Validation
- Contract Validation
- Business Rule Validation

---

# Testing Types

## Functional Testing

Verify that each endpoint performs the expected business functionality.

Examples:

- Create booking
- Update booking
- Delete booking
- Retrieve booking

---

## Positive Testing

Verify that valid requests produce successful responses.

Examples:

- Valid authentication
- Valid booking creation
- Valid update request

---

## Negative Testing

Verify that invalid requests are handled correctly.

Examples:

- Invalid credentials
- Missing required fields
- Invalid booking ID
- Invalid JSON payload
- Unauthorized access

---

## Boundary Testing

Verify how the API behaves with boundary input values.

Examples:

- Empty strings
- Large numeric values
- Maximum character limits
- Minimum character limits

---

## Data Validation Testing

Verify that request payloads and responses follow the expected structure.

Examples:

- Required fields
- Data types
- JSON schema
- Null values

---

## Authentication Testing

Verify authentication behavior.

Examples:

- Valid token
- Invalid token
- Missing token
- Expired token (if supported)

---

## Regression Testing

Regression testing is performed after updating Postman collections or modifying requests to ensure previously working endpoints continue functioning correctly.

---

# Test Design Techniques

The following techniques are applied throughout the project.

| Technique | Purpose |
|-----------|---------|
| Positive Testing | Verify expected behavior |
| Negative Testing | Verify error handling |
| Boundary Value Analysis | Validate limits |
| Equivalence Partitioning | Reduce redundant test cases |
| Error Guessing | Identify unexpected failures |

---

# Test Prioritization

| Priority | Description |
|----------|-------------|
| Critical | Authentication, Booking Creation, Update, Delete |
| High | Retrieve Booking, Retrieve Booking List |
| Medium | Response Validation, Headers, Filtering |
| Low | Ping Endpoint |

---

# Test Environment

| Item | Value |
|------|-------|
| API | Restful Booker API |
| Client | Postman |
| Automation | Postman Collection Runner |
| CLI Runner | Newman |
| Test Management | Qase.io |
| Documentation | Markdown |
| Version Control | GitHub |

---

# Entry Criteria

Testing may begin when:

- API is accessible.
- Postman environment has been configured.
- Required authentication information is available.
- Test data has been prepared.
- Test scenarios have been reviewed.

---

# Exit Criteria

Testing is considered complete when:

- All planned endpoints have been executed.
- All critical test cases have passed.
- Known defects have been documented.
- Test execution results have been recorded.
- Test summary report has been completed.
- Postman automation executes successfully.
- Newman execution completes successfully.

---

# Deliverables

This project will produce the following QA artifacts:

- API Analysis
- Test Strategy
- Test Plan
- Test Scenarios
- Test Cases
- Test Data
- Manual Test Execution
- Postman Collection
- Environment Configuration
- Automation Scripts
- Newman Report
- Bug Reports
- Test Summary Report
- Qase Test Report

---

# Risk Assessment

| Risk | Mitigation |
|------|------------|
| Public API availability | Re-run failed tests after service recovery |
| Test data changes | Create reusable dynamic test data |
| Authentication failures | Regenerate authentication token before execution |
| API updates | Review endpoint documentation before regression testing |

---

# Success Criteria

The project is considered successful when:

- All planned endpoints are tested.
- Manual test cases are completed.
- Automation scripts execute successfully.
- Newman execution completes without unexpected failures.
- Test evidence is documented.
- Bug reports are created for confirmed defects.
- Documentation is complete and reproducible.

---

# QA Workflow

The testing workflow for this project follows these phases:

```
API Analysis
      ↓
Test Strategy
      ↓
Test Plan
      ↓
Test Scenarios
      ↓
Test Cases
      ↓
Prepare Test Data
      ↓
Manual API Testing
      ↓
Postman Automation
      ↓
Newman Execution
      ↓
Qase Test Execution
      ↓
Bug Reporting
      ↓
Test Summary Report
```

---

# Conclusion

This testing strategy defines a structured and repeatable approach for validating the Restful Booker API.

The project combines manual API testing, Postman automation, Newman execution, and Qase.io test management to simulate a real-world API Quality Assurance workflow while producing professional testing documentation.
