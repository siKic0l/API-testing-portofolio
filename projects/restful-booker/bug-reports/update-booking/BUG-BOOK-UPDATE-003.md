# BUG-BOOK-UPDATE-003

## Bug Information

| Field | Value |
|-------|-------|
| Bug ID | BUG-BOOK-UPDATE-003 |
| Module | Update Booking |
| Related Test Case | TC-BOOK-UPDATE-007 |
| Severity | Medium |
| Priority | Medium |
| Status | Open |
| Environment | RESTful Booker API (Public Demo) |
| Reporter | Nurrohmi Zaki |
| Report Date | August 2026 |

---

## Summary

API accepts an invalid date format for the `checkin` field.

---

## Preconditions

- RESTful Booker API is running.
- Valid authentication token is available.
- Existing Booking ID exists.

---

## Steps to Reproduce

1. Send a PUT request to `/booking/{id}`.
2. Authenticate using a valid token.
3. Set `checkin` to `01/09/2026`.
4. Send the request.

---

## Expected Result

The API should reject the request because the supported date format is `YYYY-MM-DD`.

---

## Actual Result

The API accepts the invalid date format and updates the booking successfully.

---

## Impact

Accepting inconsistent date formats may cause parsing errors and inconsistent booking records across client applications.

---

## Evidence

[View Evidence](../../evidence/manual-testing/booking/update-booking/TC_BOOK_UPDATE_007_PASS.png)
