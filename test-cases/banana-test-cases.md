# Banana - Executed QA Test Cases

## Document Information

Product: Banana

Tester: CryptoTester

Testing Status: Completed

Testing Type:
Functional, Positive, Negative, Edge-Case, Exploratory,
Web3/Payment and UX Testing

Application:
https://banana-woad-kappa.vercel.app

---

# 1. Landing & Navigation

## TC-BANANA-001 — Landing Page Loads

Feature:
Landing Page

Type:
Functional / Positive

Priority:
High

Precondition:
Application is accessible.

Steps:
1. Open the Banana application.
2. Observe the landing page.

Expected:
The landing page should load correctly without major visual or
functional errors.

Actual:
The landing page loaded successfully.

Status:
PASS


## TC-BANANA-002 — Main Navigation

Feature:
Landing Page / Navigation

Type:
Functional / Positive

Priority:
High

Steps:
1. Open Banana.
2. Select Dashboard/Home.
3. Select Learn.
4. Select Earn.
5. Select Market.
6. Select Wallet.

Expected:
Each navigation option should take the user to the intended section.

Actual:
The main navigation sections were accessible and opened correctly.

Status:
PASS


## TC-BANANA-003 — Navigation Interaction Consistency

Feature:
Landing Page / Interactive Controls

Type:
Exploratory / UX

Priority:
Medium

Steps:
1. Interact with prominent buttons and controls on the landing page.
2. Observe whether the first click produces the expected response.

Expected:
Interactive controls should respond consistently to a single user
action.

Actual:
Some prominent controls were observed to require a second click before
responding.

Status:
OBSERVATION

Notes:
The behaviour was recorded as a UX/interaction observation rather than
a confirmed defect because standalone evidence could not be located for
the final report.


## TC-BANANA-004 — Learn Section Navigation

Feature:
Landing Page / Learn

Type:
Functional

Priority:
Medium

Steps:
1. Open the Learn section.
2. Select the available learning content.

Expected:
The user should be able to access the learning area.

Actual:
The Learn section was accessible and the lesson flows were
subsequently completed successfully.

Status:
PASS


# 2. Signup & Login

## TC-BANANA-005 — Valid Account Creation

Feature:
Signup

Type:
Functional / Positive

Priority:
High

Steps:
1. Open signup.
2. Enter a valid name.
3. Enter a valid email/phone value.
4. Continue.
5. Select Nigeria.
6. Complete account creation.

Expected:
The account should be created successfully.

Actual:
The account was created successfully and the authenticated area
became accessible.

Status:
PASS


## TC-BANANA-006 — Blank Name Validation

Feature:
Signup

Type:
Negative

Priority:
Medium

Steps:
1. Open signup.
2. Leave the name field empty.
3. Enter a valid Gmail address.
4. Continue.

Expected:
If the name is required, the user should be prevented from continuing.
If optional, the interface should clearly indicate that it is optional.

Actual:
Browser validation indicated that the name field was required, but
the flow could still proceed to country selection and account creation.

Status:
OBSERVATION

Notes:
The intended product requirement for the name field should be
confirmed before classifying this as a defect.


## TC-BANANA-007 — Country Selection

Feature:
Signup

Type:
Functional

Priority:
High

Steps:
1. Create an account.
2. Continue to country selection.
3. Select Nigeria.

Expected:
The selected country should be accepted and the user should continue.

Actual:
Nigeria could be selected and the account flow continued.

Status:
PASS


## TC-BANANA-008 — Session Persistence

Feature:
Authentication / Session

Type:
Functional / Exploratory

Priority:
High

Steps:
1. Create or access an authenticated account.
2. Navigate through the application.
3. Refresh the page.
4. Return to the application.

Expected:
The expected authenticated state should be maintained according to
the product's session design.

Actual:
Session/account state showed persistence in some flows, while refresh
and navigation behaviour produced inconsistent account-state
observations.

Status:
OBSERVATION


## TC-BANANA-009 — Logout Availability

Feature:
Authentication

Type:
Exploratory / UX

Priority:
Medium

Steps:
1. Access the authenticated account.
2. Inspect the account/profile controls.
3. Look for a visible logout/sign-out action.

