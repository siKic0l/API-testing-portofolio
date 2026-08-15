# Qase Test Metrics

## Overview

This document summarizes the test execution metrics for the RESTful Booker API based on the latest manual test run recorded in Qase.

The metrics are calculated using the latest execution result for each unique test case. Retest executions are not counted as additional test cases.

---

## Overall Test Metrics

| Metric | Result |
|--------|-------:|
| Total Unique Test Cases | 97 |
| Passed | 89 |
| Failed | 6 |
| Blocked | 2 |
| Pass Rate | 91.75% |
| Failed Rate | 6.19% |
| Blocked Rate | 2.06% |

### Calculation

**Pass Rate**

`89 / 97 × 100 = 91.75%`

**Failed Rate**

`6 / 97 × 100 = 6.19%`

**Blocked Rate**

`2 / 97 × 100 = 2.06%`

---

## Test Result Distribution

| Result | Count | Percentage |
|--------|------:|-----------:|
| Passed | 89 | 91.75% |
| Failed | 6 | 6.19% |
| Blocked | 2 | 2.06% |
| **Total** | **97** | **100%** |

---

## Metrics by Test Suite

| Test Suite | Total | Passed | Failed | Blocked | Pass Rate |
|------------|------:|-------:|-------:|--------:|----------:|
| Authentication | 15 | 15 | 0 | 0 | 100% |
| Create Booking | 22 | 16 | 6 | 0 | 72.73% |
| Get Booking | 12 | 12 | 0 | 0 | 100% |
| Update Booking | 18 | 18 | 0 | 0 | 100% |
| Partial Update Booking | 15 | 13 | 0 | 2 | 86.67% |
| Delete Booking | 10 | 10 | 0 | 0 | 100% |
| Health Check | 5 | 5 | 0 | 0 | 100% |
| **Total** | **97** | **89** | **6** | **2** | **91.75%** |

---

## Suite Performance

### Fully Passed Suites

The following test suites achieved a 100% pass rate:

- Authentication
- Get Booking
- Update Booking
- Delete Booking
- Health Check

These suites currently have no failed or blocked test cases in the latest execution.

### Suites with Findings

Two suites contain non-passed test cases:

| Test Suite | Failed | Blocked | Finding |
|------------|-------:|--------:|---------|
| Create Booking | 6 | 0 | Failed test cases |
| Partial Update Booking | 0 | 2 | Blocked test cases |

---

## Failed Test Metrics

A total of **6 test cases** were recorded as Failed.

All failed test cases belong to the Create Booking suite.

| Test Case ID | Module | Status |
|--------------|--------|--------|
| TC_BOOK_CREATE_002 | Create Booking | FAIL |
| TC_BOOK_CREATE_003 | Create Booking | FAIL |
| TC_BOOK_CREATE_009 | Create Booking | FAIL |
| TC_BOOK_CREATE_010 | Create Booking | FAIL |
| TC_BOOK_CREATE_019 | Create Booking | FAIL |
| TC_BOOK_CREATE_022 | Create Booking | FAIL |

### Failed Test Distribution

| Module | Failed | Percentage of All Failures |
|--------|-------:|---------------------------:|
| Create Booking | 6 | 100% |
| Other Modules | 0 | 0% |
| **Total** | **6** | **100%** |

---

## Blocked Test Metrics

A total of **2 test cases** were recorded as Blocked.

Both blocked test cases belong to the Partial Update Booking suite.

| Test Case ID | Module | Status |
|--------------|--------|--------|
| TC_BOOK_PATCH_010 | Partial Update Booking | BLOCKED |
| TC_BOOK_PATCH_011 | Partial Update Booking | BLOCKED |

### Blocked Test Distribution

| Module | Blocked | Percentage of All Blocked Tests |
|--------|--------:|--------------------------------:|
| Partial Update Booking | 2 | 100% |
| Other Modules | 0 | 0% |
| **Total** | **2** | **100%** |

---

## Retest Metrics

The Qase export contains multiple execution records because some test cases were executed more than once.

These additional records represent retest executions and are not counted as separate test cases in the overall metrics.

For reporting purposes:

- Test case count is based on unique test case IDs.
- The latest execution result is used as the final execution status.
- Previous executions are retained as execution history.
- Retest executions do not increase the total test case count.

---

## Test Coverage Status

| Coverage Area | Status |
|---------------|--------|
| Authentication | 100% Passed |
| Booking Creation | Partial Pass |
| Booking Retrieval | 100% Passed |
| Full Booking Update | 100% Passed |
| Partial Booking Update | Partial Pass |
| Booking Deletion | 100% Passed |
| API Health Check | 100% Passed |

---

## Quality Indicators

### Overall Stability

The overall execution achieved a **91.75% pass rate**.

Most tested API modules completed successfully without failed or blocked test cases.

### Main Area of Concern

The primary area requiring further investigation is the **Create Booking** module, which accounts for all 6 failed test cases.

### Execution Blockers

The Partial Update Booking module contains 2 blocked test cases.

These cases should be reviewed separately to determine whether the blocking condition can be removed and the tests executed successfully.

---

## Current Findings

| Finding Type | Count |
|--------------|------:|
| Passed Test Cases | 89 |
| Failed Test Cases | 6 |
| Blocked Test Cases | 2 |
| **Total Findings Requiring Attention** | **8** |

The 6 failed and 2 blocked test cases require further review.

A failed execution is not automatically treated as a confirmed software defect. Formal defect classification should be performed after reviewing the corresponding test case, actual result, evidence, and expected behavior.

---

## Execution Health Summary

| Indicator | Status |
|-----------|--------|
| Overall Pass Rate | 91.75% |
| Failed Tests | 6 |
| Blocked Tests | 2 |
| Fully Passed Suites | 5 |
| Suites with Findings | 2 |
| Overall Execution | Completed |

---

## Conclusion

The latest Qase execution demonstrates that the majority of the RESTful Booker API test scope passed successfully.

Out of 97 unique test cases:

- 89 test cases passed.
- 6 test cases failed.
- 2 test cases were blocked.

The overall pass rate is **91.75%**.

The Create Booking module represents the primary area requiring further investigation because all failed test cases were recorded in this suite.

The Partial Update Booking module contains two blocked test cases that require additional review.

These metrics represent the current execution state and do not indicate that any failed test case has already been confirmed as a software defect.
