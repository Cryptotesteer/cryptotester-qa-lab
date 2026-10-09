# Monad Feet - Test Cases

**Tester:** CryptoTester  
**Product:** Monad Feet  
**Application:** https://monadfeet.social/  
**Testing Period:** October 2026  
**Testing Type:** Manual Functional Testing, Exploratory Testing, Web3 QA, and UX Testing

---

## 1. Purpose

This document records test cases exercised during the manual QA testing of Monad Feet.

The objective is to document the steps performed, the expected behaviour, the actual observations, and the resulting status.

The test cases cover social interactions, post creation, profiles, creator features, wallet interactions, selected on-chain transactions, discovery, messaging, and session handling.

**Status definitions:**
- **PASS:** The tested behaviour worked as expected in the scenario exercised.
- **OBSERVATION:** Behaviour requiring clarification or further investigation.
- **PARTIAL:** Only part of the intended flow was tested.
- **NOT TESTED:** The scenario was not fully exercised during this engagement.

An observation is not automatically a confirmed bug. Expected behaviour must be established before a defect can be confirmed.

---

## 2. Home Feed and Navigation

### TC-001: Open the Home Feed

**Objective:** Verify that the home feed loads.

**Steps:**
1. Open Monad Feet.
2. Navigate to the home feed.
3. Observe the displayed content.

**Expected Result:** The home feed loads and displays available posts.

**Actual Result:** The home feed loaded during testing.

**Status:** PASS

### TC-002: Switch Between Latest and Top

**Objective:** Verify that users can switch between the available feed views.

**Steps:**
1. Open the home feed.
2. Select Latest.
3. Observe the post ordering.
4. Select Top.
5. Observe the displayed ordering.

**Expected Result:** Both feed views should open and display their respective content.

**Actual Result:** Switching between Latest and Top worked without an observed navigation error. Latest displayed posts in newest-to-oldest order during the observed session. The ranking criteria for Top were not immediately clear.

**Status:** PASS — Navigation; OBSERVATION — Top ranking clarity

### TC-003: Inspect Unavailable Image Cards

**Objective:** Record how the feed displays posts whose images are unavailable in the current view.

**Steps:**
1. Open the home feed.
2. Locate a post displaying an unavailable-image message.
3. Record the displayed message.

**Expected Result:** The application should communicate the image's availability or access state clearly.

**Actual Result:** Some cards displayed: "Image unavailable. Open the post to check access."

**Status:** OBSERVATION

**Follow-up:** Confirm whether the message results from access restrictions or another intended behaviour.

---

## 3. Post Creation and Management

### TC-004: Open the Post Creator

**Objective:** Verify that the post creator opens.

**Steps:**
1. Open the application.
2. Select the plus button.
3. Inspect the post-creation interface.

**Expected Result:** The post creator opens and displays the available controls.

**Actual Result:** The post creator opened successfully.

**Status:** PASS

### TC-005: Attempt to Create a Text-Only Post

**Objective:** Observe the publishing interface when no image is selected.

**Steps:**
1. Open the post creator.
2. Enter a caption.
3. Do not select an image.
4. Observe the available publishing controls.

**Expected Result:** The interface should clearly communicate the requirements for publishing a post.

**Actual Result:** The Post & Sign button was not visible when text was entered without selecting an image. The caption field was labelled optional, but the image requirement was not clearly explained.

**Status:** OBSERVATION

### TC-006: Create an Image-Based Post

**Objective:** Verify that a post containing an image can be published.

**Steps:**
1. Open the post creator.
2. Select an image.
3. Enter a caption where required or desired.
4. Initiate publication.
5. Complete the requested wallet signature.
6. Observe the result.

**Expected Result:** The application should publish the post after the required steps are completed successfully.

**Actual Result:** The image-based post was published successfully after the wallet signature.

**Status:** PASS

### TC-007: Verify Post Persistence After Refresh

**Objective:** Determine whether a published post remains visible after refreshing.

