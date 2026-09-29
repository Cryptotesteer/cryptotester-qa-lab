# Banana Test Cases

## Test Suite
BANANA-001

## Product
Banana

## Tester
CryptoTester

---

# 1. Landing Page & Navigation

## TC-BANANA-001
### Title
Verify landing page loads correctly

**Feature:** Landing Page  
**Test Type:** Functional / Positive  
**Priority:** High

### Objective
Verify that the Banana landing page loads and displays the main product sections.

### Preconditions
- Internet connection available
- Banana URL accessible

### Steps
1. Open Banana.
2. Wait for the page to finish loading.
3. Review the landing page.
4. Scroll through the main sections.

### Expected Result
- Page loads without errors.
- Main content is visible.
- Navigation and primary calls-to-action are usable.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
[Add evidence]

---

## TC-BANANA-002
### Title
Verify main navigation links

**Feature:** Navigation  
**Test Type:** Functional / Positive  
**Priority:** High

### Steps
1. Open Banana.
2. Identify available navigation links.
3. Select each major section.
4. Confirm the correct destination opens.

### Expected Result
Each navigation link opens the intended section/page without errors.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
[Add evidence]

---

# 2. Account & Onboarding

## TC-BANANA-003
### Title
Create an account with valid information

**Feature:** Account / Sign Up  
**Test Type:** Functional / Positive  
**Priority:** High

### Steps
1. Open the Sign Up flow.
2. Enter valid required information.
3. Submit the registration form.
4. Observe the result.

### Expected Result
Account creation succeeds and the user is taken to the appropriate authenticated experience.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-004
### Title
Attempt account creation with missing required fields

**Feature:** Account / Sign Up  
**Test Type:** Negative  
**Priority:** Medium

### Steps
1. Open Sign Up.
2. Leave one or more required fields empty.
3. Submit the form.

### Expected Result
The system prevents submission and clearly identifies the missing information.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
[Add evidence]

---

## TC-BANANA-005
### Title
Verify authenticated session persists after refresh

**Feature:** Account / Session  
**Test Type:** Functional / Edge Case  
**Priority:** Medium

### Steps
1. Sign in.
2. Navigate to an authenticated page.
3. Refresh the browser.
4. Observe the account state.

### Expected Result
The session behaves according to the product's intended authentication design.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

# 3. Dashboard

## TC-BANANA-006
### Title
Verify dashboard loads for authenticated user

**Feature:** Dashboard  
**Test Type:** Functional / Positive  
**Priority:** High

### Steps
1. Sign in.
2. Open Dashboard.
3. Review the displayed information.

### Expected Result
Dashboard loads successfully and displays the user's available information without errors.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-007
### Title
Verify dashboard state after page refresh

**Feature:** Dashboard  
**Test Type:** Regression / Edge Case  
**Priority:** Medium

### Steps
1. Open Dashboard.
2. Record important displayed values/state.
3. Refresh the page.
4. Compare the state before and after refresh.

### Expected Result
Relevant user data remains accurate and consistent after refresh.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

# 4. Learn

## TC-BANANA-008
### Title
Browse available learning content

**Feature:** Learn  
**Test Type:** Functional / Positive  
**Priority:** Medium

### Steps
1. Open Learn.
2. Review available lessons.
3. Open a lesson.
4. Navigate through the content.

### Expected Result
Lessons are accessible and content displays correctly.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-009
### Title
Verify lesson navigation

**Feature:** Learn  
**Test Type:** Functional  
**Priority:** Medium

### Steps
1. Open a lesson.
2. Move between available lesson sections/screens.
3. Use available navigation controls.
4. Observe the result.

### Expected Result
Navigation works correctly and does not unexpectedly lose progress or state.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

# 5. Earn

## TC-BANANA-010
### Title
Browse earning opportunities

**Feature:** Earn  
**Test Type:** Functional / Positive  
**Priority:** Medium

### Steps
1. Open Earn.
2. Browse available opportunities.
3. Open an opportunity.
4. Review its details.

### Expected Result
Opportunities load correctly and their details are accessible.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-011
### Title
Verify Earn category/filter behaviour

**Feature:** Earn  
**Test Type:** Functional  
**Priority:** Medium

### Steps
1. Open Earn.
2. Identify available categories or filters.
3. Apply a filter.
4. Review the resulting opportunities.

### Expected Result
Displayed opportunities correspond to the selected filter/category.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

# 6. Market

## TC-BANANA-012
### Title
Browse Market products

**Feature:** Market  
**Test Type:** Functional / Positive  
**Priority:** High

### Steps
1. Open Market.
2. Browse available products.
3. Open a product.

### Expected Result
Products are displayed correctly and product details can be opened.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-013
### Title
Open creator store

**Feature:** Creator Store  
**Test Type:** Functional / Positive  
**Priority:** High

### Steps
1. Open Market.
2. Select a creator store.
3. Review the store.
4. Open one or more listed products.

### Expected Result
The creator store loads and its products are accessible.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-014
### Title
Initiate product purchase

**Feature:** Market / Checkout  
**Test Type:** Functional / Positive  
**Priority:** Critical

