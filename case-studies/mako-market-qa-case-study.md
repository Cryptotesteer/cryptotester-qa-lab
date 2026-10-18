# Mako Market - QA Case Study

**Prepared by:** CryptoTester  
**Product:** Mako Market  
**Application:** https://makomarket.xyz  
**Testing Type:** Manual QA, Functional Testing, Positive Testing, Negative Testing, Exploratory Testing, Web3 Testing, Wallet Testing, and UX Evaluation  
**Testing Period:** October 2026  
**Status:** Testing completed for the scenarios documented; additional validation may be required.

---

## 1. Project Overview

Mako Market is a prediction market application that allows users to participate in markets based on future outcomes.

The product includes YES/NO prediction pools, cryptocurrency price predictions, short-duration BTC rounds, wallet interactions, betting positions, market discovery, leaderboards, and market-related news.

My goal was to evaluate the application's core user journeys, observe how its features behaved during normal and invalid interactions, and identify potential defects, usability concerns, and opportunities for product improvement.

This case study documents my manual testing experience and the product-quality insights gathered during the testing process.

## 2. Testing Objectives

My objectives were to:

- Evaluate the main application navigation and user experience.
- Test the available prediction market flows.
- Examine market rules, closing times, settlement conditions, and refund information.
- Test betting selections, stake amounts, payout estimates, and position tracking.
- Evaluate wallet funding and balance updates.
- Examine transaction validation and insufficient-balance handling.
- Explore BTC Rounds and their available controls.
- Test market comments, replies, and display-name persistence.
- Review leaderboard filters and ranking information.
- Examine market sharing functionality.
- Explore Market Intel and its category filters.
- Identify potential defects and unexpected behaviour.
- Recommend improvements that could make the product easier to understand and use.

## 3. Scope of Testing

The following application areas were explored.

### 3.1 Onboarding and Navigation

I reviewed the onboarding tour and the main sections introduced to users.

The tour explained YES/NO markets, BTC rounds, market categories, market creation, leaderboards, user positions, and test USDC funding.

### 3.2 Prediction Markets

I explored available markets and inspected market cards, categories, pool information, and market details.

I also reviewed the rules for a football prediction market and a BTC price prediction market.

### 3.3 Betting and Positions

I tested betting selections and stake amounts, examined payout estimates, and placed bets on a football market.

I then checked the displayed balance, estimated payouts, and positions in the user's account area.

### 3.4 Wallet

I explored the wallet's receive and send interfaces, copied the wallet address, examined input validation, and used the available test USDC funding flow.

I confirmed that the application balance updated after test USDC was received.

### 3.5 BTC Rounds

I explored the Rounds interface, selected UP/DOWN outcomes, examined stake limits and payout estimates, and interacted with the available chart controls.

### 3.6 Comments and Replies

I tested commenting, replying, deleting my own comment or reply, and changing the display name shown alongside comments.

### 3.7 Leaderboard

I explored leaderboard filters, including time ranges, and observed changes in displayed rankings and profit figures.

### 3.8 Sharing

I opened the market-sharing interface and tested the copy-link option.

### 3.9 Market Intel

I explored Market Intel and its category filters, including Crypto and NBA, and opened news items from the available cards.

### 3.10 Settings and Account Information

I reviewed the account area, displayed wallet information, balance, earnings, positions, and available settings.

## 4. Testing Methodology

I used manual testing and exploratory testing to evaluate the application.

My approach involved:

1. Opening a feature and identifying its intended purpose.
2. Interacting with the available controls.
3. Entering valid or invalid inputs where appropriate.
4. Observing the application's response.
5. Comparing the observed behaviour with the information presented in the interface.
6. Checking persistence or state changes where applicable.
7. Recording findings and identifying areas requiring clarification.
8. Developing recommendations based on the observed behaviour and product experience.

I distinguished between confirmed defects, potential risks, UX observations, and product improvement opportunities.

An unexpected result was not automatically classified as a confirmed defect when the intended behaviour or acceptance criteria were unclear.

