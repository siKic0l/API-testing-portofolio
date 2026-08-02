# API Testing Workflow

## Overview

This document describes the API Testing workflow used throughout this repository.

The workflow provides a structured approach for planning, designing, executing, and documenting API testing activities to ensure consistency across every project.

Each project follows the same process regardless of the API being tested.

---

# Workflow

The API Testing process consists of the following stages:

```text
1. API Documentation Review
            ↓
2. API Analysis
            ↓
3. Endpoint Analysis
            ↓
4. Test Planning
            ↓
5. Test Scenario Design
            ↓
6. Test Case Design
            ↓
7. Manual API Testing
            ↓
8. Postman Automation
            ↓
9. Test Execution
            ↓
10. Evidence Collection
            ↓
11. Bug Reporting
            ↓
12. Test Summary Report
```

---

# Workflow Stages

## 1. API Documentation Review

The testing process begins by reviewing the available API documentation.

Objectives:

- Understand the API functionality
- Identify available endpoints
- Review request methods
- Understand authentication requirements
- Review request and response formats

Deliverables:

- API Documentation Notes
- Endpoint List

---

## 2. API Analysis

Analyze the API before designing test cases.

Activities:

- Identify business functionality
- Review API resources
- Understand request flow
- Identify dependencies between endpoints

Deliverables:

- API Analysis Document

---

## 3. Endpoint Analysis

Each endpoint is analyzed individually.

Activities:

- Review HTTP Method
- Review Request URL
- Review Parameters
- Review Headers
- Review Request Body
- Review Response Body
- Review Status Codes

Deliverables:

- Endpoint Analysis Document

---

## 4. Test Planning

Define the testing scope and objectives.

Activities:

- Define testing scope
- Define test objectives
- Identify risks
- Prepare testing environment
- Prepare test data

Deliverables:

- Test Plan

---

## 5. Test Scenario Design

Design high-level testing scenarios.

Activities:

- Identify business flows
- Group related test scenarios
- Define positive scenarios
- Define negative scenarios

Deliverables:

- Test Scenarios

---

## 6. Test Case Design

Create detailed executable test cases.

Activities:

- Write test steps
- Define expected results
- Prepare test data
- Define priorities

Deliverables:

- Test Cases

---

## 7. Manual API Testing

Execute API requests manually using Postman.

Activities:

- Send API requests
- Verify responses
- Validate status codes
- Validate response body
- Validate headers

Deliverables:

- Manual Test Execution

---

## 8. Postman Automation

Automate repetitive API validations using Postman Test Scripts.

Activities:

- Create assertions
- Validate response body
- Validate status codes
- Store variables
- Reuse authentication tokens

Deliverables:

- Postman Collection
- Automation Scripts

---

## 9. Test Execution

Execute all designed test cases.

Activities:

- Execute manual tests
- Execute automated requests
- Record actual results
- Record execution status

Deliverables:

- Test Execution Report

---

## 10. Evidence Collection

Collect execution evidence.

Activities:

- Capture screenshots
- Save response examples
- Export Postman collections when necessary

Deliverables:

- Evidence Folder

---

## 11. Bug Reporting

Document identified defects.

Activities:

- Record reproduction steps
- Describe expected result
- Describe actual result
- Assign severity
- Attach supporting evidence

Deliverables:

- Bug Report

---

## 12. Test Summary Report

Summarize the overall testing activities.

Activities:

- Calculate execution metrics
- Summarize test coverage
- Record pass/fail statistics
- List discovered defects
- Provide testing conclusion

Deliverables:

- Test Summary Report

---

# Workflow Deliverables

Every API testing project should include the following artifacts:

- API Analysis
- Endpoint Analysis
- Test Plan
- Test Scenarios
- Test Cases
- Manual Test Execution
- Postman Automation
- Evidence
- Bug Reports
- Test Summary Report

---

# Notes

This workflow serves as the standard API Testing process used throughout this repository.

As additional projects are added, the same workflow will be followed to maintain consistency and documentation quality.
