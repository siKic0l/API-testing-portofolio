# Create Booking Test Execution

## Overview

This document records the manual execution results for all **Create Booking** API test cases of the RESTful Booker API.

The purpose of this document is to verify that the **Create Booking** endpoint correctly creates booking records, validates request payloads, handles invalid inputs appropriately, and consistently returns responses according to the API specification.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Booking |
| Endpoint | POST /booking |
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
| TC-BOOK-001 | Create booking using valid data | - | - | Booking is successfully created and Booking ID is returned. | - | Not Executed | - | - |
| TC-BOOK-002 | Create booking with empty firstname | - | - | API handles empty firstname appropriately. | - | Not Executed | - | - |
| TC-BOOK-003 | Create booking with empty lastname | - | - | API handles empty lastname appropriately. | - | Not Executed | - | - |
| TC-BOOK-004 | Create booking with empty totalprice | - | - | API validates missing totalprice. | - | Not Executed | - | - |
| TC-BOOK-005 | Create booking with invalid totalprice data type | - | - | API rejects invalid numeric value. | - | Not Executed | - | - |
| TC-BOOK-006 | Create booking with empty bookingdates | - | - | API validates missing booking dates. | - | Not Executed | - | - |
| TC-BOOK-007 | Create booking with invalid check-in date format | - | - | API handles invalid date format appropriately. | - | Not Executed | - | - |
| TC-BOOK-008 | Create booking with invalid check-out date format | - | - | API handles invalid date format appropriately. | - | Not Executed | - | - |
| TC-BOOK-009 | Create booking with check-out earlier than check-in | - | - | API processes or rejects invalid date range appropriately. | - | Not Executed | - | - |
| TC-BOOK-010 | Create booking without additionalneeds | - | - | Booking is successfully created without optional field. | - | Not Executed | - | - |
| TC-BOOK-011 | Create booking with special characters | - | - | API safely handles special characters. | - | Not Executed | - | - |
| TC-BOOK-012 | Create booking with SQL Injection payload | - | - | API safely rejects or neutralizes malicious input. | - | Not Executed | - | - |
| TC-BOOK-013 | Create booking with XSS payload | - | - | API safely handles script payload. | - | Not Executed | - | - |
| TC-BOOK-014 | Verify response body after successful booking creation | - | - | Response body contains Booking ID and submitted booking data. | - | Not Executed | - | - |
| TC-BOOK-015 | Verify response status code | - | - | API returns the expected success status code. | - | Not Executed | - | - |
| TC-BOOK-016 | Verify response Content-Type header | - | - | Response Content-Type is application/json. | - | Not Executed | - | - |
| TC-BOOK-017 | Verify response structure | - | - | Response JSON structure matches API specification. | - | Not Executed | - | - |
| TC-BOOK-018 | Verify response time | - | - | Response time is within acceptable threshold. | - | Not Executed | - | - |
| TC-BOOK-019 | Create multiple bookings consecutively | - | - | Multiple booking requests succeed consistently. | - | Not Executed | - | - |
| TC-BOOK-020 | Verify Booking ID uniqueness | - | - | Every created booking receives a unique Booking ID. | - | Not Executed | - | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 20 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 20 |
| Pass Rate | 0% |
| Bugs Found | 0 |

---

# Defects Found

No defects have been identified.

---

# Execution Notes

- Test execution has not started.
- Actual Result, Status Code, Response Time, and Evidence will be updated after each test case is executed.
- Newly created Booking IDs should be recorded for subsequent Get, Update, Patch, and Delete testing.
- Any identified defects will be documented in the Bug Report section and linked from this document.

---

# Conclusion

Create Booking test execution has not yet been performed.

Once execution begins, this document will be updated with actual execution results, execution metrics, supporting evidence, and any defects identified during testing.
