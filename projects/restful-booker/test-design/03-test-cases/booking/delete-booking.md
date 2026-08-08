# Delete Booking Test Cases

## Overview

This document contains manual test cases for the **Delete Booking** endpoint of the RESTful Booker API.

The objective of these test cases is to verify that booking records can be deleted successfully, authentication requirements are enforced, invalid deletion requests are handled correctly, and deleted resources are permanently removed from the system.

These test cases will be executed manually using **Postman**, managed in **Qase.io**, and later automated using **Postman Test Scripts** and **Newman**.

---

# Endpoint Information

| Item | Value |
|------|--------|
| Endpoint | `/booking/{id}` |
| HTTP Method | DELETE |
| Authentication | Required |

---

# Shared Preconditions

The following preconditions apply to all test cases unless otherwise stated.

- RESTful Booker API is accessible.
- Postman is installed and configured.
- Base URL has been configured.
- A valid authentication token has been generated.
- At least one booking record already exists.
- A valid Booking ID is available.

---

# Shared Request Headers

| Header | Value |
|--------|--------|
| Cookie | token={{auth_token}} |

---

# Positive Testing

## TC-BOOK-DEL-001

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-001 |
| Test Scenario | SC-BOOK-DEL-001 |
| Priority | High |
| Testing Type | Positive |

---

### Objective

Verify that an existing booking can be deleted successfully.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a DELETE request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Click **Send**.|
|6|Verify the response.|

---

### Expected Result

- Status Code is **201 Created**.
- Booking is successfully deleted.
- No unexpected server error occurs.

---

### Notes

This verifies the primary functionality of the DELETE endpoint.

---

## TC-BOOK-DEL-002

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-002 |
| Test Scenario | SC-BOOK-DEL-002 |
| Priority | Medium |
| Testing Type | Positive |

---

### Objective

Verify that multiple existing bookings can be deleted independently.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Another Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a DELETE request.|
|3|Replace `{id}` with another valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Click **Send**.|
|6|Verify the response.|

---

### Expected Result

- Status Code is **201 Created**.
- Selected booking is deleted successfully.
- Other bookings remain unaffected.

---

### Notes

Confirms DELETE works consistently across multiple resources.

---

# Negative Testing

## TC-BOOK-DEL-003

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-003 |
| Test Scenario | SC-BOOK-DEL-003 |
| Priority | High |
| Testing Type | Negative |

---

### Objective

Verify API behavior when attempting to delete a non-existing booking.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | 99999999 |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a DELETE request to `/booking/{id}`.|
|3|Replace `{id}` with a non-existing Booking ID.|
|4|Add a valid authentication token.|
|5|Click **Send**.|
|6|Verify the response.|

---

### Expected Result

- API returns an appropriate error response.
- No unexpected server error occurs.
- No booking data is affected.

---

### Notes

Actual status code will be confirmed during execution.

---

## TC-BOOK-DEL-004

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-004 |
| Test Scenario | SC-BOOK-DEL-004 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when the Booking ID contains invalid characters.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | abc |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a DELETE request.|
|3|Replace the Booking ID with `abc`.|
|4|Authenticate using a valid token.|
|5|Click **Send**.|
|6|Verify the response.|

---

### Expected Result

- API validates the Booking ID format.
- Appropriate error response is returned.
- No unexpected server error occurs.

---

### Notes

Observe the returned HTTP status code.

---

# Authentication Testing

## TC-BOOK-DEL-005

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-005 |
| Test Scenario | SC-BOOK-DEL-005 |
| Priority | High |
| Testing Type | Authentication |

---

### Objective

Verify API behavior when attempting to delete a booking without authentication.

---

### Test Data

No authentication token.

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a DELETE request.|
|3|Remove the Cookie authentication header.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API rejects the request.
- Booking is not deleted.
- Appropriate authentication error is returned.

---

### Notes

Authentication is mandatory for the DELETE endpoint.

---

## TC-BOOK-DEL-006

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-006 |
| Test Scenario | SC-BOOK-DEL-006 |
| Priority | High |
| Testing Type | Authentication |

---

### Objective

Verify API behavior when an invalid authentication token is used.

---

### Test Data

| Header | Value |
|--------|--------|
| Cookie | token=invalid_token |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a DELETE request.|
|3|Replace the authentication token with an invalid token.|
|4|Click **Send**.|
|5|Verify the response.|

