# Update Booking Test Execution

## Overview

This document records the manual execution results for all **Update Booking** API test cases of the RESTful Booker API.

The purpose of this document is to verify that the **Update Booking** endpoint correctly updates existing booking records, validates authentication requirements, handles invalid requests appropriately, and consistently returns responses according to the API specification.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Booking |
| Endpoint | PUT /booking/{id} |
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
| TC-PUT-001 | Update booking using valid authentication | - | - | Booking is successfully updated. | - | Not Executed | - | - |
| TC-PUT-002 | Update booking without authentication token | - | - | API rejects unauthorized request. | - | Not Executed | - | - |
| TC-PUT-003 | Update booking using invalid authentication token | - | - | API rejects invalid token. | - | Not Executed | - | - |
| TC-PUT-004 | Update non-existing booking | - | - | API returns an appropriate error response. | - | Not Executed | - | - |
| TC-PUT-005 | Update booking using invalid Booking ID | - | - | API rejects invalid Booking ID. | - | Not Executed | - | - |
| TC-PUT-006 | Update booking with empty firstname | - | - | API handles empty firstname appropriately. | - | Not Executed | - | - |
| TC-PUT-007 | Update booking with empty lastname | - | - | API handles empty lastname appropriately. | - | Not Executed | - | - |
| TC-PUT-008 | Update booking with invalid totalprice | - | - | API rejects invalid numeric value. | - | Not Executed | - | - |
| TC-PUT-009 | Update booking with invalid depositpaid value | - | - | API rejects invalid boolean value. | - | Not Executed | - | - |
| TC-PUT-010 | Update booking with invalid check-in date format | - | - | API handles invalid date format appropriately. | - | Not Executed | - | - |
| TC-PUT-011 | Update booking with invalid check-out date format | - | - | API handles invalid date format appropriately. | - | Not Executed | - | - |
| TC-PUT-012 | Update booking with checkout earlier than checkin | - | - | API processes or rejects invalid date range appropriately. | - | Not Executed | - | - |
| TC-PUT-013 | Verify response body after successful update | - | - | Updated booking information is returned correctly. | - | Not Executed | - | - |
| TC-PUT-014 | Verify response status code | - | - | API returns expected success status code. | - | Not Executed | - | - |
| TC-PUT-015 | Verify response Content-Type header | - | - | Response Content-Type is application/json. | - | Not Executed | - | - |
| TC-PUT-016 | Verify response structure | - | - | Response JSON structure matches API specification. | - | Not Executed | - | - |
| TC-PUT-017 | Verify response time | - | - | Response time is within acceptable threshold. | - | Not Executed | - | - |
| TC-PUT-018 | Verify updated booking can be retrieved successfully | - | - | GET endpoint returns the latest updated booking data. | - | Not Executed | - | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 18 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 18 |
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

Update Booking test execution has not yet been performed.

Once execution begins, this document will be updated with actual execution results, supporting evidence, execution metrics, and any defects identified during testing.
