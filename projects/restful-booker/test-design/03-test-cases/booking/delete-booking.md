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
| Expected Success Status | 201 Created |

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