---

### Expected Result

- API rejects the request.
- Booking is not deleted.
- Appropriate authentication error is returned.

---

### Notes

Actual response will be confirmed during execution.

---

# Response Validation

## TC-BOOK-DEL-007

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-007 |
| Test Scenario | SC-BOOK-DEL-007 |
| Priority | Medium |
| Testing Type | Validation |

---

### Objective

Verify that the API returns the expected response after a successful booking deletion.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Open Postman.|
|2|Create a DELETE request to `/booking/{id}`.|
|3|Replace `{id}` with a valid Booking ID.|
|4|Authenticate using a valid token.|
|5|Click **Send**.|
|6|Inspect the response.|

---

### Expected Result

- Status Code is **201 Created**.
- Response body is returned successfully.
- Response format matches the API specification.
- No unexpected server error occurs.

---

### Notes

This test validates the DELETE response only and does not verify data persistence.

---

# End-to-End Verification

## TC-BOOK-DEL-008

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-008 |
| Test Scenario | SC-BOOK-DEL-008 |
| Priority | High |
| Testing Type | End-to-End Verification |

---

### Objective

Verify that a deleted booking can no longer be retrieved.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Existing Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Create or identify an existing booking.|
|2|Send a DELETE request for the booking.|
|3|Verify that DELETE returns **201 Created**.|
|4|Send a GET request using the same Booking ID.|
|5|Verify the GET response.|

---

### Expected Result

- DELETE request returns **201 Created**.
- GET request confirms the booking no longer exists.
- Deleted data cannot be retrieved.

---

### Notes

This test verifies that deletion is permanently persisted.

---

## TC-BOOK-DEL-009

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-009 |
| Test Scenario | SC-BOOK-DEL-009 |
| Priority | Medium |
| Testing Type | Negative |

---

### Objective

Verify API behavior when attempting to delete the same booking twice.

---

### Test Data

| Field | Value |
|------|--------|
| Booking ID | Previously Deleted Booking ID |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Delete an existing booking successfully.|
|2|Repeat the DELETE request using the same Booking ID.|
|3|Verify the response.|

---

### Expected Result

- First DELETE request succeeds.
- Second DELETE request returns an appropriate error response.
- No unexpected server error occurs.

---

### Notes

This verifies that already deleted resources are handled correctly.

---

## TC-BOOK-DEL-010

### Test Information

| Field | Value |
|------|--------|
| Test Case ID | TC-BOOK-DEL-010 |
| Test Scenario | SC-BOOK-DEL-010 |
| Priority | High |
| Testing Type | End-to-End Verification |

---

### Objective

Verify that deleting one booking does not affect other existing bookings.

---

### Test Data

| Field | Value |
|------|--------|
| Booking A | Existing Booking |
| Booking B | Existing Booking |
| Booking C | Existing Booking |

---

### Test Steps

| Step | Action |
|------|--------|
|1|Prepare three existing bookings.|
|2|Delete Booking B.|
|3|Verify DELETE returns **201 Created**.|
|4|Retrieve Booking A using GET.|
|5|Retrieve Booking C using GET.|
|6|Verify both bookings are still available.|

---

### Expected Result

- Booking B is deleted successfully.
- Booking A remains accessible.
- Booking C remains accessible.
- No unrelated booking is modified or deleted.

---

### Notes

This test verifies data integrity after deletion.

---

# Test Case Summary

| Category | Total |
|----------|------:|
| Positive Testing | 2 |
| Negative Testing | 3 |
| Authentication Testing | 2 |
| Validation Testing | 1 |
| End-to-End Verification | 2 |
| **Total Test Cases** | **10** |

---

# Coverage Summary

| Coverage | Status |
|----------|:------:|
| Delete Existing Booking | Yes |
| Invalid Booking Validation | Yes |
| Authentication Validation | Yes |
| Response Validation | Yes |
| Deleted Resource Verification | Yes |
| Data Integrity Verification | Yes |

---

# Related Documents

- Test Plan
- Test Scenarios
- Test Data
- Postman Collection
- Qase Test Cases
- API Documentation

---

# Update History

| Version | Description |
|----------|-------------|
| 1.0 | Initial Delete Booking Test Cases |
| 1.1 | Added response validation and end-to-end verification |