## 5. Key Testing Results

### 5.1 Wallet Funding

I used the available Circle test USDC faucet on Monad Testnet.

After completing the funding flow, the faucet confirmed that 20 test USDC had been sent and provided a Monad Explorer transaction link.

After returning to Mako Market, I observed that the displayed balance had updated to 20 USDC.

**Result:** The test funding flow completed, and the displayed application balance updated.

### 5.2 Betting Flow

I placed a 5 USDC YES bet on a Chelsea versus Everton market.

The application confirmed the successful action. The account area subsequently displayed a balance of 15 USDC, a 5 USDC stake, and an estimated payout of 5.57 USDC.

I later placed additional bets on the same market.

The account area displayed combined YES and NO positions rather than separate visible entries for each individual bet.

**Result:** The tested bets were reflected in the displayed positions and balance.

**Product observation:** Showing the combined exposure is useful, but users could benefit from an individual transaction history showing each bet, its outcome selection, amount, and timestamp.

### 5.3 Market Rules and Settlement Information

I examined the rules for a football prediction market and a BTC price prediction market.

The football market explained the YES/NO outcomes, betting deadline, result settlement timing, refund conditions, and resolution source.

The BTC market described the target price, closing condition, betting deadline, settlement timing, refund conditions, and Chainlink price source.

**Result:** The tested market details included important information about outcomes and settlement.

**Product improvement opportunity:** Make the relevant timezone, precise settlement timestamp, and resolution-source details easy to identify and understand.

### 5.4 Comments and Replies

I tested commenting and replying.

I also changed the display name and observed that the updated name appeared in comments and remained after refreshing the application.

Deleting my own comment or reply showed a deleting state before the content disappeared.

**Result:** The tested comment and reply interactions worked.

**UX observation:** A clear deletion confirmation or undo option could help users avoid accidental deletions.

### 5.5 Leaderboard

I explored the Pools and All markets filters, followed by the Last 7 days, Last 30 days, and All time filters.

The displayed rankings, ordering, and profit figures changed across the tested time ranges.

**Result:** The time-range filters produced visible changes during testing.

**Further clarification:** The behaviour of the Pools versus All markets filter requires clearer confirmation before any defect can be established.

### 5.6 Market Sharing

I opened the sharing interface and examined the available WhatsApp, Telegram, QR-code, and copy-link options.

I copied a market link and opened it to confirm that it led to the correct market.

**Result:** The tested copy-link flow worked.

### 5.7 Market Intel

I explored the Market Intel section and its category filters.

The Crypto and NBA filters displayed category-related news, and news cards opened external websites.

**Result:** The tested news browsing and category interactions worked.

### 5.8 BTC Rounds

I explored the Rounds interface, selected a DOWN prediction, and examined the stake and payout information.

I also tested the minimum stake behaviour and interacted with the chart's timeframe controls.

The interface disabled prediction submission when the entered amount was below the displayed minimum of 0.10 USDC. At 0.10 USDC, the prediction button became enabled.

**Result:** The tested minimum-stake control behaved as expected.

This observation does not establish that every round, prediction, settlement, or payout scenario has been validated.

## 6. Potential Risks and Observations

The following items require careful classification and, where necessary, additional investigation.

### 6.1 Chart Timeframe Persistence

On cryptocurrency market charts, the selected timeframe returned to 1H after refreshing the page, even when I had selected another timeframe.

I observed this behaviour on multiple cryptocurrency markets.

**Classification:** UX/state-persistence observation.

**Recommendation:** Preserve the selected timeframe when users revisit or refresh a market, where appropriate.

### 6.2 Price Refresh and Data Freshness

During testing, the displayed BTC price appeared to change very little across screenshots taken several hours apart.

This observation alone does not prove that the price feed was stale or malfunctioning.

**Classification:** Potential data-freshness concern requiring verification.

**Recommendation:** Display a last-updated timestamp and provide a visible stale-data indicator when the price feed has not updated within an appropriate interval.

