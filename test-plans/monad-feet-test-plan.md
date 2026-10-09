# Monad Feet - QA Test Plan

**Prepared by:** CryptoTester  
**Product:** Monad Feet  
**Application URL:** https://monadfeet.social/  
**Testing Period:** October 2026  
**Testing Type:** Manual Functional Testing, Exploratory Testing, Web3 QA, and UX Testing  
**Test Status:** Initial testing completed; selected scenarios require further validation.

---

## 1. Introduction

### 1.1 Purpose

This test plan documents the objectives, scope, methodology, environment, risks, and limitations of the manual QA testing performed on Monad Feet.

Monad Feet is a social application built around the Monad blockchain. Its features include social posts, creator profiles, exclusive content, subscriptions, direct messaging, likes, comments, points, daily check-ins, and selected on-chain interactions.

The testing focused on evaluating the application's behaviour during important user journeys, verifying selected on-chain transaction references, identifying unexpected behaviour, and documenting opportunities for product improvement.

### 1.2 Testing Objectives

The main objectives were to:

- Evaluate core application functionality.
- Test important social interactions and content-creation flows.
- Check the persistence of selected actions after refreshing the page.
- Examine profile editing and creator settings.
- Verify selected transaction references through the Monad explorer.
- Inspect wallet information and selected wallet-related interactions.
- Test search, discovery, trending, and leaderboard functionality.
- Examine direct messaging, blocking, and session handling.
- Identify usability concerns and potential product-quality risks.
- Document untested scenarios and areas requiring further investigation.

### 1.3 Testing Deliverables

The testing engagement produced the following documentation:

- QA case study
- Test cases
- Exploratory testing session
- Detailed test results
- Observations and potential risks
- Product improvement recommendations
- Evidence register
- Retest plan

Actual screenshots and additional evidence should be included where available.

---

## 2. Test Scope

### 2.1 In-Scope Areas

The following application areas were included in the manual testing engagement:

**Landing Page and Navigation**
- Accessing the application.
- Navigating the main application sections.
- Observing the public landing page.

**Home Feed**
- Opening the feed.
- Switching between Latest and Top.
- Observing post ordering.
- Recording unavailable-image messages.

**Post Creation**
- Opening the post creator.
- Entering captions.
- Selecting images.
- Publishing an image-based post.
- Inspecting exclusive-post settings.
- Checking post persistence after refresh.
- Inspecting available post actions.

**Likes and Comments**
- Interacting with the like control.
- Publishing comments.
- Checking comment persistence.
- Deleting comments.
- Checking deletion persistence.
- Observing comment-loading behaviour.

**Profiles and Creator Features**
- Opening profile-editing settings.
- Saving profile changes.
- Accessing subscription-price settings.
- Opening creator analytics.

**Wallet and On-Chain Interactions**
- Inspecting displayed wallet information.
- Completing selected wallet-signature actions.
- Opening selected transaction references.
- Inspecting transaction details in the Monad explorer.
- Comparing displayed on-chain and database post counts.

**Search and Discovery**
- Searching for member profiles.
- Inspecting search filters.
- Opening Discover.
- Opening Trending.
- Opening Leaderboard.

**Notifications and Engagement**
- Opening notifications.
- Inspecting unread notification information.
- Completing the daily check-in.

**Direct Messages and Member Controls**
- Opening the Messages page.
- Sending a direct message.
- Checking message persistence.
- Blocking and unblocking a member.

**Session Handling**
- Signing out.
- Reconnecting to the application.

### 2.2 Partially Tested Areas

The following areas were accessed or inspected, but the complete user journeys were not validated:

- Creator subscription settings.
- Exclusive-post configuration.
- Creator analytics calculations.
- Wallet-related functionality beyond selected scenarios.
- On-chain information and displayed post counts.
- Blocking effects across all application areas.

Accessing a feature or observing its interface does not establish that every underlying function works correctly.

### 2.3 Out of Scope

The following activities were not part of the completed testing engagement:

- Full smart-contract security auditing.
- Source-code review.
- Comprehensive backend and database auditing.
- Load and stress testing.
- Formal penetration testing.
- Complete validation of every subscription and payment scenario.
- Exhaustive testing of all transaction failure and recovery paths.
- Independent verification of every analytics calculation.