Expected:
If users are expected to manually terminate their session, a clear
logout action should be available.

Actual:
No obvious Sign Out/Log Out control was identified during testing.

Status:
OBSERVATION


# 3. Dashboard / Home

## TC-BANANA-010 — Dashboard Loads

Feature:
Dashboard

Type:
Functional / Positive

Priority:
High

Steps:
1. Sign in to the application.
2. Open Dashboard/Home.

Expected:
Dashboard information should load correctly.

Actual:
Dashboard loaded and displayed financial summaries, spending
information, upcoming items, balances and savings goals.

Status:
PASS


## TC-BANANA-011 — Dashboard Navigation Links

Feature:
Dashboard

Type:
Functional

Priority:
Medium

Steps:
1. Open Dashboard.
2. Select Resume Lesson.
3. Select an Earn opportunity.
4. Select seller dashboard.

Expected:
Each available action should open its intended destination.

Actual:
The tested dashboard navigation actions worked.

Status:
PASS


## TC-BANANA-012 — Dashboard Summary Cards

Feature:
Dashboard

Type:
Exploratory / UX

Priority:
Low

Steps:
1. Inspect dashboard summary cards.
2. Attempt to interact with relevant cards.

Expected:
Interactive cards should provide a clear action or visual indication
if they are intended to be clickable.

Actual:
Several summary cards appeared informational rather than interactive.

Status:
OBSERVATION


# 4. Digital Wallet

## TC-BANANA-013 — Wallet Creation

Feature:
Wallet

Type:
Functional / Positive

Priority:
High

Steps:
1. Open the wallet area.
2. Select Create Digital Wallet.

Expected:
A digital wallet should be created successfully.

Actual:
The wallet opened successfully and displayed a wallet balance of
₦0 / approximately $0.00 USDC.

Status:
PASS


## TC-BANANA-014 — Wallet Persistence After Refresh

Feature:
Wallet

Type:
Functional / Regression

Priority:
High

Steps:
1. Create/access the wallet.
2. Refresh the page.
3. Reopen the wallet.

Expected:
Wallet state should remain available.

Actual:
Wallet state, balance and activity persisted after refresh.

Status:
PASS


## TC-BANANA-015 — Receive Address

Feature:
Wallet / Receive

Type:
Functional

Priority:
High

Steps:
1. Open Wallet.
2. Select Receive.
3. View Banana Tag.
4. Open advanced details.

Expected:
The user should be provided with the information required to receive
funds.

Actual:
A Banana Tag was displayed and advanced details exposed a wallet
address.

Status:
PASS


## TC-BANANA-016 — Receive Network/Asset Transparency

Feature:
Wallet / Receive

Type:
Exploratory / UX

Priority:
Medium

Steps:
1. Open Receive.
2. Inspect the advanced wallet details.
3. Check whether network and asset information are clearly displayed.

Expected:
Users should clearly understand the asset and network associated with
the receiving address.

Actual:
The wallet address was displayed, but network/asset context was not
prominent in the tested Receive interface.

Status:
OBSERVATION


## TC-BANANA-017 — Receive Demo

Feature:
Wallet / Receive

Type:
Functional

Priority:
Medium

Steps:
1. Open Wallet.
2. Use the "Demo: receive $12 from family" action.
3. Observe balance.
4. Observe Activity.
5. Refresh the wallet.

Expected:
The demo receive action should produce a visible simulated receive
state if the action is intended to demonstrate receiving funds.

Actual:
No balance update or Activity entry appeared. Refreshing the wallet did
not produce the simulated receive transaction.

Status:
FAIL

Finding:
Confirmed product behaviour requiring review.


## TC-BANANA-018 — Send With Insufficient Balance

Feature:
Wallet / Send

Type:
Negative

Priority:
High

Steps:
1. Open Send.
2. Enter an amount greater than the available balance.
3. Attempt to send.

Expected:
The transaction should be blocked.

Actual:
The transaction was blocked and an insufficient-balance message was
displayed.

Status:
PASS


## TC-BANANA-019 — Send Zero Amount

Feature:
Wallet / Send

Type:
Negative / Edge

Priority:
High

Steps:
1. Open Send.
2. Enter 0 as the amount.

