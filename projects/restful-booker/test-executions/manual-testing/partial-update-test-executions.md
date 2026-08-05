# Partial Update Booking Test Execution

## Overview

This document records the manual execution results for all **Partial Update Booking** API test cases of the RESTful Booker API.

The purpose of this document is to verify that the **Partial Update Booking** endpoint correctly updates specific booking fields without affecting other existing data, validates authentication requirements, and consistently returns responses according to the API specification.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Booking |
| Endpoint | PATCH /booking/{id} |
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
| TC-PATCH-001 | Partially update firstname | - | - | Firstname is successfully updated while other fields remain unchanged. | - | Not Executed | - | - |
| TC-PATCH-002 | Partially update lastname | - | - | Lastname is successfully updated while other fields remain unchanged. | - | Not Executed | - | - |
| TC-PATCH-003 | Partially update additionalneeds | - | - | Additional needs are successfully updated. | - | Not Executed | - | - |
| TC-PATCH-004 | Partially update multiple fields | - | - | Selected fields are successfully updated without affecting other data. | - | Not Executed | - | - |
| TC-PATCH-005 | Partial update without authentication token | - | - | API rejects unauthorized request. | - | Not Executed | - | - |
| TC-PATCH-006 | Partial update using invalid authentication token | - | - | API rejects invalid authentication token. | - | Not Executed | - | - |
| TC-PATCH-007 | Partial update using non-existing Booking ID | - | - | API returns an appropriate error response. | - | Not Executed | - | - |
| TC-PATCH-008 | Partial update using invalid Booking ID format | - | - | API rejects invalid Booking ID. | - | Not Executed | - | - |
| TC-PATCH-009 | Partial update using empty request body | - | - | API handles empty payload appropriately. | - | Not Executed | - | - |
| TC-PATCH-010 | Partial update using invalid field name | - | - | API ignores or rejects unsupported fields appropriately. | - | Not Executed | - | - |
| TC-PATCH-011 | Verify response body after partial update | - | - | Response body reflects only the updated fields. | - | Not Executed | - | - |
| TC-PATCH-012 | Verify response status code | - | - | API returns the expected success status code. | - | Not Executed | - | - |
| TC-PATCH-013 | Verify response Content-Type header | - | - | Response Content-Type is application/json. | - | Not Executed | - | - |
| TC-PATCH-014 | Verify response time | - | - | Response time is within acceptable threshold. | - | Not Executed | - | - |
| TC-PATCH-015 | Verify updated booking data using GET endpoint | - | - | GET endpoint returns the latest updated booking information. | - | Not Executed | - | - |

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
- A valid Booking ID created during **Create Booking** execution is required.
- A valid authentication token generated from the **Authentication** endpoint is required for authorized requests.
- Actual Result, Status Code, Response Time, and Evidence will be updated after each test case is executed.
- Any identified defects will be documented in the Bug Report section and linked from this document.

---

# Conclusion

Partial Update Booking test execution has not yet been performed.

Once execution begins, this document will be updated with actual execution results, supporting evidence, execution metrics, and any defects identified during testing.