### Steps
1. Open a product.
2. Select Buy.
3. Review the checkout page.
4. Continue through the available checkout flow.

### Expected Result
The purchase flow progresses correctly and clearly communicates the current transaction/payment state.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
- Screenshot:
- Screen recording:
- Transaction/payment reference:

---

## TC-BANANA-015
### Title
Cancel or abandon checkout

**Feature:** Checkout  
**Test Type:** Negative / Edge Case  
**Priority:** High

### Steps
1. Start a product purchase.
2. Enter the checkout flow.
3. Exit or cancel before payment is completed.
4. Return to the product or Market.

### Expected Result
The purchase is not incorrectly recorded as completed and the user can safely continue browsing.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

# 7. Digital Wallet

## TC-BANANA-016
### Title
Verify Digital Wallet loads

**Feature:** Digital Wallet  
**Test Type:** Functional / Positive  
**Priority:** Critical

### Steps
1. Open Digital Wallet.
2. Review displayed balance and available actions.

### Expected Result
Wallet loads correctly and displays the appropriate balance/state.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-017
### Title
Verify Receive flow

**Feature:** Wallet / Receive  
**Test Type:** Functional  
**Priority:** High

### Steps
1. Open Digital Wallet.
2. Select Receive.
3. Review the displayed receiving information.
4. Verify the information can be used as intended.

### Expected Result
Receive flow provides accurate information and clear instructions.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
[Add evidence]

---

## TC-BANANA-018
### Title
Verify Send flow with valid transaction

**Feature:** Wallet / Send  
**Test Type:** Functional / Positive  
**Priority:** Critical

### Steps
1. Open Digital Wallet.
2. Select Send.
3. Enter a valid destination.
4. Enter a valid amount.
5. Review transaction details.
6. Confirm the transaction where applicable.

### Expected Result
The transaction proceeds correctly and the resulting wallet state is accurate.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
- Screenshot:
- Transaction hash:
- Block explorer:

---

## TC-BANANA-019
### Title
Attempt Send with insufficient balance

**Feature:** Wallet / Send  
**Test Type:** Negative  
**Priority:** Critical

### Steps
1. Open Send.
2. Enter a valid destination.
3. Enter an amount greater than the available balance.
4. Attempt to continue.

### Expected Result
The system prevents an invalid transaction and clearly explains the problem.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-020
### Title
Verify Cash Out flow

**Feature:** Wallet / Cash Out  
**Test Type:** Functional  
**Priority:** Critical

### Steps
1. Open Digital Wallet.
2. Select Cash Out.
3. Review available cash-out methods.
4. Select an available method.
5. Enter valid information.
6. Continue through the flow.

### Expected Result
Cash-out flow behaves correctly and clearly communicates the transaction/payment state.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

# 8. Negative & Edge-Case Tests

## TC-BANANA-021
### Title
Reject invalid amount

**Test Type:** Negative  
**Priority:** High

### Steps
1. Open a flow requiring an amount.
2. Enter zero.
3. Enter a negative value where possible.
4. Enter an invalid/non-numeric value where possible.
5. Attempt to continue.

### Expected Result
Invalid amounts are rejected with clear feedback.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-022
### Title
Test rapid repeated action

**Test Type:** Edge Case  
**Priority:** High

### Steps
1. Open a transaction or purchase action.
2. Rapidly click/tap the confirmation/action button multiple times.
3. Observe the result.

### Expected Result
The system prevents unintended duplicate actions or transactions.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-023
### Title
Refresh during an active flow

**Test Type:** Edge Case  
**Priority:** High

### Steps
1. Start an important flow.
2. Before completion, refresh the page.
3. Observe the resulting state.
4. Continue if possible.

### Expected Result
The system handles the interruption safely and does not create an incorrect or duplicate state.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

---

## TC-BANANA-024
### Title
Test rejected or cancelled transaction

**Test Type:** Negative  
**Priority:** Critical

### Steps
1. Start a transaction requiring wallet/payment confirmation.
2. Reject or cancel the action.
3. Return to Banana.
4. Observe the resulting state.

### Expected Result
The transaction is clearly shown as rejected/cancelled and no false success state is displayed.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
- Screenshot:
- Screen recording:
- Transaction hash if applicable:

---

# 9. Responsive / Mobile Testing

## TC-BANANA-025
### Title
Verify core flows on mobile viewport

**Test Type:** Functional / Non-functional  
**Priority:** High

### Steps
1. Open Banana on a mobile device.
2. Test navigation.
3. Test Market.
4. Test checkout.
5. Test Wallet.
6. Observe layout and interactions.

### Expected Result
Core functionality remains usable and important content is accessible without significant layout or interaction problems.

### Actual Result
[Record during testing]

### Status
[Pass / Fail / Blocked / Not Run]

### Evidence
[Add screenshots]

---

# Test Execution Notes

## Environment
- Device:
- OS:
- Browser:
- Wallet:
- Network:
- Date:

## Execution Summary

- Total planned:
- Executed:
- Passed:
- Failed:
- Blocked:
- Not Run:

## Findings Generated

- Bug IDs:
- UX findings:
- Observations:
- Recommendations:

## Notes

[Record important execution notes here.]
