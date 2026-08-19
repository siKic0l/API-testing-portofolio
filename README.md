# API Testing Portfolio

A collection of my API Testing projects demonstrating **manual API testing**, **Postman automation**, **REST API validation**, and professional QA documentation using real-world REST APIs.

This repository showcases an end-to-end API Testing workflow, starting from API analysis and endpoint exploration to test design, execution, automation, and reporting.

---

# About This Repository

This repository is dedicated to API Quality Assurance and focuses on testing RESTful APIs using industry-standard tools and practices.

Each project follows a structured testing workflow to ensure API reliability, functionality, and correctness while maintaining clear and reproducible documentation.

---

# Objectives

The goals of this repository are to:

- Practice REST API Testing
- Perform Manual API Testing
- Learn Postman Automation
- Design professional API Test Cases
- Validate API Responses
- Document API Testing workflows
- Build a professional API Testing portfolio

---

# Current Project

| Project | Status |
|---------|--------|
| Restful Booker API | Manual Testing Completed |

# Execution Summary

Manual API testing for the Restful Booker API has been completed and recorded in Qase.io.
Figures below use the latest execution result per unique test case.

| Metric | Result |
|--------|-------:|
| Test Cases | 97 |
| Passed | 89 |
| Failed | 6 |
| Blocked | 2 |
| Pass Rate | 91.75% |
| Bug Reports | 10 |
| Execution Date | August 13, 2026 |

**Public Qase Report:** https://app.qase.io/public/report/debcf3c66ec50d7471d709188741133f6fefc744

## Results by Test Suite

| Test Suite | Total | Passed | Failed | Blocked | Pass Rate |
|------------|------:|-------:|-------:|--------:|----------:|
| Authentication | 15 | 15 | 0 | 0 | 100% |
| Create Booking | 22 | 16 | 6 | 0 | 72.73% |
| Get Booking | 12 | 12 | 0 | 0 | 100% |
| Update Booking | 18 | 18 | 0 | 0 | 100% |
| Partial Update Booking | 15 | 13 | 0 | 2 | 86.67% |
| Delete Booking | 10 | 10 | 0 | 0 | 100% |
| Health Check | 5 | 5 | 0 | 0 | 100% |

All 6 failed test cases belong to the Create Booking suite and relate to missing required
field validation returning `500 Internal Server Error` instead of a client error response.

## Scope Note

This project currently covers **manual API testing and test management only**.
The `automation` directory contains the intended folder structure, but the Postman collection
and Newman execution have **not been implemented yet** — they are listed under the planned
roadmap below rather than as completed work.

---

# Repository Structure

```text
api-testing-portfolio
│
├── README.md
├── CHANGELOG.md
│
├── docs
│   ├── 01-api-testing-overview.md
│   ├── 02-api-testing-workflow.md
│   ├── 03-tools-and-technologies.md
│   └── 04-best-practices.md
│
├── projects
│   │
│   └── restful-booker
│       │
│       ├── README.md
│       │
│       ├── api-documentation
│       │   ├── README.md
│       │   ├── endpoint-summary.md
│       │   └── postman-public-documentation.md
│       │
│       ├── api-analysis
│       │   ├── 01-project-overview.md
│       │   ├── 02-api-analysis.md
│       │   ├── 03-endpoint-analysis.md
│       │   └── 04-test-strategy.md
│       │
│       ├── test-design
│       │   ├── 01-test-plan.md
│       │   ├── 02-test-scenarios.md
│       │   ├── 03-test-cases
│       │   └── 04-test-data.md
│       │
│       ├── test-execution
│       │   ├── manual-test-execution.md
│       │   └── automation-test-execution.md
│       │
│       ├── automation
│       │   ├── README.md
│       │   │
│       │   ├── collections
│       │   │   └── Restful-Booker.postman_collection.json
│       │   │
│       │   ├── environments
│       │   │   └── Local.postman_environment.json
│       │   │
│       │   ├── globals
│       │   │   └── Global.postman_globals.json
│       │   │
│       │   ├── scripts
│       │   │   ├── authentication.md
│       │   │   ├── assertions.md
│       │   │   ├── variables.md
│       │   │   └── collection-runner.md
│       │   │
│       │   └── newman
│       │       └── README.md
│       │
│       ├── qase
│       │   ├── README.md
│       │   ├── test-suites.md
│       │   ├── test-runs.md
│       │   ├── test-metrics.md
│       │   └── public-report.md
│       │
│       ├── bug-reports
│       │
│       ├── evidence
│       │   ├── authentication
│       │   ├── booking
│       │   ├── update-booking
│       │   ├── partial-update
│       │   ├── delete-booking
│       │   ├── automation
│       │   └── bugs
│       │
│       └── reports
│           ├── test-summary-report.md
│           └── automation-summary.md
│
└── assets
    ├── images
    ├── diagrams
    └── icons
```

---

# API Testing Workflow

Each project follows the workflow below.

```text
API Documentation Review
            ↓
API Analysis
            ↓
Endpoint Analysis
            ↓
Test Planning
            ↓
Test Scenario Design
            ↓
Test Case Design
            ↓
Manual API Testing
            ↓
Automation using Postman
            ↓
Evidence Collection
            ↓
Bug Reporting
            ↓
Test Summary Report
```

---

# Testing Scope

This repository includes:

- API Documentation Analysis
- Endpoint Analysis
- REST API Testing
- Manual API Testing
- Test Design
- Test Execution
- Bug Reporting
- Test Summary Reports
- Evidence Collection

---

# REST API Concepts

The following REST concepts are applied throughout the projects:

- HTTP Methods
- REST Architecture
- Request & Response
- JSON
- Headers
- Query Parameters
- Path Parameters
- Authentication
- Authorization
- HTTP Status Codes
- CRUD Operations

---

# Testing Techniques

The following testing techniques are used:

- Functional Testing
- Black Box Testing
- Positive Testing
- Negative Testing
- Boundary Testing
- Error Guessing
- Exploratory Testing
- Response Validation

---

# Tools

## API Documentation

- Postman API Documentation

## API Testing

- Postman

## Test Management

- Qase.io

## Documentation

- Markdown
- Git
- GitHub

---

# Project Deliverables

Each API Testing project includes:

- Project Overview
- API Analysis
- Endpoint Analysis
- Test Plan
- Test Scenarios
- Test Cases
- Manual API Test Execution
- Postman API Documentation
- Postman Collections
- Environment Files
- Automation Scripts
- Bug Reports
- Test Summary Report

---

# Repository Metrics

| Metric | Value |
|---------|------:|
| Projects | 1 |
| APIs Tested | 1 |
| Test Cases | 97 |
| Automated Requests | Not started — planned |
| Bug Reports | 10 |

---

# Learning Roadmap

## Current

- REST API Testing
- Postman
- Swagger
- API Test Design

## Planned

- Postman Automation
- Newman CLI
- REST Assured
- PyTest API Testing
- JavaScript API Automation
- Cypress API Testing
- API CI/CD Integration

---

# Related Repositories

| Repository | Description |
|------------|-------------|
| [Manual Testing Portfolio](https://github.com/siKic0l/OrangeHRMdemo-Manual-Testing-Portofolio) | Manual QA project using OrangeHRM — completed |
| API Testing Portfolio | REST API Testing using Postman — this repository |
| Playwright Automation *(Coming Soon)* | UI Automation Testing |

---

# Contact

**Nurrohmi Zaki**

- GitHub: https://github.com/siKic0l
- LinkedIn: https://www.linkedin.com/in/nurrohmi-zaki-78b447294/
