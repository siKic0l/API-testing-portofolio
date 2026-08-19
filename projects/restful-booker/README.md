# RESTful Booker API Testing

A comprehensive **API Quality Assurance project** focused on testing the RESTful Booker API using manual API testing, structured test design, Postman, Qase.io, test evidence, and defect reporting.

This project demonstrates an end-to-end API testing workflow, starting from API documentation and endpoint analysis, followed by test planning, test scenario and test case design, manual execution, evidence collection, and defect reporting.

Automation using Postman Test Scripts and Newman is prepared as the next phase of the project.

---

# Project Overview

The **RESTful Booker API** is a public REST API that provides booking-related operations such as authentication, retrieving bookings, creating bookings, updating bookings, partially updating bookings, and deleting bookings.

This project was created to practice and demonstrate a structured API Quality Assurance workflow using a realistic REST API.

The project focuses on validating:

- API functionality
- Request and response behavior
- HTTP status codes
- Authentication
- Input validation
- CRUD operations
- Response schemas
- Error handling
- Data persistence
- Data integrity
- Defect identification

---

# Project Objectives

The main objectives of this project are to:

- Analyze RESTful Booker API documentation.
- Analyze available API endpoints and their behavior.
- Develop a structured API Test Strategy.
- Create a comprehensive Test Plan.
- Design Test Scenarios and Test Cases.
- Prepare reusable API Test Data.
- Perform Manual API Testing using Postman.
- Validate API responses and HTTP status codes.
- Verify authentication and authorization behavior.
- Validate CRUD operations.
- Identify functional and validation defects.
- Document defects with reproducible evidence.
- Manage test cases and executions using Qase.io.
- Prepare the project for API automation using Postman and Newman.

---

# API Under Test

| Item | Details |
| ---- | ------- |
| API | RESTful Booker |
| Base URL | https://restful-booker.herokuapp.com |
| API Type | REST API |
| Data Format | JSON |
| Authentication | Token-based |
| API Documentation | Postman API |
| Testing Client | Postman |

---

# API Modules

The project covers the following API modules:

| Module | HTTP Method | Endpoint | Testing Status |
| ------ | ----------- | -------- | -------------- |
| Health Check | GET | `/ping` | Completed |
| Authentication | POST | `/auth` | Completed |
| Get Booking | GET | `/booking` / `/booking/{id}` | Completed |
| Create Booking | POST | `/booking` | Completed |
| Update Booking | PUT | `/booking/{id}` | Completed |
| Partial Update Booking | PATCH | `/booking/{id}` | Completed |
| Delete Booking | DELETE | `/booking/{id}` | Completed |

> Note: The detailed manual execution documentation currently contains dedicated execution reports for Health Check, Authentication, Get Booking, Create Booking, Update Booking, Partial Update Booking, and Delete Booking.

---

# Testing Scope

## In Scope

The project covers:

### API Analysis

- API Documentation Review
- API Analysis
- Endpoint Analysis
- Request Analysis
- Response Analysis
- Authentication Analysis
- HTTP Method Analysis
- Parameter Analysis

### Functional Testing

- Health Check
- Authentication
- Booking Retrieval
- Booking Creation
- Full Booking Update
- Partial Booking Update
- Booking Deletion

### Validation Testing

- Required Field Validation
- Empty Values
- Null Values
- Invalid Data Types
- Invalid Date Formats
- Invalid Booking IDs
- Missing Request Objects
- Malformed JSON
- Unsupported Content-Type
- Boundary Values
- Invalid Authentication

### Response Validation

- HTTP Status Codes
- Response Body
- Response Schema
- Response Data Types
- Response Headers
- Response Time
- Data Persistence

### End-to-End Verification

- PUT followed by GET
- PATCH followed by GET
- DELETE followed by GET
- Data Integrity Verification

### Defect Management

- Defect Identification
- Bug Documentation
- Evidence Collection
- Test Case Traceability
- Bug-to-Test Case Traceability

---

# Out of Scope

The following activities are outside the scope of this project:

- UI Testing
- Mobile Testing
- Load Testing
- Stress Testing
- Performance Testing
- Security Penetration Testing
- Database Validation
- Source Code Review

---

# Testing Approach

The project follows a structured QA workflow.

```text
API Documentation Review
            ↓
API Analysis
            ↓
Endpoint Analysis
            ↓
Test Strategy
            ↓
Test Plan
            ↓
Test Scenario Design
            ↓
Test Case Design
            ↓
Test Data Preparation
            ↓
Manual API Testing
            ↓
Evidence Collection
            ↓
Defect Identification
            ↓
Bug Reporting
            ↓
Qase Test Execution
            ↓
API Automation
            ↓
Newman Execution
            ↓
Final Test Reporting
```

# Testing Techniques

The following testing techniques are applied throughout the project:

