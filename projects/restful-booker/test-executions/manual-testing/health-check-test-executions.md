# Health Check Test Execution

## Overview

This document records the manual execution results for all **Health Check** API test cases of the RESTful Booker API.

The purpose of this document is to verify that the **Health Check** endpoint is available, responds consistently, and returns the expected response according to the API specification.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Health Check |
| Endpoint | GET /ping |
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
| TC-PING-001 | Verify Health Check endpoint accessibility | - | - | Endpoint is accessible and returns a successful response. | - | Not Executed | - | - |
| TC-PING-002 | Verify response status code | - | - | API returns **201 Created**. | - | Not Executed | - | - |
| TC-PING-003 | Verify response body | - | - | Response body contains **Created**. | - | Not Executed | - | - |
| TC-PING-004 | Verify response time | - | - | Response time is within acceptable threshold. | - | Not Executed | - | - |
| TC-PING-005 | Verify repeated Health Check requests | - | - | Multiple requests return consistent responses. | - | Not Executed | - | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 5 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 5 |
| Pass Rate | 0% |
| Bugs Found | 0 |

---

# Defects Found

No defects have been identified.

---

# Execution Notes

- Test execution has not started.
- Actual Result, Status Code, Response Time, and Evidence will be updated after each test case is executed.
- Since this endpoint does not require authentication or request payload, execution is expected to be straightforward.
- Any identified defects will be documented in the Bug Report section and linked from this document.

---

# Conclusion

Health Check test execution has not yet been performed.

Once execution begins, this document will be updated with actual execution results, supporting evidence, execution metrics, and any defects identified during testing.
