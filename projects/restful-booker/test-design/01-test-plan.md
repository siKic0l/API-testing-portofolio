# Test Plan

## Project Information

| Item | Details |
|------|---------|
| Project | RESTful Booker API Testing Portfolio |
| API | RESTful Booker |
| Testing Type | Manual API Testing & API Automation |
| Tester | Nurrohmi Zaki |
| Version | 1.1 |
| Status | In Progress |

---

# Version History

| Version | Description |
|----------|-------------|
| 1.0 | Initial API Test Plan |
| 1.1 | Test Design Phase Completed |
| 1.2 | Manual API Testing Completed (Planned) |
| 1.3 | API Automation Completed (Planned) |

---

# 1. Introduction

This document defines the overall testing strategy for the RESTful Booker API.

The objective of this test plan is to establish the testing scope, testing approach, priorities, environment, deliverables, and quality objectives before executing manual and automated API testing.

The testing process follows a structured Quality Assurance workflow beginning with API analysis, followed by test design, manual execution, automation, and reporting.

---

# 2. Objectives

The objectives of this project are to:

- Verify that every API endpoint functions according to its specification.
- Validate request and response structures.
- Verify HTTP status codes.
- Validate API authentication.
- Detect functional defects.
- Build reusable API automation scripts.
- Produce professional API testing documentation.

---

# 3. Scope

## In Scope

The following endpoints are included in this project.

### Authentication

- Generate Authentication Token

### Booking

- Get Booking IDs
- Get Booking Detail
- Create Booking
- Update Booking
- Partial Update Booking
- Delete Booking

### Health Check

- Ping API

---

## Out of Scope

The following activities are excluded from this project.

- Performance Testing
- Load Testing
- Stress Testing
- Security Penetration Testing
- Source Code Review
- Database Validation

---

# 4. Test Environment

| Item | Details |
|------|---------|
| API | RESTful Booker |
| Base URL | https://restful-booker.herokuapp.com |
| Client | Postman |
| Operating System | Windows 11 |
| Internet | Stable Internet Connection |
| Version Control | GitHub |
| Test Management | Qase.io |

---

# 5. Testing Types

The following testing approaches will be applied.

- Manual API Testing
- Functional Testing
- Positive Testing
- Negative Testing
- Boundary Value Testing
- Error Handling Validation
- Authentication Testing
- CRUD Testing
- Regression Testing (if required)
- API Automation Testing

---

# 6. Test Strategy

Testing will be conducted in two major phases.

## Phase 1

Manual API Testing

Activities include:

- Endpoint Validation
- Request Validation
- Response Validation
- Status Code Validation
- Authentication Validation
- Data Validation
- Error Handling Validation

---

## Phase 2

API Automation

Activities include:

- Postman Test Scripts
- Assertions
- Environment Variables
- Collection Runner
- Newman Execution
- Automated Report Generation

---

# 7. Entry Criteria

Testing may begin when:

- RESTful Booker API is accessible.
- API documentation has been reviewed.
- Test Plan is completed.
- Test Scenarios are prepared.
- Test Cases are prepared.
- Test Environment is available.

---

# 8. Exit Criteria

Testing will be considered complete when:

- All planned test cases have been executed.
- Critical defects have been documented.
- Manual execution has been completed.
- Automation scripts have been implemented.
- Newman reports have been generated.
- Test Summary Report has been completed.

---

# 9. Product Risk Analysis

| Feature | Potential Risk | Impact | Priority |
|----------|----------------|--------|----------|
| Authentication | Invalid token generation | High | High |
| Create Booking | Booking creation fails | High | High |
| Update Booking | Incorrect booking update | High | High |
| Delete Booking | Booking cannot be deleted | High | High |
| Booking Retrieval | Incorrect booking information | Medium | Medium |
| Health Check | API unavailable | Low | Low |

---

# 10. Risk Mitigation

| Risk | Mitigation |
|------|------------|
| Authentication failure | Validate both valid and invalid credentials |
| Invalid request body | Perform positive and negative testing |
| Missing required fields | Boundary and validation testing |
| Authorization failure | Test authenticated and unauthenticated requests |
| API downtime | Execute health check before testing |

---

# 11. Test Prioritization

## High Priority

- Authentication
- Create Booking
- Get Booking Detail
- Update Booking
- Delete Booking

---

## Medium Priority

- Get Booking IDs
- Partial Update Booking

---

## Low Priority

- Ping API

---

# 12. Test Deliverables

The following artifacts will be produced.

- API Analysis
- API Documentation
- Test Plan
- Test Scenarios
- Test Cases
- Test Data
- Postman Collection
- Environment Configuration
- Manual Test Execution
- Bug Reports
- Automation Scripts
- Newman Reports
- Test Summary Report

---

# 13. Assumptions

The following assumptions apply during testing.

- RESTful Booker API remains publicly accessible.
- API behavior remains consistent throughout the project.
- Stable internet connection is available.
- Postman is functioning correctly.
- GitHub repository is available.

---

# 14. Constraints

The following limitations apply.

- Source code is unavailable.
- Database access is unavailable.
- Performance testing is excluded.
- Security penetration testing is excluded.
- Third-party infrastructure cannot be modified.

---

# 15. Test Schedule

| Phase | Status |
|--------|--------|
| API Analysis | Completed |
| API Documentation | Completed |
| Test Planning | Completed |
| Test Scenarios | Completed |
| Test Cases | Completed |
| Test Data | Completed |
| Manual API Testing | In Progress |
| API Automation | Planned |
| Newman Execution | Planned |
| Test Summary Report | Planned |

---

# Success Criteria

The project is considered successful if it demonstrates:

- Complete API testing documentation.
- Structured test design.
- Comprehensive manual API testing.
- Professional API automation using Postman.
- Automated execution using Newman.
- Clear and reproducible defect reporting.
- Well-organized testing evidence.
- Industry-standard QA workflow.

---

# Related Documents

This Test Plan is supported by the following project documents.

- Project Overview
- API Analysis
- Endpoint Analysis
- Test Strategy
- Test Scenarios
- Test Cases
- Test Data
- Postman Collection
- Newman Reports
- Test Summary Report

---

# Conclusion

This Test Plan defines the overall Quality Assurance strategy for the RESTful Booker API Testing Portfolio.

The project will continue with detailed Test Scenario creation, Test Case design, Manual API Testing using Postman, API Automation, Newman execution, and final reporting to demonstrate a complete API testing workflow aligned with industry practices.