### 6.3 Market Closing Information

Some market titles and countdown displays appeared to show different remaining durations.

The relationship between these displays requires clarification before the behaviour can be classified as a defect.

**Classification:** Potential UI consistency issue.

**Recommendation:** Clearly distinguish betting deadlines, market closing times, and settlement times.

### 6.4 Combined Betting Positions

Repeated bets on the same market were presented as combined YES and NO positions.

The interface did not provide a clearly visible breakdown of each individual bet in the position view I examined.

**Classification:** Product usability observation.

**Recommendation:** Provide a transaction-level betting history while retaining the combined position summary.

### 6.5 Authentication Prompt Behaviour

Authentication prompts appeared during some betting actions, while a later betting action appeared to proceed without the same prompt.

The available observations are insufficient to establish whether this was a defect or an intentional authentication policy.

**Classification:** Potential authentication-consistency concern requiring investigation.

**Recommendation:** Make authentication requirements consistent and clearly communicate when additional verification is required.

### 6.6 Comment Deletion Feedback

The comment deletion flow showed a deleting state before the content disappeared, without a visible confirmation step in the tested interaction.

**Classification:** UX observation.

**Recommendation:** Consider a confirmation or undo mechanism for comment deletion.

### 6.7 Market Discovery

I observed that category views could display different numbers of markets, including empty states.

The relationship between category counts and the markets displayed was not fully established during the documented tests.

**Classification:** Potential discovery/UI consistency observation.

**Recommendation:** Ensure category counts, market listings, and empty-state messages remain consistent.

## 7. Product Improvement Recommendations

These recommendations extend beyond the observed issues. They represent potential improvements to Mako Market and are not claims that every suggested feature is currently missing.

### 7.1 Charts and Price History

- Offer useful chart timeframes for short-duration markets.
- Consider adding 5-minute and 30-minute views.
- Preserve chart timeframe selections when appropriate.
- Display price-feed update timestamps.
- Add clear loading and stale-data states.
- Consider mini charts on market cards.
- Show recent price or probability movements where useful.

### 7.2 Early Exit and Cash-Out

Consider allowing users to exit an eligible position before market resolution.

Potential capabilities include:

- A clearly labelled Cash Out action.
- Estimated exit value before confirmation.
- Partial position exits.
- Clear explanations of fees and payout differences.
- Warnings about liquidity, slippage, or changing exit values where applicable.

This recommendation depends on the product's market mechanics and liquidity model.

### 7.3 Price Alerts and Notifications

Consider allowing users to:

- Add markets to a watchlist.
- Receive alerts when selected prices or probabilities reach a chosen threshold.
- Receive reminders before a market or round closes.
- Receive notifications when a market is resolved.
- Configure browser or mobile notifications where supported.

### 7.4 Portfolio and Trading Analytics

Consider expanding the account area with:

- Realised profit and loss.
- Unrealised profit and loss, where applicable.
- Win rate and average return.
- Performance over selectable time ranges.
- Position history.
- Individual bet records.
- Filters by market, category, outcome, and date.
- Exportable transaction history.

Financial metrics should be clearly defined so users understand how each value is calculated.

### 7.5 BTC Rounds

Potential improvements include:

- More supported assets where feasible.
- Additional round durations.
- A prominent current price.
- Clear round start and end times.
- Visible pool sizes and payout estimates.
- Recent round results.
- Clear settlement-source information.
- Automatic data refresh without unnecessary full-page reloads.

### 7.6 Market Discovery

Consider adding or improving:

- Search by market title or keyword.
- Trending markets.
- Markets ending soon.
- Highest-volume markets.
- New markets.
- Most active markets.
- Category and creator filters.
- Clear distinctions between regular prediction pools and Rounds.

### 7.7 Leaderboard and Social Features

Potential additions include:

- Shareable result cards.
- Weekly and category-specific leaderboards.
- Clear explanations of ranking calculations.
- Optional public trading profiles.
- Referral functionality where appropriate.

