# Mako Market - QA Test Plan

**Prepared by:** CryptoTester  
**Product:** Mako Market  
**Application:** https://makomarket.xyz  
**Testing Approach:** Manual, Functional, Exploratory, Positive, Negative, Edge-Case, Web3, and UX Testing  
**Testing Period:** October 2026  
**Status:** Testing performed on documented scenarios; additional validation may be required.

---

## 1. Introduction

This test plan defines the scope, objectives, methodology, and coverage areas for my manual QA testing of Mako Market.

Mako Market is a prediction market application featuring YES/NO markets, cryptocurrency price predictions, BTC Rounds, wallet interactions, betting positions, market discovery, leaderboards, comments, and Market Intel.

The purpose of this plan is to document the areas I evaluated, the types of tests I performed, and the product behaviours I examined.

This is a product QA assessment. It is not a smart-contract security audit or a comprehensive security assessment.

## 2. Testing Objectives

My testing objectives were to:

- Verify the accessibility of major application sections.
- Evaluate the onboarding experience.
- Examine market cards, categories, and market details.
- Verify how market rules and settlement information are presented.
- Test betting selections, stake inputs, and payout estimates.
- Observe balance and position updates after betting.
- Test available wallet funding and validation flows.
- Examine BTC Rounds, stake limits, payout estimates, and chart controls.
- Test comments, replies, and display-name persistence.
- Examine leaderboard filters and displayed rankings.
- Verify market-sharing functionality.
- Explore Market Intel and its category filters.
- Identify reproducible defects where the expected behaviour is established.
- Document potential risks and observations requiring clarification.
- Recommend improvements to usability, transparency, and product functionality.

## 3. Test Scope

### 3.1 Onboarding and Navigation

- Review the onboarding tour.
- Identify the main application features.
- Explore market categories and navigation.
- Examine empty states and available market listings.

### 3.2 Prediction Markets

- Open available markets.
- Review market cards and details.
- Inspect YES/NO outcome definitions.
- Review betting deadlines.
- Review settlement timing.
- Inspect refund conditions.
- Examine the stated resolution sources.

### 3.3 Betting and Positions

- Select YES and NO outcomes.
- Change the stake amount.
- Observe payout estimates.
- Examine minimum and maximum restrictions where available.
- Complete selected betting flows.
- Check displayed balance changes.
- Review active and settled positions.
- Examine how repeated bets are represented.

### 3.4 Wallet

- Open the wallet and receive interface.
- Copy and compare the displayed wallet address.
- Open the available test USDC funding flow.
- Observe wallet balance changes after funding.
- Examine recipient validation.
- Test invalid or incomplete send inputs.
- Test decimal precision validation.
- Observe insufficient-balance messages.

### 3.5 BTC Rounds

- Open the Rounds interface.
- Examine the displayed asset and round information.
- Select UP and DOWN outcomes where applicable.
- Examine stake minimums.
- Review payout estimates.
- Interact with chart timeframe controls.
- Inspect recent round results and available result details.
- Examine settlement information presented by the application.

### 3.6 Comments and Replies

- Open the comment interface.
- Publish a comment.
- Reply to a comment.
- Delete my own comment or reply.
- Change the display name.
- Check whether the updated display name persists after refresh.

### 3.7 Leaderboard

- Open the leaderboard.
- Inspect available leaderboard categories.
- Change the time-range filter.
- Compare the displayed rankings and profit figures.
- Record any unclear filter behaviour.

### 3.8 Market Sharing

- Open the share interface.
- Inspect the available sharing options.
- Copy a market link.
- Open the copied link and verify the destination.

### 3.9 Market Intel

- Open Market Intel.
- Change the category filter.
- Inspect the displayed news items.
- Open selected external news links.

### 3.10 Account and Settings

- Review displayed account information.
- Inspect wallet balance and earnings.
- Review active and settled positions.
- Inspect the available account settings.
- Observe authentication prompts during selected betting actions.

## 4. Testing Methodology

I used manual testing and exploratory investigation.

My approach followed this sequence:

**Prepare → Explore → Observe → Test → Record → Review**

For each scenario, I considered:

- The feature being tested.
- The action performed.
- The expected behaviour, where established.
- The actual behaviour observed.
- Whether the behaviour was reproducible.
- Whether the state persisted after refreshing, where relevant.
- Whether additional evidence or clarification was needed.
- Whether the result represented a pass, confirmed defect, potential risk, or UX observation.

I did not classify unexpected behaviour as a confirmed defect when the intended product behaviour was unclear.

## 5. Test Types

### 5.1 Functional Testing

I examined whether features performed their intended actions.

Examples included opening markets, selecting betting outcomes, using wallet controls, viewing positions, and opening news items.

### 5.2 Positive Testing

I tested valid user interactions, including funding the test wallet, selecting market outcomes, placing bets, replying to comments, and copying market links.

### 5.3 Negative Testing

I examined selected invalid or restricted inputs, including invalid wallet addresses, insufficient balances, and amounts exceeding the permitted decimal precision.

Only scenarios actually exercised are treated as tested.

### 5.4 Edge-Case Testing

I examined behaviour involving repeated bets, chart timeframe changes, refresh persistence, minimum stake amounts, and differences in displayed market timing.

### 5.5 Exploratory Testing

I explored application features beyond a fixed sequence of test cases to identify usability concerns and unexpected behaviour.

