# Banana - QA Test Plan

## 1. Document Information

Product: Banana

Tester: CryptoTester

Testing Type:
Functional Testing, Positive Testing, Negative Testing,
Edge-Case Testing, Exploratory Testing, Web3/Payment Testing and
UX/Product Testing

Status: Completed

Testing Environment:
Banana Web Application

Application:
https://banana-woad-kappa.vercel.app


## 2. Test Objective

The objective of this test plan is to evaluate Banana's major user
journeys and identify functional defects, usability issues,
transaction-related risks and product improvement opportunities.

The testing focuses on whether the application behaves as expected
under normal, invalid, boundary and exploratory conditions.

The assessment also considers Web3/payment-specific risks including
wallet behaviour, transaction states, balances, receipts and
transaction verification.


## 3. Scope

The following areas are included in the testing scope:

- Landing & Navigation
- Signup & Login
- Dashboard/Home
- Digital Wallet
- Learn
- Earn
- Market
- Creator Stores
- Checkout
- Send
- Receive
- Cash Out
- Transaction Activity
- Transaction Receipts
- Payment Flows
- Mobile/Responsive Behaviour
- Negative Testing
- Edge-Case Testing
- Exploratory Testing
- UX/Product Observations


## 4. Out of Scope

The following areas are outside the scope of this assessment:

- Full smart-contract security audit
- Unauthorized penetration testing
- Infrastructure/server security testing
- Source-code audit
- Backend architecture review
- Formal financial compliance assessment
- Load/stress testing
- Full accessibility certification
- Production security assessment


## 5. Testing Approach

### 5.1 Functional Testing

Verify that product features perform their intended functions.

Examples:

- Account creation
- Wallet creation
- Sending funds
- Cashing out
- Applying for opportunities
- Purchasing products
- Listing products


### 5.2 Positive Testing

Use valid inputs and expected user actions to verify successful
behaviour.

Examples:

- Valid account information
- Valid transactions
- Valid checkout
- Valid applications
- Valid cash-out


### 5.3 Negative Testing

Use invalid, incomplete or rejected conditions to determine whether
the application handles them safely and clearly.

Examples:

- Missing required fields
- Insufficient balance
- Invalid amounts
- Blank recipient
- Rejected transactions
- Abandoned checkout


### 5.4 Edge-Case Testing

Test unusual or boundary conditions that may expose unexpected
behaviour.

Examples:

- Zero transaction amount
- Very large transaction amount
- Repeated actions
- Refresh during/after a flow
- Unexpected recipient values
- Abandoned transactions


### 5.5 Exploratory Testing

Exploratory testing is used to investigate product behaviour beyond
the predefined test cases.

The exploratory process follows:

Prepare
→ Explore
→ Observe
→ Test
→ Record
→ Debrief

Exploratory testing is structured and timeboxed rather than random
clicking.


### 5.6 Web3/Payment Testing

Where applicable, testing includes:

- Wallet addresses
- Network/chain information
- Transactions
- Signatures
- Balances
- Fees
- Transaction status
- Failed/rejected transactions
- Transaction receipts
- Explorer verification
- Payment status
- Activity history
- Persistence after refresh


## 6. Key Risk Areas

The following areas receive additional attention because failures can
have significant user or financial impact:

### Account & Authentication

- Account creation
- Required-field validation
- Session persistence
- Logout/session handling


### Wallet

- Wallet creation
- Balance accuracy
- Send
- Receive
- Cash Out
- Activity
- Transaction receipts


### Payments

- Payment initiation
- Payment confirmation
- Payment failure
- Duplicate actions
- Payment state
- Product delivery


### Marketplace

- Product information
- Product purchase
- Checkout
- Digital-product delivery
- Purchase entitlement


### Web3 Transactions

- Transaction state
- Transaction hash
- Explorer verification
- Balance updates
- Failed/rejected transactions


## 7. Evidence Strategy

Evidence should be collected whenever a finding requires verification.

Possible evidence includes:

- Screenshots
- Short screen recordings
- Error messages
- Console/network information where appropriate
- Transaction hashes
- Explorer links
- Before/after states
- Timestamps

Sensitive information must never be included.

Do not upload:

- Private keys
- Seed phrases
- Passwords
- API secrets
- Confidential credentials
- Sensitive personal information


## 8. Entry Criteria

Testing can begin when:

- The application is accessible.
- Core pages can be loaded.
- A suitable test account is available.
- Required test data is available.
- Safe test conditions exist for financial/Web3 actions.


## 9. Exit Criteria

Testing can be considered complete when:

- Major user journeys have been tested.
- Positive scenarios have been tested.
- Negative scenarios have been tested.
- Relevant edge cases have been explored.
- Exploratory testing has been performed.
- Findings have been classified.
- Evidence has been recorded where available.
- Testing limitations have been documented.
- Retest recommendations have been identified.


## 10. Deliverables

The testing engagement produces:

1. Test Plan
2. Test Cases
3. Exploratory Session
4. Bug Reports
5. UX/Product Observations
6. Evidence Register
7. QA Report
8. Product Improvement Recommendations
9. QA Case Study


## 11. Classification Rules

Not every unusual behaviour is automatically classified as a defect.

A finding should be considered a confirmed defect when there is
sufficient evidence that the observed behaviour violates:

- A documented requirement
- Expected product behaviour
- Established product behaviour
- Or creates a clear, demonstrable quality risk

When the intended behaviour is unclear, the finding should instead be
documented as an:

- Observation
- Product question
- Potential risk
- UX recommendation

This prevents unsupported defect claims.


## 12. Severity and Priority

Severity describes the impact of a problem.

Priority describes how urgently the team should address it.

Severity levels used in this project:

- Blocker
- High
- Medium
- Low

Severity should be supported by the actual impact rather than simply
assuming that every Web3 issue is high severity.


## 13. Product Improvement Research

In addition to direct QA findings, product improvement recommendations
may be informed by:

- Actual Banana test results
- Web3 QA principles
- Payment UX patterns
- African fintech product patterns
- Stablecoin product patterns
- Marketplace UX patterns
- Competitive/product benchmark research

Benchmark research is used to identify useful product patterns and
improvement opportunities.

It is not treated as proof that Banana contains a defect.


## 14. Testing Limitations

This test plan applies to the environment and product state available
during the documented testing period.

The assessment does not represent:

- A security audit
- A penetration test
- A smart-contract audit
- A source-code review
- A complete assessment of Banana's backend infrastructure

Some behaviours may require product requirements or technical
documentation before they can be conclusively classified.


## 15. Final Principle

The testing process follows:

OBSERVE
→ QUESTION
→ TEST
→ REPRODUCE
→ COLLECT EVIDENCE
→ COMPARE EXPECTED VS ACTUAL
→ CLASSIFY
→ REPORT

The goal is not simply to find as many bugs as possible.

The goal is to provide reliable information about product quality,
risk, behaviour and improvement opportunities.
