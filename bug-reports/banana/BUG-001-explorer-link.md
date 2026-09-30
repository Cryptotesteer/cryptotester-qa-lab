# BUG-001 — Transaction Explorer Link Does Not Open

## Bug Information

Bug ID:
BUG-001

Product:
Banana

Feature:
Wallet / Transaction Receipts

Testing Type:
Functional / Web3

Severity:
Medium

Priority:
Medium

Status:
Open

Reproducibility:
Consistent during tested transaction receipts


## Title

Transaction "View on explorer" action does not open the transaction
explorer.


## Environment

Product:
Banana

Application:
https://banana-woad-kappa.vercel.app

Environment:
Banana test/demo environment

Tester:
CryptoTester


## Preconditions

- A completed transaction exists.
- The transaction has a receipt.
- The receipt displays a "View on explorer" action.


## Test Scenario

Verify that a user can use the transaction receipt to open the
corresponding blockchain explorer and independently verify the
transaction.


## Steps to Reproduce

1. Open Banana.
2. Open Wallet.
3. Open a completed transaction.
4. Open the transaction receipt.
5. Locate "View on explorer".
6. Select "View on explorer".


## Expected Result

The relevant blockchain explorer page should open and allow the user
to independently verify the transaction.


## Actual Result

Selecting "View on explorer" did not produce visible navigation to the
blockchain explorer.


## Reproducibility

The behaviour was observed across multiple transaction receipts,
including:

- Send transaction
- Cash-out transaction
- Earn payout
- Grant payout
- Freelance payout


## Impact

Users cannot use the provided explorer action to independently verify
their transactions.

For a financial/Web3 product, transaction verification is an important
trust and transparency feature.


## Evidence

Suggested evidence reference:

- EV-009 — Explorer-link failure

Only attach evidence that can actually be produced.


## Severity Rationale

Severity: Medium

The underlying transaction can still complete, so the issue does not
block the core transaction flow.

However, it affects an important Web3 transparency and verification
function.


## Recommended Fix

Review the explorer-link generation and navigation behaviour.

The application should:

1. Generate the correct explorer URL.
2. Use the correct network/explorer.
3. Ensure the link is actually clickable.
4. Open the relevant transaction page.
5. Handle missing explorer information clearly.


## Retest

After the fix:

1. Complete a Send transaction.
2. Open the receipt.
3. Select "View on explorer".
4. Confirm the correct explorer opens.
5. Confirm the transaction hash matches.
6. Repeat with Cash Out.
7. Repeat with Earn-related payouts.
8. Verify other transaction types.


## Notes

This finding is based on behaviour observed during the documented
testing period.

It is a product QA finding and not a security-audit conclusion.
