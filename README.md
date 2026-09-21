# Comprehensive QA & Test Suite: Pharmacy Management System

A practical Software Quality Assurance (QA) portfolio showcasing end-to-end test scenarios, Boundary Value Analysis (BVA), Postman RESTful API regression testing, and structured defect lifecycle reporting for a multi-user Web Application.

---

## 📌 Project Overview
This repository contains real-world testing artifacts designed and executed for a **Smart Pharmacy Management System**. It covers critical operations including medicine inventory thresholds, role-based access control (RBAC), discount validation, and API authentication.

---

## 📊 Executed Test Scenarios (Sample Matrix)

| Test Case ID | Module | Test Scenario | Execution Type | Expected Outcome | Status |
|---|---|---|---|---|---|
| **TC-PH-01** | Inventory | Reject expired medicine addition | Functional / Validation | Blocks addition with expiry alert | `PASSED` |
| **TC-PH-02** | POS / Cart | Sell quantity exceeding current stock | Boundary (BVA) | Prevents checkout; shows remaining stock | `PASSED` |
| **TC-PH-03** | Auth / RBAC | Cashier unauthorized access to financial reports | Security / Role Check | Returns `403 Forbidden` / Redirects | `PASSED` |
| **TC-PH-04** | Web API | Verify JWT bearer token generation on login | API Testing (Postman) | HTTP `200 OK` + Valid JWT payload | `PASSED` |
| **TC-PH-05** | Checkout | Prevent negative discount inputs | Boundary Value Analysis | System rejects values < 0% | `PASSED` |

---

## 🛠️ Testing Tools & Methodologies
- **Functional & Regression Testing:** Manual Test Design, Equivalence Partitioning (EP), Boundary Value Analysis (BVA).
- **API Testing:** Postman (Collections, Environment Variables, Status Codes, JSON Schema Validation).
- **Defect Tracking:** Standardized Bug Reporting (Severity/Priority classification, Reproduction Steps).

---

## 📂 Repository Structure
- `test-cases/`: Detailed spreadsheets and markdown files for test case executions.
- `bug-reports/`: Real bug incident reports with reproduction steps and verification logs.
