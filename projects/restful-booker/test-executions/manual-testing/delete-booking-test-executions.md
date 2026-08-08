# Delete Booking Test Execution

## Overview

This document records the manual execution results for all **Delete Booking** API test cases of the RESTful Booker API.

The purpose of this execution is to verify that existing bookings can be deleted successfully, authentication requirements are enforced, invalid deletion requests are handled appropriately, deleted resources can no longer be retrieved, repeated deletion requests are handled correctly, and deletion of one booking does not affect other existing bookings.

Testing was performed manually using **Postman** based on the predefined Delete Booking test cases. The execution results provide traceability between test cases, actual API behavior, execution status, and supporting evidence.

---

# Execution Information

| Item             | Value                                |
| ---------------- | ------------------------------------ |
| Application      | RESTful Booker API                   |
| Module           | Delete Booking                       |
| Endpoint         | DELETE /booking/{id}                 |
| Testing Type     | Manual API Testing                   |
| Tool             | Postman                              |
| Environment      | Public Demo                          |
| Base URL         | https://restful-booker.herokuapp.com |
| Tester           | Nurrohmi Zaki                        |
| Execution Date   | August 8, 2026                       |
| Execution Status | Completed                            |

---

# Test Execution Results

| Test Case ID    | Test Case                                            |     Status Code |         Response Time | Expected Result                                                                                                                                               | Actual Result                                                                                                                                                                                        | Status | Evidence                                                                                                                                                                                                                                                                                                                           | Bug ID |
| --------------- | ---------------------------------------------------- | --------------: | --------------------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| TC-BOOK-DEL-001 | Delete an existing booking successfully              |             201 |                 244ms | Status Code is **201 Created**. Booking is successfully deleted and no unexpected server error occurs.                                                        | The API successfully deleted the booking with ID `255` and returned **201 Created** with the response body `Created`.                                                                                | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_001_PASS.png)                                                                                                                                                                                                                                     | -      |
| TC-BOOK-DEL-002 | Delete another existing booking independently        |             201 |                 245ms | Status Code is **201 Created**. Selected booking is deleted successfully and other bookings remain unaffected.                                                | The API successfully deleted another booking with ID `659` and returned **201 Created** with the response body `Created`.                                                                            | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_002_PASS.png)                                                                                                                                                                                                                                     | -      |
| TC-BOOK-DEL-003 | Delete a non-existing booking                        |             405 |                 244ms | API returns an appropriate error response, no unexpected server error occurs, and no booking data is affected.                                                | The API returned **405 Method Not Allowed** when attempting to delete the non-existing booking with ID `99999999`. No unexpected server error occurred.                                              | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_003_PASS.png)                                                                                                                                                                                                            | -      |
| TC-BOOK-DEL-004 | Delete booking using an invalid Booking ID format    |             405 |                 245ms | API validates the Booking ID format, returns an appropriate error response, and no unexpected server error occurs.                                            | The API returned **405 Method Not Allowed** when the Booking ID was set to `abc`. No unexpected server error occurred.                                                                               | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_004_PASS.png)                                                                                                                                                                                                            | -      |
| TC-BOOK-DEL-005 | Delete booking without authentication                |             403 |                 245ms | API rejects the request, booking is not deleted, and an appropriate authentication error is returned.                                                         | The API rejected the unauthenticated DELETE request with **403 Forbidden**.                                                                                                                          | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_005_PASS.png)                                                                                                                                                                                                                                     | -      |
| TC-BOOK-DEL-006 | Delete booking using an invalid authentication token |             403 |                 247ms | API rejects the request, booking is not deleted, and an appropriate authentication error is returned.                                                         | The API rejected the DELETE request containing `token=invalid_token` with **403 Forbidden**.                                                                                                         | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_006_PASS.png)                                                                                                                                                                                                                                     | -      |
| TC-BOOK-DEL-007 | Validate response after successful booking deletion  |             201 |                 245ms | Status Code is **201 Created**. Response body is returned successfully, response format matches the API specification, and no unexpected server error occurs. | The API successfully deleted the booking and returned **201 Created** with the response body `Created`.                                                                                              | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_007_PASS.png)                                                                                                                                                                                                                                     | -      |
| TC-BOOK-DEL-008 | Verify deleted booking can no longer be retrieved    |       201 / 404 |        245ms / 1.028s | DELETE returns **201 Created** and subsequent GET confirms that the booking no longer exists.                                                                 | DELETE for booking ID `2808` returned **201 Created**. A subsequent GET request for the same booking returned **404 Not Found**, confirming that the deleted booking could no longer be retrieved.   | PASS   | [View DELETE Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_008_DELETE_PASS.png) [View GET Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_008_GET_PASS.png)                                                                                                                | -      |
| TC-BOOK-DEL-009 | Delete the same booking twice                        |       201 / 405 |         246ms | First DELETE succeeds. Second DELETE returns an appropriate error response without an unexpected server error.                                                | The first DELETE request successfully deleted the booking. The repeated DELETE request returned **405 Method Not Allowed**, confirming that the already-deleted resource was rejected appropriately. | PASS   | [View Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_009_PASS.png)                                                                                                                                                                                                            | -      |
| TC-BOOK-DEL-010 | Verify deletion does not affect other bookings       | 201 / 200 / 200 | 246ms | Booking B is deleted successfully while Booking A and Booking C remain accessible and unaffected.                                                             | DELETE for Booking B returned **201 Created**. Subsequent GET requests for Booking A and Booking C both returned **200 OK**, confirming that the unrelated bookings remained accessible.             | PASS   | [View DELETE Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_010_DELETE_PASS.png) [View GET A Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_010_GET_1_PASS.png) [View GET C Evidence](../../evidence/manual-testing/booking/delete-booking/TC_BOOK_DEL_010_GET_2_PASS.png) | -      |

---

# Execution Summary

| Metric           | Result |
| ---------------- | -----: |
| Total Test Cases |     10 |
| Passed           |     10 |
| Failed           |      0 |
| Blocked          |      0 |
| Pass Rate        |   100% |
| Bugs Found       |      0 |

---

# Execution Notes

## Summary

A total of **10 test cases** were executed for the **Delete Booking** module.

All **10 test cases passed**, resulting in an overall pass rate of **100%**. No test cases failed or were blocked during execution, and no functional defects were identified.

The DELETE endpoint successfully handled deletion of existing bookings and returned **201 Created** for successful deletion requests.

Negative scenarios were also handled appropriately. Attempts to delete a non-existing booking or use an invalid Booking ID returned **405 Method Not Allowed**, while unauthenticated and invalid-token requests returned **403 Forbidden**.

The end-to-end verification confirmed that a successfully deleted booking could no longer be retrieved through GET, returning **404 Not Found**. The data integrity test also confirmed that deleting one booking did not affect other existing bookings, which remained accessible with **200 OK** responses.

Overall, the Delete Booking module demonstrated stable behavior across functional deletion, authentication, invalid input, persistence, repeated deletion, and data integrity scenarios.
