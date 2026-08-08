# Partial Update Booking Test Execution

## Overview

This document contains the execution results for the **Partial Update Booking** endpoint of the RESTful Booker API.

The purpose of this execution is to verify that specific booking fields can be updated without affecting other existing data, validate request payloads, verify authentication requirements, and confirm that the API correctly processes partial updates.

Testing was executed manually using **Postman** based on the predefined test cases stored in **Qase.io**. The execution results include actual outcomes, execution status, identified defects, blocked test cases, and evidence references for traceability.

---

# Endpoint Information

| Item                    | Value            |
| ----------------------- | ---------------- |
| Endpoint                | `/booking/{id}`  |
| HTTP Method             | PATCH            |
| Authentication          | Required         |
| Content-Type            | application/json |

---

# Test Environment

| Item            | Value              |
| --------------- | ------------------ |
| Application     | RESTful Booker API |
| Environment     | Production Demo    |
| Testing Method  | Manual Testing     |
| Tool            | Postman            |
| Test Management | Qase.io            |
| Tester          | Nurrohmi Zaki      |
| Execution Date  | August 8, 2026     |

---

# Test Execution Summary

| Category           |  Total |
| ------------------ | -----: |
| Passed             |     13 |
| Failed             |      0 |
| Blocked            |      2 |
| Not Executed       |      0 |
| Defects Found      |      0 |
| **Total Executed** | **15** |

---

# Test Execution Results

| Test Case ID      | Test Case                                              | Status Code | Response Time | Expected Result                                                                                                                                        | Actual Result                                                                                                                                                                                                                                   | Status  | Evidence                                                                                                                                                                                                                              | Bug ID |
| ----------------- | ------------------------------------------------------ | ----------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| TC-BOOK-PATCH-001 | Update only the `firstname` field                      | 200         | 246ms           | Status Code is **200 OK**. Only `firstname` is updated and other booking fields remain unchanged.                                                      | The API successfully updated `firstname` to `Michael` and returned the updated booking information while retaining the other booking fields.                                                                                                    | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_001_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-002 | Update only the `lastname` field                       | 200         | 247ms           | Status Code is **200 OK**. Only `lastname` is updated and other booking fields remain unchanged.                                                       | The API successfully updated `lastname` to `Halpert` and returned the updated booking information while retaining the other booking fields.                                                                                                     | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_002_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-003 | Update only the `additionalneeds` field                | 200         | 999ms           | Status Code is **200 OK**. Only `additionalneeds` is updated and other booking fields remain unchanged.                                                | The API successfully updated `additionalneeds` to `Dinner` and returned the updated booking information.                                                                                                                                        | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_003_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-004 | Update only the `depositpaid` field                    | 200         | 995ms           | Status Code is **200 OK**. Only `depositpaid` is updated and other booking fields remain unchanged.                                                    | The API successfully updated `depositpaid` to `false` and returned the updated booking information.                                                                                                                                             | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_004_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-005 | Update multiple selected booking fields simultaneously | 200         | 245ms           | All submitted fields are updated successfully while fields not included in the request remain unchanged.                                               | The API successfully updated `firstname`, `lastname`, and `additionalneeds` according to the submitted request and returned the updated booking information.                                                                                    | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_005_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-006 | Update booking with an empty string value              | 200         | 997ms           | API handles empty values consistently without unexpected server errors.                                                                                | The API successfully processed the request containing an empty `firstname` value and returned a stable response without an unexpected server error.                                                                                             | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_006_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-007 | Update `totalprice` using an invalid string value      | 200         | 246ms           | API validates the submitted data type, handles the invalid value consistently, and does not produce an unexpected server error.                        | The API returned **200 OK** and handled the submitted string value without a server error. The resulting `totalprice` value was returned as `null`.                                                                                             | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_007_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-008 | Update booking using an invalid `checkin` date format  | 200         | 246ms           | API handles the invalid date input consistently, validates or normalizes the submitted value, and does not produce an unexpected server error.         | The API returned **200 OK** and normalized the submitted `01/09/2026` value to `2026-01-09` in the response.                                                                                                                                    | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_008_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-009 | Update `firstname` using a null value                  | 200         | 246ms           | API handles null values consistently without unexpected server errors.                                                                                 | The API successfully processed the request containing a null `firstname` value and returned a stable response without an unexpected server error.                                                                                               | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_009_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-010 | Update a non-existing booking                          | 403         | 3.25s           | API returns an appropriate error response, no booking data is modified, and no unexpected server error occurs.                                         | The API returned **403 Forbidden**. The response did not provide sufficient evidence to determine whether the rejection was caused by the non-existing Booking ID or by authentication/authorization.                                           | BLOCKED | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_010_BLOCKED.png)                                                                                                               | -      |
| TC-BOOK-PATCH-011 | Update booking using an invalid Booking ID format      | 403         | 1.02s           | API validates the Booking ID format and returns an appropriate response.                                                                               | The API returned **403 Forbidden**. The response did not provide sufficient evidence to confirm that the `abc` Booking ID format was actually validated as the cause of the rejection.                                                          | BLOCKED | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_011_BLOCKED.png)                                                                                                               | -      |
| TC-BOOK-PATCH-012 | Update booking without authentication                  | 403         | 247ms           | API rejects unauthenticated requests and booking data is not updated.                                                                                  | The API rejected the PATCH request with **403 Forbidden** when authentication was not provided.                                                                                                                                                 | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_012_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-013 | Update booking using an invalid authentication token   | 403         | 248ms           | API rejects invalid authentication tokens and returns an appropriate authentication error.                                                             | The API rejected the PATCH request with **403 Forbidden** when an invalid authentication token was provided.                                                                                                                                    | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_013_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-014 | Verify response schema after successful partial update | 200         | 247ms           | Status Code is **200 OK**. Response body follows the expected JSON schema containing all required booking fields with the expected data types.         | The API returned **200 OK** with a valid JSON response containing the required booking fields: `firstname`, `lastname`, `totalprice`, `depositpaid`, `bookingdates`, and `additionalneeds`, with the expected data types.                       | PASS    | [View Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_014_PASS.png)                                                                                                                              | -      |
| TC-BOOK-PATCH-015 | Verify updated booking data using GET after PATCH      | 200         | 1.01s           | PATCH returns **200 OK**. GET returns the latest booking information. Only the intended field is changed and the other booking data remains unchanged. | The PATCH request successfully updated the intended field. The subsequent GET request returned the updated booking data, and the comparison confirmed that the intended change was persisted while the other booking fields remained unchanged. | PASS    | [View PATCH Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_015_PATCH_PASS.png) [View GET Evidence](../../evidence/manual-testing/booking/partial-update-booking/TC_BOOK_PATCH_015_GET_PASS.png) | -      |

