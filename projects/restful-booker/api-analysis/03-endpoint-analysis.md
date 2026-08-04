# Endpoint Analysis

## Overview

This document analyzes each endpoint provided by the Restful Booker API.

The objective is to understand the purpose, request structure, authentication requirements, expected responses, and testing opportunities for every endpoint before creating test scenarios and test cases.

---

# API Base URL

```
https://restful-booker.herokuapp.com
```

---

# Endpoint Summary

| Endpoint | Method | Authentication | Purpose |
|-----------|--------|----------------|---------|
| /ping | GET | No | Check API availability |
| /auth | POST | No | Generate authentication token |
| /booking | GET | No | Retrieve booking IDs |
| /booking/{id} | GET | No | Retrieve booking details |
| /booking | POST | No | Create a booking |
| /booking/{id} | PUT | Yes | Replace booking |
| /booking/{id} | PATCH | Yes | Update booking partially |
| /booking/{id} | DELETE | Yes | Delete booking |

---

# GET /ping

## Purpose

Checks whether the API server is available.

## Authentication

Not Required

## Request

No request body.

## Expected Response

```
201 Created
```

Response body:

```
Created
```

## QA Testing Opportunities

- Verify endpoint availability
- Verify response status code
- Verify response time
- Verify response body

---

# POST /auth

## Purpose

Generates an authentication token.

## Authentication

Not Required

## Request Body

```json
{
  "username": "admin",
  "password": "password123"
}
```

## Successful Response

```json
{
  "token": "abc123xyz"
}
```

## Expected Status Code

```
200 OK
```

## Negative Scenarios

- Invalid username
- Invalid password
- Empty username
- Empty password
- Missing request body
- Invalid JSON

## QA Testing Opportunities

- Token generation
- Required field validation
- Authentication failure
- Response schema validation
- Response time validation

---

# GET /booking

## Purpose

Retrieve booking IDs.

## Authentication

Not Required

## Query Parameters

Optional

- firstname
- lastname
- checkin
- checkout

Example

```
GET /booking?firstname=Jim
```

## Successful Response

```json
[
  {
    "bookingid": 15
  },
  {
    "bookingid": 16
  }
]
```

## Expected Status Code

```
200 OK
```

## QA Testing Opportunities

- Retrieve all bookings
- Filter by firstname
- Filter by lastname
- Filter by date
- Invalid query parameters
- Empty response

---

# GET /booking/{id}

## Purpose

Retrieve booking details.

## Authentication

Not Required

## Path Parameter

bookingid

Example

```
GET /booking/15
```

## Successful Response

```json
{
  "firstname": "Jim",
  "lastname": "Brown",
  "totalprice": 120,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-08-10",
    "checkout": "2026-08-15"
  },
  "additionalneeds": "Breakfast"
}
```

## Expected Status Code

```
200 OK
```

## Negative Scenarios

- Invalid booking ID
- Non-existing booking ID
- Alphabetic booking ID
- Special characters

## QA Testing Opportunities

- Existing booking
- Invalid booking
- Response schema validation
- Response content validation

---

# POST /booking

## Purpose

Create a new booking.

## Authentication

Not Required

## Request Body

```json
{
  "firstname": "John",
  "lastname": "Doe",
  "totalprice": 150,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-08-10",
    "checkout": "2026-08-15"
  },
  "additionalneeds": "Breakfast"
}
```

## Successful Response

```json
{
  "bookingid": 123,
  "booking": { }
}
```

## Expected Status Code

```
200 OK
```

## QA Testing Opportunities

- Valid booking creation
- Missing fields
- Invalid data types
- Boundary values
- Empty body
- Invalid JSON

---

# PUT /booking/{id}

## Purpose

Replace an existing booking.

## Authentication

Required

Authentication Token or Cookie

## Expected Status Code

```
200 OK
```

## QA Testing Opportunities

- Update all fields
- Invalid token
- Missing token
- Invalid booking ID
- Invalid request body
- Data replacement validation

---

# PATCH /booking/{id}

## Purpose

Update one or more booking fields.

## Authentication

Required

## Expected Status Code

```
200 OK
```

## QA Testing Opportunities

- Partial update
- Single field update
- Multiple field update
- Invalid field
- Invalid token
- Missing token

---

# DELETE /booking/{id}

## Purpose

Delete an existing booking.

## Authentication

Required

## Expected Status Code

```
201 Created
```

## QA Testing Opportunities

- Successful deletion
- Delete non-existing booking
- Invalid token
- Missing token
- Verify resource deletion

---

# Endpoint Coverage

| Endpoint | CRUD Operation | Priority |
|-----------|---------------|----------|
| GET /ping | Read | Low |
| POST /auth | Authentication | Critical |
| GET /booking | Read | High |
| GET /booking/{id} | Read | High |
| POST /booking | Create | Critical |
| PUT /booking/{id} | Update | Critical |
| PATCH /booking/{id} | Update | High |
| DELETE /booking/{id} | Delete | Critical |

---

# QA Notes

The endpoint analysis identifies all API operations that will be covered during testing.

These endpoints will later be translated into:

- Test Plan
- Test Scenarios
- Test Cases
- Manual API Testing
- Postman Automation
- Newman Execution
- Qase Test Management

This document serves as the primary reference for designing comprehensive API test coverage.
