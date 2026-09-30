# Banana — Web3 Product QA Case Study

## Overview

Banana is an Africa-focused digital financial and commerce platform
combining financial education, earning opportunities, digital wallet
functionality, marketplace features and creator stores.

I conducted a structured QA assessment of the Banana web application as
an independent QA tester.

The assessment focused on real user journeys, financial actions,
Web3/payment behaviour, negative scenarios, edge cases, exploratory
testing and product usability.

---

# 1. My Role

Role:
Independent QA Tester

Tester:
CryptoTester

Testing Focus:

- Manual QA
- Functional testing
- Exploratory testing
- Positive testing
- Negative testing
- Edge-case testing
- Web3/payment testing
- UX/product analysis
- Defect documentation
- Product improvement recommendations

---

# 2. Product Under Test

Product:
Banana

Application:
https://banana-woad-kappa.vercel.app

Product areas tested:

- Landing & Navigation
- Signup & Login
- Dashboard
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
- Digital Product Delivery
- Purchase Access/Entitlement
- Mobile interaction

---

# 3. Testing Objective

The main objective was to determine how Banana behaves across normal,
invalid, boundary and exploratory user conditions.

The testing was designed to answer questions such as:

- Can users complete the main journeys successfully?
- Are invalid actions handled safely?
- Are financial balances updated correctly?
- Are transaction states communicated clearly?
- Can users verify blockchain transactions?
- Are purchased digital products delivered correctly?
- Can customers access products they have already purchased?
- What happens when users provide unexpected input?
- Are important financial actions understandable?
- Where can the product experience be improved?

---

# 4. Testing Methodology

The testing followed a structured QA workflow:

```text
PRODUCT TYPE
      ↓
SCOPE
      ↓
RISK
      ↓
TEST SCENARIOS
      ↓
POSITIVE TESTING
      ↓
NEGATIVE TESTING
      ↓
EDGE-CASE TESTING
      ↓
EXPLORATORY TESTING
      ↓
EVIDENCE
      ↓
DEFECT / OBSERVATION / UX CLASSIFICATION
      ↓
SEVERITY & PRIORITY
      ↓
REPORT
      ↓
PRODUCT IMPROVEMENT


# 5. Test Coverage

## Landing & Navigation

Tested:

- Landing page loading
- Main navigation
- Interactive controls
- Learn navigation
- Navigation consistency
- Section transitions

Result:

Major navigation flows were functional.

An interaction inconsistency was observed where some prominent controls
appeared to require a second click before responding. This was retained
as an observation rather than a confirmed defect because standalone
evidence could not be located for the final report.


## Signup & Login

Tested:

- Account creation
- Name validation
- Email/phone flow
- Country selection
- Session behaviour
- Account state
- Logout visibility

Result:

Account creation and country selection worked.

A validation inconsistency was observed around the name field, and
logout/session-management behaviour required further product
clarification.


## Dashboard

Tested:

- Dashboard loading
- Financial summaries
- Spending information
- Upcoming items
- Wallet information
- Savings information
- Dashboard navigation

Result:

Dashboard loaded successfully and the tested navigation actions
worked.

Some dashboard cards appeared informational rather than interactive.


## Digital Wallet

Tested:

- Wallet creation
- Wallet persistence
- Receive
- Send
- Cash Out
- Insufficient balance
- Zero amount
- Blank amount
- Blank recipient
- Unusual recipient
- Transaction Activity
- Transaction receipts
- Explorer verification

Result:

Core wallet functionality generally worked.

Successful Send and Cash Out flows correctly updated the wallet and
Activity.

Several important findings were discovered around Receive demo
behaviour, transaction verification and recipient validation.


## Learn

Tested all six available lessons:

1. What is inflation?
2. How do I protect myself from scams?
3. How does a stablecoin work?
4. What's USDC?
5. What's a wallet?
6. What does gas mean?

Result:

All six lessons were successfully completed and progress reached 6/6.


## Earn

Tested:

- Opportunity browsing
- Category filtering
- Bounties
- Hackathons
- Freelance
- Grants
- Applications
- Submission
- Demo review/payment
- Wallet payout
- Activity

Result:

The tested Earn flows worked successfully.

The wallet correctly reflected tested payouts and corresponding
Activity records appeared.


## Market

Tested:

- Product browsing
- Search
- Category filtering
- Product details
- Checkout
- Payment
- Product unlocking
- Digital-product download
- Existing purchase access

Result:

The main marketplace and checkout flow worked.

Testing of digital-product delivery and entitlement identified
important product issues.


## Creator Stores

Tested:

- Product creation
- Product listing
- Product details
- Payout options
- Store sharing
- Seller recent sales

Result:

The tested creator-store flows worked successfully.

Seller-side sales visibility was confirmed after a completed test
purchase.


# 6. Key Defects

Four main issues were documented as individual bug reports.

## BUG-001 — Transaction Explorer Link Does Not Open

Area:
Wallet / Transaction Receipts

Severity:
Medium

The "View on explorer" action did not open the relevant blockchain
explorer.

The behaviour was observed across multiple transaction receipts.

Impact:

Users cannot use the provided action to independently verify their
transactions.

Recommendation:

Ensure the correct explorer URL is generated and that the action
actually opens the relevant transaction page.


## BUG-002 — Receive Demo Produces No Visible Transaction

Area:
Wallet / Receive

Severity:
Medium

The "Demo: receive $12 from family" action produced no visible wallet
balance or Activity change.

Impact:

The action provides no meaningful feedback if it is intended to
demonstrate the Receive flow.

Recommendation:

Either make the demo produce a clear simulated transaction state or
clearly explain that the action is educational and does not modify
wallet state.


## BUG-003 — Digital Product Content Does Not Match Advertisement

Area:
Market / Digital Product Delivery

Severity:
High

A digital product advertised 12 redemption codes.

After purchase, the downloaded file contained instructions rather than
the promised usable redemption codes.

Impact:

Customers may pay for a digital product without receiving the
advertised content.

Recommendation:

Validate digital-product files before publication and provide sellers
with a final customer-download preview.


## BUG-004 — Previously Purchased Product Access

Area:
Market / Digital Product Entitlement

Severity:
Medium

A previously purchased digital product was not clearly retained as an
accessible entitlement when the user returned to the product.

A second completed charge was not confirmed.

Impact:

Customers may be unable to easily recover products they have already
purchased.

Recommendation:

Introduce persistent purchase entitlements and a buyer-side purchase
history.


# 7. Potential Risk Requiring Product Clarification

## Recipient Validation

During exploratory testing, an arbitrary recipient value such as
"xyz123" was accepted and the transaction was processed.

This behaviour was documented as a potential high-risk validation issue.

It was deliberately NOT classified as a confirmed security
vulnerability because the intended recipient-resolution model was not
available during testing.

The product team should clarify:

- What formats are valid recipients?
- How are recipients resolved?
- Should unknown identifiers be rejected?
- Should the recipient's name be displayed before confirmation?
- Should the user confirm the final recipient before authorization?

This should be retested against the confirmed product requirements.


# 8. What Worked Well

The assessment also identified many successful areas.

Successful tested flows included:

- Main navigation
- Account creation
- Country selection
- Dashboard
- Lesson completion
- Earn opportunity filtering
- Earn applications
- Demo payouts
- Wallet creation
- Wallet persistence
- Successful Send
- Insufficient-balance handling
- Zero-amount handling
- Blank-field handling
- Cash Out
- Wallet Activity
- Marketplace browsing
- Search/filtering
- Checkout
- Payment-method switching
- Abandoned checkout
- Creator product listing
- Seller payout options
- Store sharing
- Seller recent sales
- Mobile navigation
- Mobile forms/actions

The purpose of the assessment was not simply to find problems.

Successful behaviour was documented alongside defects so that the
results represent the product more accurately.


# 9. Product Improvement Research

In addition to direct QA findings, I reviewed relevant Web3, fintech,
payment, marketplace and stablecoin product patterns to identify areas
where Banana could potentially improve.

The benchmark research was used as a product-quality reference.

It was not used as proof that a Banana behaviour was a bug.


# 10. Product Improvement Recommendations

## 10.1 Improve Transaction Verification

Every completed financial transaction should provide a reliable path
to verification.

Recommended receipt information:

- Transaction status
- Amount
- Asset
- Network
- Transaction hash
- Explorer link
- Timestamp
- Relevant fee information

The explorer link should be tested for every supported transaction
type.


## 10.2 Improve Wallet Transparency

Users should clearly understand:

- What type of wallet they have
- Who controls the wallet
- Whether the wallet is custodial or non-custodial
- How recovery works
- Which assets are supported
- Which networks are supported

This is especially important for users who may be new to Web3.


## 10.3 Strengthen Recipient Confirmation

Before a financial transaction is authorized, Banana should make the
final recipient clear.

A useful confirmation step could display:

Recipient:
Name / Identifier

Amount:
₦10,000

Fee:
₦X

You send:
₦10,000

Recipient receives:
₦X

Network:
[Network]

[Confirm Send]

This reduces the chance of users sending funds to the wrong
destination.


## 10.4 Improve Payment and Transaction States

Financial products benefit from clearly named states.

For example:

Payment Started
→ Payment Processing
→ Payment Confirmed
→ Payment Completed

For failed transactions:

Payment Failed

Reason:
Insufficient balance

Next step:
Add funds and try again

Users should not be left wondering whether a payment actually
completed.


## 10.5 Add Buyer Purchase History

A buyer-side purchase history would improve the Market experience.

Useful information could include:

- Product
- Seller
- Order/reference number
- Purchase date
- Amount
- Payment method
- Status
- Download/access button
- Receipt

This would also make digital-product entitlement easier to understand.


## 10.6 Strengthen Digital Product Delivery

For creator-sold digital products, Banana should consider validating
the actual deliverable before allowing publication.

Possible workflow:

Seller uploads product
→ Banana validates file
→ Seller previews customer download
→ Seller confirms contents
→ Product goes live

This could reduce cases where the listing promises content that the
customer does not receive.


## 10.7 Improve Error Recovery

Error messages should explain:

1. What happened
2. Why it happened
3. What the user should do next

Example:

Transaction failed

Your balance is not enough for this transaction.

Available:
₦25,000

Required:
₦30,000

Next step:
Add ₦5,000 or reduce the amount.


## 10.8 Make Important Financial Information More Visible

For financial actions, users should be able to understand:

- Amount
- Currency
- Fee
- Exchange rate where applicable
- Final amount received
- Processing time
- Destination
- Status
- Limits
- Supported methods

This is particularly important for Send, Cash Out and checkout.


## 10.9 Contextual Education

Banana already contains a learning section.

The education layer could also be connected to relevant financial
actions.

For example:

When a new user opens a wallet:

> What's a wallet?

When a user prepares a blockchain transaction:

> What's gas?

When a user receives stablecoins:

> What's USDC?

This can reduce the gap between learning and performing the action.


## 10.10 Mobile-First Financial UX

Financial actions should remain especially easy to use on mobile.

Important actions should be:

- Easy to reach
- Easy to read
- Clearly labelled
- Large enough to tap
- Clear about amounts
- Clear about confirmation
- Clear about success/failure


# 11. Suggested Product Priority Areas

Based on the observed findings and benchmark research, the following
areas should receive focused product attention.

## Transaction Trust

- Reliable explorer links
- Clear receipts
- Transaction hashes
- Status visibility
- Recipient confirmation

## Digital Commerce

- Persistent purchase entitlements
- Buyer purchase history
- Accurate digital-product delivery
- Order/reference tracking

## Wallet Experience

- Clear wallet model
- Asset/network transparency
- Better transaction explanations
- Clear recovery/support paths

## Payment Experience

- Clear fees
- Clear final amount
- Clear processing states
- Better failure recovery

## User Education

- Contextual explanations
- Beginner-friendly financial terminology
- Education directly connected to financial actions


# 12. QA Lessons From the Engagement

This engagement demonstrated several important QA principles.

## Happy-path testing is not enough.

A flow can work correctly when everything is valid while still having
important problems under unusual conditions.

## Financial products require state verification.

A success message alone is not enough.

The tester should verify:

- Balance
- Activity
- Receipt
- Transaction information
- Explorer verification where applicable

## Product requirements matter.

An unusual behaviour should not automatically become a bug.

Where intended behaviour is unclear, the correct approach is to
document the observation and request clarification.

## Evidence matters.

A professional defect report should allow another person to
understand and reproduce the finding.

## QA can contribute to product improvement.

Testing can identify not only defects but also opportunities to improve:

- Trust
- Transparency
- Usability
- Recovery
- Product architecture
- Customer experience


# 13. Testing Limitations

This assessment was performed against the Banana environment available
during the documented testing period.

The assessment does not represent:

- A smart-contract audit
- A penetration test
- A full security audit
- A source-code audit
- An infrastructure security assessment
- A compliance assessment
- A load/stress test

Some behaviours require confirmation of Banana's internal product
requirements before they can be definitively classified.


# 14. Documentation

The Banana QA engagement is documented in this repository through:

- [Banana Test Plan](../test-plans/banana-test-plan.md)
- [Banana Executed Test Cases](../test-cases/banana-test-cases.md)
- [Banana Exploratory Session](../exploratory-sessions/banana-exploratory-session.md)
- [Banana Bug Reports](../bug-reports/banana/)


# 15. Final Summary

The Banana assessment covered the application's major financial,
educational, earning, marketplace and creator-commerce journeys.

The majority of core tested flows were functional.

The assessment identified four documented product issues involving:

1. Transaction explorer verification
2. Receive demo behaviour
3. Digital-product delivery
4. Digital-product entitlement

Additional observations were documented around:

- Recipient validation
- Wallet transparency
- Session/logout behaviour
- Signup validation
- Dashboard interaction
- Purchase history
- Network/asset transparency

The assessment also produced product improvement recommendations
covering transaction trust, wallet transparency, payments, digital
commerce, user education and mobile UX.

The goal of the engagement was not simply to produce a list of bugs.

It was to provide evidence-based information that can help a product
team understand:

- What works
- What fails
- What is uncertain
- What carries risk
- What can be improved
- What should be retested


## Tester

**CryptoTester**

Web3 Product QA  
Manual Testing • Exploratory Testing • Web3 QA • Product Testing