- Functional Testing
- Black Box Testing
- Positive Testing
- Negative Testing
- Validation Testing
- Boundary Value Analysis
- Equivalence Partitioning
- Error Guessing
- Exploratory Testing
- Authentication Testing
- Response Validation
- Data Integrity Testing
- End-to-End Verification

# Test Design

The project contains the following test design artifacts:

```
test-design/
│
├── 01-test-plan.md
├── 02-test-scenarios.md
├── 03-test-cases/
└── 04-test-data.md
```

The Test Case documentation is organized into:

```
03-test-cases/
│
├── authentication/
│   └── auth-test-cases.md
│
├── booking/
│   ├── create-booking.md
│   ├── get-booking.md
│   ├── update-booking.md
│   ├── partial-update-booking.md
│   └── delete-booking.md
│
└── health-check/
    └── health-check-test-cases.md
```

# Manual Testing

Manual API testing was performed using Postman.

Each module was executed against the public RESTful Booker API and documented with:

- Test Case ID
- Test Case Description
- HTTP Status Code
- Response Time
- Expected Result
- Actual Result
- Execution Status
- Evidence
- Bug ID
- Execution Notes

# Manual Test Execution Results

The current repository contains manual execution results for all major modules.

| Module                 | Test Cases | Passed | Failed | Blocked |   Bugs |
| ---------------------- | ---------: | -----: | -----: | ------: | -----: |
| Authentication         |         15 |     15 |      0 |       0 |      0 |
| Get Booking            |         12 |     12 |      0 |       0 |      0 |
| Create Booking         |         22 |     16 |      6 |       0 |      6 |
| Update Booking         |         18 |     18 |      0 |       0 |      4 |
| Partial Update Booking |         15 |     13 |      0 |       2 |      0 |
| Delete Booking         |         10 |     10 |      0 |       0 |      0 |
| Health Check           |          5 |      5 |      0 |       0 |      0 |
| **Total**              |     **97** | **89** |  **6** |   **2** | **10** |

## Overall Manual Testing Result

| Metric             | Result                               |
| ------------------ | ------------------------------------ |
| Total Test Cases   | 97                                   |
| Passed             | 89                                   |
| Failed             | 6                                    |
| Blocked            | 2                                    |
| Bugs Identified    | 10                                   |
| Execution Coverage | 100% of documented execution modules |

`The overall result above is based on the individual manual execution reports currently stored in the repository. Blocked test cases are not counted as failed because the intended behavior could not be conclusively evaluated.`

# Module Results

## Authentication

15 test cases were executed.
```
Passed: 15
Failed: 0
Blocked: 0
Bugs: 0
Pass Rate: 100%
```

The authentication module successfully validated token generation and authentication-related behavior.

[view authentication test executions](test-executions/manual-testing/auth-test-executions.md)

## Get Booking

12 test cases were executed.
```
Passed: 12
Failed: 0
Blocked: 0
Bugs: 0
Pass Rate: 100%
```

The module covered valid and invalid Booking IDs, boundary values, response schema, and response headers.

[view get booking test executions](test-executions/manual-testing/get-booking-test-executions.md)

## Create Booking

22 test cases were executed.
```
Passed: 16
Failed: 6
Blocked: 0
Bugs: 6
Pass Rate: 72.73%
```

The failed scenarios primarily involved validation and request-handling behavior, including:
```
Missing firstname
Missing lastname
Missing bookingdates
Empty JSON object
Invalid Content-Type
Null field values
```

[view create booking test executions](test-executions/manual-testing/create-booking-test-executions.md)

## Update Booking

18 test cases were executed.
```
Passed: 18
Failed: 0
Blocked: 0
Bugs: 4
Execution Pass Rate: 100%
```

Although all test cases passed according to the predefined execution criteria, several validation and business-rule weaknesses were identified.

Identified issues include:
```
totalprice accepts string values.
totalprice accepts negative values.
Invalid checkin date formats are accepted.
checkout dates earlier than checkin are accepted.
```

These issues were documented as separate defects.

[view update booking test executions](test-executions/manual-testing/update-booking-test-executions.md)

## Partial Update Booking

15 test cases were executed.
```
Passed: 13
Failed: 0
Blocked: 2
Bugs: 0
```

Two test cases were blocked because the API returned 403 Forbidden, which did not provide sufficient evidence to independently evaluate the intended Booking ID conditions.

Blocked scenarios:

- Non-existing Booking ID
- Invalid Booking ID format

These were intentionally marked BLOCKED rather than PASS or FAIL.

[view partial update booking test executions](test-executions/manual-testing/partial-update-test-executions.md)

## Delete Booking

10 test cases were executed.
```
Passed: 10
Failed: 0
Blocked: 0
Bugs: 0
Pass Rate: 100%
```

