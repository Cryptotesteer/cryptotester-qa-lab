# Banana - Exploratory Testing Session

## Session Information

Session ID:
BANANA-EXP-001

Product:
Banana

Tester:
CryptoTester

Application:
https://banana-woad-kappa.vercel.app

Testing Status:
Completed

Testing Type:
Structured Exploratory Testing

Timebox:
Multiple focused exploratory sessions conducted during the Banana QA
engagement.

---

# 1. Exploratory Testing Charter

Explore Banana's major user journeys with particular attention to
financial actions, wallet behaviour, transaction states, payment
flows, product access and unexpected user behaviour.

The purpose of the session was to discover issues that may not be
identified through predefined test cases alone.

---

# 2. Mission

Investigate whether Banana remains reliable when users:

- Navigate between different product areas.
- Provide incomplete or unusual input.
- Attempt financial actions with insufficient funds.
- Perform wallet transactions.
- Complete or abandon payments.
- Refresh after important actions.
- Interact with transaction receipts.
- Purchase digital products.
- Return to previously purchased products.
- Use unexpected recipient values.
- Move between Earn, Wallet, Market and Creator Store flows.

---

# 3. Scope

The exploratory investigation covered:

- Landing and navigation
- Signup and account state
- Dashboard
- Digital Wallet
- Send
- Receive
- Cash Out
- Transaction Activity
- Transaction Receipts
- Learn
- Earn
- Market
- Creator Stores
- Checkout
- Digital-product delivery
- Product entitlement
- Mobile interaction
- Error handling
- Edge cases
- State persistence

---

# 4. Out of Scope

The session did not include:

- Unauthorized penetration testing
- Smart-contract auditing
- Source-code review
- Infrastructure security testing
- Load/stress testing
- Credential attacks
- Attempts to access other users' private information
- Destructive production testing

---

# 5. Test Ideas

The following ideas were used to guide exploration.

## Navigation

- Test main navigation.
- Test prominent interactive controls.
- Observe URL/hash changes.
- Test navigation after authentication.
- Refresh during different application states.

## Account

- Test valid signup.
- Test missing information.
- Test country selection.
- Observe session persistence.
- Look for logout/session controls.

## Wallet

- Create wallet.
- Receive funds.
- Send funds.
- Test insufficient balance.
- Test zero amount.
- Test blank amount.
- Test blank recipient.
- Test unusually large amounts.
- Test unusual recipient values.
- Refresh after transactions.
- Inspect transaction Activity.
- Inspect receipts.
- Test explorer verification.

## Earn

- Browse opportunities.
- Filter opportunities.
- Submit applications.
- Complete available demo review/payment flows.
- Verify wallet payout.
- Verify Activity.

## Market

- Browse products.
- Search/filter.
- Open product details.
- Purchase product.
- Complete checkout.
- Download digital product.
- Compare delivered content with advertised content.
- Return to previously purchased product.

## Creator Store

- List product.
- Review product details.
- Test payout options.
- Share store.
- Verify seller sales records.

## Checkout

- Review displayed price.
- Review payment method.
- Switch payment methods.
- Abandon checkout.
- Complete payment.
- Verify product access.


# 6. Exploratory Observations

## Observation 1 — Interaction Consistency

Some prominent interactive controls were observed to require a second
click before responding.

Classification:
UX/interaction observation.

Note:
This was recorded during testing, but a standalone screenshot or
recording could not be located for the final evidence set.


## Observation 2 — Signup Validation

The name field appeared to be treated as required by browser
validation, but the flow could still proceed without a name.

Classification:
Potential validation inconsistency.

Requirement clarification is needed before classifying this as a
confirmed defect.


## Observation 3 — Session/Logout

No obvious Sign Out/Log Out control was identified in the tested
account interface.

Classification:
UX/session-management observation.


## Observation 4 — Wallet Transparency

Wallet creation did not visibly explain the wallet's custody or
recovery model.

Classification:
Product/security-transparency observation.


## Observation 5 — Receive Information

The Receive flow exposed a wallet address, but network/asset context
was not prominent in the tested interface.

Classification:
UX/transparency observation.


## Observation 6 — Dashboard Cards

Some dashboard summary cards appeared informational rather than
interactive.

Classification:
UX observation.


## Observation 7 — Buyer Purchase History

A clear buyer-side purchase history area was not identified during
testing.

Classification:
Product/UX observation.


# 7. Exploratory Findings

## Finding 1 — Receive Demo Produces No Visible State Change

Action:

The "Demo: receive $12 from family" action was triggered.

Expected:

A visible simulated receive result if the action is intended to
demonstrate receiving funds.

Observed:

- Wallet balance did not change.
- Activity did not receive a corresponding entry.
- Refreshing the wallet did not reveal the transaction.

Classification:
Confirmed defect.

Severity:
Medium.

Related Test Case:
TC-BANANA-017


## Finding 2 — Transaction Explorer Link Does Not Work

Action:

Completed transaction receipts were opened and "View on explorer"
was selected.

Expected:

The relevant blockchain explorer should open.

Observed:

The action produced no visible navigation.

The behaviour was observed across multiple receipts, including:

- Send
- Cash Out
- Earn payout
- Grant payout
- Freelance payout

Classification:
Confirmed defect.

Severity:
Medium.

Related Test Cases:
TC-BANANA-028
TC-BANANA-052


## Finding 3 — Digital Product Content Mismatch

Action:

A digital product was purchased and the downloaded file was inspected.

Expected:

The delivered file should contain the content advertised on the
product page.

Observed:

The product advertised 12 redemption codes, while the downloaded
file contained instructions rather than the promised usable codes.

Classification:
Confirmed product-content/delivery defect.

Severity:
High.

