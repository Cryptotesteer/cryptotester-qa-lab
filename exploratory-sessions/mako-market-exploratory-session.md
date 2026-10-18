# Mako Market - Exploratory Testing Session

## 1. Session Overview

- **Product:** Mako Market
- **Website:** https://makomarket.xyz
- **Tester:** CryptoTester (@CryptoTesteer)
- **Testing approach:** Manual exploratory testing
- **Environment:** Web application accessed through a browser
- **Session period:** October 2026
- **Status:** Exploratory testing completed for the areas documented below

## 2. Session Objective

I explored Mako Market to understand its core user journeys, identify usability concerns, evaluate visible validation and feedback, and document potential product improvements.

The session focused on:

- Market discovery and navigation
- Market rules and settlement conditions
- Betting and payout previews
- Wallet funding and sending
- User positions and portfolio visibility
- Bitcoin prediction rounds
- Comments and replies
- Leaderboards and sharing
- Market Intel
- Chart behaviour and displayed market information

This was exploratory testing, not a comprehensive security audit or full verification of every possible application state.

## 3. Testing Notes and Observations

### 3.1 Onboarding and Navigation

**Actions performed**
- Completed the onboarding tour.
- Explored the Pools, Rounds, Leaderboard, Market Intel, and Me sections.
- Reviewed the categories available in Pools.

**Observations**
- The onboarding tour introduces the main product areas and their intended purposes.
- Pools includes categories such as crypto, football, NBA, forex, commodities, and stocks.
- Some categories displayed empty states when no markets were available.
- The Rounds area presents short-duration UP/DOWN predictions, including Bitcoin rounds.
- Some features, including badges and notifications, were marked as coming soon.

**Assessment**

The main product areas are discoverable. Empty categories and upcoming features should communicate their availability clearly so users can distinguish an empty market category from a feature that is not yet active.

### 3.2 Market Discovery and Listing

**Actions performed**
- Reviewed the Pools listing.
- Opened different categories.
- Inspected market cards and available market information.

**Observations**
- The Pools page displayed open markets and an aggregate amount in play.
- Market availability differed between categories.
- Some categories contained markets while others displayed empty states.
- I observed a possible inconsistency between category counts and the markets displayed, but I did not establish enough evidence to classify this as a confirmed defect.

**Recommendation**

Consider adding discovery filters such as Trending, Ending Soon, Highest Volume, Most Active, Newest, and Most Discussed. Make it easier to distinguish open, upcoming, settled, and unavailable markets.

### 3.3 Market Rules and Settlement Transparency

**Actions performed**
- Opened a football market for Chelsea versus Everton.
- Reviewed the YES and NO outcome definitions.
- Reviewed the betting deadline, settlement timing, resolution source, and refund conditions.
- Opened a Bitcoin price prediction market and reviewed its rules.

**Observations**
- The football market defined YES as an away-team win and NO as a draw or home-team win.
- The football market identified football-data.org as its result source.
- The market rules described refunds for postponed or cancelled matches.
- The Bitcoin market specified a price threshold, a closing time, a settlement time, and Chainlink Data Streams as its resolution source.
- Refund conditions were documented for cases where settlement did not occur within the stated period.
- I could not clearly identify the timezone used for every displayed deadline from the information reviewed.

**Assessment**

The market rules provide useful resolution details. Displaying the timezone beside every deadline would reduce ambiguity, particularly for users in different regions.

**Recommendation**

Keep the outcome condition, resolution source, deadline, settlement window, and refund rules visible and consistent across market types.

### 3.4 Countdown and Deadline Presentation

**Actions performed**
- Compared market titles with their displayed countdowns.
- Reviewed more than one market with a deadline description.

**Observation**

I encountered a market title describing a longer closing period while its countdown displayed a shorter duration. A similar discrepancy appeared on another pool.

I did not establish whether the title and countdown referred to different events or whether the displayed information was inconsistent.

