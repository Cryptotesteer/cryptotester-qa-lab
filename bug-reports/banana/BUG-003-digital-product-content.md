# BUG-003 — Digital Product Content Does Not Match Advertisement

## Bug Information

Bug ID:
BUG-003

Product:
Banana

Feature:
Market / Digital Product Delivery

Testing Type:
Functional / Content Validation

Severity:
High

Priority:
High

Status:
Open

Reproducibility:
Confirmed during testing


## Title

Purchased digital product does not contain the content advertised on
the product page.


## Environment

Product:
Banana

Application:
https://banana-woad-kappa.vercel.app

Tester:
CryptoTester


## Preconditions

- A digital product is available for purchase.
- The product description advertises specific deliverable content.
- The user can complete the purchase and download the product.


## Test Scenario

Verify that the digital product delivered after purchase matches the
content advertised to the customer.


## Steps to Reproduce

1. Open Banana.
2. Navigate to Market.
3. Open the tested digital product.
4. Review the advertised product contents.
5. Complete the purchase.
6. Download the delivered file.
7. Open and inspect the downloaded file.
8. Compare the delivered content with the product description.


## Expected Result

The downloaded product should contain the content advertised on the
product page.

If the product advertises 12 usable redemption codes, the downloaded
file should contain the 12 usable redemption codes or the exact
deliverable described to the customer.


## Actual Result

The product advertised 12 redemption codes.

After purchase, the downloaded file contained instructions but did not
contain the advertised usable redemption codes.


## Impact

This can result in a customer paying for a digital product without
receiving the advertised content.

Potential impact includes:

- Customer dissatisfaction
- Loss of trust
- Refund/support requests
- Seller reputation damage
- Incorrect product expectations
- Possible financial loss to customers


## Evidence

Suggested evidence:

- EV-013 — Downloaded digital-product file
- Screenshot of the product page showing the advertised contents
- Screenshot or copy of the downloaded file contents

Only attach evidence that can actually be produced.


## Severity Rationale

Severity: High

The issue affects a paid product and results in a mismatch between the
advertised deliverable and the content received by the customer.

The underlying checkout/payment process can complete successfully, but
the customer may not receive the purchased content.


## Recommended Fix

The product delivery system should ensure that the delivered file
matches the product listing.

Recommended controls:

1. Validate uploaded digital-product files before publication.
2. Compare advertised product metadata with the actual deliverable.
3. Provide sellers with a preview of the final customer download.
4. Validate that required product content exists before listing.
5. Allow sellers to replace incorrect files.
6. Consider automated checks for digital-product completeness where
   practical.


## Retest

After the fix:

1. Open the product page.
2. Confirm the advertised deliverable.
3. Purchase the product using an approved test account.
4. Download the file.
5. Inspect the complete file contents.
6. Compare the delivered content with the advertisement.
7. Confirm that all promised content is present and usable.


## Notes

This is a confirmed product-content/delivery defect based on the
downloaded product observed during testing.

It is not a security-audit finding.
