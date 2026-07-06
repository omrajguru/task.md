# TASK.md

## 0. Scope Tier
Select one: Minor / Standard / Major / System

Minor: copy change, style tweak, small bug fix, single component adjustment. Fill sections 1, 5, 6, 21 only.
Standard: new component, new page, new endpoint, existing flow change. Fill sections 1 through 12, plus 17, 18, 21.
Major: new module, checkout style flow, anything touching payments, auth, or user data at scale. Fill all sections.
System: cross service change, infra change, anything affecting multiple teams or products. Fill all sections plus a linked architecture doc.

## 1. Summary
Name:
One line description:
Owner:
Priority:
Reference links (design, screenshot, competitor app, existing PR):
Related tickets or dependencies on other teams:

## 2. Reference Material Handling
Elements to borrow from reference (layout pattern, interaction style):
Elements to leave aside from reference (their color palette, their font, their exact copy):
Existing components to reuse from this codebase:
Existing design tokens to follow (spacing scale, color scale, typography scale):
Areas where the reference conflicts with existing codebase conventions, and which convention wins:

## 3. Requirements and Non Goals
Functional requirements, listed explicitly:
Technical constraints (framework, library, performance budget):
Excluded from this task (features deliberately deferred to a later round):
Assumptions made where the request is ambiguous:

## 4. Data and State
New or changed data model fields:
Source of truth for this data (client cache, server, both):
Caching strategy and cache invalidation trigger:
Migration plan for existing records when the schema changes:
Conflict resolution when two sessions edit the same record:
Stale data handling (how old cached data gets refreshed):

## 5. UI and Layout States
Zero items state (empty array, blank result):
One item state:
Two item state:
Three or more item state (grid overflow, "plus N more" pattern):
Mixed media state (photo alongside video):
Video only state:
Photo only state, caption only state:
Long text handling (title, caption, username truncation and expansion):
Missing metadata handling (absent avatar, absent timestamp):
Broken or slow loading media handling:
Loading skeleton state:
Error state (failed fetch, failed submit):
Partial data state (some fields loaded, others still pending):
Dark mode and light mode:
Reduced motion preference:
Mobile layout:
Tablet layout:
Desktop layout:
Portrait versus landscape media handling:

## 6. Interaction and Logic
Repeat tap or double submit protection:
Debounce or throttle rules on frequent actions (typing, scrolling, dragging):
Undo or redo support for destructive actions:
Bulk selection and bulk action behavior:
Optimistic UI update followed by a failed server response, rollback behavior:
Pagination boundaries (first page, last page, single page total):
Empty result set after a filter or search:
Retry behavior after a network drop mid action:
Timezone and locale handling for any displayed date or time:
Draft or unsaved state persistence on navigation away:
Race condition when two actions target the same resource at once:

## 7. Content and Copy
Tone and voice reference:
Character limits per field, and truncation behavior at the limit:
Pluralization rules (one item versus many items):
Error message copy, written to reveal minimal internal detail:
Empty state copy:
Confirmation dialog copy for destructive actions:

## 8. Permissions and Roles
Roles that interact with this feature (guest, member, admin, owner):
Actions restricted per role:
Behavior when a user lacks permission for an action (hidden control versus disabled control versus explicit message):
Behavior for a logged out or guest user:

## 9. API and Backend Contract
Endpoints added or changed, with method and path:
Request and response shape:
Versioning approach, and backward compatibility with older clients:
Error codes returned, and what triggers each:
Timeout and retry policy:
Rate limit applied to this endpoint:

## 10. Security and Privacy
Auth check location, confirmed server side prior to any client side check:
Authorization check confirming the acting user owns or holds permission on the resource:
Input validation rules per field (length, allowed characters, format):
File upload limits (type, size, virus or content scanning):
Idempotency key or equivalent guard on payment or one time actions:
CSRF and session handling for any new form:
PII or sensitive data touched by this feature, and how it stays encrypted at rest and in transit:
Third party data sharing introduced by this feature:
Regulatory scope (GDPR, CCPA, HIPAA, or similar), if applicable:

## 11. Performance
Load time budget for this feature:
Bundle size impact:
Image and video optimization approach (compression, lazy loading, responsive sizes):
Database query cost, and indexing needs:
Infinite scroll or pagination performance at large data volume:

## 12. User Behavior Edge Cases
First time user with an empty account:
Power user with a very large data set (hundreds or thousands of items):
User on a slow or flaky connection:
User who navigates away and returns (back button, deep link, refresh):
Session expiry mid action:
Multiple browser tabs or devices open to the same account at once:
Permission denial from the user (camera, location, notifications):
Interrupted flow (phone call, app switch, tab close) mid task:

## 13. Accessibility
Screen reader labels for every interactive element:
Keyboard navigation path and focus order:
Color contrast ratio for text and interactive elements:
Captions or transcripts for video content:
Touch target size on mobile:

## 14. Internationalization and Localization
Text expansion allowance for translated strings:
Right to left layout support:
Date, number, and currency formatting per locale:
Timezone display rules:

## 15. Cross Platform and Device Compatibility
Browsers supported, with minimum version:
Operating systems and minimum device specs supported:
Responsive breakpoints list:
Behavior on very small screens and very large screens:

## 16. Third Party Dependencies
Libraries or services newly introduced:
Version constraints and licensing terms:
Behavior when the third party service is slow or down:
Cost implication of the new dependency:

## 17. Notifications and Communications
Emails, push notifications, or in app messages triggered by this feature:
Frequency and rate limiting of notifications:
Behavior when a notification fails to send:
User controls to opt out:

## 18. Analytics and Observability
Events to track, with property definitions:
Success metric this feature is measured against:
Logging added for debugging production issues:
Alerting threshold for error rate or latency:
Dashboard updated to reflect this feature:

## 19. Testing Plan
Unit tests covering core logic:
Integration tests covering the full flow:
Edge case test list, mapped to sections 5, 6, and 12 above:
Manual QA checklist:
Load testing plan, if relevant:

## 20. Rollout and Deployment
Feature flag plan and default state:
Staged rollout percentage and timeline:
Rollback plan if a critical issue appears post launch:
Backward compatibility maintained during the deploy window:
Internal or external documentation updated as part of this launch:

## 21. Acceptance Checklist
- [ ] All UI states in Section 5 verified at all breakpoints
- [ ] All logic edge cases in Section 6 handled
- [ ] Permissions in Section 8 enforced correctly per role
- [ ] Security checklist in Section 10 satisfied
- [ ] Performance budget in Section 11 met
- [ ] Accessibility checklist in Section 13 satisfied
- [ ] Feature matches existing codebase conventions
- [ ] Reference material rules from Section 2 followed
- [ ] Analytics events in Section 18 firing correctly
- [ ] Rollout plan in Section 20 confirmed with the team