Expected:
A zero-value transaction should not be submitted.

Actual:
The Send action remained disabled.

Status:
PASS


## TC-BANANA-020 — Send Blank Amount

Feature:
Wallet / Send

Type:
Negative

Priority:
High

Steps:
1. Open Send.
2. Leave amount empty.
3. Attempt to send.

Expected:
Send should remain unavailable.

Actual:
Send remained disabled.

Status:
PASS


## TC-BANANA-021 — Send Without Recipient

Feature:
Wallet / Send

Type:
Negative

Priority:
High

Steps:
1. Open Send.
2. Enter a valid amount.
3. Leave recipient empty.

Expected:
The transaction should not be submitted.

Actual:
Send remained disabled.

Status:
PASS


## TC-BANANA-022 — Successful Send

Feature:
Wallet / Send

Type:
Functional / Positive

Priority:
High

Steps:
1. Fund the wallet.
2. Open Send.
3. Select a valid recipient.
4. Enter ₦10,000.
5. Submit the transaction.
6. Open the receipt.
7. Check Activity.
8. Check wallet balance.

Expected:
The transaction should complete successfully, Activity should update,
and the wallet balance should decrease correctly.

Actual:
The transaction succeeded. Activity recorded the send, the balance was
reduced, and a transaction receipt was generated.

Status:
PASS


## TC-BANANA-023 — Very Large Send Amount

Feature:
Wallet / Send

Type:
Negative / Edge

Priority:
High

Steps:
1. Enter an amount significantly greater than the available balance.
2. Attempt to send.

Expected:
The transaction should be blocked.

Actual:
The transaction was blocked with an insufficient-balance message.

Status:
PASS


## TC-BANANA-024 — Arbitrary Recipient Value

Feature:
Wallet / Send

Type:
Exploratory / Risk

Priority:
High

Steps:
1. Open Send.
2. Enter an arbitrary recipient value such as "xyz123".
3. Enter a valid amount.
4. Submit the transaction.

Expected:
Behaviour depends on the product's recipient-resolution rules.

Actual:
The recipient value was accepted and the transaction was processed.

Status:
OBSERVATION / POTENTIAL RISK

Notes:
This behaviour is confirmed, but it is not classified as a confirmed
security defect because the intended recipient model requires product
clarification.

If unresolved identifiers are not intended to be valid recipients,
this behaviour should be reviewed as a high-risk validation issue.


## TC-BANANA-025 — Cash Out

Feature:
Wallet / Cash Out

Type:
Functional / Positive

Priority:
High

Steps:
1. Fund the wallet.
2. Open Cash Out.
3. Select GTBank.
4. Enter ₦100,000.
5. Confirm the cash-out.

Expected:
The cash-out should complete and the wallet balance should decrease.

Actual:
The cash-out completed successfully. The wallet balance decreased by
₦100,000 and Activity recorded the cash-out.

Status:
PASS


## TC-BANANA-026 — Cash Out Above Available Balance

Feature:
Wallet / Cash Out

Type:
Negative

Priority:
High

Steps:
1. Open Cash Out.
2. Enter an amount greater than the available balance.

Expected:
The transaction should be blocked.

Actual:
Amounts above the available balance were blocked.

Status:
PASS


## TC-BANANA-027 — Transaction Receipt

Feature:
Wallet / Transaction Receipt

Type:
Functional

Priority:
High

Steps:
1. Complete a transaction.
2. Open the transaction receipt.

Expected:
Receipt should show relevant transaction information.

Actual:
Receipts displayed transaction status, amount, timestamp and
transaction information.

Status:
PASS


## TC-BANANA-028 — View on Explorer

Feature:
Wallet / Transaction Receipt

Type:
Functional / Web3

Priority:
Medium

Steps:
1. Complete a transaction.
2. Open the transaction receipt.
3. Select "View on explorer".

Expected:
The relevant blockchain explorer should open.

Actual:
The action did not produce visible navigation to the explorer.

The behaviour was observed across multiple transaction receipts.

Status:
FAIL

Finding:
Confirmed defect.

Impact:
Users cannot use the provided explorer action to independently verify
the transaction.


# 5. Learn

## TC-BANANA-029 — Learn Page

Feature:
Learn

