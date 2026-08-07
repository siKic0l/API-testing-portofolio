# BUG-BOOK-UPDATE-004

## Bug Information

| Field | Value |
|-------|-------|
| Bug ID | BUG-BOOK-UPDATE-004 |
| Module | Update Booking |
| Related Test Case | TC-BOOK-UPDATE-008 |
| Severity | High |
| Priority | High |
| Status | Open |
| Environment | RESTful Booker API (Public Demo) |
| Reporter | Nurrohmi Zaki |
| Report Date | August 2026 |

---

## Summary

API allows a booking where the checkout date is earlier than the checkin date.

---

## Preconditions

- RESTful Booker API is running.
- Valid authentication token is available.
- Existing Booking ID exists.

---

## Steps to Reproduce

1. Send a PUT request to `/booking/{id}`.
2. Authenticate using a valid token.
3. Set:
   - `checkin` = `2026-09-10`
   - `checkout` = `2026-09-05`
4. Send the request.

---

## Expected Result

The API should reject the request because the checkout date cannot be earlier than the checkin date.

---

## Actual Result

The API accepts the request and updates the booking successfully.

---

## Impact

Bookings with invalid date ranges can result in inconsistent reservation data and may affect room availability calculations and business processes.

---

## Evidence

[View Evidence](../../evidence/manual-testing/booking/update-booking/TC_BOOK_UPDATE_008_PASS.png)