**Classification:** Observation requiring investigation; not a confirmed defect.

**Recommendation**

Clarify the distinction between the betting deadline, event time, and settlement time. Ensure each countdown is labelled according to the event it represents.

### 3.5 Payout Preview and Betting Flow

**Actions performed**
- Selected YES and NO outcomes.
- Changed the proposed stake amount.
- Reviewed payout previews.
- Placed bets on the Chelsea–Everton market.
- Opened the resulting position through the Me section.

**Observations**
- Selecting a side displayed a corresponding payout estimate.
- Changing the stake changed the displayed estimate.
- I successfully placed a 5 USDC YES bet.
- I later placed additional YES and NO bets on the same market.
- The Me page showed combined exposure for the same market and outcome rather than a separate visible position row for every individual bet.
- Opening the position returned me to the associated market.

**Assessment**

The betting flow provided payout estimates and reflected the resulting positions in the account area.

However, combining repeated bets makes it harder to review each individual action.

**Recommendation**

Retain a combined-position summary while providing a transaction-level history showing each bet's outcome, stake, timestamp, transaction status, and resulting exposure.

### 3.6 Authentication Behaviour

**Actions performed**
- Placed bets that triggered an authenticator-code prompt.
- Continued testing the betting flow with additional bets.

**Observation**

The authenticator prompt appeared during some betting actions, but I observed a later bet that appeared to proceed without the same prompt.

I did not establish the precise conditions governing when authentication is required.

**Classification:** Needs investigation; not a confirmed security defect.

**Recommendation**

Document the authentication rules and verify that prompts behave consistently according to those rules. Record the exact action, session state, and outcome when investigating this behaviour.

### 3.7 Wallet Funding and Balance Updates

**Actions performed**
- Opened the Receive section.
- Copied the displayed wallet address.
- Opened the test-USDC funding option.
- Used the Circle faucet on Monad Testnet.
- Returned to Mako Market to inspect the balance.

**Observations**
- The Receive section displayed a QR code and wallet address.
- The copied address matched the address displayed in the interface.
- The test-USDC option opened the Circle faucet.
- The faucet confirmed that 20 test USDC had been sent.
- After returning to Mako Market, the displayed balance updated to 20 USDC.

**Assessment**

The test-funding journey completed successfully in the observed session.

### 3.8 Wallet Input Validation

**Actions performed**
- Opened the Send flow.
- Attempted to continue without a valid recipient address.
- Tested a very small decimal amount.
- Tested an amount with six decimal places.
- Entered an amount greater than the available balance.

**Observations**
- An empty recipient produced a validation message requesting a valid `0x` address.
- An amount with more than six decimal places triggered a precision validation message.
- An amount with six decimal places was accepted by the precision validation, although the balance warning remained.
- Entering more than the available balance produced a balance warning.
- I did not submit a transfer during these validation checks.

**Assessment**

The interface provided visible input validation for the cases tested. Since no transfer was submitted, this session does not establish the outcome of a completed send transaction.

### 3.9 Market Chart Behaviour

**Actions performed**
- Opened Bitcoin price prediction markets.
- Viewed the chart in different timeframes.
- Expanded the chart.
- Refreshed the page after selecting a timeframe.

**Observations**
- The chart displayed BTC/USD price information and a candlestick view when expanded.
- After selecting timeframes such as 15 minutes or 2 hours, refreshing the market page returned the chart to the 1-hour timeframe.
- I observed this behaviour across multiple crypto pools.
- The displayed Bitcoin price appeared to change very little across screenshots taken several hours apart.

**Classification**
- Timeframe reset after refresh: reproducible behaviour observed during the session.
- Price freshness: concern requiring further verification.

**Important limitation**

The screenshots alone do not establish that the underlying price feed was stale or incorrect. A live-data check with timestamps and an independent reference would be needed before making that claim.

