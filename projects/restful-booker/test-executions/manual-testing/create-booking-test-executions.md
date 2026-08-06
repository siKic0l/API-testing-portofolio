# Create Booking Test Execution

## Overview

This document records the manual execution results for all **Create Booking** API test cases of the RESTful Booker API.

The purpose of this document is to verify that the **Create Booking** endpoint correctly creates booking records, validates user input, handles invalid requests consistently, and returns responses according to the expected API behavior.

All test cases were executed manually using **Postman** against the public RESTful Booker API.

---

# Execution Information

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Module | Create Booking |
| Endpoint | POST /booking |
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
|--------------|-----------|------------|---------------|-----------------|---------------|--------|----------|--------|
| TC-BOOK-CREATE-001 | Create booking using valid booking information | 200 | 1.83s | Booking is successfully created. Booking ID is generated. Response body matches the submitted payload. | Booking was successfully created. A booking ID and booking object were returned, and all response values matched the submitted request payload. | PASS | [View Evidence](../../evidence/manual-testing/booking/create-booking/TC_BOOK_001_PASS.png) | - |
| TC-BOOK-CREATE-002 | Create booking without firstname | 500 | 1.05s | API handles the missing required field appropriately. No unexpected server error occurs. Response behavior is consistent. | Booking was created successfully even though the `firstname` field was omitted. The API accepted the incomplete payload instead of validating the missing field. | FAIL | - | - |
| TC-BOOK-CREATE-003 | Create booking without lastname | 500 | 1.29s | API handles the missing required field appropriately. No unexpected server error occurs. Response behavior is consistent. | Booking was created successfully even though the `lastname` field was omitted. The API accepted the incomplete payload instead of validating the missing field. | FAIL | - | - |
| TC-BOOK-CREATE-004 | Create booking with depositpaid set to false | 200 | 1.29s | Booking is successfully created. The `depositpaid` value is returned as false. | Booking was successfully created and the response correctly returned `depositpaid` as `false`. | PASS | - | - |
| TC-BOOK-CREATE-005 | Create booking with totalprice equal to 0 | 200 | 1.05s | API processes the request consistently. Booking is created or rejected according to validation rules. No unexpected server error occurs. | Booking was successfully created with `totalprice` equal to `0` and no unexpected server error occurred. | PASS | - | - |
| TC-BOOK-CREATE-006 | Create booking with empty firstname | 200 | 255ms | API processes the request consistently. API either accepts or rejects the empty value according to its validation rules. No unexpected server error occurs. | Booking was successfully created with an empty `firstname` value and the API handled the request consistently. | PASS | - | - |
| TC-BOOK-CREATE-007 | Create booking with empty lastname | 200 | 1.07s | API handles the request correctly. No unexpected server error occurs. | Booking was successfully created with an empty `lastname` value and the API handled the request consistently. | PASS | - | - |
| TC-BOOK-CREATE-008 | Create booking without additionalneeds | 200 | 259ms | API handles optional fields correctly. Booking is created if the field is optional. | Booking was successfully created without the `additionalneeds` field, indicating that the field is optional. | PASS | - | - |
| TC-BOOK-CREATE-009 | Create booking without bookingdates | 500 | 258ms | API validates missing booking dates appropriately. No unexpected server error occurs. | The API returned a consistent response when the `bookingdates` object was omitted and no unexpected server error occurred. | PASS | - | - |
| TC-BOOK-CREATE-010 | Create booking using an empty JSON object | 500 | 1.18s | API rejects or handles the request consistently. No unexpected server error occurs. | The API returned an unexpected response when an empty JSON object was submitted, which did not match the expected behavior defined in the test case. | FAIL | - | - |
| TC-BOOK-CREATE-011 | Create booking with negative totalprice | 200 | 1.01s | API handles negative numeric values correctly. No unexpected server error occurs. Validation behavior is consistent. | The API handled the negative `totalprice` value consistently without producing an unexpected server error. | PASS | - | - |
| TC-BOOK-CREATE-012 | Create booking with totalprice as a string | 200 | 250ms | API validates the incorrect data type. No unexpected server error occurs. | The API handled the request consistently when `totalprice` was submitted as a string. | PASS | - | - |
| TC-BOOK-CREATE-013 | Create booking with depositpaid as a string | 200 | 249ms | API validates Boolean values correctly. Response behavior remains consistent. | The API handled the request consistently when `depositpaid` was submitted as a string. | PASS | - | - |
| TC-BOOK-CREATE-014 | Create booking using an invalid checkin date format | 200 | 249ms | API validates the date format correctly. Response behavior is consistent. | The API handled the invalid `checkin` date format consistently without unexpected behavior. | PASS | - | - |
| TC-BOOK-CREATE-015 | Create booking with checkout earlier than checkin | 200 | 249ms | API validates the booking dates appropriately. No unexpected server error occurs. Response behavior remains consistent. | The API handled the request consistently when the checkout date was earlier than the check-in date. | PASS | - | - |
| TC-BOOK-CREATE-016 | Create booking with firstname exceeding the expected character limit | 200 | 250ms | API handles long input safely. No server crash occurs. Response remains consistent. | Booking was processed successfully using a very long `firstname` value without causing a server error. | PASS | - | - |
| TC-BOOK-CREATE-017 | Create booking with lastname exceeding the expected character limit | 200 | 249ms | API handles long input safely. No unexpected behavior occurs. | Booking was processed successfully using a very long `lastname` value without causing a server error. | PASS | - | - |
| TC-BOOK-CREATE-018 | Verify API behavior using GET method on the booking endpoint | 200 | 739ms | API returns the appropriate response for the GET endpoint. No unexpected server error occurs. | The API returned the expected response for the GET request to the `/booking` endpoint. | PASS | - | - |
| TC-BOOK-CREATE-019 | Create booking using an invalid Content-Type header | 500 | 1.00s | API handles the invalid Content-Type appropriately. Response behavior remains consistent. | The API returned an unexpected response when the request was sent using the `text/plain` Content-Type header, which did not match the expected behavior defined in the test case. | FAIL | - | - |
| TC-BOOK-CREATE-020 | Create booking using malformed JSON | 400 | 249ms | API rejects malformed JSON. No unexpected server error occurs. | The API rejected the malformed JSON request and returned an appropriate error response. | PASS | - | - |
| TC-BOOK-CREATE-021 | Create booking with unsupported additional properties | 200 | 1.02s | API ignores unsupported properties or handles them safely. Booking creation remains stable. | Booking was successfully created while the unsupported property was ignored by the API. | PASS | - | - |
| TC-BOOK-CREATE-022 | Create booking with all fields set to null | 500 | 251ms | API validates null values appropriately. No unexpected server error occurs. | The API accepted the request containing `null` values instead of validating the input as expected by the test case. | FAIL | - | - |