**Steps:**
1. Publish an image-based post.
2. Refresh the application.
3. Locate the published post.

**Expected Result:** The published post remains visible after refresh.

**Actual Result:** The post remained visible after refreshing.

**Status:** PASS

### TC-008: Inspect Exclusive-Post Controls

**Objective:** Verify the behaviour of the exclusive-content toggle.

**Steps:**
1. Open the post creator.
2. Enable Make Exclusive.
3. Read the displayed explanation.
4. Disable the toggle.
5. Observe the interface.

**Expected Result:** The toggle should change state and communicate the intended access restriction.

**Actual Result:** The toggle worked. When enabled, the interface displayed: "Only verified subscribers can see this post; others see a locked preview."

**Status:** PASS — Toggle interaction

**Limitation:** Subscriber access to exclusive content was not fully validated.

### TC-009: Cancel and Reopen the Post Creator

**Objective:** Observe the state of the creator after cancelling an unfinished post.

**Steps:**
1. Open the post creator.
2. Begin composing a post.
3. Cancel the operation.
4. Reopen the creator.
5. Inspect the form.

**Expected Result:** The reopened form should follow the application's intended reset or draft-retention behaviour.

**Actual Result:** The form reopened cleanly rather than retaining the previous unfinished content.

**Status:** PASS — Observed behaviour

### TC-010: Inspect Post Deletion

**Objective:** Determine whether a published post can be deleted through the available interface.

**Steps:**
1. Open a published post.
2. Inspect the available post actions.
3. Look for a deletion control.

**Expected Result:** The available controls should match the product's documented deletion policy.

**Actual Result:** A post-deletion option was not identified during testing.

**Status:** OBSERVATION

**Follow-up:** Confirm the deletion policy with the product team. This test does not establish that deletion is impossible.

---

## 4. Likes, Comments and Replies

### TC-011: Publish a Comment

**Objective:** Verify that a comment can be published.

**Steps:**
1. Open another member's post.
2. Open the comment section.
3. Enter a comment.
4. Submit the comment.
5. Observe the result.

**Expected Result:** The comment should be published and displayed.

**Actual Result:** The comment was published successfully without a wallet signature in the tested scenario.

**Status:** PASS

### TC-012: Verify Comment Persistence

**Objective:** Check whether a published comment remains after refresh.

**Steps:**
1. Publish a comment.
2. Refresh the page.
3. Reopen the relevant post or comment section.
4. Locate the comment.

**Expected Result:** The published comment remains available.

**Actual Result:** The comment remained after refreshing.

**Status:** PASS

### TC-013: Delete a Comment

**Objective:** Verify that a published comment can be deleted.

**Steps:**
1. Locate a published comment.
2. Use the available deletion control.
3. Observe the result.

**Expected Result:** The selected comment should be deleted according to the application's intended behaviour.

**Actual Result:** The comment was deleted successfully.

**Status:** PASS

### TC-014: Verify Comment Deletion After Refresh

**Objective:** Determine whether a deleted comment remains deleted after refresh.

**Steps:**
1. Delete a comment.
2. Refresh the page.
3. Reopen the relevant comment section.
4. Check whether the comment is still present.

**Expected Result:** The deleted comment should remain deleted.

**Actual Result:** The deleted comment remained absent after refresh.

**Status:** PASS

### TC-015: Inspect Comment Loading

**Objective:** Observe how comments are retrieved and displayed.

**Steps:**
1. Open a post containing comments.
2. Observe the initial comment view.
3. If comments are not displayed, open the comment section.
4. Select Load comments where available.
5. Observe the result.

**Expected Result:** The interface should clearly communicate comment-loading behaviour.

**Actual Result:** In some instances, comments appeared only after opening the comment section and selecting Load comments.

**Status:** OBSERVATION

### TC-016: Inspect Like-State Behaviour

**Objective:** Observe how the interface responds to a like action.