**Recommendations**
- Preserve the selected timeframe after refresh, or make the default behaviour explicit.
- Display a clear timestamp for the latest price update.
- Consider a stale-data indicator if the displayed price has not updated within an appropriate interval.
- Provide more historical price context and additional useful timeframes.

### 3.10 Comments, Replies, and Display Names

**Actions performed**
- Added or reviewed comments.
- Tested replies.
- Changed the display name.
- Refreshed the page.
- Deleted a comment or reply.

**Observations**
- Comments initially displayed a wallet address.
- After changing the display name to `Cryptoblinks`, the updated name appeared in comments.
- Replies worked during the session.
- The display name persisted after refresh.
- During deletion, the interface displayed a deleting state and the comment or reply subsequently disappeared.
- I did not observe a separate deletion confirmation step.

**Assessment**

The comment and reply flow worked for the actions tested. The absence of a confirmation step is a UX consideration rather than a confirmed defect.

**Recommendation**

Consider a confirmation prompt or a clear undo option for deletion, especially where users may remove content accidentally.

### 3.11 Leaderboard

**Actions performed**
- Viewed the Pools leaderboard.
- Compared the Last 7 Days, Last 30 Days, and All Time ranges.
- Inspected the available leaderboard filters.

**Observations**
- Rankings and displayed figures changed across the tested time ranges.
- The leaderboard displayed user identifiers, profit figures, and bet counts.
- Rounds-related leaderboard functionality was marked as coming soon.
- I did not observe a clear visible difference between the Pools and All Markets filters in the view I tested.

**Classification**
- Time-range behaviour: observed working.
- Pools versus All Markets filter: requires further investigation to establish the expected distinction.

**Recommendation**

Make the scope of each leaderboard filter clear and ensure that changing filters produces an understandable result when the underlying data differs.

### 3.12 Sharing

**Actions performed**
- Opened a market's Share panel.
- Reviewed the available sharing options.
- Copied a market link and opened it.

**Observations**
- The Share panel provided options including WhatsApp, Telegram, QR code, and copying a link.
- The copied link opened the correct market.

**Result:** Passed for the sharing action tested.

**Recommendation**

Consider shareable result cards that display the market, outcome, and result for users who want to share completed predictions.

### 3.13 Rounds

**Actions performed**
- Opened the Rounds section.
- Reviewed the Bitcoin pair, round information, countdown, UP/DOWN options, stake controls, and payout estimate.
- Changed chart timeframes.
- Expanded the chart.
- Reviewed settled-round information.

**Observations**
- The interface displayed round information, start and end times, and a countdown.
- Selecting DOWN displayed a payout estimate.
- A stake below the displayed 0.10 USDC minimum disabled the prediction action.
- At the 0.10 USDC minimum, the action became enabled.
- The Rounds chart timeframe controls changed the displayed view during the session.
- The expanded chart opened correctly.
- Settled-round details included starting and closing prices, movement, winner, pot, fees, payout or distribution information, and an on-chain verification link.
- I did not submit a prediction during the minimum-stake test.

**Assessment**

The tested Rounds controls provided visible stake validation and round information. The timeframe reset observed on regular market charts should not automatically be attributed to the separate Rounds chart, whose controls behaved differently during this session.

**Recommendations**
- Consider adding more assets and round durations.
- Keep the current price, remaining time, potential payout, and relevant pool information easy to access.
- Consider automatic updates without requiring a full-page reload.
- Provide clear recent-round results and an obvious countdown to the next round.

### 3.14 Market Intel

**Actions performed**
- Opened Market Intel.
- Applied category filters, including Crypto and NBA.
- Opened news cards.

**Observations**
- The Crypto filter changed the displayed news.
- The NBA filter displayed NBA-related news.
- News cards opened external websites.

**Assessment**

The category-filter and external-link behaviour worked for the cases tested.