Type:
Functional / Positive

Priority:
Medium

Steps:
1. Open Learn.
2. Review available lessons.

Expected:
Lessons should be displayed and accessible.

Actual:
The Learn page loaded and lessons were displayed.

Status:
PASS


## TC-BANANA-030 — Complete Lessons

Feature:
Learn

Type:
Functional

Priority:
Medium

Steps:
1. Open each available lesson.
2. Complete the lesson.
3. Continue through the learning flow.

Expected:
Lessons should be completed and progress should update.

Actual:
All six tested lessons were completed successfully.

Lessons completed:

- What is inflation?
- How do I protect myself from scams?
- How does a stablecoin work?
- What's USDC?
- What's a wallet?
- What does gas mean?

Progress reached 6/6.

Status:
PASS


# 6. Earn

## TC-BANANA-031 — Earn Opportunities

Feature:
Earn

Type:
Functional / Positive

Priority:
High

Steps:
1. Open Earn.
2. Browse available opportunities.

Expected:
Available opportunities should load.

Actual:
Earn opportunities loaded successfully.

Status:
PASS


## TC-BANANA-032 — Earn Category Filters

Feature:
Earn

Type:
Functional

Priority:
Medium

Steps:
1. Open Earn.
2. Select All.
3. Select Bounties.
4. Select Hackathons.
5. Select Freelance.
6. Select Grants.

Expected:
The opportunity list should update according to the selected category.

Actual:
Filters worked correctly.

Observed counts:

All: 8
Bounties: 4
Hackathons: 1
Freelance: 2
Grants: 1

Status:
PASS


## TC-BANANA-033 — Bounty Submission

Feature:
Earn / Bounties

Type:
Functional

Priority:
High

Steps:
1. Open a bounty.
2. Start the bounty.
3. Submit work.
4. Complete the demo review/payment flow.

Expected:
The submission should be recorded and the resulting payment state
should be displayed.

Actual:
Bounty submission and demo payment flows worked.

Status:
PASS


## TC-BANANA-034 — Hackathon Application

Feature:
Earn / Hackathons

Type:
Functional

Priority:
High

Steps:
1. Open a hackathon.
2. Apply.
3. Submit the application.
4. Complete the demo review/payment flow.

Expected:
Application and resulting payment state should be recorded.

Actual:
Application was submitted and the demo payout completed. Wallet
balance and Activity reflected the payout.

Status:
PASS


## TC-BANANA-035 — Grant Application

Feature:
Earn / Grants

Type:
Functional

Priority:
High

Steps:
1. Open a grant.
2. Apply.
3. Submit the application.
4. Complete the demo payout flow.

Expected:
Application should be submitted and the payout should be recorded.

Actual:
The grant flow completed and the wallet/activity reflected the
payout.

Status:
PASS


## TC-BANANA-036 — Freelance Application

Feature:
Earn / Freelance

Type:
Functional

Priority:
High

Steps:
1. Open a freelance opportunity.
2. Apply.
3. Submit the application.
4. Complete the demo payment flow.

Expected:
Application and payment state should be recorded.

Actual:
The flow completed successfully and wallet/activity were updated.

Status:
PASS


# 7. Market

## TC-BANANA-037 — Market Browsing

Feature:
Market

Type:
Functional / Positive

Priority:
Medium

Steps:
1. Open Market.
2. Browse available products.

Expected:
Products should load correctly.

Actual:
Products loaded successfully.

Status:
PASS


## TC-BANANA-038 — Market Search and Filters

Feature:
Market

Type:
Functional

Priority:
Medium

Steps:
1. Open Market.
2. Search for products.
3. Apply category filters.

Expected:
Results should update according to the search/filter criteria.

Actual:
Search and category filtering worked.

Status:
PASS


## TC-BANANA-039 — Product Details

Feature:
Market

Type:
Functional

Priority:
Medium

Steps:
1. Open a product.
2. Review product information.

Expected:
Product information should be displayed correctly.

Actual:
Product details opened successfully.

Status:
PASS


## TC-BANANA-040 — Product Purchase

Feature:
Market / Checkout

Type:
Functional / Positive

Priority:
High

Steps:
1. Open a product.
2. Start checkout.
3. Complete payment.
4. Return to the product.