Public position sharing should include privacy controls so users can decide what information they disclose.

### 7.8 Market Creation

Potential improvements include:

- Market creation templates.
- Clear rule-writing guidance.
- Required resolution-source selection.
- Explicit deadlines and timezones.
- A preview of market rules before publication.
- Creator dashboards showing market activity and earnings.
- Reporting and moderation tools.

### 7.9 Liquidity and Incentives

Potential options for consideration include:

- Liquidity incentives.
- Creator rewards tied to clearly defined criteria.
- Early-round participation incentives.
- Transparent fee-sharing arrangements where appropriate.

Any incentive mechanism should be evaluated for economic sustainability and unintended behaviour.

### 7.10 Mobile Experience

Consider improving the mobile experience through:

- A streamlined Rounds interface.
- Accessible betting controls.
- Clear confirmation and transaction-status messages.
- Responsive chart controls.
- Easier access to active positions and recent results.
- Clear loading, failure, and retry states.

### 7.11 Market Intel

Potential improvements include:

- Stronger connections between relevant news and related markets.
- More useful category filtering.
- Clear source attribution.
- Clear publication dates.
- Better handling of unavailable external links.
- Optional watchlist-related news updates.

### 7.12 Onboarding and Trust

Consider making the following information easy to find:

- How YES/NO markets work.
- How payouts are calculated.
- What fees apply.
- How markets are resolved.
- What happens when a market is cancelled or delayed.
- How refunds work.
- Which network and assets are involved.
- How users can verify relevant on-chain transactions.

## 8. Suggested Product Improvement Priorities

The following is a proposed prioritisation, not an assessment of Mako Market's internal engineering roadmap.

### Priority 1 — Clarity and Reliability

- Improve market deadlines and settlement information.
- Clarify price-data freshness.
- Investigate chart timeframe persistence.
- Clarify authentication behaviour.
- Improve transaction and position history.

### Priority 2 — Trading Experience

- Improve charts and price history.
- Improve the Rounds interface.
- Add clearer portfolio analytics.
- Improve market search and discovery.

### Priority 3 — Engagement

- Add configurable alerts.
- Improve shareable results.
- Expand leaderboard options.
- Improve relevant news discovery.

### Priority 4 — Advanced Features

- Evaluate early exit and partial cash-out.
- Consider additional round assets and durations.
- Explore creator tools and liquidity incentives.
- Evaluate advanced trading controls where suitable.

## 9. Testing Limitations

This case study reflects the scenarios documented during my manual testing.

The work does not constitute:

- A smart-contract security audit.
- A source-code audit.
- A formal penetration test.
- A load or stress test.
- A comprehensive audit of all market settlement mechanisms.
- Independent verification of every displayed financial figure.
- Full validation of every betting, refund, or payout edge case.

Some observations require clarification of intended product behaviour before they can be classified as confirmed defects.

Product improvement recommendations are proposals and should not be interpreted as proof that a feature is absent or malfunctioning.

## 10. Conclusion

My testing of Mako Market covered key user journeys across prediction markets, betting, wallet funding, BTC Rounds, comments, leaderboards, market sharing, and Market Intel.

I confirmed that several core flows worked during the scenarios I exercised, including test USDC funding, displayed balance updates, betting actions, market sharing, and selected account interactions.

The testing also identified areas worth investigating further, particularly chart timeframe persistence, price-data freshness, market deadline presentation, combined position history, and authentication prompt consistency.

Beyond individual findings, I identified opportunities to improve market discovery, portfolio analytics, alerts, charts, early exit options, creator tools, and the mobile trading experience.

The purpose of this case study is to document my testing process, distinguish observed behaviour from assumptions, and provide practical recommendations that could help improve Mako Market's usability, transparency, and overall product experience.

---

**Prepared by CryptoTester**  
**QA Portfolio:** https://github.com/Cryptotesteer/cryptotester-qa-lab  
**Product:** https://makomarket.xyz
