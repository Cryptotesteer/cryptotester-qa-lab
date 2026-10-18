# Mako Market - Test Cases

**Prepared by:** CryptoTester  
**Product:** Mako Market  
**Application:** https://makomarket.xyz  
**Testing Type:** Manual Functional, Positive, Negative, Exploratory, Web3, and UX Testing  
**Testing Period:** October 2026

---

## 1. Purpose

This document records the test scenarios I executed while evaluating Mako Market.

Each test case describes the feature under test, the actions performed, the expected behaviour where established, the actual behaviour observed, and the resulting status.

I distinguish successful tests from observations, potential risks, and scenarios that require additional validation.

### Status Definitions

- **PASS:** The tested behaviour worked as expected.
- **OBSERVATION:** Behaviour was observed that may warrant a product improvement or clarification.
- **NEEDS INVESTIGATION:** The available evidence is insufficient to establish whether the behaviour is incorrect.
- **NOT FULLY TESTED:** The complete scenario has not been validated.
- **FAIL:** The observed behaviour demonstrably contradicts an established requirement.

A test is not marked FAIL merely because its behaviour is unusual.

---

## 2. Onboarding and Navigation

### TC-001: Review onboarding information

**Objective:** Understand the features presented to new users.

**Steps:**
1. Open the application.
2. Review the onboarding tour.
3. Record the features and explanations presented.

**Expected Result:** The tour explains the main features and helps users understand the application.

**Actual Result:** The tour introduced YES/NO markets, upcoming BTC rounds, market categories, pool creation, leaderboards, user positions, and test USDC funding.

**Status:** PASS — Information reviewed.

---

### TC-002: Review market categories

**Objective:** Examine market discovery and category navigation.

**Steps:**
1. Open the market listing.
2. Review the available categories.
3. Select different categories.
4. Observe the displayed markets and empty states.

**Expected Result:** The application displays markets associated with the selected category and communicates empty states clearly.

**Actual Result:** The listing displayed 17 open pools and 91 USDC in play during the observed session. Categories displayed different numbers of markets, and some categories showed empty states.

**Status:** OBSERVATION — Category counts and listing consistency require further validation.

---

## 3. Prediction Market Details

### TC-003: Inspect a football prediction market

**Objective:** Evaluate market rules and outcome descriptions.

**Steps:**
1. Open the Chelsea versus Everton market.
2. Review the YES and NO descriptions.
3. Inspect the betting deadline.
4. Review settlement timing and refund conditions.
5. Identify the stated resolution source.

**Expected Result:** The rules clearly explain the outcomes, deadlines, resolution source, and refund conditions.

**Actual Result:** YES represented an away-team win. NO represented a draw or home-team win. The rules described the betting deadline, settlement timing, postponement/cancellation refunds, and football-data.org as the resolution source.

**Status:** PASS — The documented rules were available for inspection.

**Limitation:** This test did not independently validate the eventual match settlement.

---

### TC-004: Inspect a BTC price prediction market

**Objective:** Examine price conditions and settlement rules.

**Steps:**
1. Open the BTC price prediction market.
2. Inspect the target price.
3. Review the YES and NO conditions.
4. Inspect betting and settlement deadlines.
5. Review the stated price source and refund conditions.

**Expected Result:** The market explains the target price, outcome conditions, deadlines, price source, and refund process.

**Actual Result:** The rules described a BTC/USD target of $80,000, a closing-price condition, betting and settlement times, refund conditions, and Chainlink Data Streams as the stated price source.

**Status:** PASS — The rules were available for inspection.

**Limitation:** The underlying price feed and eventual settlement were not independently validated in this test.

---

### TC-005: Review betting deadlines and countdowns

**Objective:** Compare the market title and countdown information.

**Steps:**
1. Open a market displaying a closing duration.
2. Compare the duration stated in the title with the countdown.
3. Repeat the observation on another market.

**Expected Result:** The time information is consistent or clearly explains the different time references.

**Actual Result:** Some titles and countdown displays appeared to show different remaining durations.

**Status:** NEEDS INVESTIGATION.

**Recommendation:** Clarify whether each display refers to betting closure, market closure, or settlement.

---

## 4. Betting and Payouts