Related Test Case:
TC-BANANA-041


## Finding 4 — Digital Product Entitlement

Action:

A previously purchased digital product was accessed again later.

Expected:

If Banana provides persistent purchase ownership, the customer should
retain access to the purchased product.

Observed:

The previous purchase was not clearly retained as an accessible
entitlement and access required another purchase flow.

A second completed charge was not confirmed.

Classification:
Product-access issue requiring requirement confirmation.

Severity:
Medium/High depending on intended product behaviour.

Related Test Case:
TC-BANANA-049


## Finding 5 — Recipient Validation Behaviour

Action:

An arbitrary recipient value such as "xyz123" was entered into the
Send flow.

Expected:

The correct behaviour depends on Banana's recipient-resolution model.

Observed:

The value was accepted and the transaction was processed.

Classification:
Potential high-risk validation issue requiring product clarification.

Important:

This is not classified as a confirmed security vulnerability because
the intended recipient model was not available during testing.

Related Test Case:
TC-BANANA-024


# 8. Successful Exploratory Areas

Exploration also confirmed several successful behaviours.

The following were observed to work during the session:

- Main navigation
- Account creation
- Country selection
- Dashboard loading
- Lesson completion
- Earn filtering
- Earn applications
- Demo payouts
- Wallet creation
- Wallet persistence
- Successful Send
- Insufficient-balance handling
- Zero-amount handling
- Blank-amount handling
- Blank-recipient handling
- Cash Out
- Wallet Activity
- Marketplace browsing
- Search/filtering
- Checkout
- Payment method switching
- Abandoned checkout
- Product listing
- Seller sales visibility
- Store sharing
- Mobile navigation
- Mobile forms and actions


# 9. Evidence

Evidence associated with the exploratory session should be mapped to
the available screenshots, recordings and transaction information.

Suggested evidence IDs:

- EV-001 — Landing/navigation interaction
- EV-002 — Signup validation
- EV-003 — Wallet creation
- EV-004 — Receive details
- EV-005 — Receive demo result
- EV-006 — Successful Send
- EV-007 — Insufficient balance
- EV-008 — Cash-out receipt
- EV-009 — Explorer-link failure
- EV-010 — Earn payout
- EV-011 — Grant payout
- EV-012 — Marketplace product
- EV-013 — Downloaded digital-product file
- EV-014 — Creator store listing
- EV-015 — Seller recent sales
- EV-016 — Checkout
- EV-017 — Product entitlement behaviour

Only evidence that can actually be produced should be attached to the
final report.


# 10. Blockers

No major blocker prevented completion of the overall Banana exploratory
testing engagement.

Some individual actions did not produce the expected result, but
alternative testing paths remained available.


# 11. Coverage

The exploratory session covered the following major product areas:

| Area | Explored |
|------|----------|
| Landing & Navigation | Yes |
| Signup & Login | Yes |
| Dashboard | Yes |
| Wallet | Yes |
| Send | Yes |
| Receive | Yes |
| Cash Out | Yes |
| Learn | Yes |
| Earn | Yes |
| Market | Yes |
| Creator Stores | Yes |
| Checkout | Yes |
| Payment flows | Yes |
| Transaction receipts | Yes |
| Mobile interaction | Yes |
| Negative scenarios | Yes |
| Edge cases | Yes |
| State persistence | Yes |


# 12. Debrief

## What Worked Well

Banana's major user journeys were generally usable and several
important financial and marketplace flows completed successfully.

Particularly successful areas included:

- Learn completion
- Earn opportunity discovery
- Earn application flows
- Wallet creation
- Successful Send
- Cash Out
- Marketplace checkout
- Creator product listing
- Seller sales visibility


## What Required Attention

The most important issues discovered during exploration involved:

- Transaction verification
- Digital-product delivery
- Digital-product entitlement
- Receive simulation
- Recipient validation
- Session/navigation consistency
- Wallet transparency


## What Was Learned

The testing demonstrated the importance of testing beyond the happy
path.

Several issues were not simply discovered by asking whether a feature
worked.

They required questions such as:

- What happens if the balance is insufficient?
- What happens if the amount is zero?
- What happens if the recipient is unusual?
- What happens after refreshing?
- Can a user verify a transaction?
- What happens after purchasing a digital product?
- Can the customer access that product later?
- Does the delivered content actually match the product description?


# 13. Product Improvement Opportunities

The exploratory findings also identified opportunities to improve the
product.

Recommended areas include:

- Make transaction verification reliable.
- Improve wallet custody/security explanations.
- Improve recipient confirmation before financial actions.
- Provide clearer payment and transaction states.
- Improve purchase history and entitlement.
- Improve digital-product delivery validation.
- Provide clearer error and recovery paths.
- Make fees, rates and final amounts transparent.
- Improve transaction receipts.
- Improve support/recovery after failed financial actions.


# 14. Follow-Up / Retest

The following areas should be retested after fixes:

1. Receive demo behaviour.
2. Transaction explorer links.
3. Digital-product content delivery.
4. Digital-product entitlement.
5. Recipient validation.
6. Signup validation.
7. Session/logout behaviour.
8. Wallet information transparency.

Regression testing should also confirm that fixes do not affect:

- Wallet balances
- Send
- Cash Out
- Earn payouts
- Marketplace checkout
- Product access
- Seller settlement
- Transaction Activity


# 15. Exploratory Session Conclusion

The exploratory testing session successfully expanded coverage beyond
the predefined test cases.

The session identified confirmed defects, potential risks and UX
observations while also confirming that many core Banana workflows
functioned successfully.

The findings from this session were carried forward into:

- Banana bug reports
- Banana QA report
- Product improvement recommendations
- Banana GitHub case study

---

End of Exploratory Testing Session
