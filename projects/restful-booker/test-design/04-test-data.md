# Test Data

## Overview

This document contains the standardized test data used throughout the manual API testing activities for the RESTful Booker API.

The purpose of this document is to ensure consistent, reusable, and traceable test data across all test scenarios, test cases, manual executions, and future automation testing.

---

# Purpose

This document serves as the central reference for all test data used during testing.

It helps ensure:

- Consistent test execution
- Reusable test datasets
- Easier maintenance
- Better traceability
- Standardized documentation

---

# Environment

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Environment | Public Demo |
| Base URL | https://restful-booker.herokuapp.com |
| Tester | Nurrohmi Zaki |

---

# Authentication Test Data

## TD-AUTH-001 — Valid Credential

| Field | Value |
|------|--------|
| Username | admin |
| Password | password123 |

---

## TD-AUTH-002 — Invalid Password

| Field | Value |
|------|--------|
| Username | admin |
| Password | wrongpassword |

---

## TD-AUTH-003 — Invalid Username

| Field | Value |
|------|--------|
| Username | wronguser |
| Password | password123 |

---

## TD-AUTH-004 — Invalid Credential

| Field | Value |
|------|--------|
| Username | wronguser |
| Password | wrongpassword |

---

## TD-AUTH-005 — Empty Username

| Field | Value |
|------|--------|
| Username | *(empty)* |
| Password | password123 |

---

## TD-AUTH-006 — Empty Password

| Field | Value |
|------|--------|
| Username | admin |
| Password | *(empty)* |

---

## TD-AUTH-007 — Empty Credential

| Field | Value |
|------|--------|
| Username | *(empty)* |
| Password | *(empty)* |

---

# Create Booking Test Data

## TD-BOOK-001 — Valid Booking

```json
{
  "firstname": "James",
  "lastname": "Brown",
  "totalprice": 250,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-09-01",
    "checkout": "2026-09-05"
  },
  "additionalneeds": "Breakfast"
}
```

---

## TD-BOOK-002 — Empty First Name

```json
{
  "firstname": "",
  "lastname": "Brown",
  "totalprice": 250,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-09-01",
    "checkout": "2026-09-05"
  },
  "additionalneeds": "Breakfast"
}
```

---

## TD-BOOK-003 — Empty Last Name

```json
{
  "firstname": "James",
  "lastname": "",
  "totalprice": 250,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-09-01",
    "checkout": "2026-09-05"
  },
  "additionalneeds": "Breakfast"
}
```

---

## TD-BOOK-004 — Invalid Total Price

```json
{
  "firstname": "James",
  "lastname": "Brown",
  "totalprice": "invalid",
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-09-01",
    "checkout": "2026-09-05"
  },
  "additionalneeds": "Breakfast"
}
```

---

## TD-BOOK-005 — Invalid Deposit Paid

```json
{
  "firstname": "James",
  "lastname": "Brown",
  "totalprice": 250,
  "depositpaid": "true",
  "bookingdates": {
    "checkin": "2026-09-01",
    "checkout": "2026-09-05"
  },
  "additionalneeds": "Breakfast"
}
```

---

## TD-BOOK-006 — Invalid Check-in Date

```json
{
  "firstname": "James",
  "lastname": "Brown",
  "totalprice": 250,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "01/09/2026",
    "checkout": "2026-09-05"
  },
  "additionalneeds": "Breakfast"
}
```

---

## TD-BOOK-007 — Invalid Checkout Date

```json
{
  "firstname": "James",
  "lastname": "Brown",
  "totalprice": 250,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-09-01",
    "checkout": "05/09/2026"
  },
  "additionalneeds": "Breakfast"
}
```

---

# Get Booking Test Data

## TD-GET-001 — Existing Booking ID

A valid Booking ID created during testing.

---

## TD-GET-002 — Non-existing Booking ID

```
99999999
```

---

## TD-GET-003 — Invalid Booking ID

```
abc
```

---

# Update Booking Test Data

## TD-UPD-001 — Valid Full Update

```json
{
  "firstname": "Dwight",
  "lastname": "Schrute",
  "totalprice": 500,
  "depositpaid": false,
  "bookingdates": {
    "checkin": "2026-10-01",
    "checkout": "2026-10-05"
  },
  "additionalneeds": "Lunch"
}
```

---

# Partial Update Test Data

## TD-PATCH-001 — Update First Name

```json
{
  "firstname": "Jim"
}
```

---

## TD-PATCH-002 — Update Last Name

```json
{
  "lastname": "Halpert"
}
```

---

## TD-PATCH-003 — Update Additional Needs

```json
{
  "additionalneeds": "Dinner"
}
```

---

# Delete Booking Test Data

## TD-DEL-001 — Existing Booking

Existing Booking ID generated during testing.

---

## TD-DEL-002 — Non-existing Booking

```
99999999
```

---

## TD-DEL-003 — Invalid Booking ID

```
abc
```

---

# Special Character Test Data

These values are used for robustness and security observation.

| Value | Purpose |
|------|---------|
| @#$%^&* | Special Characters |
| 😀 | Emoji |
| 中文 | Unicode |
| `<script>alert(1)</script>` | XSS Observation |
| `' OR 1=1 --` | SQL Injection Observation |

---

# Date Test Data

| Scenario | Check-in | Check-out |
|----------|----------|------------|
| Valid Date | 2026-09-01 | 2026-09-05 |
| Same Day | 2026-09-01 | 2026-09-01 |
| Check-out Before Check-in | 2026-09-05 | 2026-09-01 |
| Leap Year | 2028-02-29 | 2028-03-02 |
| Invalid Format | 01/09/2026 | 05/09/2026 |

---

# Data Management

During test execution:

- Newly created Booking IDs should be recorded.
- Deleted bookings should not be reused.
- Temporary test data should be cleaned up whenever possible.
- Booking IDs generated during execution should be referenced in the Test Execution Report.

---

# Related Documents

- Test Plan
- Test Scenarios
- Test Cases
- Test Execution
- API Documentation

---

# Update History

| Version | Description |
|----------|-------------|
| 1.0 | Initial Test Data |
| 1.1 | Synchronized with Authentication, Create Booking, Get Booking, Update Booking, Partial Update, Delete Booking, and Health Check test cases |