### TC-006: Inspect YES and NO payout estimates

**Objective:** Verify that the displayed payout estimate responds to the selected outcome and stake.

**Steps:**
1. Open the Chelsea versus Everton market.
2. Select YES.
3. Enter a 1 USDC stake.
4. Record the payout estimate.
5. Select NO.
6. Record the payout estimate.
7. Change the stake and observe the preview.

**Expected Result:** The interface updates the displayed estimate according to the selected outcome and amount.

**Actual Result:** A 1 USDC YES selection displayed an estimated payout of 1.13 USDC. A 1 USDC NO selection displayed an estimated payout of 5.89 USDC. The preview also changed when the amount was changed.

**Status:** PASS — The displayed preview responded to the tested selections.

**Limitation:** The estimates were not independently recalculated or verified against final settlement.

---

### TC-007: Place a YES bet

**Objective:** Verify a selected betting flow and the resulting account state.

**Steps:**
1. Open the Chelsea versus Everton market.
2. Select YES.
3. Enter a 5 USDC stake.
4. Complete the requested authentication step.
5. Submit the bet.
6. Inspect the confirmation and account balance.
7. Review the active position.

**Expected Result:** A successful bet produces confirmation and updates the relevant account information.

**Actual Result:** The application confirmed the bet. The displayed balance became 15 USDC, and the position showed a 5 USDC stake with an estimated payout of 5.57 USDC.

**Status:** PASS — The documented bet was reflected in the account view.

---

### TC-008: Inspect repeated bets on the same market

**Objective:** Examine how repeated bets are represented in the account area.

**Steps:**
1. Place additional bets on the same market.
2. Use different outcome selections where applicable.
3. Open the account's active positions.
4. Compare the displayed position summaries.

**Expected Result:** The account accurately represents the user's exposure and provides enough detail to understand individual transactions.

**Actual Result:** Repeated bets were displayed as combined YES and NO positions rather than separate visible entries for each bet. The displayed summaries showed a combined 6 USDC YES position and a 2 USDC NO position.

**Status:** OBSERVATION.

**Recommendation:** Provide an individual betting history showing each bet's amount, outcome, timestamp, and status, alongside the combined position summary.

---

### TC-009: Review betting authentication prompts

**Objective:** Observe authentication requirements during betting.

**Steps:**
1. Complete a betting action requiring authentication.
2. Continue testing other betting actions.
3. Observe whether additional authentication is requested.

**Expected Result:** Authentication behaviour follows the application's intended verification policy.

**Actual Result:** Authentication prompts appeared during some actions, while a later betting action appeared to proceed without the same prompt.

**Status:** NEEDS INVESTIGATION.

**Limitation:** The observations do not establish whether this behaviour violated the intended authentication policy.

---

## 5. Wallet and Test USDC Funding

### TC-010: Copy and compare the wallet address

**Objective:** Check the wallet address displayed in the receive interface.

**Steps:**
1. Open the receive interface.
2. Copy the wallet address.
3. Compare the copied value with the displayed address.

**Expected Result:** The copied address matches the displayed wallet address.

**Actual Result:** The copied address matched the displayed address.

**Status:** PASS.

---

### TC-011: Receive test USDC

**Objective:** Examine the test funding flow and displayed balance update.

**Steps:**
1. Open the receive interface.
2. Select the test USDC funding option.
3. Follow the Circle faucet flow on Monad Testnet.
4. Enter the required wallet information.
5. Submit the faucet request.
6. Review the faucet confirmation.
7. Return to Mako Market.
8. Check the displayed balance.

**Expected Result:** The funding process provides confirmation, and the application reflects the received test funds.

**Actual Result:** The faucet confirmed that 20 test USDC had been sent and provided a Monad Explorer transaction link. The Mako Market balance subsequently updated to 20 USDC.

**Status:** PASS — The documented funding flow completed.

**Limitation:** This test does not establish that all wallet transactions or funding scenarios work.

---

### TC-012: Validate an empty recipient

**Objective:** Examine recipient validation in the Send interface.

**Steps:**
1. Open Send.
2. Leave the recipient field empty.
3. Attempt to proceed to the review step.

**Expected Result:** The application prevents an invalid recipient from proceeding and explains the required correction.

