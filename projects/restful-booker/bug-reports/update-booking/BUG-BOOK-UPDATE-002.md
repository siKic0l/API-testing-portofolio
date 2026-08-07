# BUG-BOOK-UPDATE-002

## Bug Information

| Field | Value |
|-------|-------|
| Bug ID | BUG-BOOK-UPDATE-002 |
| Module | Update Booking |
| Related Test Case | TC-BOOK-UPDATE-006 |
| Severity | Medium |
| Priority | Medium |
| Status | Open |
| Environment | RESTful Booker API (Public Demo) |
| Reporter | Nurrohmi Zaki |
| Report Date | August 2026 |

---

## Summary

API accepts negative values for the `totalprice` field.

---

## Preconditions

- RESTful Booker API is running.
- Valid authentication token is available.
- Existing Booking ID exists.

---

## Steps to Reproduce

1. Send a PUT request to `/booking/{id}`.
2. Authenticate using a valid token.
3. Set `totalprice` to `-100`.
4. Send the request.

---

## Expected Result

The API should reject negative values because booking prices cannot be less than zero.

---

## Actual Result

The API accepts the negative value and updates the booking successfully.

---

## Impact

Negative booking prices create invalid business data and may affect reporting, billing, and financial calculations.

---

## Evidence

[View Evidence](../../evidence/manual-testing/booking/update-booking/TC_BOOK_UPDATE_006_PASS.png)
