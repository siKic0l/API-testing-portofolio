# Manual Test Execution

## Overview

This directory contains the execution results of all **manual API testing** activities performed on the RESTful Booker API.

Each document records the actual execution outcome of the corresponding test cases, including execution status, response validation, evidence, execution metrics, and any defects identified during testing.

The execution documents provide traceability between:

- Test Cases
- Test Data
- API Responses
- Evidence
- Bug Reports

---

# Objectives

The objectives of the Manual Test Execution phase are:

- Execute all designed test cases.
- Verify API behavior against expected results.
- Record actual execution outcomes.
- Collect execution evidence.
- Measure response consistency.
- Identify and document defects.

---

# Testing Scope

The following RESTful Booker API endpoints are covered.

| Module | Endpoint | Status |
|---------|----------|--------|
| Authentication | POST /auth | Ready for Execution |
| Create Booking | POST /booking | Ready for Execution |
| Get Booking | GET /booking/{id} | Ready for Execution |
| Update Booking | PUT /booking/{id} | Ready for Execution |
| Partial Update | PATCH /booking/{id} | Ready for Execution |
| Delete Booking | DELETE /booking/{id} | Ready for Execution |
| Health Check | GET /ping | Ready for Execution |

---

# Execution Workflow

Each endpoint follows the same execution process.

```text
Test Case
      ↓
Prepare Test Data
      ↓
Execute Request in Postman
      ↓
Validate Response
      ↓
Capture Evidence
      ↓
Record Execution Result
      ↓
Report Defects (if any)
```

---

# Execution Artifacts

Each execution document includes:

- Execution Information
- Test Execution Results
- Expected Result
- Actual Result
- HTTP Status Code
- Response Time
- Execution Status
- Evidence Reference
- Bug Reference
- Execution Summary
- Execution Notes
- Conclusion

---

# Execution Status

The following execution statuses are used throughout this project.

| Status | Description |
|---------|-------------|
| Not Executed | Test case has not been executed. |
| Passed | Expected result matches the actual result. |
| Failed | Actual result differs from the expected result. |
| Blocked | Test execution cannot proceed due to dependencies or environment issues. |

---

# Folder Structure

```text
manual-testing
│
├── README.md
│
├── auth-test-execution.md
├── create-booking-test-execution.md
├── get-booking-test-execution.md
├── update-booking-test-execution.md
├── partial-update-booking-test-execution.md
├── delete-booking-test-execution.md
└── health-check-test-execution.md
```

---

# Related Documents

This phase is connected with the following project documentation.

- API Analysis
- Test Strategy
- Test Plan
- Test Scenarios
- Test Cases
- Test Data
- Bug Reports

---

# Notes

All execution results contained in this directory are based on actual manual testing performed using **Postman** against the public RESTful Booker API.

Evidence and bug reports will be linked from each execution document after testing has been completed.
