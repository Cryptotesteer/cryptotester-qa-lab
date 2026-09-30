# BUG-004 — Previously Purchased Digital Product Is Not Retained as an Accessible Entitlement

## Bug Information

Bug ID:
BUG-004

Product:
Banana

Feature:
Market / Digital Product Access

Testing Type:
Functional / Edge-Case / Product UX

Severity:
Medium

Priority:
High

Status:
Open

Reproducibility:
Observed during testing


## Title

Previously purchased digital product does not remain clearly accessible
after the initial purchase.


## Environment

Product:
Banana

Application:
https://banana-woad-kappa.vercel.app

Tester:
CryptoTester


## Preconditions

- User has successfully purchased a digital product.
- The purchase completed successfully.
- The product became available after purchase.


## Test Scenario

Verify that a customer who has already purchased a digital product can
identify and access their existing purchase without being required to
purchase the same product again.


## Steps to Reproduce

1. Open Banana Market.
2. Open a digital product.
3. Complete the product purchase.
4. Confirm that the product becomes available after purchase.
5. Leave the product.
6. Return to the product later.
7. Attempt to access the previously purchased product without starting
   another purchase.


## Expected Result

If Banana provides persistent ownership of purchased digital products,
the customer should be able to access the previously purchased product
without being required to purchase it again.

The product should clearly indicate that it has already been purchased
and provide an appropriate access/download action.


## Actual Result

The previous purchase was not clearly retained as an accessible
entitlement.

When returning to the product, access was not preserved in a way that
allowed the customer to download the previously purchased product
without entering another purchase flow.


## Important Testing Note

A second completed charge was NOT confirmed during testing.

Therefore, this report does not claim that Banana charged the customer
twice.

The finding concerns the absence of clearly retained purchase
entitlement/access.


## Impact

If this behaviour reflects the intended production architecture, a
customer may have difficulty accessing a digital product they have
already purchased.

Potential consequences include:

- Customer confusion
- Repeated purchase attempts
- Increased support requests
- Loss of confidence in purchase records
- Difficulty recovering previously purchased digital products


## Evidence

Suggested evidence:

- EV-017 — Product entitlement behaviour
- Screenshot of the original successful purchase/unlocked state
- Screenshot showing the later product state
- Relevant order/purchase information if available


## Severity Rationale

Severity: Medium

The initial purchase can complete successfully, and a second completed
charge was not confirmed.

However, persistent access to purchased digital goods is an important
part of the customer experience and should be clearly handled.


## Recommended Fix

Banana should implement or expose a clear purchase-entitlement model
for digital products.

Recommended behaviour:

1. Record the completed purchase against the customer's account.
2. Store the relevant product/order entitlement.
3. Display a clear "Purchased" or equivalent state.
4. Provide access/download without requiring another purchase.
5. Provide a buyer-side purchase history.
6. Allow customers to recover previously purchased digital products.
7. Ensure the entitlement remains available after refresh and
   subsequent sessions.


## Retest

After the fix:

1. Purchase a digital product.
2. Confirm the product becomes available.
3. Leave the product page.
4. Return to the product.
5. Confirm the product shows a purchased state.
6. Download/access the product without another purchase.
7. Refresh the application.
8. Repeat the access attempt.
9. Confirm the entitlement remains available.
10. Verify that a new purchase is not incorrectly required.


## Related Product Improvement

A dedicated buyer purchase-history page would also improve the
experience.

A useful purchase-history record could include:

- Product name
- Seller
- Purchase date
- Order/reference number
- Amount paid
- Payment method
- Current access status
- Download/access action
- Receipt


## Notes

This finding should be reviewed against Banana's intended product
requirements and entitlement architecture.

The report does not claim a duplicate charge occurred.

This is a product QA finding and not a security-audit conclusion.
