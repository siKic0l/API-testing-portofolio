# Get Booking Test Execution

## Overview

This document records the manual execution results for all **Get Booking** API test cases of the RESTful Booker API.

The purpose of this document is to verify that the **Get Booking** endpoint correctly retrieves booking information, handles invalid booking identifiers appropriately, and consistently returns responses according to the API specification.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Booking |
| Endpoint | GET /booking/{id} |
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
| TC-GET-001 | Retrieve booking using a valid Booking ID | - | - | Booking details are successfully returned. | - | Not Executed | - | - |
| TC-GET-002 | Retrieve booking using a non-existing Booking ID | - | - | API returns an appropriate error response. | - | Not Executed | - | - |
| TC-GET-003 | Retrieve booking using an invalid Booking ID format | - | - | API rejects invalid Booking ID format. | - | Not Executed | - | - |
| TC-GET-004 | Retrieve booking using Booking ID zero | - | - | API handles Booking ID zero appropriately. | - | Not Executed | - | - |
| TC-GET-005 | Retrieve booking using a negative Booking ID | - | - | API rejects negative Booking ID. | - | Not Executed | - | - |
| TC-GET-006 | Verify response body structure | - | - | Response body matches API specification. | - | Not Executed | - | - |
| TC-GET-007 | Verify response headers | - | - | Response headers match API specification. | - | Not Executed | - | - |
| TC-GET-008 | Verify Content-Type header | - | - | Response Content-Type is application/json. | - | Not Executed | - | - |
| TC-GET-009 | Verify response time | - | - | Response time is within acceptable threshold. | - | Not Executed | - | - |
| TC-GET-010 | Retrieve the same booking multiple times | - | - | API consistently returns identical booking information. | - | Not Executed | - | - |
| TC-GET-011 | Verify booking data consistency | - | - | Retrieved booking matches previously created booking data. | - | Not Executed | - | - |
| TC-GET-012 | Verify GET operation does not modify booking data | - | - | Booking data remains unchanged after retrieval. | - | Not Executed | - | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 12 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 12 |
| Pass Rate | 0% |
| Bugs Found | 0 |

---

# Defects Found

No defects have been identified.

---

# Execution Notes

- Test execution has not started.
- A valid Booking ID generated during **Create Booking** execution should be used for positive testing.
- Actual Result, Status Code, Response Time, and Evidence will be updated after each test case is executed.
- Any identified defects will be documented in the Bug Report section and linked from this document.

---

# Conclusion

Get Booking test execution has not yet been performed.

Once execution begins, this document will be updated with actual execution results, supporting evidence, execution metrics, and any defects identified during testing.