The module verified:
```
Successful booking deletion
Authentication requirements
Invalid Booking IDs
Repeated deletion
Deleted resource retrieval
Data integrity of unrelated bookings
```

[view delete booking test executions](test-executions/manual-testing/delete-booking-test-executions.md)

## Health Check

5 test cases were executed.
```
Passed: 5
Failed: 0
Blocked: 0
Bugs: 0
Pass Rate: 100%
```

The /ping endpoint consistently returned:

`201 Created`

with the response body:

`Created`

[view update booking test executions](test-executions/manual-testing/health-check-test-executions.md)

## Defect Management

A total of 10 defects are currently documented in the project.

| Module                 | Defects |
| ---------------------- | ------: |
| Create Booking         |       6 |
| Update Booking         |       4 |
| Partial Update Booking |       0 |
| Get Booking            |       0 |
| Delete Booking         |       0 |
| Authentication         |       0 |
| Health Check           |       0 |
| **Total**              |  **10** |

## Create Booking Defects
| Bug ID         | Related Test Case  | Description                                                               | Severity |
| -------------- | ------------------ | ------------------------------------------------------------------------- | -------- |
| BUG-CREATE-001 | TC-BOOK-CREATE-002 | Missing `firstname` is not handled as expected.                           | Medium   |
| BUG-CREATE-002 | TC-BOOK-CREATE-003 | Missing `lastname` is not handled as expected.                            | Medium   |
| BUG-CREATE-003 | TC-BOOK-CREATE-010 | Empty JSON request is not handled consistently.                           | Medium   |
| BUG-CREATE-004 | TC-BOOK-CREATE-019 | Invalid `Content-Type` is not handled according to the expected behavior. | Low      |
| BUG-CREATE-005 | TC-BOOK-CREATE-022 | Null values are not validated as expected.                                | Medium   |
| BUG-CREATE-006 | TC-BOOK-CREATE-009 | Missing `bookingdates` causes an unexpected `500 Internal Server Error`.  | Medium   |

[view create booking bug reports](bug-reports/create-booking)

## Update Booking Defects
| Bug ID              | Related Test Case  | Description                                                      | Severity |
| ------------------- | ------------------ | ---------------------------------------------------------------- | -------- |
| BUG-BOOK-UPDATE-001 | TC-BOOK-UPDATE-005 | `totalprice` accepts string values without data type validation. | Medium   |
| BUG-BOOK-UPDATE-002 | TC-BOOK-UPDATE-006 | Negative `totalprice` values are accepted.                       | Medium   |
| BUG-BOOK-UPDATE-003 | TC-BOOK-UPDATE-007 | Invalid `checkin` date formats are accepted.                     | Medium   |
| BUG-BOOK-UPDATE-004 | TC-BOOK-UPDATE-008 | `checkout` dates earlier than `checkin` are accepted.            | High     |

[view update booking bug reports](bug-reports/update-booking)

## Test Evidence

Evidence from manual testing is stored under:
```
evidence/
└── manual-testing/
    ├── auth/
    ├── booking/
    │   ├── create-booking/
    │   ├── delete-booking/
    │   ├── get-booking/
    │   ├── partial-update-booking/
    │   └── update-booking/
    │
    └── health-check/
```

The evidence files provide visual traceability between executed test cases and their actual API responses.

# Qase Test Management

Qase.io is used as the test management platform for the project.

The project includes documentation related to:

- Test Suites
- Test Runs
- est Metrics
- Public Reports

Qase is used to maintain traceability between:
```
Test Scenarios
      ↓
Test Cases
      ↓
Test Execution
      ↓
Defects
```

Qase-related documentation can be found in:

View Qase Documentation (soon)

# API Documentation

The project contains API documentation and endpoint analysis artifacts.
```
api-documentation/
│
├── README.md
├── endpoint-summary.md
└── postman-public-documentation.md
```

These documents provide information about the API endpoints, request methods, parameters, request bodies, responses, and API documentation references.

View API Documentation (soon)

# API Analysis

The API analysis phase contains:
```
api-analysis/
│
├── 01-project-overview.md
├── 02-api-analysis.md
├── 03-endpoint-analysis.md
└── 04-test-strategy.md
```

This phase establishes the API understanding and testing strategy before test execution.

View API Analysis (soon)

# Automation

The project repository contains the initial structure for Postman automation.
```
automation/
│
├── collections/
│   └── Restful-Booker.postman_collection.json
│
├── environments/
│   └── Local.postman_environment.json
│
├── globals/
│   └── Global.postman_globals.json
│
├── scripts/
│   ├── authentication.md
│   ├── assertions.md
│   ├── variables.md
│   └── collection-runner.md
│
└── newman/
    └── README.md
```

The automation phase is the next stage of this project and will focus on:

- Postman Test Scripts
- JavaScript Assertions
- Environment Variables
- Collection Variables
- Automated Response Validation
- Collection Runner
- Newman CLI
- Automated Execution Reports

