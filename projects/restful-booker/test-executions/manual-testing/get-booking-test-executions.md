# Get Booking Test Execution

## Overview

This document records the manual execution results for all Get Booking API test cases of the RESTful Booker API.

The purpose of this document is to verify that booking information can be retrieved correctly using an existing Booking ID, validate API behavior for invalid and non-existing Booking IDs, verify response schema and headers, provide traceability between test cases and execution evidence, and document any defects identified during testing.

---

# Execution Information

| Item | Value |
|------|-------|
| Application | RESTful Booker API |
| Module | Get Booking |
| Endpoint | GET /booking/{id} |
| Testing Type | Manual API Testing |
| Tool | Postman |
| Environment | Public Demo |
| Base URL | https://restful-booker.herokuapp.com |
| Tester | Nurrohmi Zaki |
| Execution Date | August 7, 2026 |
| Execution Status | Completed |

---

# Test Execution Results

| Test Case ID | Test Case | Status Code | Response Time | Expected Result | Actual Result | Status | Evidence | Bug ID |
|---------------|-----------|-------------|---------------|-----------------|---------------|--------|----------|--------|
| TC-BOOK-GET-001 | Retrieve booking using a valid Booking ID | 200 | 252ms | Booking information is successfully retrieved. Response contains the correct booking details. | The API successfully returned the booking information for the specified Booking ID. The response body was returned in JSON format and matched the requested booking record. | PASS | - | - |
| TC-BOOK-GET-002 | Retrieve another existing booking | 200 | 2.05s | Booking information is successfully retrieved. Response structure remains consistent. | The API successfully returned another existing booking record. The response structure remained consistent with previous successful requests. | PASS | - | - |
| TC-BOOK-GET-003 | Retrieve a non-existing Booking ID | 404 | 253ms | API returns an appropriate error response. No unexpected server error occurs. Response behavior is consistent. | The API returned an appropriate error response when a non-existing Booking ID was requested. The request was handled consistently without any unexpected server error. | PASS | - | - |
| TC-BOOK-GET-004 | Retrieve booking using a negative Booking ID | 404 | 255ms | API handles invalid numeric values correctly. No unexpected server error occurs. | The API handled the negative Booking ID consistently and returned an appropriate response without producing any unexpected server error. | PASS | - | - |
| TC-BOOK-GET-005 | Retrieve booking using Booking ID 0 | 404 | 253ms | API processes the request consistently. Appropriate response is returned. No unexpected server error occurs. | The API processed the request using Booking ID `0` consistently and returned an appropriate response without any unexpected behavior. | PASS | - | - |
| TC-BOOK-GET-006 | Retrieve booking using a decimal Booking ID | 200 | 255ms | API validates the Booking ID format. Appropriate response is returned. No unexpected server error occurs. | The API processed the decimal Booking ID consistently and returned a valid response without causing any unexpected server error. | PASS | - | - |
| TC-BOOK-GET-007 | Retrieve booking using alphabetic Booking ID | 404 | 253ms | API validates the Booking ID format. Response remains consistent. No unexpected server error occurs. | The API handled the alphabetic Booking ID consistently by returning an appropriate response without any unexpected server error. | PASS | - | - |
| TC-BOOK-GET-008 | Retrieve booking using special character Booking ID | 404 | 253ms | API validates invalid path values correctly. Appropriate response is returned. No unexpected server error occurs. | The API handled the special character Booking ID consistently and returned an appropriate response without causing any unexpected server error. | PASS | - | - |
| TC-BOOK-GET-009 | Retrieve booking without providing Booking ID | 200 | 1.50s | API returns an appropriate response. No unexpected server error occurs. Response behavior is consistent. | The API handled the request without a Booking ID consistently and returned an appropriate response without any unexpected server error. | PASS | - | - |
| TC-BOOK-GET-010 | Retrieve booking using an extremely large Booking ID | 404 | 253ms | API handles large numeric values safely. Appropriate response is returned. No unexpected server error occurs. | The API processed the extremely large Booking ID safely and returned an appropriate response without any unexpected behavior or server error. | PASS | - | - |
| TC-BOOK-GET-011 | Validate successful booking response schema | 200 | 253ms | Response contains the expected JSON schema and correct data types. | The returned response body contained all expected fields and matched the JSON schema defined in the API specification. | PASS | - | - |
| TC-BOOK-GET-012 | Validate response headers | 200 | 253ms | Response contains the expected HTTP response headers including `Content-Type: application/json`. | The API returned the expected HTTP response headers, including the correct `Content-Type`, and the response header structure matched the expected behavior. | PASS | - | - |

---

# Execution Summary

| Metric | Result |
|---------|--------|
| Total Test Cases | 12 |
| Passed | 12 |
| Failed | 0 |
| Blocked | 0 |
| Pass Rate | 100% |
| Bugs Found | 0 |

---

# Defects Found

No functional defects were identified during the execution of the Get Booking module.
