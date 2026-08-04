# API Documentation

## Overview

This directory contains the API documentation used throughout the **RESTful Booker API Testing Portfolio**.

The purpose of this documentation is to provide a centralized reference for all available API endpoints, request structures, response formats, and authentication mechanisms before designing test scenarios and executing API tests.

Rather than relying solely on external documentation during testing, this folder summarizes the essential information required for planning, executing, and maintaining API test cases.

---

# Objectives

The documentation in this directory aims to:

- Understand the available REST API endpoints
- Identify request and response structures
- Document authentication requirements
- Provide a quick reference during test design
- Support manual and automated API testing
- Maintain traceability between documentation and test artifacts

---

# Documentation Source

This project uses **Postman Public Documentation** as the primary API reference.

Postman provides interactive API documentation generated directly from the testing collection, ensuring that the documentation always reflects the latest implementation used in this portfolio.

---

# Documentation Structure

```text
api-documentation
│
├── README.md
├── endpoint-summary.md
└── postman-public-documentation.md
```

---

# File Description

## README.md

Provides an overview of the API documentation directory, its purpose, structure, and documentation workflow.

---

## endpoint-summary.md

Summarizes every endpoint included in this project, including:

- HTTP Method
- Endpoint URL
- Authentication Requirement
- Description
- Expected Status Codes

This document serves as a quick reference during test design and execution.

---

## postman-public-documentation.md

Contains information related to the published Postman Documentation, including:

- Public Documentation URL
- Documentation Overview
- Screenshots
- Usage Instructions

---

# Documentation Workflow

The API documentation follows the workflow below.

```text
Official API
      │
      ▼
Endpoint Analysis
      │
      ▼
Postman Collection
      │
      ▼
Postman Public Documentation
      │
      ▼
Test Design
      │
      ▼
Test Execution
      │
      ▼
API Automation
```

---

# Relationship with Other Project Documents

The API documentation serves as the foundation for the following project artifacts.

| Project Artifact | Purpose |
|------------------|---------|
| API Analysis | Understand application behavior and available endpoints |
| Test Plan | Define testing objectives and scope |
| Test Scenarios | Identify business flows and testing conditions |
| Test Cases | Create detailed API validation steps |
| Postman Collection | Execute API requests |
| Automation Scripts | Validate API responses automatically |

---

# Documentation Maintenance

The API documentation should be updated whenever:

- A new endpoint is added
- Request or response formats change
- Authentication methods are modified
- API versions are updated
- Postman Documentation is republished

Keeping this documentation synchronized with the Postman Collection helps ensure consistency across manual testing, automated testing, and project documentation.

---

# Related Resources

- API Analysis
- Endpoint Summary
- Postman Public Documentation
- Test Design Documents
- Automation Collection
