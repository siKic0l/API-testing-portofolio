# Delete Booking Test Execution

## Overview

This document records the manual execution results for all **Delete Booking** API test cases of the RESTful Booker API.

The purpose of this document is to verify that the **Delete Booking** endpoint correctly removes existing booking records, enforces authentication requirements, handles invalid requests appropriately, and consistently returns responses according to the API specification.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Booking |
| Endpoint | DELETE /booking/{id} |
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
| TC-DEL-001 | Delete booking using valid authentication | - | - | Booking is successfully deleted. | - | Not Executed | - | - |
| TC-DEL-002 | Delete booking without authentication token | - | - | API rejects unauthorized request. | - | Not Executed | - | - |
| TC-DEL-003 | Delete booking using invalid authentication token | - | - | API rejects invalid authentication token. | - | Not Executed | - | - |
| TC-DEL-004 | Delete non-existing booking | - | - | API returns an appropriate error response. | - | Not Executed | - | - |
| TC-DEL-005 | Delete booking using invalid Booking ID format | - | - | API rejects invalid Booking ID. | - | Not Executed | - | - |
| TC-DEL-006 | Delete the same booking twice | - | - | First deletion succeeds, second deletion returns an appropriate response. | - | Not Executed | - | - |
| TC-DEL-007 | Verify deleted booking cannot be retrieved | - | - | GET endpoint no longer returns deleted booking data. | - | Not Executed | - | - |
| TC-DEL-008 | Verify response status code | - | - | API returns the expected success status code. | - | Not Executed | - | - |
| TC-DEL-009 | Verify response headers | - | - | Response headers match API specification. | - | Not Executed | - | - |
| TC-DEL-010 | Verify response time | - | - | Response time is within acceptable threshold. | - | Not Executed | - | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 10 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 10 |
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
- After successful deletion, the deleted Booking ID should be verified using the **Get Booking** endpoint.
- Any identified defects will be documented in the Bug Report section and linked from this document.

---

# Conclusion

Delete Booking test execution has not yet been performed.

Once execution begins, this document will be updated with actual execution results, supporting evidence, execution metrics, and any defects identified during testing.
