# Monad Feet — Web3 QA Case Study

**Prepared by:** CryptoTester  
**Product:** Monad Feet  
**Application:** https://monadfeet.social/  
**Testing Period:** October 2026  
**Testing Type:** Manual QA, Functional Testing, Exploratory Testing, Web3 QA, and UX Testing  
**Project Status:** Initial testing completed; selected flows require further validation.

---

## 1. Project Overview

Monad Feet is a social application built around the Monad blockchain. Its features include social posts, creator profiles, exclusive content, subscriptions, direct messaging, likes, comments, points, daily check-ins, and selected on-chain interactions.

I conducted manual testing to evaluate the application's core functionality, examine user journeys, verify selected on-chain transaction references, document unexpected behaviour, and identify opportunities to improve the product.

The goal was to assess the application from both a functional QA perspective and a user's perspective.

## 2. Testing Objectives

The objectives of this engagement were to:

- Test major user journeys across the application.
- Evaluate social interactions, including posts and comments.
- Check whether selected actions persisted after refreshing the page.
- Examine profile editing and creator analytics.
- Verify selected on-chain transaction references.
- Inspect wallet-related functionality.
- Test search, discovery, trending, and leaderboard pages.
- Examine direct messaging and blocking.
- Identify potential usability and product-quality improvements.
- Document limitations and scenarios requiring further investigation.

## 3. Testing Scope

The following areas were included in the testing engagement:

- Landing page and navigation
- Signup and login session handling
- Home feed
- Post creation and exclusive-post settings
- Likes, comments, and replies
- Profiles and creator settings
- Creator analytics
- Wallet and on-chain activity
- Search and discovery
- Trending and leaderboard
- Notifications and daily check-in
- Direct messages and blocking
- Application settings
- Selected transaction references and explorer verification
- State persistence after refreshing the page

Testing depth varied by feature. Not every feature or possible scenario was fully validated.

## 4. Testing Methodology

### Functional Testing

I tested selected features to determine whether they performed their intended actions.

### Positive Testing

I exercised valid user journeys, including creating posts, publishing comments, editing profile information, and sending direct messages.

### Exploratory Testing

I explored the application to identify unexpected behaviour, unclear interface states, and opportunities for improvement.

### State Persistence Testing

I refreshed the application after selected actions to determine whether posts, comments, deleted comments, and sent messages retained their expected states.

### Web3 Testing

I examined selected wallet-related actions and opened transaction references in the Monad explorer.

### UX Testing

I documented areas where interface behaviour, product explanations, or user feedback could be clearer.

## 5. Key Results

The following flows worked during the documented tests:

- Creating an image-based post.
- Viewing a published post after refreshing the page.
- Publishing and deleting comments.
- Confirming comment changes after refreshing.
- Editing profile information.
- Accessing creator analytics.
- Searching for member profiles.
- Opening Discover, Trending, and Leaderboard.
- Completing the daily check-in using a wallet signature.
- Sending a direct message and confirming its persistence.
- Blocking and unblocking a member.
- Signing out and reconnecting to the application.
- Opening selected transaction references in the Monad explorer.

These results apply to the specific scenarios tested. They do not establish that every feature or edge case has been validated.

## 6. Key Observations

### 6.1 Like-State Behaviour

During testing, the visible like state temporarily changed and could later return to its previous state after waiting or refreshing.

The expected behaviour and underlying state-handling process require further investigation. This has not been classified as a confirmed defect.

### 6.2 Top Feed Ranking

The Latest feed displayed posts in newest-to-oldest order during the observed session. However, the ranking criteria used by the Top feed were not immediately understandable from the visible information.

Clarifying the general ranking criteria could improve transparency for users and creators.

### 6.3 Comment Loading

Some comments did not appear immediately in the initial post view. In certain instances, opening the comment section and selecting "Load comments" was necessary.

Clearer loading feedback could make this interaction easier to understand.

### 6.4 Post Creation Requirements

The caption field was labelled optional, but the Post & Sign button was not visible when I attempted to create a text-only post without selecting an image.

The interface could communicate the image requirement more clearly.

### 6.5 On-chain and Database Post Counts

The application displayed 63 posts on-chain, while the database count showed 75 posts.

The counting rules were not established during testing. The difference requires clarification before either figure can be classified as incorrect.

### 6.6 Post Deletion and Permanence

I did not identify a post-deletion option during the testing session.

The product team should clarify whether deletion is supported and explain the difference between removing content from the application and removing information recorded on-chain.

### 6.7 Subscription Validation

The creator subscription-price settings and exclusive-post controls were accessible. However, the complete subscription purchase, payment, content-access, expiry, and cancellation journeys were not fully tested.

Further end-to-end testing is required before the complete monetisation system can be considered validated.

## 7. On-chain Transaction Verification

A successfully published post displayed an on-chain indicator and transaction reference.

I opened the reference in the Monad explorer and inspected the transaction details. I also opened a selected wallet activity transaction reference.

These checks verified selected transaction references only. They do not constitute a complete smart-contract security audit or verification of every blockchain interaction used by the application.

## 8. Product Improvement Recommendations

Based on my testing and product analysis, I identified the following opportunities:

1. Improve clarity around wallet signatures and on-chain posting.
2. Explain post-creation requirements before users compose content.
3. Make feed-ranking criteria easier to understand.
4. Improve feedback for likes and comments.
5. Clarify content deletion and permanence.
6. Explain the difference between on-chain and database metrics.
7. Validate the complete subscription and exclusive-content journey.
8. Improve clarity around creator analytics.
9. Explain points and future-reward expectations accurately.
10. Improve transaction-status communication.

These are proposed product improvements based on my observations. They are not claims that every existing implementation is defective.

## 9. Testing Limitations

This engagement focused on manual product QA.

The testing did not include:

- A full smart-contract security audit.
- A source-code audit.
- Comprehensive backend or database verification.
- Load or stress testing.
- Full validation of subscription purchases, cancellation, and expiry.
- Exhaustive testing of transaction rejection and failure scenarios.

The findings reflect the scenarios exercised during the testing period.

## 10. Final Assessment

The testing demonstrated that several important Monad Feet user journeys worked during the documented scenarios, including post creation, comment management, profile editing, direct messaging, discovery, and selected on-chain interactions.

The main opportunities identified concern interaction consistency, product clarity, content permanence, creator monetisation, and the interpretation of on-chain information.

Some observations require further verification or product clarification before they can be classified as confirmed defects.

This case study documents my practical experience in manual QA testing, exploratory testing, Web3 product evaluation, selected on-chain transaction verification, test documentation, and UX-focused product analysis.

---

**Prepared by CryptoTester**  
**Repository:** CryptoTester QA Lab