**Actual Result:** The interface displayed a validation message requesting a valid 0x address.

**Status:** PASS — Validation feedback was displayed.

---

### TC-013: Validate decimal precision

**Objective:** Examine how the Send interface handles amounts exceeding its accepted decimal precision.

**Steps:**
1. Open Send.
2. Enter an amount with more than six decimal places.
3. Observe the validation response.
4. Enter an amount using six decimal places.
5. Observe the response.

**Expected Result:** The interface clearly communicates its accepted amount precision.

**Actual Result:** An amount using more than six decimal places produced a maximum-six-decimal-places validation message. An amount of 0.000001 USDC was accepted by the precision check, although the balance warning remained.

**Status:** PASS — The documented precision validation behaved as described.

**Limitation:** This test did not submit a send transaction.

---

### TC-014: Validate an amount exceeding the available balance

**Objective:** Examine insufficient-balance handling.

**Steps:**
1. Open Send.
2. Enter an amount exceeding the available balance.
3. Observe the application's response.

**Expected Result:** The interface prevents the user from proceeding with an unsupported amount and explains the balance restriction.

**Actual Result:** The application displayed a balance warning.

**Status:** PASS — A warning was displayed.

**Limitation:** No transaction was submitted during this test.

---

## 6. BTC Rounds

### TC-015: Examine round outcome controls

**Objective:** Check the available UP/DOWN selections.

**Steps:**
1. Open BTC Rounds.
2. Review the displayed round information.
3. Select DOWN.
4. Observe the displayed stake and payout estimate.

**Expected Result:** The selected outcome and payout preview are displayed clearly.

**Actual Result:** The DOWN selection could be made, and the displayed payout estimate remained 0.14 USDC for a 0.15 USDC stake.

**Status:** PASS — The tested selection and preview were displayed.

**Limitation:** The payout calculation was not independently verified.

---

### TC-016: Examine minimum stake validation

**Objective:** Check the minimum permitted stake.

**Steps:**
1. Open a round.
2. Enter 0.05 USDC.
3. Observe the prediction button.
4. Change the amount to 0.10 USDC.
5. Observe the prediction button again.

**Expected Result:** The application prevents submission below the minimum and enables the action when the minimum is met.

**Actual Result:** The prediction button was disabled at 0.05 USDC and enabled at 0.10 USDC.

**Status:** PASS — The documented minimum-stake interaction behaved as expected.

**Limitation:** No prediction was submitted during this specific test.

---

### TC-017: Examine market chart timeframe persistence

**Objective:** Observe whether the selected timeframe persists after refreshing a cryptocurrency market.

**Steps:**
1. Open a cryptocurrency market chart.
2. Select a timeframe other than 1H.
3. Refresh the page.
4. Observe the selected timeframe.
5. Repeat on another cryptocurrency market.

**Expected Result:** The chart follows its intended timeframe persistence behaviour.

**Actual Result:** The chart returned to 1H after refresh, including after selecting other timeframes on multiple cryptocurrency markets.

**Status:** OBSERVATION.

**Recommendation:** Consider preserving the selected timeframe when the user refreshes or revisits the market.

---

### TC-018: Examine BTC price-data freshness

**Objective:** Record a potential price-refresh concern.

**Steps:**
1. Observe the displayed BTC price.
2. Compare screenshots taken at different times.
3. Record whether the displayed value appears to change.

**Expected Result:** The price display reflects sufficiently current data according to the product's intended update frequency.

**Actual Result:** The displayed BTC price appeared to change very little across screenshots taken several hours apart.

**Status:** NEEDS INVESTIGATION.

**Limitation:** The observation does not prove that the price feed was stale.

**Recommendation:** Display a last-updated timestamp and an appropriate stale-data warning.

---

## 7. Comments and Replies

### TC-019: Publish a comment and reply

**Objective:** Examine comment and reply interactions.

**Steps:**
1. Open a market's comment section.
2. Publish a comment.
3. Reply to a comment.
4. Observe the displayed content.

**Expected Result:** The submitted comment and reply appear in the appropriate conversation.

**Actual Result:** The tested comment and reply interactions worked.

**Status:** PASS.

---

### TC-020: Delete a comment or reply