These activities would require separate testing procedures, tools, access, or technical investigation.

---

## 3. Testing Approach

### 3.1 Manual Functional Testing

I exercised selected application features to determine whether they performed their intended actions.

Examples included creating posts, publishing comments, editing profile information, sending direct messages, and accessing application sections.

### 3.2 Positive Testing

I tested selected valid user journeys to confirm that the application could complete expected actions.

Examples included:

- Publishing an image-based post.
- Publishing a comment.
- Deleting a comment.
- Saving profile changes.
- Sending a direct message.
- Completing a daily check-in.

### 3.3 Exploratory Testing

I explored the application without restricting the session to predefined test cases.

The objective was to identify unexpected behaviour, unclear interface states, and areas where additional investigation or product improvements might be useful.

### 3.4 State Persistence Testing

After selected actions, I refreshed the application to observe whether the resulting state remained consistent.

Scenarios included:

- Published posts.
- Published comments.
- Deleted comments.
- Sent direct messages.

The results apply only to the specific scenarios exercised.

### 3.5 Web3 Testing

I examined selected wallet-related interactions and transaction references.

A successfully published post displayed an on-chain indicator and transaction reference. The reference opened the Monad explorer, where transaction details were displayed.

These checks did not constitute a complete smart-contract audit.

### 3.6 UX Testing

I documented situations where interface behaviour or product explanations could be clearer.

Examples included:

- Unclear Top feed ranking criteria.
- Image requirements during post creation.
- Comment-loading behaviour.
- Like-state feedback.
- Content deletion and permanence.
- Differences between displayed on-chain and database post counts.

These observations require classification against the intended product requirements before being treated as confirmed defects.

---

## 4. Test Environment

| Item | Details |
|---|---|
| Product | Monad Feet |
| Application URL | https://monadfeet.social/ |
| Testing Method | Manual testing |
| Testing Period | October 2026 |
| Tester | CryptoTester |
| Application Type | Web-based social application |
| Blockchain Context | Monad |
| Testing Focus | Functional behaviour, exploratory testing, selected on-chain interactions, and UX |
| Evidence | Application observations, screenshots where available, and selected transaction references |

The report reflects the application behaviour observed during the testing period.

The browser, device, operating-system version, and other environment details should only be added if they were recorded during testing.

---

## 5. Test Execution Strategy

### 5.1 Initial Application Exploration

The first stage involved navigating the application and identifying the available features.

The objective was to understand the main user journeys and establish which areas could be tested.

### 5.2 Core Functional Testing

The next stage focused on important application interactions, including post creation, comments, profile editing, search, discovery, messaging, and session handling.

### 5.3 Persistence Checks

Selected actions were followed by a page refresh to determine whether the expected state remained visible.

### 5.4 Selected Web3 Verification

Selected transaction references were opened in the Monad explorer to inspect the associated transaction information.

### 5.5 Observation and Risk Documentation

Unexpected or unclear behaviour was documented separately from successful test results.

Where the intended behaviour was not established, the finding remained an observation requiring clarification.

### 5.6 Retesting

Outstanding observations and incomplete user journeys should be revisited after the expected behaviour is clarified or relevant product changes are made.

---

## 6. Entry and Exit Criteria

### 6.1 Entry Criteria

Testing could begin when:

- The application was accessible.
- The required account and wallet access were available.
- The main application sections could be opened.
- The tester could exercise the selected user journeys.

### 6.2 Exit Criteria

The initial testing phase was considered complete when:

- The selected scenarios had been exercised.
- The observed results had been documented.
- Successful scenarios were distinguished from observations.
- Untested areas were identified.
- Potential product improvements were recorded.
- Outstanding questions and retest requirements were documented.

Completion of the initial testing phase does not mean that the entire application has been fully validated.

---

## 7. Risks and Mitigation

### Risk 1: Unclear Expected Behaviour

**Description:** Some application behaviours could not be conclusively classified because the intended requirements were not established.

**Examples:**
- Like-state behaviour.
- Comment-loading behaviour.
- Top feed ranking.
- Post deletion.
- Differences between post counts.

