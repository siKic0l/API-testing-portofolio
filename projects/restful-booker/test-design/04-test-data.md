# Test Data

## Overview

This document contains the test data used throughout the manual API testing activities for the RESTful Booker API.

The purpose of this document is to ensure consistent, reusable, and traceable test data across all test cases and execution activities.

---

# Purpose

This test data supports the following testing activities:

- Authentication Testing
- Create Booking
- Get Booking
- Update Booking
- Partial Update
- Delete Booking
- Health Check

---

# Environment

| Item | Value |
|------|--------|
| Application | RESTful Booker API |
| Environment | Public Demo |
| Base URL | https://restful-booker.herokuapp.com |
| Tester | Nurrohmi Zaki |

---

# Authentication Data

## Valid Credentials

| Field | Value |
|------|--------|
| Username | admin |
| Password | password123 |

---

## Invalid Credentials

| Username | Password | Purpose |
|-----------|----------|----------|
| admin | wrongpassword | Invalid Password |
| wronguser | password123 | Invalid Username |
| wronguser | wrongpassword | Invalid Credentials |
| *(empty)* | password123 | Empty Username |
| admin | *(empty)* | Empty Password |
| *(empty)* | *(empty)* | Empty Credentials |

---

# Booking Data

## Valid Booking Data

| Field | Value |
|------|--------|
| firstname | Michael |
| lastname | Scott |
| totalprice | 250 |
| depositpaid | true |
| checkin | 2026-09-01 |
| checkout | 2026-09-05 |
| additionalneeds | Breakfast |

---

## Boundary Value Data

| Field | Value | Purpose |
|------|--------|----------|
| firstname | A | Minimum length |
| firstname | 100 Characters | Long input |
| totalprice | 0 | Minimum numeric value |
| totalprice | 999999 | Large numeric value |

---

## Invalid Data

| Field | Value | Purpose |
|------|--------|----------|
| firstname | *(empty)* | Empty string |
| firstname | null | Null value |
| totalprice | invalid | Invalid data type |
| depositpaid | invalid | Invalid boolean |
| checkin | 01/09/2026 | Invalid date format |
| checkout | yesterday | Invalid date |

---

## Update Test Data

Used for **PUT /booking/{id}**

| Field | Value |
|------|--------|
| firstname | Dwight |
| lastname | Schrute |
| totalprice | 500 |
| depositpaid | false |
| checkin | 2026-10-01 |
| checkout | 2026-10-05 |
| additionalneeds | Lunch |

---

## Partial Update Test Data

Used for **PATCH /booking/{id}**

| Field | Value |
|------|--------|
| firstname | Jim |
| lastname | Halpert |
| additionalneeds | Dinner |

---

# Special Characters

The following values are used for input validation.

| Test Value | Purpose |
|------------|----------|
| @#$%^&* | Special Characters |
| 中文 | Unicode Characters |
| 😀 | Emoji |
| ' OR 1=1 -- | SQL Injection Observation |
| `<script>alert(1)</script>` | XSS Observation |

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

# Data Cleanup

During execution:

- Temporary bookings may be created.
- Created bookings should be deleted after testing whenever possible.
- Booking IDs used during testing should be recorded in the Test Execution Report.

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