**Recommendations**
- Expand Market Intel coverage.
- Make relevant news easy to discover from related markets.
- Consider explaining important price movements where reliable information is available.

## 4. Findings Summary

| ID | Observation | Classification | Follow-up |
|---|---|---|---|
| OBS-01 | Regular market chart timeframe returned to 1H after refresh | Reproducible behaviour observed | Confirm intended behaviour and consider preserving selection |
| OBS-02 | Displayed BTC price appeared to change very little across several hours | Requires verification | Check timestamp and compare against an independent price source |
| OBS-03 | Market title duration and countdown appeared inconsistent | Requires investigation | Clarify the meaning of each time indicator |
| OBS-04 | Repeated bets were represented as combined positions | Product improvement opportunity | Add a transaction-level bet history |
| OBS-05 | Authenticator prompt appeared inconsistently across observed betting actions | Requires investigation | Verify expected authentication rules |
| OBS-06 | Pools and All Markets leaderboard filters showed no clear difference in the tested view | Requires investigation | Confirm filter definitions and expected results |
| OBS-07 | Comment deletion had no separate confirmation step | UX improvement opportunity | Consider confirmation or undo |
| OBS-08 | Some categories displayed empty states | Product/discovery observation | Improve empty-state messaging and discovery |

These observations should not all be treated as confirmed defects. Several require clarification of expected behaviour or additional evidence.

## 5. Product Improvement Opportunities

Based on the session, I recommend considering the following improvements:

### Charts and Price Information
- Preserve chart timeframe selection after refresh.
- Display the latest price update timestamp.
- Add more useful timeframes and historical price context.
- Consider mini charts and historical round comparisons.

### Betting and Positions
- Add a transaction-level history for repeated bets.
- Show individual bet timestamps, stakes, outcomes, and statuses.
- Make the estimated payout and any applicable fees clear before confirmation.
- Consider partial exits and early cash-out as future product features.

### Rounds
- Consider adding more supported assets and round durations.
- Keep price, countdown, stake, and payout information prominent.
- Improve automatic updates and recent-round discovery.

### Discovery and Notifications
- Add search and more useful market filters.
- Consider Trending, Ending Soon, Highest Volume, and Most Discussed views.
- Consider watchlists, price alerts, round reminders, and resolution notifications.

### Portfolio and Analytics
- Consider a dashboard for realized and unrealized PnL, win rate, total volume, and historical performance.
- Add time-range and category filters to portfolio analytics.
- Consider an exportable transaction history.

### Social and Sharing
- Consider shareable win or result cards.
- Improve the clarity of leaderboard filters.
- Consider a clear undo or confirmation step for comment deletion.

### Market Rules and Trust
- Display the timezone for market deadlines.
- Clearly distinguish betting deadlines, event times, and settlement times.
- Keep resolution sources and refund rules easy to find.
- Provide clear transaction states and error feedback.

## 6. Limitations

- This was manual exploratory testing of selected application flows.
- Not every market, account state, device, browser, or network condition was tested.
- I did not perform a comprehensive security audit.
- I did not verify every displayed price against an independent live data source.
- I did not submit a wallet transfer during the validation checks described above.
- I did not submit a prediction during the Rounds minimum-stake validation test.
- Where the intended behaviour was unclear, I recorded an observation or investigation item instead of claiming a confirmed defect.

## 7. Conclusion

My exploratory session covered Mako Market's main discovery, betting, wallet-funding, Rounds, social, leaderboard, sharing, and Market Intel journeys.

Several core actions worked in the scenarios tested, including test-USDC funding, payout previews, betting, comment replies, market sharing, and the Rounds minimum-stake control.

The main follow-up areas are chart timeframe persistence, price-data freshness visibility, deadline clarity, authentication behaviour, leaderboard filter expectations, and transaction-level position history.

I recommend validating the investigation items against the product's intended behaviour before classifying them as defects. The broader product recommendations can then be prioritised separately from confirmed functional issues.
