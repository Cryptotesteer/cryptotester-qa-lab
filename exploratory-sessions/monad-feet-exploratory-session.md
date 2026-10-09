# Monad Feet - Exploratory Testing Session

**Tester:** CryptoTester  
**Product:** Monad Feet  
**Application:** https://monadfeet.social/  
**Testing Period:** October 2026  
**Testing Type:** Manual Exploratory Testing, Functional Testing, Web3 QA, and UX Testing

---

## 1. Session Objective

The objective of this exploratory testing session was to investigate Monad Feet's core user journeys, observe how its features behaved during real interactions, identify unexpected behaviour, and document opportunities to improve the user experience.

The session covered social interactions, post creation, profile settings, creator features, wallet interactions, selected on-chain transaction references, discovery, direct messaging, notifications, and session handling.

Testing was exploratory. The observations recorded here reflect the scenarios exercised and are not automatically confirmed software defects.

## 2. Areas Explored

The following areas were explored:

- Landing page and navigation
- Home feed and feed switching
- Post creation and exclusive-post settings
- Likes, comments, and replies
- Profile editing
- Creator subscription settings and analytics
- Wallet information and selected on-chain activity
- Search and discovery
- Trending and leaderboard
- Notifications and daily check-in
- Direct messages and blocking
- Application settings
- Sign-out and reconnection

## 3. Session Findings

### ES-001: Latest Feed Ordering

**Area:** Home Feed

**Observation:**
The Latest feed displayed posts in newest-to-oldest order during the observed session.

**Result:**
The feed view worked as expected in the tested scenario.

**Classification:** Passed scenario

### ES-002: Top Feed Ranking Clarity

**Area:** Home Feed

**Observation:**
The ordering of posts in the Top feed was not immediately understandable from the visible engagement information.

**Potential Impact:**
Users and creators may find it difficult to understand how content is ranked.

**Recommendation:**
Clarify the general ranking criteria used by the Top feed.

**Classification:** UX observation; ranking logic not independently verified

### ES-003: Unavailable Post Images

**Area:** Home Feed

**Observation:**
Some cards displayed the message: "Image unavailable. Open the post to check access."

**Potential Impact:**
Users may be uncertain whether the content is restricted or unavailable for another reason.

**Recommendation:**
Ensure the message clearly communicates the reason for the unavailable image where possible.

**Classification:** Observation; underlying cause not established

### ES-004: Post Creation Requirements

**Area:** Post Creation

**Observation:**
The caption field was labelled optional, but the Post & Sign button was not visible when text was entered without selecting an image.

**Potential Impact:**
Users may not understand why they cannot proceed with publishing.

**Recommendation:**
Clearly communicate the image requirement before users compose a post.

**Classification:** UX observation

### ES-005: Image-Based Post Publication

**Area:** Post Creation

**Observation:**
An image-based post was published successfully after the required wallet signature.

The published post remained visible after refreshing the page.

**Result:**
The tested publication and persistence scenarios worked.

**Classification:** Passed scenarios

### ES-006: Exclusive-Post Toggle

**Area:** Exclusive Content

**Observation:**
The Make Exclusive toggle worked and displayed an explanation that only verified subscribers could see the post, while others would see a locked preview.

**Result:**
The toggle interaction and explanatory message were observed.

**Limitation:**
The complete subscriber-access journey was not validated.

**Classification:** Passed interface interaction; access flow not fully tested

### ES-007: Like-State Behaviour

**Area:** Social Interactions

**Observation:**
The visible like state temporarily disappeared or entered a loading state. The previous state could return after waiting or refreshing.

**Potential Impact:**
Users may be uncertain whether their interaction succeeded.

**Recommendation:**
Investigate the expected state-handling behaviour and improve feedback for pending, successful, and unsuccessful actions.

**Classification:** Requires further verification

### ES-008: Comment Publication and Deletion

**Area:** Comments

**Observation:**
A comment was published successfully and remained after refresh. Deleting the comment also worked, and the deleted comment remained absent after refresh.

**Result:**
The tested comment publication, persistence, deletion, and deletion-persistence scenarios worked.

**Classification:** Passed scenarios

### ES-009: Comment Loading

**Area:** Comments

