# Test Cases Specification: Pharmacy System

### TC-PH-01: Expiry Date Validation
- **Module:** Inventory Management
- **Preconditions:** Logged in with valid staff credentials (`Pharmacist` / `Admin`).
- **Steps:**
  1. Open the "Add New Drug" form.
  2. Input valid medicine name, category, and unit price.
  3. Select an expiration date prior to current system date.
  4. Click "Save Medicine".
- **Expected Result:** Form submission is blocked with validation error: "Expiry date must be a future date."
- **Status:** PASS

---

### TC-PH-02: Quantity Boundary Check at Dispensing / Sales
- **Module:** Medicine Dispensing & Sales
- **Preconditions:** Available stock for selected drug = 5 units.
- **Steps:**
  1. Select the drug into the active dispensing order.
  2. Enter quantity value as `6`.
  3. Attempt to confirm and process the order.
- **Expected Result:** Order processing blocked with alert: "Requested quantity exceeds available stock (5 remaining)."
- **Status:** PASS

---

### TC-PH-03: Role-Based Access Control (RBAC) & Privileged Operations
- **Module:** Security & User Management
- **Preconditions:** User session active with role `Pharmacist` (non-administrative).
- **Steps:**
  1. Attempt to navigate directly to `/admin/manage-users` or call the user-deletion endpoint via API.
  2. Attempt to permanently purge an existing drug record from the master catalog.
- **Expected Result:** Operation blocked with HTTP `403 Forbidden`; UI redirects to unauthorized access warning.
- **Status:** PASS

---

### TC-PH-04: API Authentication & JWT Expiration
- **Module:** Backend API (Authentication)
- **Preconditions:** Registered user account exists in SQL database.
- **Steps:**
  1. Send `POST` request to `/api/auth/login` with valid credentials.
  2. Capture the returned Bearer Token.
  3. Send request to a protected endpoint `/api/inventory` using an expired/tampered token.
- **Expected Result:** Step 1 returns HTTP `200 OK` with valid JWT; Step 3 immediately rejects with HTTP `401 Unauthorized`.
- **Status:** PASS
