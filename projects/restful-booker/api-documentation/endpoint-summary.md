# Endpoint Summary

## Overview

This document provides a summary of all RESTful Booker API endpoints included in this project.

The objective of this document is to provide a quick reference for understanding the available API resources before creating test scenarios, test cases, Postman collections, and automation scripts.

The information presented here is derived from the official RESTful Booker API documentation and will be used throughout the testing process.

---

# Base URL

```text
https://restful-booker.herokuapp.com
```

All endpoints described in this project use the Base URL above.

---

# Authentication

RESTful Booker uses **Token-Based Authentication** for protected operations.

Authentication is performed by sending valid administrator credentials to the authentication endpoint.

A successful authentication request returns a token that must be included in subsequent requests requiring authorization.

---

# Endpoint Overview

| Method | Endpoint | Authentication | Description |
|---------|----------|:--------------:|-------------|
| POST | `/auth` | No | Generate authentication token |
| GET | `/booking` | No | Retrieve all booking IDs |
| GET | `/booking/{id}` | No | Retrieve booking details |
| POST | `/booking` | No | Create a new booking |
| PUT | `/booking/{id}` | Yes | Replace an existing booking |
| PATCH | `/booking/{id}` | Yes | Partially update booking information |
| DELETE | `/booking/{id}` | Yes | Delete an existing booking |
| GET | `/ping` | No | Verify API availability |

---

# Endpoint Categories

## Authentication

### POST /auth

Purpose

Generate an authentication token used for protected API requests.

Typical Operations

- Generate Token
- Validate Credentials

Expected Status Codes

- 200 OK
- 401 Unauthorized

---

## Booking

### GET /booking

Purpose

Retrieve all available booking IDs.

Typical Operations

- Retrieve Booking List
- Search Booking IDs

Expected Status Codes

- 200 OK

---

### GET /booking/{id}

Purpose

Retrieve detailed information for a specific booking.

Typical Operations

- Retrieve Booking Detail

Expected Status Codes

- 200 OK
- 404 Not Found

---

### POST /booking

Purpose

Create a new booking record.

Typical Operations

- Create Booking

Expected Status Codes

- 200 OK
- 500 Internal Server Error

---

### PUT /booking/{id}

Purpose

Replace an existing booking with new information.

Typical Operations

- Full Update

Expected Status Codes

- 200 OK
- 403 Forbidden
- 405 Method Not Allowed

---

### PATCH /booking/{id}

Purpose

Modify selected booking information.

Typical Operations

- Partial Update

Expected Status Codes

- 200 OK
- 403 Forbidden
- 405 Method Not Allowed

---

### DELETE /booking/{id}

Purpose

Delete an existing booking.

Typical Operations

- Delete Booking

Expected Status Codes

- 201 Created
- 403 Forbidden
- 405 Method Not Allowed

---

## Health Check

### GET /ping

Purpose

Verify that the API service is running and accessible.

Typical Operations

- API Availability Check

Expected Status Codes

- 201 Created

---

# CRUD Mapping

The Booking endpoint supports complete CRUD operations.

| Operation | Method | Endpoint |
|-----------|---------|----------|
| Create | POST | `/booking` |
| Read All | GET | `/booking` |
| Read One | GET | `/booking/{id}` |
| Update | PUT | `/booking/{id}` |
| Partial Update | PATCH | `/booking/{id}` |
| Delete | DELETE | `/booking/{id}` |

---

# Testing Priority

The endpoints are prioritized based on their business importance.

| Priority | Endpoints |
|----------|-----------|
| High | POST /auth |
| High | POST /booking |
| High | GET /booking/{id} |
| High | PUT /booking/{id} |
| High | DELETE /booking/{id} |
| Medium | GET /booking |
| Medium | PATCH /booking/{id} |
| Low | GET /ping |

---

# Dependencies

Several endpoints depend on others during testing.

```text
POST /auth
        │
        ▼
Authentication Token
        │
        ▼
PUT /booking/{id}
PATCH /booking/{id}
DELETE /booking/{id}
```

Likewise, a booking must first be created before it can be updated or deleted.

```text
POST /booking
        │
        ▼
Booking ID
        │
        ├────────► GET /booking/{id}
        │
        ├────────► PUT /booking/{id}
        │
        ├────────► PATCH /booking/{id}
        │
        └────────► DELETE /booking/{id}
```

---

# Related Documents

This endpoint summary is referenced by:

- API Analysis
- Test Plan
- Test Scenarios
- Test Cases
- Postman Collection
- Postman Documentation
- Automation Scripts
