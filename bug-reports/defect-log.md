# Defect & Bug Tracking Log

### Bug ID: BUG-PH-102
- **Module:** Dispensing & Order Invoicing
- **Title:** Order discount field accepts negative numerical values, incorrectly inflating total order amount
- **Severity:** High
- **Priority:** P1 (Urgent)
- **Environment:** Chrome v128 / Windows 11 / Local Staging (React + ASP.NET Core API)

#### Steps to Reproduce:
1. Navigate to the "Dispense Medicine / Create Invoice" screen.
2. Add any prescription item to the active bill (e.g., unit price: 100 EGP).
3. In the "Discount %" input field, type `-10`.
4. Click "Calculate Total" or proceed to confirm order.

#### Results:
- **Expected Result:** Input validation fires immediately, displaying: "Discount percentage must be between 0% and 100%", preventing form submission.
- **Actual Result:** The negative value is evaluated as a mathematical addition, increasing the total invoice price to 110 EGP.

#### Status:
- **Status:** Verified Fixed & Closed (Server-side model validation and client-side boundary checks applied).
