# Mako Market - Observation and Investigation Report

## 1. Report Information

- **Product:** Mako Market
- **Website:** https://makomarket.xyz
- **Tester:** CryptoTester (@CryptoTesteer)
- **Testing type:** Manual exploratory testing
- **Report status:** Open — investigation required
- **Testing period:** October 2026

## 2. Purpose

This document records behaviours observed while testing Mako Market that may require clarification, further testing, or product improvement.

I have separated reproducible observations from potential concerns. I have not classified a behaviour as a confirmed defect where the expected behaviour or underlying cause has not been established.

---

## OBS-01: Market Chart Timeframe Resets After Refresh

**Area:** Market charts  
**Classification:** Reproducible behaviour observed  
**Status:** Requires confirmation of expected behaviour

### Observation

I selected chart timeframes other than 1H on regular crypto market pages. After refreshing the page, the chart returned to the 1H timeframe.

I observed this behaviour across multiple crypto pools.

### Expected Behaviour

If the selected timeframe is intended to persist, the chart should restore the user's previous selection after refresh.

If resetting to 1H is intentional, the default behaviour should be clear and consistent.

### Actual Behaviour

The chart returned to 1H after refresh.

### User Impact

Users who regularly inspect shorter or longer timeframes may need to select their preferred timeframe again.

### Recommendation

Confirm the intended behaviour. If appropriate, preserve the selected timeframe across refreshes.

### Evidence

Add screenshots showing:
1. A regular crypto market with a non-default timeframe selected.
2. The same market after refresh, showing the chart returned to 1H.

### Retest Criteria

- Select a non-default timeframe.
- Refresh the market page.
- Record whether the selected timeframe persists.
- Repeat on another crypto market.

---

## OBS-02: Bitcoin Price Freshness Requires Verification

**Area:** Market price data  
**Classification:** Investigation required  
**Status:** Unconfirmed concern

### Observation

The displayed Bitcoin price appeared to change very little across screenshots taken several hours apart.

The screenshots alone do not establish that the price feed was stale or incorrect.

### Expected Behaviour

The displayed price should follow the application's intended data-update behaviour and communicate when the price was last updated.

### Actual Behaviour

The price appeared nearly unchanged in the screenshots reviewed. I have not established the underlying cause.

### User Impact

If displayed prices do not update as intended, users may make decisions based on outdated information.

### Recommendation

- Display the latest price-update timestamp.
- Verify the feed against an independent price source.
- Confirm the update frequency expected by the product.
- Consider a stale-data indicator if updates stop.

### Evidence

Attach the relevant screenshots with their original timestamps, if available.

### Retest Criteria

- Record the displayed price and update timestamp.
- Observe the market over a defined period.
- Compare the displayed price with an independent reference at matching times.
- Record the results before classifying this as a defect.

---

## OBS-03: Market Deadline and Countdown Appear Inconsistent

**Area:** Market details and timing  
**Classification:** Requires investigation  
**Status:** Unconfirmed

### Observation

On one market, the title described a longer closing period while the countdown displayed a shorter duration. I noticed a similar discrepancy on another pool.

I have not established whether the title and countdown referred to different events or whether the information was inconsistent.

### Expected Behaviour

The interface should clearly distinguish between the betting deadline, event time, and settlement time.

### Actual Behaviour

The displayed duration and countdown appeared inconsistent during the session.

### User Impact

Users may misunderstand how much time remains to place a bet or when the market will resolve.

### Recommendation

- Label each time indicator clearly.
- Display the relevant timezone.
- Ensure the market title and countdown refer to clearly defined events.

### Evidence

Attach screenshots showing the market title, countdown, and rules together.

### Retest Criteria

- Record the exact wording and countdown.
- Identify what each time indicator represents.
- Compare the displayed values with the market rules.
- Reclassify only after the expected behaviour is clear.

---

## OBS-04: Repeated Bets Are Displayed as Combined Positions

**Area:** Betting and portfolio  
**Classification:** Product improvement opportunity  
**Status:** Observed

### Observation

I placed multiple bets on the same market, including repeated bets on the same outcome.

The Me page displayed combined exposure for the same market and outcome rather than a separate visible row for each individual bet.

### Expected Behaviour

A combined position summary can be useful, but users should also be able to review the individual bets that contribute to that position.

### Actual Behaviour

The visible position summary showed aggregated stakes and estimated payouts.

### User Impact

Users may find it difficult to review individual betting actions, their timing, or the changes in their exposure.

### Recommendation

Consider providing a transaction-level history containing:

