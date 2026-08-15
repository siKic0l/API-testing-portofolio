# Qase Public Test Report

## Overview

This document provides the reference to the public Qase test execution report for the RESTful Booker API project.

The public report provides an externally accessible view of the latest test execution results recorded in Qase.

---

## Public Report

**Qase Public Report:**  
https://app.qase.io/public/report/debcf3c66ec50d7471d709188741133f6fefc744

The report contains the execution results of the RESTful Booker API test suites included in the current testing scope.

---

## Test Execution Information

| Item | Value |
|------|-------|
| Application | RESTful Booker API |
| Testing Type | Manual API Testing |
| Execution Tool | Postman |
| Test Management Tool | Qase |
| Environment | Public Demo |
| Execution Status | Completed |
| Execution Date | August 13, 2026 |

---

## Testing Scope

The public report covers the following test suites:

| Test Suite | Test Cases |
|------------|-----------:|
| Authentication | 15 |
| Create Booking | 22 |
| Get Booking | 12 |
| Update Booking | 18 |
| Partial Update Booking | 15 |
| Delete Booking | 10 |
| Health Check | 5 |
| **Total** | **97** |

---

## Execution Summary

The latest execution contains the following results based on the final execution status of each unique test case:

| Result | Count |
|--------|------:|
| Passed | 89 |
| Failed | 6 |
| Blocked | 2 |
| **Total** | **97** |

### Pass Rate

**91.75%**

The pass rate is calculated using the latest execution result for each unique test case.

---

## Failed Test Cases

The following test cases were recorded as Failed:

| Test Case ID | Module | Status |
|--------------|--------|--------|
| TC_BOOK_CREATE_002 | Create Booking | FAIL |
| TC_BOOK_CREATE_003 | Create Booking | FAIL |
| TC_BOOK_CREATE_009 | Create Booking | FAIL |
| TC_BOOK_CREATE_010 | Create Booking | FAIL |
| TC_BOOK_CREATE_019 | Create Booking | FAIL |
| TC_BOOK_CREATE_022 | Create Booking | FAIL |

All six failed test cases belong to the Create Booking module.

Detailed execution information is documented in:

`../test-executions/manual-testing/create-booking-test-executions.md`

---

## Blocked Test Cases

The following test cases were recorded as Blocked:

| Test Case ID | Module | Status |
|--------------|--------|--------|
| TC_BOOK_PATCH_010 | Partial Update Booking | BLOCKED |
| TC_BOOK_PATCH_011 | Partial Update Booking | BLOCKED |

Detailed execution information is documented in:

`../test-executions/manual-testing/partial-update-test-executions.md`

---

## Defect Traceability

Failed test cases are linked to the corresponding defect documentation where applicable.

Create Booking failures:

| Test Case ID | Defect |
|--------------|--------|
| TC_BOOK_CREATE_002 | BUG-CREATE-001 |
| TC_BOOK_CREATE_003 | BUG-CREATE-002 |
| TC_BOOK_CREATE_009 | BUG-CREATE-006 |
| TC_BOOK_CREATE_010 | BUG-CREATE-003 |
| TC_BOOK_CREATE_019 | BUG-CREATE-004 |
| TC_BOOK_CREATE_022 | BUG-CREATE-005 |

The blocked Partial Update Booking test cases currently have no defect assigned.

---

## Related Documentation

### Test Suites

`test-suites.md`

Contains the documented test suite structure and test case distribution.

### Test Runs

`test-runs.md`

Contains detailed information about the latest Qase test execution.

### Test Metrics

`test-metrics.md`

Contains execution metrics and result analysis.

### Manual Test Executions

`../test-executions/manual-testing/`

Contains module-level execution documentation, including actual results and evidence references.

### Bug Reports

`../bug-reports/`

Contains documented defects associated with failed test cases.

---

## Notes

- This document serves as a reference to the public Qase report.
- Test execution results are documented separately in the test execution documentation.
- Metrics are documented separately in `test-metrics.md`.
- Failed execution results are not automatically considered confirmed defects unless supported by further analysis.
- Blocked test cases are documented as blocked and are not classified as defects at this stage.
- Retest executions are retained in Qase as execution history and are not counted as additional unique test cases in the summary above.

---

## Conclusion

The public Qase report provides traceability between the manual test execution performed in Qase and the testing documentation maintained in this repository.

The latest execution covers **97 unique test cases**, with **89 Passed, 6 Failed, and 2 Blocked**, resulting in an overall pass rate of **91.75%**.

Further investigation of the failed and blocked test cases is documented separately from the public report.
