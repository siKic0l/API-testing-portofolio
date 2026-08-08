# Test Scenarios

## Overview

This document defines the high-level testing scenarios for the RESTful Booker API.

The objective of these scenarios is to identify all major API behaviors that require validation before creating detailed test cases.

Each scenario represents a business objective rather than an individual test case. A single scenario may be decomposed into multiple detailed test cases.

These scenarios will later be mapped to detailed test cases and executed using Postman.

---

# Scope

The following API resources are included in this document.

- Authentication
- Booking
- Health Check

---

# Scenario Summary

| Module         | Total Scenarios |
| -------------- | --------------: |
| Authentication |               5 |
| Booking        |              28 |
| Health Check   |               2 |
| **Total**      |          **35** |

---

# Authentication

## SC-AUTH-001

Generate authentication token using valid credentials.

Priority

High

---

## SC-AUTH-002

Generate authentication token using an invalid username.

Priority

High

---

## SC-AUTH-003

Generate authentication token using an invalid password.

Priority

High

---

## SC-AUTH-004

Generate authentication token using empty credentials.

Priority

Medium

---

## SC-AUTH-005

Generate authentication token using malformed request body.

Priority

Medium

---

# Booking

## Retrieve Booking

### SC-BOOK-001

Retrieve all booking IDs.

Priority

High

---

### SC-BOOK-002

Retrieve booking details using a valid booking ID.

Priority

High

---

### SC-BOOK-003

Retrieve booking details using an invalid booking ID.

Priority

High

---

### SC-BOOK-004

Retrieve booking details using a non-existing booking ID.

Priority

Medium

---

### SC-BOOK-005

Retrieve booking details using an invalid endpoint format.

Priority

Low

---

# Create Booking

### SC-BOOK-006

Create a booking using valid data.

Priority

High

---

### SC-BOOK-007

Create a booking with missing required fields.

Priority

High

---

### SC-BOOK-008

Create a booking using empty values.

Priority

Medium

---

### SC-BOOK-009

Create a booking using invalid data types.

Priority

Medium

---

### SC-BOOK-010

Create a booking using boundary values.

Priority

Medium

---

### SC-BOOK-011

Create a booking with additional unexpected fields.

Priority

Low

---

# Update Booking

### SC-BOOK-012

Update an existing booking using valid authentication.

Priority

High

---

### SC-BOOK-013

Update booking without authentication.

Priority

High

---

### SC-BOOK-014

Update booking using an invalid token.

Priority

High

---

### SC-BOOK-015

Update booking using invalid request data.

Priority

Medium

---

### SC-BOOK-016

Update booking using a non-existing booking ID.

Priority

Medium

---

### SC-BOOK-017

Replace booking using empty values.

Priority

Medium

---

# Partial Update

### SC-BOOK-018

Update selected booking fields.

Priority

High

---

### SC-BOOK-019

Update booking without authentication.

Priority

High

---

### SC-BOOK-020

Update booking using invalid token.

Priority

High

---

### SC-BOOK-021

Update booking using invalid field values.

Priority

Medium

---

### SC-BOOK-022

Update booking using unsupported fields.

Priority

Low

---

# Delete Booking

### SC-BOOK-023

Delete booking using valid authentication.

Priority

High

---

### SC-BOOK-024

Delete booking without authentication.

Priority

High

---

### SC-BOOK-025

Delete booking using invalid authentication.

Priority

High

---

### SC-BOOK-026

Delete non-existing booking.

Priority

Medium

---

### SC-BOOK-027

Delete the same booking twice.

Priority

Medium

---

### SC-BOOK-028

Delete booking using an invalid booking ID.

Priority

Low

---

# Health Check

## SC-PING-001

Verify API availability and successful response.

Priority

High

---

## SC-PING-002

Verify API response time and response consistency.

Priority

Medium

---

# Scenario Coverage

The following table summarizes the coverage of the API.

| Endpoint             | Covered |
| -------------------- | :-----: |
| POST /auth            |   Yes   |
| GET /booking          |   Yes   |
| GET /booking/{id}     |   Yes   |
| POST /booking         |   Yes   |
| PUT /booking/{id}     |   Yes   |
| PATCH /booking/{id}   |   Yes   |
| DELETE /booking/{id}  |   Yes   |
| GET /ping             |   Yes   |

---

# Testing Techniques

The scenarios in this document were designed using the following testing techniques.

- Functional Testing
- Positive Testing
- Negative Testing
- Boundary Value Testing
- Error Handling Validation
- Authentication Testing
- Data Validation
- CRUD Validation
- Response Validation
- Reliability Observation
- Performance Observation

---

# Traceability Structure

The relationship between testing artifacts follows this hierarchy:

```text
Test Scenario
      ↓
Test Case
      ↓
Test Execution
      ↓
Evidence
      ↓
Bug Report

```

# Related Documents

This document is supported by:

- Test Plan
- Test Cases
- Test Data
- API Documentation
- Endpoint Summary
