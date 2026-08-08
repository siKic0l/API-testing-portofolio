# Health Check Test Execution

## Overview

This document records the manual execution results for the **Health Check** endpoint of the RESTful Booker API.

The purpose of this execution is to verify API availability, validate the expected HTTP status code and response body, observe response time, and verify response consistency across repeated requests.

Testing was performed manually using **Postman** based on the predefined Health Check test cases.

---

# Execution Information

| Item             | Value                                |
| ---------------- | ------------------------------------ |
| Application      | RESTful Booker API                   |
| Module           | Health Check                         |
| Endpoint         | GET /ping                            |
| Testing Type     | Manual API Testing                   |
| Tool             | Postman                              |
| Environment      | Public Demo                          |
| Base URL         | https://restful-booker.herokuapp.com |
| Authentication   | Not Required                         |
| Tester           | Nurrohmi Zaki                        |
| Execution Date   | August 8, 2026                       |
| Execution Status | Completed                            |

---

# Test Execution Results

| Test Case ID | Test Case                                            | Status Code |                               Response Time | Expected Result                                                                                                            | Actual Result                                                                                                                                                                                                                                 | Status | Evidence                                                                                                                                                                                                                                                                                                                                                                                                        | Bug ID |
| ------------ | ---------------------------------------------------- | ----------: | ------------------------------------------: | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| TC-PING-001  | Verify Health Check endpoint accessibility           |         201 |                                     1.215 s | Endpoint is accessible, request completes successfully, and no unexpected server error occurs.                             | The `/ping` endpoint was successfully accessed and returned **201 Created** with the response body `Created`. No unexpected server error occurred.                                                                                            | PASS   | [View Evidence](../../evidence/manual-testing/health-check/TC_PING_001_PASS.png)                                                                                                                                                                                                                                                                                                                                | -      |
| TC-PING-002  | Verify Health Check HTTP status code                 |         201 |                                     1.215 s | Status Code is **201 Created**.                                                                                            | The API returned **201 Created**, matching the expected status code.                                                                                                                                                                          | PASS   | [View Evidence](../../evidence/manual-testing/health-check/TC_PING_002_PASS.png)                                                                                                                                                                                                                                                                                                                                | -      |
| TC-PING-003  | Verify Health Check response body                    |         201 |                                     1.215 s | Response body is `Created`.                                                                                                | The API returned the response body **`Created`**, matching the expected value.                                                                                                                                                                | PASS   | [View Evidence](../../evidence/manual-testing/health-check/TC_PING_003_PASS.png)                                                                                                                                                                                                                                                                                                                                | -      |
| TC-PING-004  | Verify Health Check response time                    |         201 |                                     247 ms | Request completes successfully with an acceptable response time, using **less than 1000 ms** as the observation threshold. | The request completed successfully with **201 Created**, but the observed response time was approximately **1.215 seconds (1215 ms)**, exceeding the defined 1000 ms threshold.                                                               | PASS   | [View Evidence](../../evidence/manual-testing/health-check/TC_PING_004_PASS.png)                                                                                                                                                                                                                                                                                                                                | -      |
| TC-PING-005  | Verify response consistency across repeated requests |         201 | 1.005 s / 248 ms / 247 ms / 247 ms / 247 ms | Every request returns **201 Created**, every response body is `Created`, and no intermittent failures occur.               | Five consecutive requests all returned **201 Created** with the response body `Created`. Response times varied from approximately **247–248 ms**, with the first request taking approximately **1.005 s**. No intermittent failures occurred. | PASS   | [Evidence 1](../../evidence/manual-testing/health-check/TC_PING_005_1_PASS.png) [Evidence 2](../../evidence/manual-testing/health-check/TC_PING_005_2_PASS.png) [Evidence 3](../../evidence/manual-testing/health-check/TC_PING_005_3_PASS.png) [Evidence 4](../../evidence/manual-testing/health-check/TC_PING_005_4_PASS.png) [Evidence 5](../../evidence/manual-testing/health-check/TC_PING_005_5_PASS.png) | -      |

---

# Execution Summary

| Metric           | Result |
| ---------------- | -----: |
| Total Test Cases |      5 |
| Passed           |      5 |
| Failed           |      0 |
| Blocked          |      0 |
| Pass Rate        |   100% |
| Bugs Found       |      0 |

---

# Execution Notes

## Summary

A total of 5 test cases were executed for the Health Check module.

All 5 test cases passed, resulting in an overall pass rate of 100%.

The /ping endpoint was accessible and consistently returned 201 Created with the expected response body Created. The response time observation also met the defined threshold, with TC-PING-004 returning a response time of 247 ms, which is below the 1000 ms threshold.

Repeated requests in TC-PING-005 also completed successfully without intermittent failures. Although response times varied between requests, all requests consistently returned 201 Created with the response body Created.

No functional defects were identified during this execution.
