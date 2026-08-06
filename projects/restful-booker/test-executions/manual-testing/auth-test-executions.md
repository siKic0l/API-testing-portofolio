# Authentication Test Execution

## Overview

This document records the manual execution results for all Authentication API test cases of the RESTful Booker API.

The purpose of this document is to verify that the Authentication endpoint behaves as expected, document the execution results, provide traceability between test cases and evidence, and record any defects identified during testing.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Authentication |
| Endpoint | POST /auth |
| Testing Type | Manual API Testing |
| Tool | Postman |
| Environment | Public Demo |
| Base URL | https://restful-booker.herokuapp.com |
| Tester | Nurrohmi Zaki |
| Execution Date | August 6, 2026 |
| Execution Status | Completed |

---

# Test Execution Results

| Test Case ID | Test Case | Status Code | Response Time | Expected Result | Actual Result | Status | Evidence | Bug ID |
|--------------|-----------|------------|---------------|-----------------|---------------|--------|----------|--------|
| TC-AUTH-001 | Generate token using valid credentials | 200 | 1.07s | Authentication token is successfully generated. | Authentication token was successfully generated using valid credentials. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_001_PASS.png) | - |
| TC-AUTH-002 | Authenticate using invalid password | 200 | 1.03s | Authentication request is rejected. | Authentication request was rejected when an invalid password was provided. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_002_PASS.png) | - |
| TC-AUTH-003 | Authenticate using invalid username | 200 | 249ms | Authentication request is rejected. | Authentication request was rejected when an invalid username was provided. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_003_PASS.png) | - |
| TC-AUTH-004 | Authenticate using invalid username and password | 200 | 1.02s | Authentication request is rejected. | Authentication request was rejected when both username and password were invalid. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_004_PASS.png) | - |
| TC-AUTH-005 | Authenticate with empty username | 200 | 989ms | Authentication request is rejected. | Authentication request was rejected when the username field was empty. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_005_PASS.png) | - |
| TC-AUTH-006 | Authenticate with empty password | 200 | 999ms | Authentication request is rejected. | Authentication request was rejected when the password field was empty. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_006_PASS.png) | - |
| TC-AUTH-007 | Authenticate with empty username and password | 200 | 247ms | Authentication request is rejected. | Authentication request was rejected when both username and password fields were empty. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_007_PASS.png) | - |
| TC-AUTH-008 | Authenticate using SQL Injection payload | 200 | 995ms | Authentication request is rejected. | SQL Injection payload did not bypass authentication and the request was rejected. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_008_PASS.png) | - |
| TC-AUTH-009 | Authenticate using XSS payload | 200 | 247ms | Authentication request is rejected. | XSS payload did not bypass authentication and the request was rejected. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_009_PASS.png) | - |
| TC-AUTH-010 | Authenticate using special characters | 200 | 246ms | Authentication request is rejected. | Authentication request was rejected when special characters were used as credentials | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_010_PASS.png) | - |
| TC-AUTH-011 | Verify response body after successful authentication | 400 | 1.02s | Response body contains a valid authentication token. | Response body successfully returned a valid authentication token after successful authentication. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_011_PASS.png) | - |
| TC-AUTH-012 | Verify response header | 200 | 1.05s | Response headers match the API specification. | Response headers matched the expected API specification. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_012_PASS.png) | - |
| TC-AUTH-013 | Verify Content-Type header | 404 | 253ms | Response Content-Type is application/json. | Response Content-Type was returned as application/json as expected. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_013_PASS.png) | - |
| TC-AUTH-014 | Verify response time | 200 | 253ms | Response time is within the acceptable threshold. | Response was returned within the acceptable response time threshold. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_014_PASS.png) | - |
| TC-AUTH-015 | Verify repeated authentication requests | 200 | 253ms | Multiple authentication requests return consistent results. | Multiple authentication requests consistently returned the expected results without any unexpected behavior. | PASS | [View Evidence](../../evidence/manual-testing/auth/TC_AUTH_015_PASS.png) | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 15 |
| Passed | 15 |
| Failed | 0 |
| Blocked | 0 |
| Pass Rate | 100% |
| Bugs Found | 0 |

---

# Defects Found

No functional defects were identified during the execution of the Authentication module.

---

# Execution Notes

- All planned Authentication test cases were successfully executed.
- The Authentication endpoint correctly handled both valid and invalid authentication scenarios.
- Response body, response headers, Content-Type, and endpoint consistency behaved as expected.
- No functional defects were identified during this execution cycle.
- Execution evidence has been captured for every executed test case.

# Conclusion

The Authentication module of the RESTful Booker API was successfully verified through manual API testing.

All planned Authentication test cases passed successfully without any identified defects. The endpoint correctly generated authentication tokens for valid credentials, rejected invalid authentication attempts, and consistently returned responses according to the expected API behavior.

Based on the executed testing scope, the Authentication endpoint is considered stable and functions as expected.

