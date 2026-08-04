# API Analysis

## Overview

This document analyzes the Restful Booker API from a Quality Assurance perspective.

The objective of this analysis is to understand how the API works, identify available endpoints, determine testing scope, and prepare the foundation for API test design.

---

# API Information

| Item | Value |
|------|-------|
| API Name | Restful Booker |
| API Type | REST API |
| Protocol | HTTPS |
| Data Format | JSON |
| Authentication | Token-Based Authentication |
| Documentation | Postman Public Documentation |
| Base URL | https://restful-booker.herokuapp.com |

---

# Business Purpose

Restful Booker simulates a hotel booking management system.

The API allows clients to:

- Create hotel bookings
- Retrieve booking information
- Update existing bookings
- Partially update bookings
- Delete bookings
- Authenticate users
- Perform health checks

Although designed as a learning API, it represents common CRUD operations found in real-world REST services.

---

# REST Architecture

The API follows REST architectural principles.

Characteristics include:

- Resource-based endpoints
- Standard HTTP methods
- Stateless communication
- JSON request and response bodies
- HTTP status codes
- Token-based authentication

---

# Authentication Mechanism

The API uses token-based authentication.

Authentication workflow:

```text
User Credentials
        ↓
POST /auth
        ↓
Authentication Token
        ↓
Protected Endpoints
```

The generated token is required when performing authorized operations such as:

- Update Booking
- Partial Update Booking
- Delete Booking

---

# Available Resources

The API exposes several resources.

| Resource | Description |
|----------|-------------|
| Authentication | Generate authentication token |
| Booking | Create and manage bookings |
| Ping | Health check endpoint |

---

# Supported HTTP Methods

The API implements common REST operations.

| Method | Purpose |
|---------|----------|
| GET | Retrieve data |
| POST | Create data |
| PUT | Replace existing data |
| PATCH | Update partial data |
| DELETE | Remove data |

---

# Request Components

Each API request may contain the following components.

| Component | Required | Description |
|------------|----------|-------------|
| URL | Yes | Endpoint address |
| HTTP Method | Yes | API operation |
| Headers | Depends | Content-Type, Accept, Cookie |
| Authentication | Depends | Token or Cookie |
| Query Parameters | Optional | Filtering data |
| Path Parameters | Optional | Resource identifier |
| Request Body | Depends | JSON payload |

---

# Response Components

Each response typically contains:

- HTTP Status Code
- Response Headers
- Response Body
- Response Time

The response body is formatted in JSON.

---

# Expected HTTP Status Codes

| Status Code | Meaning |
|-------------|----------|
| 200 | Request completed successfully |
| 201 | Resource created successfully |
| 204 | Resource deleted successfully |
| 400 | Bad Request |
| 403 | Forbidden |
| 404 | Resource not found |
| 405 | Method not allowed |
| 500 | Internal Server Error |

---

# Data Format

The API exchanges data using JSON.

Typical JSON structure:

```json
{
  "firstname": "John",
  "lastname": "Doe",
  "totalprice": 120,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-08-10",
    "checkout": "2026-08-15"
  },
  "additionalneeds": "Breakfast"
}
```

---

# API Strengths

The Restful Booker API is suitable for learning because it provides:

- CRUD operations
- Authentication
- JSON request validation
- Multiple HTTP methods
- Public accessibility
- Realistic business workflow

---

# QA Analysis

From a testing perspective, the API supports several testing activities:

## Functional Testing

- Authentication testing
- CRUD operation testing
- Data validation
- Response validation
- Error handling
- Authorization testing

## Non-Functional Testing

- Response time validation
- Contract validation
- Security testing
- Reliability testing

---

# Risks

Potential testing risks include:

- Public API availability
- Shared testing environment
- Existing data modified by other users
- Rate limiting
- Temporary server instability

These factors should be considered during test execution.

---

# Conclusion

The Restful Booker API provides a complete environment for learning professional API testing.

Its support for authentication, CRUD operations, JSON communication, and REST principles makes it an ideal application for demonstrating both manual API testing and Postman automation workflows.