---

# Execution Notes

## Summary

A total of **15 test cases** were executed for the **Partial Update Booking** module.

A total of **13 test cases passed**, while **2 test cases were blocked**. No test cases failed during execution.

The API remained stable throughout the executed tests, and no unexpected server crashes or unhandled server errors were observed.

The successful test cases confirmed that individual and multiple booking fields can be partially updated, authentication requirements are enforced, response data follows the expected schema, and updated booking information can be persisted and verified through a subsequent GET request.

---

## Blocked Test Cases

The following test cases were blocked during execution:

* **TC-BOOK-PATCH-010 — Update a non-existing booking**
* **TC-BOOK-PATCH-011 — Update booking using an invalid Booking ID format**

Both test cases returned **403 Forbidden**. However, the available evidence does not establish that the `403 Forbidden` response was caused by the Booking ID condition being tested. The request may have been rejected at the authentication/authorization layer before the non-existing or invalid Booking ID condition could be properly evaluated.

Therefore, these test cases were marked **BLOCKED** rather than PASS or FAIL.

The test cases should be re-executed after the authentication/authorization condition has been verified so that the behavior of the non-existing and invalid Booking IDs can be evaluated independently.

---

## General Observation

The Partial Update Booking endpoint demonstrated stable behavior across the executed positive, validation, authentication, response schema, and persistence scenarios.

The API successfully processed partial updates for individual fields as well as multiple selected fields. Authentication controls also behaved as expected for requests without authentication and requests using an invalid authentication token.

For the validation scenarios involving invalid values, the API processed the requests without unexpected server errors. Some behaviors, such as the handling of an invalid `totalprice` value and normalization of an invalid date format, were observed during execution but were not classified as confirmed defects because the predefined test case expected consistent handling rather than a specific rejection status.

The primary execution limitation was the inability to independently verify the behavior of non-existing and invalid Booking IDs because both requests returned **403 Forbidden** before the intended ID-specific behavior could be conclusively established.
