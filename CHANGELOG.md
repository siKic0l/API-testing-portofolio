# Changelog

This document records the development and documentation progress of the **RESTful Booker API Testing Project**.

The changelog tracks major changes to the test documentation, test coverage, manual execution results, defect reporting, and traceability improvements throughout the project.

---

# Project Progress

## Current Status

The project has established the core manual API testing documentation and execution workflow for the modules that have been worked on so far.

The current focus is on reviewing and improving the quality, consistency, and traceability of the manual testing documentation before proceeding to Qase integration and API automation.

The current testing workflow is:

```text
Test Plan
    ↓
Test Scenarios
    ↓
Test Cases
    ↓
Test Execution
    ↓
Evidence
    ↓
Bug Reports
```
The current focus is on reviewing and improving the quality, consistency, and traceability of the manual testing documentation before proceeding to Qase integration and API automation.

# Version History

## Version 1.0 — Initial Project Setup

### Added

- Initial RESTful Booker API testing project structure.
- Test Plan documentation.
- Initial Test Scenarios documentation.
- Initial Test Cases documentation.
- Initial manual testing scope for:
- Authentication
- Booking
- Health Check
- Initial documentation structure for test execution.
- Initial evidence directory structure.
- Initial bug report structure.

### Testing Scope

The initial project scope covered the following API endpoints:

- POST /auth
- GET /booking
- GET /booking/{id}
- POST /booking
- PUT /booking/{id}
- PATCH /booking/{id}
- DELETE /booking/{id}
- GET /ping

## Version 1.1 — Test Scenario Expansion

### Updated

Expanded the Test Scenario documentation to provide broader coverage of the RESTful Booker API.

### Authentication Scenarios

Added scenarios covering:

- Valid authentication credentials.
- Invalid username.
- Invalid password.
- Empty credentials.
- Malformed authentication request body.

### Booking Scenarios

Added scenarios covering:

### Retrieve Booking
- Retrieve all booking IDs.
- Retrieve booking using a valid booking ID.
- Retrieve booking using an invalid booking ID.
- Retrieve a non-existing booking.
- Invalid endpoint format.

### Create Booking

- Create booking using valid data.
- Missing required fields.
- Empty values.
- Invalid data types.
- Boundary values.
- Unexpected additional fields.

### Update Booking

- Valid authenticated update.
- Update without authentication.
- Invalid authentication token.
- Invalid request data.
- Non-existing booking ID.
- Empty values.

### Partial Update

- Update selected fields.
- Update without authentication.
- Invalid authentication token.
- Invalid field values.
- Unsupported fields.

### Delete Booking

- Delete using valid authentication.
- Delete without authentication.
- Invalid authentication.
- Delete non-existing booking.
- Delete the same booking twice.
- Invalid booking ID.

### Health Check Scenarios

Added scenarios covering:

- API availability.
- API response time.

## Version 1.2 — Create Booking Test Case Development

### Added

Developed detailed manual test cases for the Create Booking module.

A total of 22 test cases were created.

### Coverage Added

The Create Booking test cases cover:

- Valid booking creation.
- Missing required fields.
- Empty values.
- Optional fields.
- Missing booking dates.
- Empty JSON payload.
- Negative numeric values.
- Invalid data types.
- Invalid date format.
- Invalid date sequence.
- Long input values.
- HTTP method behavior.
- Invalid Content-Type.
- Malformed JSON.
- Unsupported properties.
- Null values.

### Test Case Categories

| Category           |  Total |
| ------------------ | -----: |
| Positive Testing   |      2 |
| Negative Testing   |      8 |
| Validation Testing |      9 |
| Boundary Testing   |      3 |
| **Total**          | **22** |

## Version 1.3 — Health Check Test Case Development

### Added

Developed detailed manual test cases for the Health Check endpoint.

The Health Check module contains 5 test cases covering:

- Endpoint availability.
- HTTP status code validation.
- Response body validation.
- Response time observation.
- Response consistency.

### Execution

The Health Check test cases were manually executed using Postman.

Response-time evidence was reviewed and updated where necessary because response time may vary between executions.

## Version 1.4 — Manual Test Execution

### Added

Created manual Test Execution documentation for the test cases that had been executed at this stage.

Execution records include:

- Test Case ID.
- Test Case description.
- Status code.
- Response time.
- Expected result.
- Actual result.
- Execution status.
- Evidence reference.
- Related Bug ID where applicable.

### Execution Status

The manual execution process was performed using:

Postman
Public RESTful Booker API

Execution evidence was captured for executed test cases.

## Version 1.5 — Create Booking Defect Identification

### Added

During Create Booking execution, several API behaviors were identified that did not match the expected validation behavior defined in the test cases.

The following defects were documented:

