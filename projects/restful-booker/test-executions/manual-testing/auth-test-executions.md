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
| Execution Date | - |
| Execution Status | Not Started |

---

# Test Execution Results

| Test Case ID | Test Case | Status Code | Response Time | Expected Result | Actual Result | Status | Evidence | Bug ID |
|--------------|-----------|------------|---------------|-----------------|---------------|--------|----------|--------|
| TC-AUTH-001 | Generate token using valid credentials | - | - | Authentication token is successfully generated. | - | Not Executed | - | - |
| TC-AUTH-002 | Authenticate using invalid password | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-003 | Authenticate using invalid username | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-004 | Authenticate using invalid username and password | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-005 | Authenticate with empty username | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-006 | Authenticate with empty password | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-007 | Authenticate with empty username and password | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-008 | Authenticate using SQL Injection payload | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-009 | Authenticate using XSS payload | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-010 | Authenticate using special characters | - | - | Authentication request is rejected. | - | Not Executed | - | - |
| TC-AUTH-011 | Verify response body after successful authentication | - | - | Response body contains a valid authentication token. | - | Not Executed | - | - |
| TC-AUTH-012 | Verify response header | - | - | Response headers match the API specification. | - | Not Executed | - | - |
| TC-AUTH-013 | Verify Content-Type header | - | - | Response Content-Type is application/json. | - | Not Executed | - | - |
| TC-AUTH-014 | Verify response time | - | - | Response time is within the acceptable threshold. | - | Not Executed | - | - |
| TC-AUTH-015 | Verify repeated authentication requests | - | - | Multiple authentication requests return consistent results. | - | Not Executed | - | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 15 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 15 |
| Pass Rate | 0% |
| Bugs Found | 0 |

---

# Defects Found

No defects have been identified.

---

# Execution Notes

- Test execution has not started.
- Actual Result, Status Code, Response Time, and Evidence will be updated after each test case is executed in Postman.
- Any identified defects will be documented in the Bug Report section and linked from this document.

---

# Conclusion

Authentication test execution has not yet been performed.

Once execution begins, this document will be updated with actual execution results, supporting evidence, execution metrics, and any defects identified during testing.