**Objective:** Examine the deletion interaction.

**Steps:**
1. Open a comment or reply owned by the user.
2. Initiate deletion.
3. Observe the interface response.
4. Check whether the content disappears.

**Expected Result:** The content is deleted according to the application's intended behaviour, with clear feedback.

**Actual Result:** The interface displayed a deleting state before the content disappeared. No visible confirmation step was observed in the tested interaction.

**Status:** OBSERVATION.

**Recommendation:** Consider a confirmation or undo option to reduce accidental deletion.

---

### TC-021: Check display-name persistence

**Objective:** Verify that the updated display name remains visible after refresh.

**Steps:**
1. Change the display name to Cryptoblinks.
2. Publish or inspect a comment.
3. Refresh the application.
4. Check the displayed name.

**Expected Result:** The updated display name remains visible where the application uses it.

**Actual Result:** The updated name appeared in comments and persisted after refresh.

**Status:** PASS.

---

## 8. Leaderboard

### TC-022: Test leaderboard time-range filters

**Objective:** Observe the available time-range filters.

**Steps:**
1. Open the leaderboard.
2. Select Last 7 days.
3. Record the displayed ranking information.
4. Select Last 30 days.
5. Select All time.
6. Compare the displayed rankings and profit figures.

**Expected Result:** The displayed leaderboard reflects the selected time range.

**Actual Result:** Rankings, ordering, and profit figures changed across the tested time ranges.

**Status:** PASS — The documented time-range interactions produced visible changes.

---

### TC-023: Examine Pools and All markets filters

**Objective:** Observe the behaviour of the market-type filters.

**Steps:**
1. Open the leaderboard.
2. Select Pools.
3. Select All markets.
4. Compare the visible information.

**Expected Result:** Each filter displays the corresponding intended dataset.

**Actual Result:** No visible difference was observed in the view examined.

**Status:** NEEDS INVESTIGATION.

**Limitation:** The intended filter behaviour and dataset differences require clarification before a defect can be confirmed.

---

## 9. Market Sharing

### TC-024: Copy and open a market link

**Objective:** Verify that the copy-link action produces a link to the intended market.

**Steps:**
1. Open a market.
2. Open the share interface.
3. Select Copy link.
4. Open the copied link.
5. Verify the destination.

**Expected Result:** The copied link opens the intended market.

**Actual Result:** The copied link opened the correct market.

**Status:** PASS.

---

## 10. Market Intel

### TC-025: Test Market Intel category filters

**Objective:** Examine category filtering in Market Intel.

**Steps:**
1. Open Market Intel.
2. Select Crypto.
3. Observe the displayed news.
4. Select NBA.
5. Observe the displayed news.
6. Open a news card.

**Expected Result:** The interface displays relevant content for the selected category, and available news links open their destinations.

**Actual Result:** Crypto and NBA displayed category-related news during the observed session. News cards opened external websites.

**Status:** PASS — The tested interactions worked.

**Limitation:** This test did not validate the completeness or accuracy of all news content.

---

## 11. Test Coverage Limitations

The test cases above document selected scenarios that I actually exercised.

The following areas have not been established as comprehensively validated:

- Every wallet send and receive scenario.
- Successful on-chain betting transaction verification.
- All market settlement outcomes.
- All cancellation and refund scenarios.
- Every authentication edge case.
- All chart data-update conditions.
- Every Rounds payout and settlement scenario.
- All possible leaderboard datasets.
- All external news-link destinations.
- Smart-contract security and economic correctness.

These limitations must be considered when interpreting the results.

---

## 12. Summary

The documented tests covered market navigation, prediction rules, betting, wallet funding, BTC Rounds, comments, leaderboards, sharing, and Market Intel.

Several tested flows worked as expected. Other behaviours were recorded as observations or areas requiring investigation.

The most important follow-up areas include chart timeframe persistence, price-data freshness, market timing clarity, individual bet history, authentication consistency, and leaderboard filter behaviour.

The findings in this document should be read alongside the Mako Market QA case study, test plan, exploratory session notes, and individual finding reports.

---

**Prepared by CryptoTester**

**QA Portfolio:** https://github.com/Cryptotesteer/cryptotester-qa-lab

**Product:** https://makomarket.xyz