**Mitigation:** Obtain clarification from the product team and verify the behaviour against the agreed requirements.

### Risk 2: Incomplete Subscription Validation

**Description:** The complete subscription purchase, payment, content-access, expiry, and cancellation journeys were not fully tested.

**Mitigation:** Perform dedicated end-to-end testing before concluding that the monetisation system is fully validated.

### Risk 3: Transaction Failure Scenarios

**Description:** Successful selected transactions were inspected, but all wallet rejection, failure, timeout, and recovery scenarios were not tested.

**Mitigation:** Add controlled failure-path scenarios to the next testing cycle.

### Risk 4: Unverified Analytics and Metrics

**Description:** Creator analytics and displayed post counts were observed, but their underlying calculations were not independently verified.

**Mitigation:** Confirm metric definitions and compare displayed values with authoritative records.

### Risk 5: Evidence Gaps

**Description:** Not every observation may have a corresponding screenshot or independently verifiable technical record.

**Mitigation:** Capture relevant evidence during follow-up testing and maintain a consistent evidence register.

---

## 8. Test Status Definitions

The following classifications are used throughout the project documentation.

**PASS**

The tested behaviour worked as expected in the specific scenario exercised.

**OBSERVATION**

Behaviour was observed that may require clarification, investigation, or a UX improvement.

**PARTIAL**

Only part of the intended functionality or user journey was tested.

**NOT TESTED**

The scenario was not exercised during the documented testing engagement.

**CONFIRMED BUG**

A reproducible failure has been established against a known or agreed product requirement.

An observation should not be classified as a confirmed bug solely because the behaviour appears unusual.

---

## 9. Known Testing Observations

The initial testing identified the following areas for further review:

1. The Top feed ranking criteria were not immediately clear.
2. Some feed cards displayed unavailable-image messages.
3. The image requirement in post creation was not clearly communicated.
4. The visible like state changed temporarily and could return to its previous state.
5. Some comments required the Load comments control to be selected.
6. The post-deletion policy was not established.
7. The displayed on-chain post count differed from the database count.
8. The complete subscription and exclusive-content journeys were not validated.
9. The confirmation behaviour for blocking a member could be reviewed.

These are documented observations, not automatically confirmed defects.

---

## 10. Retesting Priorities

The following scenarios should be prioritised for further testing:

### Priority 1: Subscription and Exclusive Content

Validate subscription purchase, transaction outcomes, subscriber access, expiry, and cancellation where supported.

### Priority 2: Like-State Behaviour

Determine whether the displayed state accurately reflects the intended saved state.

### Priority 3: Post Deletion and Permanence

Confirm the deletion policy and verify how the application handles content that has an on-chain record.

### Priority 4: Post Count Discrepancy

Clarify the definitions used for on-chain and database post counts.

### Priority 5: Comment Loading

Verify the intended loading behaviour and whether the interface communicates it clearly.

### Priority 6: Transaction Failure Handling

Test selected rejected or failed transactions where safely available.

### Priority 7: Analytics and Ranking

Confirm the definitions and intended calculations used for creator metrics and feed ranking.

---

## 11. Deliverables and Evidence

The testing documentation is organised within the CryptoTester QA Lab repository.

The project includes:

- A Monad Feet QA case study.
- A Monad Feet test-case document.
- A Monad Feet exploratory-testing session.
- This test plan.
- Detailed results and observations in the main QA report.
- Product improvement recommendations.
- An evidence register and retest plan.

Actual screenshots and transaction references should be added where available.

No evidence should be represented as captured if it does not exist.

---

## 12. Final Test Plan Summary

This test plan defines the approach used to evaluate selected Monad Feet user journeys.

The initial engagement demonstrated successful behaviour across several core social interactions, profile functions, discovery features, messaging, session handling, and selected on-chain transaction-reference checks.

It also identified areas requiring further investigation, particularly like-state behaviour, comment loading, feed ranking, content permanence, post-count interpretation, and subscription validation.

The next testing cycle should focus on clarifying requirements, validating incomplete user journeys, gathering supporting evidence, and retesting outstanding observations.

The findings and conclusions remain limited to the scenarios exercised during the documented testing period.

---

**Prepared by CryptoTester**  
**CryptoTester QA Lab**