**Steps:**
1. Open a post.
2. Interact with the like control.
3. Observe the immediate state.
4. Wait and observe any subsequent changes.
5. Refresh if necessary and compare the displayed state.

**Expected Result:** The displayed state should consistently reflect the intended saved behaviour and communicate pending actions clearly.

**Actual Result:** The visible like state temporarily disappeared or entered a loading state. The previous state could return after waiting or refreshing.

**Status:** OBSERVATION

**Follow-up:** Verify the expected behaviour and underlying state handling before classifying this as a defect.

---

## 5. Profile and Creator Features

### TC-017: Open Edit Profile

**Objective:** Verify that the profile editor is accessible.

**Steps:**
1. Open the relevant profile.
2. Select Edit Profile.
3. Inspect the available fields.

**Expected Result:** The profile editor opens and displays the available profile fields.

**Actual Result:** The editor opened and displayed fields for profile picture, display name, username, and bio.

**Status:** PASS

### TC-018: Save Profile Changes

**Objective:** Verify that profile changes can be saved.

**Steps:**
1. Open Edit Profile.
2. Enter the intended profile changes.
3. Initiate saving.
4. Complete the requested wallet signature.
5. Observe the result.

**Expected Result:** The application should complete the save operation according to its intended workflow.

**Actual Result:** Saving profile changes required a wallet signature.

**Status:** PASS — Save flow exercised

**Limitation:** Every possible profile validation and failure scenario was not tested.

### TC-019: Open Creator Subscription Settings

**Objective:** Verify that the creator subscription-price settings are accessible.

**Steps:**
1. Open the relevant creator settings.
2. Open the subscription-price interface.
3. Inspect the price field, slider, and presets.

**Expected Result:** The settings interface should display the available subscription controls.

**Actual Result:** The monthly price field, slider, and preset values were accessible. Presets ranged from 10 MON to 5,000 MON, and the interface displayed a maximum of 8,000 MON.

**Status:** PASS — Interface accessibility

**Limitation:** Saving every permitted price and completing a subscription purchase were not verified.

### TC-020: Open Creator Analytics

**Objective:** Verify that creator analytics are accessible.

**Steps:**
1. Open Creator Analytics.
2. Inspect the displayed metrics.

**Expected Result:** The analytics page opens and displays available creator information.

**Actual Result:** The page displayed subscriber count, monthly revenue, total revenue, private posts, and top posts by likes.

**Status:** PASS — Interface accessibility

**Limitation:** The underlying accuracy of the metrics was not independently verified.

---

## 6. Wallet and On-Chain Activity

### TC-021: Inspect Wallet Information

**Objective:** Verify that wallet information is displayed.

**Steps:**
1. Open the wallet section.
2. Inspect the displayed MON balance.
3. Inspect the points balance.
4. Check the connected wallet address.

**Expected Result:** The wallet interface displays the available wallet information.

**Actual Result:** MON balance, points, and connected wallet information were displayed.

**Status:** PASS — Displayed information

**Limitation:** This does not establish that every balance calculation or wallet operation has been validated.

### TC-022: Verify a Published Post's Transaction Reference

**Objective:** Verify that a selected published post's transaction reference opens the Monad explorer.

**Steps:**
1. Publish an image-based post.
2. Locate the on-chain indicator and transaction reference.
3. Open the reference.
4. Inspect the explorer page.

**Expected Result:** The reference opens the corresponding explorer page and displays transaction details.

**Actual Result:** The transaction reference opened the Monad explorer and displayed transaction details.

**Status:** PASS — Selected transaction reference

### TC-023: Open a Wallet Activity Transaction

**Objective:** Verify that a selected wallet activity transaction reference is accessible.

**Steps:**
1. Open wallet activity.
2. Select a transaction reference.
3. Inspect the explorer page.

**Expected Result:** The reference opens the relevant explorer page.

**Actual Result:** The selected wallet activity transaction opened the corresponding explorer page.

**Status:** PASS — Selected transaction reference