**Observation:**
Some comments did not appear immediately in the initial post view. In certain instances, opening the comment section and selecting Load comments was necessary.

**Potential Impact:**
Users may assume that a post has no comments when comments have not yet loaded.

**Recommendation:**
Clarify loading states and ensure the comment interface communicates when additional action is required.

**Classification:** UX observation; expected loading behaviour requires clarification

### ES-010: Profile Editing

**Area:** Profile

**Observation:**
The Edit Profile interface opened and displayed fields for profile picture, display name, username, and bio. Saving changes required a wallet signature.

**Result:**
The profile-editing flow was exercised.

**Classification:** Passed scenario

### ES-011: Creator Analytics

**Area:** Creator Features

**Observation:**
Creator Analytics displayed subscriber count, monthly revenue, total revenue, private posts, and top posts by likes.

**Result:**
The analytics interface was accessible.

**Limitation:**
The underlying accuracy of the displayed metrics was not independently verified.

**Classification:** Passed interface-access scenario

### ES-012: On-Chain Post Reference

**Area:** Web3 Interaction

**Observation:**
A successfully published post displayed an on-chain indicator and transaction reference. Opening the reference led to the Monad explorer, where transaction details were displayed.

**Result:**
The selected transaction-reference navigation worked.

**Classification:** Passed selected transaction-reference check

### ES-013: Difference in Post Counts

**Area:** On-Chain Information

**Observation:**
The application displayed 63 posts on-chain, while the database count showed 75 posts.

**Potential Impact:**
Users may be uncertain about the meaning of the two figures if their definitions are not clear.

**Recommendation:**
Clarify the counting rules and labels for both metrics.

**Classification:** Requires product clarification; no defect confirmed

### ES-014: Search and Discovery

**Area:** Discovery

**Observation:**
Search returned matching member profiles. Discover, Trending, and Leaderboard pages also loaded during testing.

**Result:**
The tested discovery interfaces were accessible.

**Classification:** Passed scenarios

### ES-015: Direct Messaging

**Area:** Messaging

**Observation:**
The Messages page initially displayed an empty state. A Message button was available from another member's profile. A direct message was sent successfully and remained visible after refresh.

**Result:**
The tested direct-message and persistence scenarios worked.

**Classification:** Passed scenarios

### ES-016: Blocking Behaviour

**Area:** Member Controls

**Observation:**
The Block control changed state without displaying a confirmation prompt. The available unblock control returned the interface to the unblocked state.

**Potential Impact:**
A user may block another member accidentally.

**Recommendation:**
Consider whether a confirmation prompt or clearer feedback would improve the experience.

**Classification:** UX observation

### ES-017: Daily Check-In

**Area:** Engagement Features

**Observation:**
The daily check-in was completed using the required wallet signature.

**Result:**
The tested check-in scenario worked.

**Classification:** Passed scenario

### ES-018: Sign-Out and Reconnection

**Area:** Session Handling

**Observation:**
Signing out returned the user to the public landing page, which displayed an option to connect and sign in. Reconnection was subsequently confirmed.

**Result:**
The tested sign-out and reconnection scenarios worked.

**Classification:** Passed scenarios

## 4. Areas Requiring Further Testing

The following scenarios were not fully validated during this session:

- Complete subscription purchase and payment confirmation
- Subscriber access to exclusive content
- Subscription expiry and cancellation
- Failed or rejected subscription transactions
- Wallet transaction rejection and recovery scenarios
- The underlying calculation of creator analytics
- The rules used to calculate on-chain and database post counts
- The intended behaviour of the Top feed ranking system
- The actual post-deletion policy

These areas require additional testing or clarification before definitive conclusions can be made.

## 5. Exploratory Testing Summary

The exploratory session covered multiple core areas of Monad Feet and demonstrated successful behaviour across several social, profile, discovery, messaging, session-handling, and selected on-chain scenarios.

The session also identified areas where the product could communicate its behaviour more clearly, particularly around feed ranking, comment loading, post requirements, like-state feedback, content permanence, and on-chain metrics.

The observations provide a basis for further verification and product improvement. They should not be treated as confirmed defects unless subsequent testing establishes a violation of the intended requirements.

---

**Prepared by CryptoTester**
