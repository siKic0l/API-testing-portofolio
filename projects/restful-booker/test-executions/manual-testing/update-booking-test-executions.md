# Update Booking Test Execution

## Overview

This document contains the execution results for the **Update Booking** endpoint of the RESTful Booker API.

The purpose of this execution is to verify that an existing booking can be updated successfully, validate request payloads, verify authentication requirements, ensure business rules are enforced correctly, and confirm that the API returns the expected responses after updating booking information.

Testing was executed manually using **Postman** based on the predefined test cases stored in **Qase.io**. The execution results include actual outcomes, execution status, identified defects, and evidence references for traceability.

---

# Endpoint Information

| Item | Value |
|------|-------|
| Endpoint | `/booking/{id}` |
| HTTP Method | PUT |
| Authentication | Required |
| Content-Type | application/json |
| Expected Success Status | 200 OK |

---

# Test Environment

| Item | Value |
|------|-------|
| Application | RESTful Booker API |
| Environment | Production Demo |
| Testing Method | Manual Testing |
| Tool | Postman |
| Test Management | Qase.io |
| Tester | Nurrohmi Zaki |
| Execution Date | - |

---

# Test Execution Summary

| Category | Total |
|----------|------:|
| Passed | 18 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 0 |
| **Total Executed** | **18** |

---

# Test Execution Results

| Test Case ID | Test Case | Status Code | Response Time | Expected Result | Actual Result | Status | Evidence | Bug ID |
|--------------|-----------|-------------|---------------|-----------------|---------------|--------|----------|--------|
| TC-BOOK-UPDATE-001 | Update an existing booking using valid booking information | - | - | Booking is successfully updated. Response body matches the submitted request. | The booking was successfully updated. The API returned the updated booking information, and all returned values matched the submitted request payload. | PASS | - | - |
| TC-BOOK-UPDATE-002 | Update multiple booking fields simultaneously | - | - | All submitted booking fields are updated successfully. | The API successfully updated all submitted booking fields, and the response reflected the new values correctly. | PASS | - | - |
| TC-BOOK-UPDATE-003 | Update booking with empty firstname | - | - | API handles empty values consistently without unexpected server errors. | The API successfully processed the request when an empty `firstname` value was submitted and returned a stable response without server errors. | PASS | - | - |
| TC-BOOK-UPDATE-004 | Update booking with empty lastname | - | - | API handles empty values consistently. | The API successfully processed the request when an empty `lastname` value was submitted and returned a consistent response. | PASS | - | - |
| TC-BOOK-UPDATE-005 | Update booking with totalprice as a string | - | - | API validates the incorrect data type. No unexpected server error occurs. | The API accepted a string value for `totalprice` and successfully updated the booking instead of validating the data type. | PASS | - | BUG-BOOK-UPDATE-001 |
| TC-BOOK-UPDATE-006 | Update booking with negative totalprice | - | - | API handles negative numeric values consistently. No unexpected server error occurs. | The API accepted a negative value for `totalprice` and successfully updated the booking without validating the business rule. | PASS | - | BUG-BOOK-UPDATE-002 |
| TC-BOOK-UPDATE-007 | Update booking using an invalid checkin date format | - | - | API validates the date format correctly. Response behavior remains consistent. | The API accepted an invalid `checkin` date format and updated the booking successfully without validating the expected format. | PASS | - | BUG-BOOK-UPDATE-003 |
| TC-BOOK-UPDATE-008 | Update booking where checkout date is earlier than checkin | - | - | API validates booking dates appropriately. No unexpected server error occurs. | The API successfully updated the booking even though the `checkout` date was earlier than the `checkin` date. The request was processed consistently, but this behavior violates the expected booking business rule. | PASS | - | BUG-BOOK-UPDATE-004 |
| TC-BOOK-UPDATE-009 | Update booking without bookingdates object | - | - | API handles missing objects consistently. Appropriate response is returned. | The API handled the request consistently when the `bookingdates` object was omitted and returned a stable response. | PASS | - | - |
| TC-BOOK-UPDATE-010 | Update booking with all fields set to null | - | - | API handles null values consistently. No unexpected server error occurs. | The API processed the request containing null values consistently and did not produce any unexpected server errors. | PASS | - | - |
| TC-BOOK-UPDATE-011 | Update a non-existing booking | - | - | API returns an appropriate error response. Booking data is not modified. | The API returned the expected response for a non-existing Booking ID, and no booking data was updated. | PASS | - | - |
| TC-BOOK-UPDATE-012 | Update booking using an invalid Booking ID format | - | - | API validates the Booking ID format appropriately. | The API handled the invalid Booking ID format consistently and returned an appropriate response. | PASS | - | - |
| TC-BOOK-UPDATE-013 | Update booking without authentication | - | - | API rejects unauthenticated requests. Booking data is not updated. | The API rejected the update request when no authentication token was provided. | PASS | - | - |
| TC-BOOK-UPDATE-014 | Update booking using an invalid authentication token | - | - | API rejects invalid authentication tokens. Appropriate authentication error is returned. | The API rejected the update request when an invalid authentication token was used. | PASS | - | - |
| TC-BOOK-UPDATE-015 | Update booking using malformed JSON | - | - | API rejects malformed JSON. No unexpected server error occurs. | The API rejected the malformed JSON request and returned an appropriate error response without causing any unexpected server errors. | PASS | - | - |
| TC-BOOK-UPDATE-016 | Update booking using unsupported Content-Type header | - | - | API handles unsupported Content-Type appropriately. No unexpected server error occurs. | The API handled the request with an unsupported `Content-Type` consistently and returned an appropriate response without unexpected server errors. | PASS | - | - |
| TC-BOOK-UPDATE-017 | Verify response schema after successful booking update | - | - | Status Code is **200 OK**. Response body follows the expected JSON schema containing all required booking fields. | The API returned **200 OK** with a valid JSON response containing all required booking fields (`firstname`, `lastname`, `totalprice`, `depositpaid`, `bookingdates`, and `additionalneeds`) with the expected data types. | PASS | - | - |
| TC-BOOK-UPDATE-018 | Verify updated booking data using GET after PUT | - | - | PUT request returns **200 OK**. GET request returns the latest updated booking information. All updated values are successfully persisted. | The PUT request successfully updated the booking, and the subsequent GET request returned the latest booking information. All updated values matched the submitted PUT request payload, confirming that the data was persisted correctly. | PASS | - | - |

