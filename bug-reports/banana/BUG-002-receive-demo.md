# BUG-002 — Receive Demo Produces No Visible Transaction

## Bug Information

Bug ID:
BUG-002

Product:
Banana

Feature:
Digital Wallet / Receive

Testing Type:
Functional / Exploratory

Severity:
Medium

Priority:
Medium

Status:
Open

Reproducibility:
Reproduced during testing


## Title

"Demo: receive $12 from family" produces no visible wallet or
transaction state change.


## Environment

Product:
Banana

Application:
https://banana-woad-kappa.vercel.app

Tester:
CryptoTester


## Preconditions

- User has access to the Banana Digital Wallet.
- Receive functionality is available.
- The wallet is accessible.


## Test Scenario

Verify that the Receive demo action produces the expected simulated
receive result.


## Steps to Reproduce

1. Open Banana.
2. Open Digital Wallet.
3. Select Receive.
4. Use the "Demo: receive $12 from family" action.
5. Check the wallet balance.
6. Check Activity.
7. Refresh the wallet.
8. Check the balance and Activity again.


## Expected Result

If the action is intended to simulate receiving $12, the application
should provide a visible result.

For example:

- Wallet balance should update.
- A receive transaction should appear in Activity.
- The user should receive clear confirmation that the demo action was
  completed.

The exact expected behaviour should follow Banana's intended demo
design.


## Actual Result

No visible state change occurred.

Observed behaviour:

- Wallet balance did not increase.
- No corresponding Activity entry appeared.
- Refreshing the wallet did not reveal a simulated transaction.


## Impact

The action gives the user no visible confirmation that it performed
anything.

If this is intended to demonstrate the Receive functionality, the
current behaviour may confuse users and makes the demonstration
ineffective.

If the button is not intended to change wallet state, the interface
should clearly communicate what the action is supposed to demonstrate.


## Evidence

Suggested evidence reference:

- EV-005 — Receive demo result

Only attach evidence that can actually be produced.


## Severity Rationale

Severity: Medium

The issue does not prevent real wallet transactions from functioning.

However, it affects a wallet demonstration flow and provides no useful
feedback after the user performs the action.


## Recommended Fix

Clarify the intended behaviour of the Receive demo.

If it is intended to simulate a transaction:

1. Update the simulated wallet balance.
2. Create a corresponding Activity entry.
3. Display a clear success state.
4. Make the simulated transaction distinguishable from a real
   transaction.

If it is only an educational demonstration:

1. Clearly explain what the action does.
2. Provide visible feedback after activation.
3. Avoid making the control appear to perform a real receive.


## Retest

After the fix:

1. Open Receive.
2. Trigger the demo action.
3. Verify the expected balance/state change.
4. Verify Activity.
5. Refresh the wallet.
6. Confirm the expected state remains consistent.
7. Confirm real Receive functionality is not affected.


## Notes

This finding is based on observed behaviour during the documented
Banana QA testing period.

It is a product QA finding and not a security-audit conclusion.