Automation is currently in progress and is not included in the completed manual testing results above.

View Automation Documentation (soon)

# Project Documentation

The project documentation is organized into the following sections:

| Section                                                    | Description                                          |
| ---------------------------------------------------------- | ---------------------------------------------------- |
| [API Analysis](./api-analysis/)                            | API analysis, endpoint analysis, and test strategy   |
| [API Documentation](./api-documentation/)                  | Endpoint and API documentation                       |
| [Test Design](./test-design/)                              | Test Plan, Test Scenarios, Test Cases, and Test Data |
| [Manual Test Execution](./test-executions/manual-testing/) | Manual execution results and evidence references     |
| [Bug Reports](./bug-reports/)                              | Documented API defects                               |
| [Qase](./qase/)                                            | Test management documentation                        |
| [Automation](./automation/)                                | Postman and Newman automation resources              |
| [Evidence](./evidence/)                                    | Manual testing evidence                              |
| [Reports](./reports/)                                      | Project-level testing reports                        |

# Repository Structure
```
restful-booker/
│
├── README.md
│
├── api-documentation/
│   ├── README.md
│   ├── endpoint-summary.md
│   └── postman-public-documentation.md
│
├── api-analysis/
│   ├── 01-project-overview.md
│   ├── 02-api-analysis.md
│   ├── 03-endpoint-analysis.md
│   └── 04-test-strategy.md
│
├── test-design/
│   ├── 01-test-plan.md
│   ├── 02-test-scenarios.md
│   ├── 03-test-cases/
│   └── 04-test-data.md
│
├── test-executions/
│   └── manual-testing/
│       ├── README.md
│       ├── auth-test-executions.md
│       ├── create-booking-test-executions.md
│       ├── get-booking-test-executions.md
│       ├── update-booking-test-executions.md
│       ├── partial-update-test-executions.md
│       ├── delete-booking-test-executions.md
│       └── health-check-test-executions.md
│
├── automation/
│   ├── README.md
│   ├── collections/
│   ├── environments/
│   ├── globals/
│   ├── scripts/
│   └── newman/
│
├── qase/
│   ├── README.md
│   ├── test-suites.md
│   ├── test-runs.md
│   ├── test-metrics.md
│   └── public-report.md
│
├── bug-reports/
│   ├── create-booking/
│   └── update-booking/
│
├── evidence/
│   └── manual-testing/
│
└── reports/
```

# Tools & Technologies
## API Testing
- Postman
## API Documentation
- Postman API Documentation
## Test Management
- Qase.io
## Automation
- Postman Test Scripts
- JavaScript
- Newman
## Documentation
- Markdown
- Git
- GitHub

## Project Status
| Phase                    |     Status    |
| ------------------------ | :-----------: |
| API Documentation Review |  Completed  |
| API Analysis             |  Completed  |
| Endpoint Analysis        |  Completed  |
| Test Strategy            |  Completed  |
| Test Plan                |  Completed  |
| Test Scenarios           |  Completed  |
| Test Case Design         |  Completed  |
| Test Data                |  Completed  |
| Manual API Testing       |  Completed  |
| Test Evidence            |  Completed  |
| Defect Identification    |  Completed  |
| Bug Reporting            |  Completed  |
| Qase Test Management     |  Documented |
| Postman Automation       |   Planned   |
| Newman Execution         |   Planned   |
| Automation Reporting     |   Planned   |
| Final Project Report     |   Planned   |

# Key Findings

The manual testing phase identified several API validation weaknesses, particularly around booking creation and booking updates.

The most significant findings include:

- Missing required booking fields may not be validated correctly.
- Missing bookingdates may result in an unexpected server error.
- Invalid Content-Type handling is inconsistent.
- Null values may not be validated appropriately.
- totalprice accepts invalid string values.
- Negative totalprice values are accepted.
- Invalid booking date formats are accepted.
- Invalid booking date relationships are accepted.

These findings are documented individually in the project's Bug Reports section.

# Conclusion

The RESTful Booker API project demonstrates a complete manual API Quality Assurance workflow, from API analysis and test design through execution, evidence collection, and defect reporting.

The manual testing phase covered 97 documented test cases across seven API modules.

The execution resulted in:

- 89 passed test cases
- 6 failed test cases
- 2 blocked test cases
- 10 documented defects

The project provides traceability between API analysis, test cases, manual execution results, evidence, and bug reports.

The next phase of the project is API automation using Postman Test Scripts and Newman, building on the manual test cases and validation scenarios already established.

# Related Documents
- [API Analysis](api-analysis)
- [API Documentation](api-documentation)
- [Test Design](test-design)
- [Manual Test Execution](test-executions/manual-testing)
- [Bug Reports](bug-reports)
- [Qase Documentation](qase)
- [Automation](automation) (soon)