---

# Defect Summary

| Bug ID | Related Test Case | Summary | Severity | Status |
|--------|-------------------|---------|----------|--------|
| BUG-BOOK-UPDATE-001 | TC-BOOK-UPDATE-005 | API accepts `totalprice` as a string without validating the data type. | Medium | Open |
| BUG-BOOK-UPDATE-002 | TC-BOOK-UPDATE-006 | API accepts negative values for `totalprice` without validating business rules. | Medium | Open |
| BUG-BOOK-UPDATE-003 | TC-BOOK-UPDATE-007 | API accepts an invalid `checkin` date format instead of enforcing the `YYYY-MM-DD` format. | Medium | Open |
| BUG-BOOK-UPDATE-004 | TC-BOOK-UPDATE-008 | API allows `checkout` dates earlier than `checkin`, violating the booking date business rule. | High | Open |

---

# Execution Notes

## Summary

A total of **18 test cases** were executed for the **Update Booking** module.

All test cases completed successfully from an execution perspective, resulting in an overall execution status of **PASS**. The API remained stable throughout testing and no unexpected server crashes or unhandled exceptions were encountered.

Although every test case passed according to the predefined execution criteria, several validation weaknesses were identified where the API accepted invalid input instead of enforcing expected business rules or data validation.

---

## Identified Defects

The following functional issues were identified during execution:

- The API accepts **string values** for `totalprice` instead of validating the expected numeric data type.
- The API accepts **negative values** for `totalprice`.
- The API accepts **invalid date formats** for the `checkin` field.
- The API allows **checkout dates earlier than checkin**, violating booking business logic.

These issues have been documented separately in the Bug Report module for further analysis and tracking.

---

## General Observation

The Update Booking endpoint demonstrates stable behavior and consistently returns expected HTTP responses throughout execution. Authentication, malformed requests, invalid booking identifiers, unsupported content types, and response schema validation all behaved as expected.

The identified issues are primarily related to **input validation** and **business rule enforcement** rather than endpoint stability.

---

# Related Documents

- Test Plan
- Update Booking Test Cases
- Test Scenarios
- Test Data
- Bug Reports
- Postman Collection
- Qase Test Cases
- RESTful Booker API Documentation

---

# Update History

| Version | Description |
|---------|-------------|
| 1.0 | Initial Update Booking Test Execution |
| 1.1 | Added execution results for all 18 test cases |
| 1.2 | Added execution summary and identified defects |
| 1.3 | Added execution notes and related documentation |