| Bug ID         | Related Test Case  | Description                                                |
| -------------- | ------------------ | ---------------------------------------------------------- |
| BUG-CREATE-001 | TC-BOOK-CREATE-002 | Missing `firstname` results in an unexpected server error. |
| BUG-CREATE-002 | TC-BOOK-CREATE-003 | Missing `lastname` results in an unexpected server error.  |
| BUG-CREATE-003 | TC-BOOK-CREATE-010 | Empty JSON request produces unexpected behavior.           |
| BUG-CREATE-004 | TC-BOOK-CREATE-019 | Invalid `Content-Type` produces unexpected behavior.       |
| BUG-CREATE-005 | TC-BOOK-CREATE-022 | Null values are not validated as expected.                 |

### Bug Reporting

Individual bug reports were created using a consistent structure containing:

- Bug information.
- Environment.
- Preconditions.
- Steps to reproduce.
- Request body.
- Expected result.
- Actual result.
- Impact.
- Evidence.
- Suggested fix.

## Version 1.6 — Bug Validation and Resolution

### Updated

Previously reported Create Booking defects were reviewed against their corresponding test executions and evidence.

Bug status and resolution were updated based on the latest validation results.

Where a defect was fixed, the corresponding test case was re-executed to verify the fix.

### Testing Principle

A test case is classified as:

- **PASS** when the observed behavior satisfies the documented Expected Result.
- **FAIL** when the observed behavior does not satisfy the documented Expected Result.
- **BLOCKED** when execution cannot be completed because of an external blocking condition.

## Version 1.7 — Test Scenario Traceability Improvement

### Updated

The relationship between Test Scenarios and Test Cases was reviewed.

Previously, some test cases used scenario IDs that duplicated the test case structure, for example:

```
SC-BOOK-CREATE-001
SC-BOOK-CREATE-002
SC-BOOK-CREATE-003
```
This did not properly correspond to the master Test Scenario document.

### Changed

Test Cases were updated to reference the existing master scenario IDs.

Example:

```
SC-BOOK-006
Create a booking using valid data.
        ↓
TC-BOOK-CREATE-001
Create booking using valid booking information
```

Another example:

```
SC-BOOK-007
Create a booking with missing required fields.
        ↓
TC-BOOK-CREATE-002
Create booking without firstname

TC-BOOK-CREATE-003
Create booking without lastname
```

### Traceability Model

The documentation relationship is now:

```
Test Scenario
      ↓
Test Case
      ↓
Test Execution
      ↓
Evidence
      ↓
Bug Report
```

### Reason

The Test Scenario document represents business-level testing objectives, while Test Cases represent specific validation conditions.

This allows one high-level scenario to be associated with multiple detailed Test Cases where appropriate.

## Version 1.8 — Test Scenario Documentation Finalization

### Updated

Finalized the master Test Scenario documentation and standardized scenario IDs across Authentication, Booking, and Health Check.

The master scenario structure now contains:

| Module | Scenarios |
| --- | ---: |
| Authentication | 5 |
| Booking | 28 |
| Health Check | 2 |
| **Total** | **35** |

Scenario IDs are now used consistently by the corresponding Test Cases.

## Version 1.9 — Documentation Consistency Review

### Updated

A broader review of the testing documentation was performed.

The review focused on:

- Test Scenario ↔ Test Case traceability.
- Test Case ↔ Test Execution consistency.
- Expected Result ↔ Actual Result consistency.
- PASS / FAIL classification.
- Bug ID relationships.
- Evidence references.
- Test Execution summaries.
- Bug Report consistency.
- Documentation structure.

### Improved

The documentation was adjusted to ensure that:

- Test Executions are based on the corresponding Test Cases.
- Failed executions are linked to relevant Bug Reports.
- Evidence references match the executed Test Case.
- Bug Reports contain reproducible steps.
- Test Scenario IDs come from the master Test Scenario document.
- One Test Scenario can support multiple detailed Test Cases.
- Execution results are evaluated against the defined Expected Result.
- HTTP status codes are considered together with the complete expected API behavior.
- Response-time observations account for normal variation between executions.

# Current Project Structure

The current documentation workflow is structured as follows:
```
01-test-plan.md
        │
        ▼
02-test-scenarios.md
        │
        ▼
03-test-cases/
        │
        ├── authentication/
        ├── booking/
        └── health-check/
        │
        ▼
04-test-executions/
        │
        ├── authentication/
        ├── booking/
        └── health-check/
        │
        ▼
evidence/
        │
        └── manual-testing/
                │
                ├── authentication/
                ├── booking/
                └── health-check/
        │
        ▼
bug-reports/
        │
        ├── authentication/
        ├── booking/
        └── health-check/
```

# Current Testing Coverage

The master Test Scenario documentation currently covers:

| Module         | Scenarios |
| -------------- | --------: |
| Authentication |         5 |
| Booking        |        28 |
| Health Check   |         2 |
| **Total**      |    **35** |

The Booking scenarios cover:

- Retrieve Booking.
- Create Booking.
- Update Booking.
- Partial Update.
- Delete Booking.

# Current Manual Testing Progress

| Area                 | Status |
| -------------------- | :----: |
| Test Plan            | Completed |
| Test Scenarios       | Completed |
| Test Cases           | In Progress |
| Test Executions      | In Progress |
| Manual Evidence      | In Progress |
| Bug Reports          | In Progress |
| Qase Integration     | Not Started |
| Postman Test Scripts | Not Started |
| Newman Automation    | Not Started |