### 5.6 Web3 and Wallet Testing

I examined the test USDC funding flow, wallet information, balance updates, transaction references, and the relationship between displayed account state and selected blockchain-related actions.

This did not constitute independent verification of every smart-contract operation.

### 5.7 UX Testing

I considered whether important information was easy to understand, whether controls provided clear feedback, and whether users could understand market rules, betting exposure, payouts, and settlement conditions.

## 6. Test Environment

| Item | Detail |
|---|---|
| Product | Mako Market |
| Application | https://makomarket.xyz |
| Tester | CryptoTester |
| Testing Method | Manual testing |
| Testing Context | Web application |
| Blockchain Context | Monad Testnet for the documented test USDC funding flow |
| Evidence | Screenshots and observed application behaviour |
| Test Period | October 2026 |

## 7. Test Coverage Summary

| Area | Coverage | Notes |
|---|---|---|
| Onboarding and Navigation | Tested | Onboarding information and main features reviewed |
| Prediction Markets | Tested | Market details, outcomes, rules, and settlement information examined |
| Betting and Positions | Tested | Selected bets completed and displayed positions reviewed |
| Wallet Funding | Tested | Test USDC funding completed and displayed balance updated |
| Wallet Validation | Partially Tested | Selected invalid inputs and insufficient-balance behaviour examined |
| BTC Rounds | Partially Tested | Outcome controls, minimum stake, payout estimate, and charts explored |
| Comments and Replies | Tested | Commenting, replying, deletion, and display-name persistence examined |
| Leaderboard | Tested | Time-range filters tested; another filter requires clarification |
| Market Sharing | Tested | Copied market link opened the correct market |
| Market Intel | Tested | Selected category filters and external news links examined |
| Account and Settings | Partially Tested | Account information and available settings reviewed |
| Settlement and Refunds | Partially Tested | Rules inspected; all settlement and refund outcomes were not independently validated |

Coverage labels describe the documented testing performed. They do not imply that every possible scenario in an area has passed.

## 8. Entry Criteria

Testing could begin when:

- The application was accessible.
- Relevant features were available.
- The tester could navigate to the feature being examined.
- Required test assets or test funding were available for the relevant scenario.

## 9. Exit Criteria

The documented testing phase is considered complete when:

- The executed scenarios have been recorded.
- Important findings have been classified appropriately.
- Supporting evidence has been organised where available.
- Unverified behaviour is clearly identified.
- Product improvement recommendations have been documented.
- Remaining validation needs have been recorded.

Completion of this phase does not mean that every feature or edge case has been validated.

## 10. Out of Scope

The following activities were not established as part of this testing engagement:

- Full smart-contract security audit.
- Source-code audit.
- Formal penetration testing.
- Backend architecture review.
- Infrastructure security assessment.
- Load and stress testing.
- Comprehensive economic or tokenomics audit.
- Independent verification of every settlement and payout calculation.
- Comprehensive testing of every refund and cancellation scenario.
- Formal accessibility certification.

## 11. Risks and Limitations

Potential limitations include:

- Some product requirements were not available for comparison.
- Selected observations require product-team clarification.
- Displayed price behaviour was not sufficient to prove a stale price feed.
- Selected settlement rules were inspected but not exhaustively validated.
- Authentication prompt consistency requires further investigation.
- The documented test USDC funding flow does not establish that every wallet or transaction scenario works.
- Recommendations for future features do not establish that those features are absent or defective.

## 12. Retest Recommendations

If relevant fixes or product changes are introduced, I recommend retesting:

1. Chart timeframe persistence.
2. Price-data freshness indicators.
3. Market closing and settlement time presentation.
4. Individual bet history and combined position calculations.
5. Authentication prompt consistency.
6. Wallet input validation and balance handling.
7. Rounds minimum stake validation.
8. Leaderboard filter behaviour.
9. Category counts and market listing consistency.
10. Transaction, settlement, and refund status communication.

Retesting should compare the updated behaviour with documented expectations and the original evidence.

## 13. Product Improvement Workstream

In addition to findings from the executed tests, I identified opportunities for future product development.

These include:

- More flexible chart timeframes and clearer price history.
- Price alerts and notifications.
- Portfolio analytics and individual bet history.
- Early exit or partial cash-out, subject to the market mechanics.
- More assets and durations for Rounds.
- Improved search, sorting, and market discovery.
- Shareable results and expanded leaderboard options.
- Market creation templates and creator dashboards.
- Clearer liquidity and incentive information.
- Mobile UX improvements.
- Better connections between Market Intel and relevant markets.
- Clearer onboarding, settlement, fee, and refund explanations.
- More comprehensive loading, error, and transaction-status feedback.

These are product recommendations rather than confirmed defects.

## 14. Final Test Plan Summary

My testing plan focused on the most important user journeys across Mako Market's prediction pools, betting interface, wallet funding, BTC Rounds, comments, leaderboards, sharing, and Market Intel.

The documented results provide a basis for the detailed test cases, exploratory session notes, finding records, and product improvement recommendations in my QA portfolio.

The next stage is to ensure that each executed scenario and significant observation is represented accurately in the supporting QA documentation.

---

**Prepared by CryptoTester**

**QA Portfolio:** https://github.com/Cryptotesteer/cryptotester-qa-lab

**Product:** https://makomarket.xyz