### TC-024: Compare On-Chain and Database Post Counts

**Objective:** Document the displayed post counts and identify whether their definitions are clear.

**Steps:**
1. Open the relevant on-chain information page.
2. Record the displayed on-chain post count.
3. Compare it with the database count observed during testing.

**Expected Result:** The metrics should follow their intended definitions and be understandable to users.

**Actual Result:** The observed on-chain count was 63 posts, while the database count was 75 posts.

**Status:** OBSERVATION

**Follow-up:** Confirm what each count represents before determining whether the difference is incorrect.

---

## 7. Search, Discovery and Rankings

### TC-025: Search for Member Profiles

**Objective:** Verify that member search returns matching profiles.

**Steps:**
1. Open search.
2. Search for a member.
3. Inspect the returned results.

**Expected Result:** Matching member profiles should be displayed when available.

**Actual Result:** Search returned matching member profiles during testing.

**Status:** PASS

### TC-026: Inspect Search Filters

**Objective:** Verify access to the available search filters.

**Steps:**
1. Open search.
2. Inspect the available filters.
3. Use the member and post filters.

**Expected Result:** The available filters should be accessible.

**Actual Result:** Member and post filters were accessible.

**Status:** PASS — Filter accessibility

### TC-027: Open Discover

**Objective:** Verify that the Discover page loads.

**Steps:**
1. Navigate to Discover.
2. Inspect the displayed content.

**Expected Result:** The page opens and displays available discovery information.

**Actual Result:** Discover loaded and displayed member and activity information, including online members, profiles, streaks, posts, likes, and points.

**Status:** PASS

### TC-028: Open Trending

**Objective:** Verify that the Trending page loads.

**Steps:**
1. Navigate to Trending.
2. Inspect the displayed content.

**Expected Result:** The page opens and displays trending content.

**Actual Result:** Trending loaded successfully.

**Status:** PASS

### TC-029: Open Leaderboard

**Objective:** Verify that the leaderboard is accessible.

**Steps:**
1. Navigate to Leaderboard.
2. Inspect the displayed rankings and points.

**Expected Result:** The leaderboard loads and displays available rankings.

**Actual Result:** The leaderboard loaded and displayed rankings and points.

**Status:** PASS — Interface accessibility

**Limitation:** Ranking calculations and points accuracy were not independently verified.

---

## 8. Notifications and Daily Check-In

### TC-030: Open Notifications

**Objective:** Verify that notifications are accessible.

**Steps:**
1. Open notifications.
2. Inspect unread notification information and available badges.

**Expected Result:** The notification interface opens and displays available notifications.

**Actual Result:** Notifications loaded. Unread notification information, badges, and invite-code reward information were displayed.

**Status:** PASS — Interface accessibility

### TC-031: Complete Daily Check-In

**Objective:** Verify that the daily check-in can be completed through the available workflow.

**Steps:**
1. Open the daily check-in feature.
2. Initiate the check-in.
3. Complete the requested wallet signature.
4. Observe the result.

**Expected Result:** The check-in completes according to the application's intended workflow.

**Actual Result:** The daily check-in was completed using an on-chain transaction signature.

**Status:** PASS — Tested scenario

**Limitation:** Duplicate attempts, streak boundaries, rejected transactions, and points-calculation scenarios were not fully tested.

---

## 9. Direct Messages and Blocking

### TC-032: Open the Messages Page

**Objective:** Inspect the Messages page.

**Steps:**
1. Open Messages.
2. Observe the initial state.

**Expected Result:** The page should display existing conversations or an appropriate empty state.

**Actual Result:** The page initially displayed an empty state. A Message button was available from another member's profile.

**Status:** PASS — Page accessibility; OBSERVATION — Initial empty state

### TC-033: Send a Direct Message

**Objective:** Verify that a direct message can be sent.

**Steps:**
1. Open another member's profile.
2. Select Message.
3. Enter a message.
4. Send it.
5. Observe the conversation.