Expected:
Payment should complete and the product should become available.

Actual:
Payment completed and the product became unlocked.

Status:
PASS


## TC-BANANA-041 — Digital Product Delivery

Feature:
Market / Digital Product

Type:
Functional / Content Validation

Priority:
High

Steps:
1. Purchase the tested digital product.
2. Download the delivered file.
3. Compare the delivered content with the advertised product.

Expected:
The delivered file should contain the content advertised by the
product.

Actual:
The product advertised 12 redemption codes, but the downloaded file
contained instructions rather than the promised usable redemption
codes.

Status:
FAIL

Finding:
Confirmed product-content/delivery defect.

Impact:
A customer may pay for a digital product without receiving the
advertised content.


# 8. Creator Stores

## TC-BANANA-042 — List Product

Feature:
Creator Store

Type:
Functional / Positive

Priority:
High

Steps:
1. Open seller dashboard.
2. Create a product.
3. Enter product name.
4. Enter description.
5. Enter price.
6. Publish/list the product.

Expected:
The product should be listed and available in the store.

Actual:
The product was listed successfully and appeared on the product page.

Status:
PASS


## TC-BANANA-043 — Seller Payout Destination

Feature:
Creator Store

Type:
Functional

Priority:
Medium

Steps:
1. Open product listing/payout settings.
2. Review payout options.
3. Select available payout destinations.

Expected:
Available payout options should be displayed and selectable.

Actual:
USDC, NGN and Banana balance payout options were available and
worked during testing.

Status:
PASS


## TC-BANANA-044 — Store Sharing

Feature:
Creator Store

Type:
Functional

Priority:
Low

Steps:
1. Open the creator store.
2. Test Copy Link.
3. Test X sharing.
4. Test WhatsApp sharing.
5. Test Telegram sharing.

Expected:
Each sharing option should perform its intended action.

Actual:
The tested sharing options worked.

Status:
PASS


## TC-BANANA-045 — Seller Recent Sales

Feature:
Creator Store

Type:
Functional

Priority:
High

Steps:
1. Complete a test purchase.
2. Open the seller dashboard.
3. Review recent sales.

Expected:
The completed sale should appear in seller records.

Actual:
The completed purchase appeared in Recent Sales with settlement
information.

Status:
PASS


# 9. Checkout

## TC-BANANA-046 — Checkout Information

Feature:
Checkout

Type:
Functional / UX

Priority:
High

Steps:
1. Start checkout for a product.
2. Review the checkout screen.

Expected:
Product, price, payment method and final amount should be clear.

Actual:
Product name, price, email, payment method and final amount were
displayed.

Status:
PASS


## TC-BANANA-047 — Payment Method Switching

Feature:
Checkout

Type:
Functional

Priority:
Medium

Steps:
1. Start checkout.
2. Select Paystack.
3. Select MoMo.
4. Select Card.

Expected:
Available payment methods should switch correctly without unexpected
changes to the amount.

Actual:
Payment method switching worked and the amount remained consistent.

Status:
PASS


## TC-BANANA-048 — Abandoned Checkout

Feature:
Checkout

Type:
Negative

Priority:
High

Steps:
1. Start checkout.
2. Do not complete payment.
3. Exit/abandon checkout.
4. Return to the product.

Expected:
The product should not be incorrectly marked as purchased.

Actual:
The product was not incorrectly marked as paid/unlocked.

Status:
PASS


## TC-BANANA-049 — Existing Product Entitlement

Feature:
Market / Purchases

Type:
Functional / Edge

Priority:
High

Steps:
1. Purchase a digital product.
2. Return to the product later.
3. Attempt to access/download the previously purchased product without
making another purchase.

Expected:
A previously purchased product should remain accessible if the
platform provides persistent ownership/entitlement.

Actual:
The previous purchase was not clearly retained as an accessible
entitlement, and access required another purchase flow.

A second completed charge was not confirmed during testing.

Status:
FAIL / PRODUCT REQUIREMENT REVIEW

Finding:
Potential confirmed product-access/entitlement defect depending on
intended product requirements.


# 10. Transaction and Payment Consistency

## TC-BANANA-050 — Balance Updates After Transactions

