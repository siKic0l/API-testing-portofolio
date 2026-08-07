# BUG-BOOK-UPDATE-001

## Bug Information

| Field | Value |
|-------|-------|
| Bug ID | BUG-BOOK-UPDATE-001 |
| Module | Update Booking |
| Related Test Case | TC-BOOK-UPDATE-005 |
| Severity | Medium |
| Priority | Medium |
| Status | Open |
| Environment | RESTful Booker API (Public Demo) |
| Reporter | Nurrohmi Zaki |
| Report Date | August 2026 |

---

## Summary

API accepts a string value for the `totalprice` field instead of validating that the field must contain a numeric value.

---

## Preconditions

- RESTful Booker API is running.
- Valid authentication token has been generated.
- Existing Booking ID is available.

---

## Steps to Reproduce

1. Send a PUT request to `/booking/{id}`.
2. Use a valid Booking ID.
3. Authenticate using a valid token.
4. Set `totalprice` to `"abc"`.
5. Send the request.

---

## Expected Result

The API should reject the request because `totalprice` must be a numeric value.

---

## Actual Result

The API accepts the request and updates the booking successfully.

---

## Impact

Invalid data types can be stored in booking records, reducing data integrity and increasing the risk of downstream processing errors.

---

## Evidence

`evidence/manual-testing/booking/update-booking/TC_BOOK_UPDATE_005_PASS.png`