**Expected Result:** The message should be sent and displayed in the conversation.

**Actual Result:** The direct message was sent successfully.

**Status:** PASS

### TC-034: Verify Message Persistence

**Objective:** Check whether a sent message remains after refresh.

**Steps:**
1. Send a direct message.
2. Refresh the application.
3. Reopen the conversation.
4. Locate the message.

**Expected Result:** The sent message remains visible.

**Actual Result:** The message remained visible after refreshing.

**Status:** PASS

### TC-035: Block and Unblock a Member

**Objective:** Observe the available blocking controls.

**Steps:**
1. Open a member profile.
2. Select Block.
3. Observe the button state.
4. Use the available unblock control.
5. Observe the resulting state.

**Expected Result:** The interface should communicate the resulting block state and allow the supported reversal action.

**Actual Result:** The control changed to a blocked state, and the available unblock control returned the interface to the unblocked state. No confirmation prompt appeared during the tested blocking interaction.

**Status:** PASS — Control interaction; OBSERVATION — Confirmation behaviour

**Limitation:** All effects of blocking on messaging, visibility, and existing conversations were not tested.

---

## 10. Session Handling

### TC-036: Sign Out

**Objective:** Verify the result of signing out.

**Steps:**
1. Open the authenticated application.
2. Select Sign Out.
3. Observe the resulting page.

**Expected Result:** The application ends the authenticated session and displays the intended public or signed-out state.

**Actual Result:** Signing out returned the user to the public landing page, which displayed an option to connect and sign in.

**Status:** PASS

### TC-037: Reconnect After Sign-Out

**Objective:** Verify that the user can reconnect after signing out.

**Steps:**
1. Sign out.
2. Select the available connect/sign-in option.
3. Complete the reconnection process.
4. Observe the result.

**Expected Result:** The user can reconnect through the supported workflow.

**Actual Result:** Reconnection was confirmed during testing.

**Status:** PASS

---

## 11. Subscription and Exclusive-Content Scenarios Requiring Testing

The following scenarios were not fully validated during this engagement. They must not be marked as passed until they have been exercised.

### TC-038: Complete a Subscription Purchase

**Status:** NOT TESTED — End-to-end validation required.

Scenarios to exercise:
- Open a creator's subscription page.
- Review the price and terms.
- Initiate a subscription.
- Complete the required wallet approval or transaction.
- Verify the final transaction status.
- Confirm the resulting subscription state.

### TC-039: Verify Exclusive-Content Access

**Status:** NOT TESTED — End-to-end validation required.

Scenarios to exercise:
- Publish or locate an exclusive post.
- Check the view available to a verified subscriber.
- Check the view available to a non-subscriber.
- Verify whether access matches the product's intended rules.

### TC-040: Test Subscription Cancellation and Expiry

**Status:** NOT TESTED — Requires confirmation of supported functionality.

Scenarios to exercise:
- Confirm whether cancellation is supported.
- Complete the available cancellation flow.
- Verify the resulting subscription state.
- Check access after expiry or cancellation according to the documented rules.

### TC-041: Test Rejected or Failed Subscription Transactions

**Status:** NOT TESTED.

Scenarios to exercise:
- Reject a wallet request where safely available.
- Observe the application response.
- Check whether the interface communicates the failure.
- Confirm that subscription access and payment state remain consistent with the transaction outcome.

---

## 12. Testing Summary

The documented tests confirmed successful behaviour for several important user journeys, including image-based post creation, comment management, profile editing, search, discovery, direct messaging, session handling, and selected transaction-reference verification.

Several observations require further investigation or product clarification, particularly like-state behaviour, comment loading, Top feed ranking, post requirements, post permanence, and the difference between displayed on-chain and database post counts.

The complete subscription and exclusive-content journey remains insufficiently tested.

This document records the scenarios actually exercised and distinguishes successful results from observations and untested flows.

**Prepared by CryptoTester**