Feature:
Wallet / Transactions

Type:
Functional / Regression

Priority:
High

Steps:
1. Complete an Earn payout.
2. Check wallet balance.
3. Complete a Send transaction.
4. Check wallet balance.
5. Complete a Cash Out.
6. Check wallet balance.

Expected:
Wallet balance should update consistently after each completed
transaction.

Actual:
Balances updated correctly during the tested successful payout,
Send and Cash Out flows.

Status:
PASS


## TC-BANANA-051 — Activity Updates

Feature:
Wallet / Activity

Type:
Functional

Priority:
High

Steps:
1. Complete a supported transaction.
2. Open Activity.
3. Review the latest transaction.

Expected:
The transaction should appear in Activity.

Actual:
Successful payouts, sends and cash-outs appeared in Activity.

Status:
PASS


## TC-BANANA-052 — Receipt Verification Path

Feature:
Transaction Receipts

Type:
Web3 / Exploratory

Priority:
Medium

Steps:
1. Complete a transaction.
2. Open the receipt.
3. Inspect transaction hash.
4. Attempt to use the explorer verification action.

Expected:
The user should have a functional path to verify the transaction.

Actual:
Transaction information and hashes were displayed, but the
"View on explorer" action did not open the explorer.

Status:
FAIL


# 11. Mobile / Responsive Testing

## TC-BANANA-053 — Mobile Navigation and Scrolling

Feature:
Mobile / Responsive

Type:
Functional / UX

Priority:
Medium

Steps:
1. Use Banana on a mobile viewport/device.
2. Navigate through major sections.
3. Scroll through content.

Expected:
Content should remain usable and navigable on mobile.

Actual:
Major scrolling and navigation flows were usable during testing.

Status:
PASS


## TC-BANANA-054 — Mobile Forms and Actions

Feature:
Mobile / Forms

Type:
Functional / UX

Priority:
High

Steps:
1. Use major forms on mobile.
2. Test wallet actions.
3. Test checkout actions.
4. Observe buttons and layouts.

Expected:
Forms, controls and actions should remain usable.

Actual:
The tested mobile forms, wallet actions, checkout interactions and
scrolling remained usable.

Status:
PASS


# 12. Test Result Summary

## PASS

The following major areas successfully completed their tested flows:

- Landing page loading
- Main navigation
- Account creation
- Country selection
- Dashboard
- Learn
- Six lesson completions
- Earn browsing
- Earn filtering
- Bounty submissions
- Hackathon application
- Grant application
- Freelance application
- Wallet creation
- Wallet persistence
- Valid Send
- Insufficient balance handling
- Zero amount handling
- Blank amount handling
- Blank recipient handling
- Cash Out
- Wallet Activity
- Market browsing
- Search/filtering
- Product checkout
- Payment method switching
- Abandoned checkout
- Creator product listing
- Seller payout options
- Store sharing
- Seller recent sales
- Mobile navigation
- Mobile forms/actions


## FAIL

The following tested scenarios produced confirmed or significant
issues:

- Receive demo produced no visible state change.
- View on Explorer action did not work.
- Advertised digital-product content did not match delivered content.
- Previously purchased digital-product access was not clearly retained.


## OBSERVATION / REVIEW

The following require product clarification or UX review:

- Some buttons required a second click.
- Signup name validation was inconsistent.
- Logout/session controls were not obvious.
- Wallet custody/security model was not clearly explained.
- Network/asset information could be clearer in Receive.
- Some Dashboard cards appeared informational rather than interactive.
- Arbitrary recipient value was accepted by Send.
- Buyer purchase history was not clearly available.


# 13. Testing Conclusion

The tested Banana application demonstrated that its major user journeys
are generally functional.

The strongest successful areas included:

- Learning
- Earn opportunities
- Wallet operations
- Send
- Cash Out
- Marketplace browsing
- Checkout
- Creator stores
- Seller-side sales visibility

The most important areas requiring attention are:

- Transaction verification
- Digital-product delivery
- Digital-product entitlement
- Receive simulation
- Recipient validation
- Session/navigation consistency
- Wallet transparency

These results form the basis for the Banana bug reports,
exploratory-testing record and final QA case study.