- Market and outcome
- Individual stake
- Timestamp
- Transaction status
- Estimated payout at the time of the bet, where available
- Transaction reference, where available
- Combined position exposure

### Evidence

Attach a screenshot of the combined position shown in the Me page.

### Retest Criteria

- Place more than one bet on the same outcome.
- Inspect the position summary.
- Determine whether individual bet records are available elsewhere in the application.
- Confirm whether the current presentation is intentional.

---

## OBS-05: Authentication Prompt Behaviour Requires Investigation

**Area:** Betting authentication  
**Classification:** Investigation required  
**Status:** Unconfirmed

### Observation

An authenticator-code prompt appeared during some betting actions. A later betting action appeared to proceed without the same prompt.

I have not established the conditions under which authentication is required.

### Expected Behaviour

Authentication prompts should follow the application's intended security rules and session policy.

### Actual Behaviour

The prompt appeared during some observed actions but not all.

### User Impact

If the behaviour differs from the intended policy, users may encounter inconsistent authentication experiences.

### Recommendation

Document the authentication requirements and verify the behaviour under controlled, comparable conditions.

### Evidence

Record:
- The action being performed
- Whether authentication was requested
- The relevant session state
- The resulting application behaviour

Do not include authenticator codes, passwords, private keys, or other secrets in the report.

### Retest Criteria

Repeat comparable actions under the same documented conditions and compare the results with the intended authentication policy.

Do not classify this as a security vulnerability without evidence that the application violates its intended policy.

---

## OBS-06: Pools and All Markets Leaderboard Filters Need Clarification

**Area:** Leaderboard  
**Classification:** Investigation required  
**Status:** Unconfirmed

### Observation

I tested the Pools and All Markets leaderboard filters but did not observe a clear difference in the view I inspected.

The Last 7 Days, Last 30 Days, and All Time ranges changed the displayed rankings and figures as expected during the session.

### Expected Behaviour

Each filter should have a clearly defined scope and should display the appropriate results.

### Actual Behaviour

The distinction between Pools and All Markets was not clear in the tested view.

### User Impact

Users may not understand which markets or activities contribute to the displayed rankings.

### Recommendation

- Clarify the scope of each filter.
- Verify whether the two filters should produce different results.
- Provide an empty state or explanatory message when the underlying results are identical.

### Retest Criteria

Test the filters using data that should distinguish their scopes, if such data is available.

Do not classify the filter as broken solely because two views happen to look alike.

---

## OBS-07: Comment Deletion Has No Separate Confirmation Step

**Area:** Comments and replies  
**Classification:** UX improvement opportunity  
**Status:** Observed

### Observation

When I deleted a comment or reply, the interface showed a deleting state and the item subsequently disappeared.

I did not observe a separate confirmation step.

### Expected Behaviour

The product should make destructive actions understandable and help users avoid accidental deletion.

### Actual Behaviour

The item disappeared after the deletion action without a separate confirmation step.

### User Impact

A user may delete content unintentionally.

### Recommendation

Consider adding a confirmation prompt or an undo option.

### Evidence

Attach a screenshot or screen recording of the deletion flow, if available.

### Retest Criteria

Verify whether the deletion behaviour is consistent for comments and replies and whether any undo mechanism is available.

---

## 3. Classification Summary

| ID | Area | Classification | Current Status |
|---|---|---|---|
| OBS-01 | Market charts | Reproducible behaviour observed | Expected behaviour needs confirmation |
| OBS-02 | Price data | Investigation required | Unconfirmed concern |
| OBS-03 | Market timing | Investigation required | Unconfirmed |
| OBS-04 | Portfolio | Product improvement opportunity | Observed |
| OBS-05 | Authentication | Investigation required | Unconfirmed |
| OBS-06 | Leaderboard | Investigation required | Unconfirmed |
| OBS-07 | Comment deletion | UX improvement opportunity | Observed |

## 4. Limitations

- This report is based on manual exploratory testing.
- The intended behaviour has not been confirmed for every observation.
- The price-freshness concern has not been verified against an independent source.
- No security vulnerability is claimed.
- No defect is labelled confirmed without sufficient evidence and a clear expected result.
- Screenshots or recordings should be attached where available.

## 5. Conclusion

The observations in this report identify areas where Mako Market's behaviour, presentation, or expected functionality may benefit from clarification or improvement.

The next step is to validate each investigation item against the intended product behaviour, capture supporting evidence, and update its classification.

I will keep confirmed defects separate from usability recommendations and unverified concerns.
