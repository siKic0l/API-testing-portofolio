# Qase Test Runs

## Overview

This document records the latest manual test execution results for the RESTful Booker API project based on the Qase test run exported on **August 13, 2026**.

The execution was performed using **Postman** against the public RESTful Booker API and managed in **Qase.io**.

This document reflects the execution results as recorded in Qase. It does not represent a retest after fixing the API or changing the test cases.

---

## Latest Test Run

| Item | Value |
|------|-------|
| Test Run | RBOOKER Test Run 2026-08-13 |
| Execution Type | Manual API Testing |
| Tool | Postman |
| Test Management | Qase.io |
| Environment | Public Demo |
| Execution Started | August 13, 2026 |
| Latest Execution | August 14, 2026 |
| Unique Test Cases Executed | 97 |
| Passed | 89 |
| Failed | 6 |
| Blocked | 2 |
| Pass Rate | 91.75% |

> **Note:** The Qase export contains 119 execution records because some test cases were executed more than once. The summary above uses the **latest execution result for each unique test case**.

---

## Execution Summary by Suite

| Suite | Total | Passed | Failed | Blocked | Pass Rate |
|-------|------:|-------:|-------:|--------:|----------:|
| Authentication | 15 | 15 | 0 | 0 | 100% |
| Create Booking | 22 | 16 | 6 | 0 | 72.73% |
| Get Booking | 12 | 12 | 0 | 0 | 100% |
| Update Booking | 18 | 18 | 0 | 0 | 100% |
| Partial Update Booking | 15 | 13 | 0 | 2 | 86.67% |
| Delete Booking | 10 | 10 | 0 | 0 | 100% |
| Health Check | 5 | 5 | 0 | 0 | 100% |
| **Total** | **97** | **89** | **6** | **2** | **91.75%** |

---

## Result Distribution

| Status | Total | Percentage |
|--------|------:|-----------:|
| Passed | 89 | 91.75% |
| Failed | 6 | 6.19% |
| Blocked | 2 | 2.06% |
| **Total** | **97** | **100%** |

---

# Failed Test Cases

The following test cases were recorded as **Failed** in the latest execution.

| Test Case ID | Test Case | Suite | Priority | Status |
|--------------|-----------|-------|----------|--------|
| TC_BOOK_CREATE_002 | Reject booking creation when firstname is omitted | Create Booking | High | FAIL |
| TC_BOOK_CREATE_003 | Reject booking creation when lastname is omitted | Create Booking | High | FAIL |
| TC_BOOK_CREATE_009 | Create booking without booking dates | Create Booking | Medium | FAIL |
| TC_BOOK_CREATE_010 | Create booking with empty JSON object | Create Booking | Medium | FAIL |
| TC_BOOK_CREATE_019 | Create booking with invalid Content-Type header | Create Booking | Medium | FAIL |
| TC_BOOK_CREATE_022 | Create booking with all fields set to null | Create Booking | Low | FAIL |

## Failed Execution Notes

These failures are recorded as execution findings based on the Qase test run. A failed test case is not automatically treated as a confirmed software defect until the result has been reviewed and the failure has been triaged.

The corresponding Create Booking defect documentation is maintained separately under:

```text
bug-reports/create-booking/
```

---

# Blocked Test Cases

The following test cases were recorded as **Blocked** in the latest execution.

| Test Case ID | Test Case | Suite | Priority | Status |
|--------------|-----------|-------|----------|--------|
| TC_BOOK_PATCH_010 | Update Non-Existing Booking | Partial Update Booking | High | BLOCKED |
| TC_BOOK_PATCH_011 | Update Booking with Invalid ID Format | Partial Update Booking | Medium | BLOCKED |

## Blocked Execution Notes

The blocked test cases are documented as execution results only. They are not automatically classified as defects.

No defect report is associated with these blocked executions at this stage.

---

# Retest / Multiple Execution Records

The Qase export contains multiple execution records for several test cases. The latest execution result is used for the project-level summary above.

The following test cases had multiple execution records in the exported run:

| Test Case ID | Execution Records |
|--------------|------------------:|
| TC_BOOK_CREATE_002 | 3 |
| TC_BOOK_UPDATE_005 | 3 |
| TC_BOOK_PATCH_001 | 3 |
| TC_BOOK_PATCH_002 | 3 |
| TC_BOOK_PATCH_003 | 3 |
| TC_BOOK_PATCH_004 | 3 |
| TC_BOOK_PATCH_005 | 3 |
| TC_BOOK_PATCH_006 | 3 |
| TC_BOOK_PATCH_007 | 3 |
| TC_BOOK_PATCH_008 | 3 |
| TC_BOOK_PATCH_011 | 3 |

> Multiple execution records are retained in Qase for execution history. This document reports the latest result for each unique test case.

---

# Current Testing Status

At the end of the latest recorded execution:

- **89 test cases passed successfully.**
- **6 test cases failed.**
- **2 test cases were blocked.**
- No additional test case or API implementation changes are represented in this report.
- Failed and blocked cases require review/triage before any further action is taken.

---

# Traceability

The execution results can be traced across the following project documentation:

```text
Qase Test Cases
      ↓
Qase Test Run
      ↓
Manual Test Execution Documentation
      ↓
Evidence
      ↓
Bug Reports (where applicable)
```

Related documentation:

- `../test-design/03-test-cases/`
- `../test-executions/manual-testing/`
- `../evidence/manual-testing/`
- `../bug-reports/`
- `test-suites.md`
- `test-metrics.md`
- `public-report.md`

---

# Conclusion

The latest Qase execution covered **97 unique test cases** across seven RESTful Booker API suites.

The overall result was **89 Passed, 6 Failed, and 2 Blocked**, resulting in a **91.75% pass rate**.

The execution results documented here represent the current state of the test run and should be treated as the baseline for subsequent defect triage, retesting, regression testing, and future execution cycles.
