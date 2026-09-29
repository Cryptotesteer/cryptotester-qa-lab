# Banana Test Plan

## Test Plan ID
TP-BANANA-001

## Product
Banana

## Product Version / Build
[Record deployment/version/date observed during testing]

## Tester
CryptoTester

## Test Objective
Evaluate Banana's core user journeys, functionality, usability, failure handling and Web3/payment-related flows through structured manual and exploratory testing.

The testing will focus on identifying reproducible defects, UX issues, unclear behaviour, edge cases and areas requiring further investigation.

## Scope

### In Scope

- Landing page and navigation
- Account creation and onboarding
- Dashboard
- Learn
- Earn
- Market
- Creator stores
- Product purchasing and checkout
- Digital Wallet
- Receive
- Send
- Cash out
- Payment and transaction states
- Wallet/network behaviour where applicable
- Mobile/responsive behaviour
- Error handling
- Boundary and edge cases
- Exploratory testing
- UX observations
- On-chain verification where applicable

### Out of Scope

- Full smart-contract security audit
- Penetration testing without authorization
- Infrastructure/server security testing
- Source-code review unless access is explicitly provided
- Testing production systems in ways that could cause financial loss
- Any activity requiring unauthorized access or exploitation

## Test Environment

- Device:
- OS:
- Browser:
- App/version:
- Network:
- Wallet:
- Account:
- Test environment:
- Date/time:
- Other relevant configuration:

## Preconditions

- Stable internet connection
- Test account where required
- Test wallet where required
- Sufficient test funds where required
- Required network selected
- Browser with wallet extension/mobile wallet available where applicable
- Permission to perform transactions or payment tests where applicable

## Key User Flows

### Flow 1 — Account / Onboarding
1. Open Banana
2. Explore the landing page
3. Create an account
4. Complete required onboarding
5. Access the dashboard

### Flow 2 — Dashboard
1. Open dashboard
2. Review displayed balances/activity
3. Navigate between dashboard sections
4. Test available actions
5. Refresh/reload
6. Check whether state remains correct

### Flow 3 — Learn
1. Open Learn
2. Browse available lessons
3. Open a lesson
4. Read/interact with the lesson
5. Navigate between lessons
6. Test completion/progress behaviour where available

### Flow 4 — Earn
1. Open Earn
2. Browse opportunities
3. Test filters/categories
4. Open an opportunity
5. Review details
6. Test available application/action flow

### Flow 5 — Market
1. Open Market
2. Browse products
3. Search/filter where available
4. Open a creator store
5. Open a product
6. Initiate purchase
7. Complete checkout
8. Verify resulting state

### Flow 6 — Digital Wallet
1. Open Digital Wallet
2. Review balance
3. Test Receive
4. Test Send
5. Test Cash out
6. Review activity
7. Verify transaction/state where applicable

### Flow 7 — Cross-Border Payment
1. Select a product
2. Initiate checkout
3. Enter required payment information
4. Test available payment method
5. Complete or reject payment
6. Verify checkout result
7. Verify creator/payment state where accessible
8. Verify on-chain information where applicable

## Test Approach

### Functional Testing

Verify that documented product features perform their intended functions.

### Positive Testing

Test valid inputs and normal user journeys.

Examples:

- Valid account information
- Valid product selection
- Valid payment
- Valid wallet action
- Valid amount
- Supported network

### Negative Testing

Test invalid inputs, rejected actions and failure conditions.

Examples:

- Invalid input
- Missing required field
- Rejected wallet signature
- Insufficient balance
- Insufficient gas
- Unsupported network
- Cancelled payment
- Failed transaction
- Duplicate action
- Expired or invalid session

### Edge-Case Testing

Test unusual but realistic conditions.

Examples:

- Minimum/maximum amounts
- Zero amount
- Very large amount
- Rapid repeated clicks
- Refresh during an operation
- Closing the page during a transaction
- Network switching during a flow
- Slow internet connection
- Mobile viewport
- Empty states
- Very long text/input
- Special characters
- Session expiration

### Exploratory Testing

Conduct structured exploratory sessions using a defined charter and timebox.

Exploration will be used to investigate areas where predefined test cases may not reveal unexpected behaviour.

### Regression Testing

If defects are fixed during the engagement, retest affected functionality and relevant surrounding flows.

## Risk Areas

- Account and authentication state
- Payment processing
- Checkout state
- Wallet balance accuracy
- Send/receive transactions
- Cash-out behaviour
- Transaction status
- Duplicate transactions/actions
- Network switching
- Failed or rejected transactions
- Incorrect financial information
- Cross-border settlement
- User confusion around payment/wallet states
- Data persistence after refresh or navigation

## Test Data

Record test data used during testing.

- Test account:
- Test wallet:
- Wallet address:
- Network:
- Token:
- Product:
- Purchase amount:
- Payment method:
- Cash-out method:
- Other:

**Do not record private keys, seed phrases, passwords or other secrets.**

## Evidence to Collect

- Screenshots
- Screen recordings
- Error messages
- Console evidence where relevant
- Network request evidence where relevant
- Transaction hashes
- Block explorer links
- Before/after state
- Relevant timestamps
- Reproduction attempts

## Entry Criteria

Testing can begin when:

- Banana is accessible
- Required test account is available
- Required wallet is available
- Required test funds are available where applicable
- Testing environment is recorded
- Product flows have been mapped

## Exit Criteria

Planned testing is considered complete when:

- Major in-scope user flows have been tested
- Positive scenarios have been covered
- Negative scenarios have been covered
- Relevant edge cases have been explored
- Exploratory testing sessions have been completed
- Findings have been documented
- Reproducible defects have supporting evidence
- Testing limitations have been recorded
- Required retesting has been completed or documented as pending

## Known Limitations

[Record limitations discovered during testing.]

Examples:

- Feature unavailable
- Test funds unavailable
- Payment provider unavailable
- Wallet/network unavailable
- Environment instability
- Feature requires founder/admin access
- Testing performed only on one device/browser

## Deliverables

- Banana test cases
- Exploratory testing session(s)
- Bug reports
- Testing summary
- Private QA report
- Public case study where permitted
- X/public documentation where appropriate

## Notes

All findings must be based on observed behaviour and supporting evidence.

A behaviour should not be classified as a defect unless there is a reasonable basis for the expected result, such as product documentation, stated requirements, established behaviour or clearly intended user flow.

Where expected behaviour is unclear, document the issue as an observation or ambiguity and investigate further.