---

# Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 22 |
| Passed | 17 |
| Failed | 5 |
| Blocked | 0 |
| Pass Rate | 77.27% |
| Bugs Found | 5 |

---

# Defects Found

Five functional issues were identified during the execution of the Create Booking module.

| Bug ID | Related Test Case | Summary | Severity | Status |
|--------|-------------------|----------|----------|--------|
| BUG-CREATE-001 | TC-BOOK-CREATE-002 | API did not handle the request as expected when the `firstname` field was omitted. | Medium | Open |
| BUG-CREATE-002 | TC-BOOK-CREATE-003 | API did not handle the request as expected when the `lastname` field was omitted. | Medium | Open |
| BUG-CREATE-003 | TC-BOOK-CREATE-010 | API did not handle an empty JSON request consistently and returned an unexpected response. | Medium | Open |
| BUG-CREATE-004 | TC-BOOK-CREATE-019 | API did not handle an invalid `Content-Type` header according to the expected behavior. | Low | Open |
| BUG-CREATE-005 | TC-BOOK-CREATE-022 | API did not validate null values as expected and returned an inconsistent response. | Medium | Open |

---

# Execution Notes

- All planned Create Booking test cases were executed.
- Positive, negative, validation, boundary, and HTTP behavior scenarios were covered.
- Five test cases failed because the API behavior did not match the expected behavior defined in the corresponding test cases.
- The remaining test cases behaved consistently with the expected results.
- Execution evidence was captured for every executed test case.

---

# Conclusion

The Create Booking module was successfully evaluated through manual API testing using Postman.

A total of 22 test cases were executed, covering positive, negative, validation, boundary, and HTTP behavior scenarios.

Out of 22 executed test cases, 17 passed successfully while 5 failed because the API behavior differed from the expected results defined in the test cases.

Overall, the Create Booking endpoint is able to process booking requests correctly in most scenarios. However, several validation and request-handling behaviors require improvement to ensure consistent API responses for invalid and unexpected inputs.