`Qase integration and automation are intentionally not the current focus of the project.`

# Current Create Booking Progress

The Create Booking module currently contains:

```
22 detailed Test Cases.
Manual Test Execution records.
Execution evidence.
Identified defects.
Individual Bug Reports.
Bug validation and resolution tracking.
Improved Test Scenario ↔ Test Case traceability.
```

The module is currently undergoing documentation and execution review to ensure consistency before moving to the next module.

# Current Health Check Progress

The Health Check module currently contains:

```
5 detailed Test Cases.
Manual Test Execution results.
Response validation.
Response-time observation.
Reliability testing.
Execution evidence.
```

Response time is treated as an observation because API response time can vary between executions.

# Current Defect Tracking

Create Booking defects identified during manual execution are tracked through individual Bug Reports.

Current known Create Booking defect records include:

| Bug ID         | Related Test Case  | Current Tracking |
| -------------- | ------------------ | ---------------- |
| BUG-CREATE-001 | TC-BOOK-CREATE-002 | Tracked          |
| BUG-CREATE-002 | TC-BOOK-CREATE-003 | Tracked          |
| BUG-CREATE-003 | TC-BOOK-CREATE-010 | Tracked          |
| BUG-CREATE-004 | TC-BOOK-CREATE-019 | Tracked          |
| BUG-CREATE-005 | TC-BOOK-CREATE-022 | Tracked          |

`Bug status should be maintained in the individual Bug Report. The changelog records the existence and tracking of the defect rather than acting as the source of truth for its current lifecycle status.`

# Documentation Principles

The project currently follows these principles.

## 1. Scenario-Level Planning

Test Scenarios represent high-level testing objectives rather than individual Test Cases.

## 2. Detailed Test Cases

Test Cases define specific:
```
Input conditions.
Test data.
Request bodies.
Test steps.
Expected results.
```

## 3. Evidence-Based Execution

Test Execution results are supported by Postman evidence.

## 4. Result-Based Classification

A Test Case is marked:
```

PASS when the observed behavior satisfies the documented Expected Result.
FAIL when the observed behavior does not satisfy the documented Expected Result.
BLOCKED when execution cannot be completed because of an external blocking condition.
```

## 5. Defect Traceability

Failed Test Cases may be linked to individual Bug IDs.

The relationship is:

```
Test Case
    ↓
Test Execution
    ↓
Bug Report
```

## 6. Scenario Traceability

Test Cases reference the appropriate master Test Scenario.

One Test Scenario may contain multiple related Test Cases.

Example:

```
SC-BOOK-007
Create a booking with missing required fields.
        │
        ├── TC-BOOK-CREATE-002
        │   Missing firstname
        │
        └── TC-BOOK-CREATE-003
            Missing lastname
```

## 7. Evidence Traceability

Each executed Test Case should have corresponding evidence where evidence is required.

The relationship is:
```
Test Case
    ↓
Test Execution
    ↓
Evidence
```

## 8. Bug Traceability

When an execution fails because the API behavior does not satisfy the Expected Result, the execution should reference the relevant Bug ID.

The complete relationship is:
```
Test Scenario
      ↓
Test Case
      ↓
Test Execution
      ↓
Evidence
      ↓
Bug Report
```

# Future Activities

After the manual testing documentation is stable:

```
Manual Testing
      ↓
Qase Integration
      ↓
Postman Test Scripts
      ↓
Newman
      ↓
API Test Automation
```

These activities are intentionally deferred until the manual testing documentation and traceability are sufficiently stable.

# Project Status

Current Phase: Manual Testing Documentation & Review

The project has progressed from initial planning to:

```
Test Scenario development.
Detailed Test Case development.
Manual Test Execution.
Evidence collection.
Defect identification.
Bug reporting.
Bug validation.
Test Scenario ↔ Test Case traceability improvement.
Documentation consistency review.
```

The current priority is to complete the manual testing documentation and review the remaining modules before moving to Qase integration and automation.

# Update History
| Version | Description                                                                                       |
| ------- | ------------------------------------------------------------------------------------------------- |
| 1.0     | Initial project setup and testing documentation.                                                  |
| 1.1     | Expanded Test Scenario coverage for Authentication, Booking, and Health Check.                    |
| 1.2     | Developed detailed Create Booking Test Cases.                                                     |
| 1.3     | Developed Health Check Test Cases.                                                                |
| 1.4     | Added manual Test Execution documentation and evidence.                                           |
| 1.5     | Identified and documented Create Booking defects.                                                 |
| 1.6     | Reviewed Create Booking defects and revalidated fixes where applicable.                           |
| 1.7     | Improved Test Scenario ↔ Test Case traceability.                                                  |
| 1.8     | Finalized the master Test Scenario structure and scenario IDs.                                    |
| 1.9     | Reviewed documentation consistency across Test Cases, Test Executions, Evidence, and Bug Reports. |
