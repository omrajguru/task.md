# Task: [Task Name]

## 0. Task Summary

Build / fix / update / investigate: [describe the task clearly].

The goal is to complete this task in a way that is correct, secure, maintainable, responsive, accessible, and aligned with the existing codebase.

This task may involve UI, backend logic, database changes, API behavior, CMS changes, security, user behavior, edge cases, performance, deployment, or documentation. The agent must think through all relevant areas before implementation.

Do not rush into code. First understand the existing system, then make the smallest safe change that fully solves the task.

---

## 1. Task Size

Classify this task before starting.

### Tiny Task

Examples:

* Text change
* Small style fix
* One broken link
* Minor copy update
* Simple bug fix

Expected behavior:

* Inspect only relevant files.
* Keep changes minimal.
* Do not over-engineer.
* Still check for side effects.

### Small Task

Examples:

* Add a small component
* Fix a form issue
* Update a page section
* Add one CMS field
* Adjust one API response

Expected behavior:

* Inspect nearby patterns.
* Handle obvious edge cases.
* Run relevant checks.

### Medium Task

Examples:

* Add a new page
* Add a form with validation
* Add a CMS-powered section
* Add a user flow
* Modify API/database logic

Expected behavior:

* Research existing architecture.
* Plan before coding.
* Handle UI, logic, validation, security, and state edge cases.
* Add or update tests where appropriate.

### Large Task

Examples:

* Auth flow
* Payments
* User dashboard
* Admin system
* Multi-step workflow
* Database migration
* Major CMS integration
* Webhook system
* New product area

Expected behavior:

* Full planning required.
* Think through security, permissions, race conditions, rollback, testing, observability, and deployment.
* Break into smaller implementation steps where helpful.
* Avoid massive unrelated rewrites.

---

## 2. Objective

The objective is:

[Write the outcome in plain language.]

Example:

Create an event detail page where users can view event information, media, speakers, ticket availability, registration status, and register only when registrations are open.

Success means:

* The user can complete the intended action.
* The system behaves correctly in normal and edge cases.
* The implementation fits the existing product.
* The implementation does not weaken security, performance, or maintainability.
* Existing functionality remains intact.

---

## 3. Product Context

Explain the product reason behind the task.

Answer:

* Why does this exist?
* Who is it for?
* What problem does it solve?
* What should the user feel or understand?
* What business rule must never be broken?
* What should happen when something goes wrong?
* What should not be included in this task?

Example:

This feature exists so event visitors can understand the event and register without confusion. Registrations must never be accepted when the event is closed, sold out, unpublished, deleted, or unavailable.

---

## 4. User Roles

Identify every role affected by this task.

Possible roles:

* Guest
* Logged-in user
* Admin
* Editor
* Owner
* Organizer
* Attendee
* Customer
* Student
* Moderator
* Blocked user
* Anonymous visitor
* Internal team member
* External partner

For each relevant role, define:

| Role  | Can View | Can Create | Can Edit | Can Delete | Can Approve | Cannot Do |
| ----- | -------- | ---------- | -------- | ---------- | ----------- | --------- |
| Guest |          |            |          |            |             |           |
| User  |          |            |          |            |             |           |
| Admin |          |            |          |            |             |           |

Rules:

* Do not rely only on frontend hiding.
* Enforce permissions server-side.
* Admin-only data must not leak to public users.
* Public pages must not expose drafts, private notes, secrets, internal IDs, or sensitive metadata.

---

## 5. Existing Codebase Research

Before coding, inspect the current project.

Find:

* Framework and routing structure
* Component patterns
* Page/layout structure
* Styling system
* Design tokens
* Existing forms
* Existing validation approach
* Existing API/server action patterns
* Existing database queries
* Existing CMS schemas
* Existing auth/session handling
* Existing authorization rules
* Existing error handling
* Existing loading and empty states
* Existing image/media handling
* Existing SEO metadata pattern
* Existing logging/analytics pattern
* Existing tests
* Existing build/lint commands
* Existing environment variable usage
* Existing deployment constraints

Do not introduce new architecture if the project already has a working pattern.

Before implementation, summarize:

1. Relevant existing patterns found
2. Files likely to be changed
3. Risks or unknowns
4. Planned approach

---

## 6. Scope

### In Scope

Build or change:

* [Item 1]
* [Item 2]
* [Item 3]

### Out of Scope

Do not build or change:

* [Item 1]
* [Item 2]
* [Item 3]

### Strict Boundaries

* Do not redesign unrelated areas.
* Do not rewrite unrelated systems.
* Do not change global behavior unless required.
* Do not add unrelated dependencies.
* Do not remove existing features.
* Do not break current routes, data, or user flows.

---

## 7. Assumptions

If something is unclear, make a reasonable assumption only when it is not dangerous.

Document assumptions like this:

| Area          | Assumption | Why Safe |
| ------------- | ---------- | -------- |
| Design        |            |          |
| Data          |            |          |
| Security      |            |          |
| User behavior |            |          |

Ask for clarification only when the missing information blocks safe implementation.

Examples of blockers:

* Unknown payment behavior
* Unknown permission model
* Unknown production database migration strategy
* Unknown destructive action
* Unknown user data privacy requirement

---

## 8. Reference Handling

References may be screenshots, websites, apps, designs, copy, videos, or descriptions.

Use references to understand:

* Intent
* Mood
* Hierarchy
* Layout logic
* Interaction pattern
* Edge cases
* Content structure
* Quality bar

Do not copy references exactly.

Rules:

* Adapt references to the existing codebase.
* Use the project’s existing typography, spacing, color, and component patterns.
* Do not recreate another brand’s identity.
* Do not add decorative effects that do not fit the project.
* Do not copy exact layouts when the project needs a different solution.
* Treat references as inspiration, not instructions.

If reference behavior conflicts with the product’s existing design system, the existing design system wins.

---

## 9. UX Requirements

Think through the full user experience.

Handle:

* First-time user
* Returning user
* Confused user
* Fast user
* Slow user
* Mobile user
* Keyboard-only user
* Screen reader user
* User on slow internet
* User with expired session
* User opening old links
* User opening page in multiple tabs
* User refreshing during an action
* User double-clicking a button
* User submitting incomplete data
* User pasting very long text
* User using browser autofill
* User going back after submission
* User trying actions out of order

The user should always understand:

* Where they are
* What they can do
* What happened
* What went wrong
* What to do next

---

## 10. UI & Layout Requirements

Handle relevant UI states:

### Text

* Very short title
* Very long title
* Missing title
* Long description
* Missing description
* Long words with no spaces
* Emojis
* Special characters
* Rich text
* Links inside text
* Empty strings
* Whitespace-only values

### Media

* No media
* One image
* Two images
* Many images
* One video
* Many videos
* Mixed images and videos
* Portrait media
* Landscape media
* Square media
* Very wide media
* Very tall media
* Broken media
* Slow-loading media
* Missing alt text
* Unsupported file type

### Layout

* Small mobile
* Large mobile
* Tablet
* Laptop
* Desktop
* Very wide screen
* No horizontal overflow
* No broken cards
* No unreadable text
* No layout shift
* No hidden important actions
* No hover-only behavior on touch devices

---

## 11. Responsive Requirements

The implementation must work on:

* 320px mobile width
* Standard mobile screens
* Tablets
* Laptops
* Desktops
* Large displays

Check:

* Text wraps cleanly.
* Buttons remain tappable.
* Forms are usable.
* Media scales safely.
* Modals fit the viewport.
* Sticky elements do not block content.
* Tables/cards do not overflow.
* Navigation remains usable.
* Important CTAs are reachable.
* Long content does not destroy the layout.

Mobile must be designed intentionally, not patched later.

---

## 12. Business Logic

Define rules clearly.

Think through:

* What is allowed?
* What is forbidden?
* What is required?
* What is optional?
* What happens when limits are reached?
* What happens when status changes?
* What happens when dates pass?
* What happens when content is unpublished?
* What happens when content is deleted?
* What happens when an admin changes something while a user is active?
* What happens when two users do the same action at the same time?
* What happens when the same request is sent twice?
* What happens when a user already completed the action?

Examples:

* A user cannot register twice for the same event.
* A closed event cannot accept registrations.
* A sold-out event cannot create new tickets.
* A deleted item should not be publicly accessible.
* Draft content should remain private.
* Webhooks must be idempotent.
* Admin-only actions must be enforced server-side.

---

## 13. State Model

List all possible states.

Examples:

* Draft
* Published
* Unpublished
* Archived
* Deleted
* Open
* Closed
* Sold out
* Pending
* Approved
* Rejected
* Paid
* Failed
* Cancelled
* Refunded
* Expired
* Processing
* Disabled
* Hidden

For each state, define:

| State  | User Sees | Allowed Actions | Blocked Actions | Message |
| ------ | --------- | --------------- | --------------- | ------- |
| Open   |           |                 |                 |         |
| Closed |           |                 |                 |         |
| Error  |           |                 |                 |         |

Avoid using one boolean when the feature clearly needs multiple states.

---

## 14. Data Validation

Validate data on both client and server.

Client-side validation improves UX.
Server-side validation protects the system.

Handle:

* Missing required fields
* Empty strings
* Whitespace-only strings
* Very long strings
* Invalid email
* Invalid phone number
* Invalid URL
* Invalid date
* Invalid number
* Negative number
* Invalid enum/status
* Invalid slug
* Duplicate value
* Invalid file type
* Oversized file
* Malformed JSON
* Unexpected null
* Special characters
* Emojis
* HTML/script input
* Case sensitivity
* Timezone issues

Never assume CMS, API, database, or frontend data is clean.

---

## 15. Security Requirements

Think through security before implementation.

Check for:

* Authentication bypass
* Authorization bypass
* Broken access control
* Insecure direct object references
* Trusting client-side state
* Missing server validation
* XSS
* CSRF where applicable
* SQL/query injection
* Unsafe redirects
* File upload abuse
* API key exposure
* Secret leakage
* Sensitive data in logs
* Sensitive data in client bundle
* Public exposure of private CMS fields
* Draft content leakage
* Admin-only fields leaking to frontend
* Webhook spoofing
* Replay attacks
* Missing rate limits
* Overly broad database queries
* User enumeration
* Session expiry issues

Rules:

* Secrets stay server-side.
* Privileged actions require server-side authorization.
* Private data must not be sent to the client unless required.
* Never trust hidden form fields for security.
* Never trust disabled buttons for security.
* Never mark payment/order/registration success from frontend alone.

---

## 16. Abuse & Misuse Cases

Assume some users will misuse the system.

Handle:

* Spam submissions
* Bot submissions
* Repeated requests
* Rapid button clicking
* Oversized payloads
* Malicious URLs
* Script injection attempts
* Fake email/phone values
* Uploading harmful files
* Guessing IDs or slugs
* Accessing another user’s data
* Manipulating API payloads
* Replaying requests
* Bypassing frontend restrictions
* Creating duplicate records
* Scraping public endpoints
* Brute forcing invitation/admin links

Backend logic must reject invalid or unauthorized actions even if the UI hides them.

---

## 17. Authentication & Authorization

If auth is involved, define:

* Who can access the route?
* Who can call the API?
* Who owns the data?
* Who can edit the data?
* Who can delete the data?
* Who can approve/publish the data?
* What happens when the session expires?
* What happens when user permissions change?
* What happens when a user is removed or blocked?

Rules:

* Check permissions close to the data/action.
* Do not rely on client-only checks.
* Avoid leaking existence of private resources.
* Return safe errors for unauthorized users.
* Do not expose role/admin data unnecessarily.

---

## 18. Database Requirements

If database changes are needed:

* Research existing schema.
* Follow existing naming conventions.
* Add constraints where needed.
* Add indexes where needed.
* Add uniqueness where needed.
* Avoid destructive migrations unless required.
* Preserve existing data.
* Add defaults carefully.
* Handle nullable fields deliberately.
* Avoid storing sensitive data unnecessarily.
* Document migration steps.
* Plan rollback if risky.

For each new field/table:

| Name | Type | Required | Default | Public/Private | Validation | Notes |
| ---- | ---- | -------- | ------- | -------------- | ---------- | ----- |

Think through:

* Duplicate records
* Race conditions
* Concurrent writes
* Orphaned records
* Cascading deletes
* Soft delete vs hard delete
* Migration safety
* Backfilling old data
* Query performance
* Data retention

---

## 19. CMS Requirements

If CMS changes are needed:

* Follow existing schema structure.
* Keep editor experience simple.
* Use clear field names.
* Add helpful descriptions.
* Add validation.
* Add preview configuration if existing project uses it.
* Add sensible defaults.
* Avoid exposing private/internal fields publicly.
* Make optional content render safely.
* Handle draft/unpublished content correctly.

Consider editor controls for:

* Show/hide section
* Ordering
* Featured item
* Status
* Registration open/closed
* Start/end date
* Media
* Captions
* Alt text
* SEO title
* SEO description
* Open Graph image
* External links
* Internal notes
* Public/private toggle

---

## 20. API / Server Actions

For every API route, server action, or backend function, define:

| Endpoint/Action | Caller | Input | Validation | Auth Required | Side Effects | Errors |
| --------------- | ------ | ----- | ---------- | ------------- | ------------ | ------ |

Requirements:

* Validate input server-side.
* Check permissions server-side.
* Return clear errors.
* Do not expose stack traces.
* Do not leak private records.
* Handle duplicate requests.
* Handle retries safely.
* Handle partial failures.
* Log useful errors safely.
* Use existing response patterns.
* Keep responses minimal.
* Avoid returning fields the frontend does not need.

---

## 21. Forms

If forms are involved, handle:

* Required fields
* Optional fields
* Field-level errors
* Form-level errors
* Loading state
* Disabled state
* Success state
* Failed submission
* Duplicate submission
* Double-click submit
* Browser autofill
* Mobile keyboard types
* Long input
* Invalid input
* Reset behavior
* Back button behavior
* Refresh during submission
* Session expiry
* Server validation errors
* Accessibility labels
* Error message announcements

Rules:

* Do not rely only on client validation.
* Disable submit while submitting, but also protect server-side.
* Preserve user input after recoverable errors.
* Make success/failure clear.

---

## 22. Payments & Webhooks

Use this section only if payments, orders, bookings, or external webhooks are involved.

Handle:

* Webhook signature verification
* Idempotency
* Duplicate webhook events
* Out-of-order webhook events
* Payment started
* Payment pending
* Payment completed
* Payment failed
* Payment cancelled
* Payment refunded
* Webhook delayed
* User closes payment page
* User refreshes after payment
* Amount mismatch
* Currency mismatch
* Product/event sold out during payment
* Registration created before payment
* Registration created after payment
* Manual reconciliation
* Fraud/spam attempts
* Secret leakage
* Test mode vs live mode

Rules:

* Never trust frontend payment success alone.
* Confirm payment on the server.
* Store external payment IDs safely.
* Make webhook handlers idempotent.
* Avoid creating duplicate orders/registrations.

---

## 23. Email, Notifications & Messaging

If emails or notifications are involved, define:

* Trigger
* Recipient
* Subject
* Message content
* Retry behavior
* Failure behavior
* Unsubscribe/opt-out if needed
* Admin copy if needed
* User copy if needed
* Sensitive data restrictions

Think through:

* Duplicate emails
* Failed email provider
* Delayed email
* User changes email
* Invalid email
* Notification sent before transaction completes
* Notification sent after rollback

Do not include private/admin-only data in user-facing messages.

---

## 24. File Uploads & Media

If uploads are involved, handle:

* Allowed file types
* Max file size
* Image dimensions
* Video duration
* File naming
* Storage location
* Public/private access
* Virus/malware considerations
* Duplicate uploads
* Failed uploads
* Slow uploads
* Upload progress
* Deleting/replacing files
* Orphaned files
* Alt text
* Captions
* Compression/optimization
* CDN behavior

Never trust file extensions alone.

---

## 25. Search, Filtering & Pagination

If lists/search are involved, handle:

* Empty results
* Large result sets
* Pagination
* Infinite scroll if existing pattern supports it
* Sorting
* Filtering
* Search query validation
* No results state
* Slow queries
* Debouncing
* URL query params
* Back/forward navigation
* Mobile filter UI
* Server-side limits
* Query performance
* Indexes if needed

Do not fetch unlimited records.

---

## 26. Caching & Freshness

If data is cached, define:

* What is cached?
* Where is it cached?
* How long is it cached?
* When is it invalidated?
* What happens after edits?
* What happens after publish/unpublish?
* What happens after payment/status change?
* What happens when stale content is shown?

Rules:

* Do not cache private user data publicly.
* Be careful with auth-dependent pages.
* Make admin changes reflect reasonably.
* Avoid stale payment, registration, or permission states.

---

## 27. Performance

Protect performance.

Check:

* Bundle size
* Unnecessary client-side JavaScript
* Large dependencies
* Image optimization
* Video loading
* Lazy loading
* Server rendering/static rendering
* Database query count
* N+1 queries
* Slow API routes
* Large payloads
* Layout shift
* Re-renders
* Blocking scripts
* Homepage impact
* Critical route impact

Rules:

* Do not add a heavy library for a simple task.
* Fetch only needed data.
* Paginate large lists.
* Lazy-load heavy media.
* Keep initial render fast.
* Avoid making global performance worse.

---

## 28. Accessibility

Accessibility is required.

Check:

* Semantic HTML
* Proper heading order
* Keyboard navigation
* Visible focus states
* Correct button/link usage
* Labels for form fields
* Error messages linked to fields
* Alt text support
* Color contrast
* Screen reader structure
* No hover-only interactions
* Reduced motion support
* Escape key for modals
* Focus trap for modals
* Focus return after modal closes
* ARIA only where needed

Do not sacrifice accessibility for visual polish.

---

## 29. SEO & Sharing

If the task affects public pages, handle:

* Page title
* Meta description
* Canonical URL
* Open Graph title
* Open Graph description
* Open Graph image
* Twitter/social card data
* Slug handling
* Not-found page
* Redirects if needed
* Structured data if existing project uses it
* Sitemap if relevant
* Robots/noindex for private/draft pages

Do not expose private or draft content to search engines.

---

## 30. Analytics & Logging

If analytics/logging exists in the project, consider tracking:

* Page view
* CTA click
* Form started
* Form submitted
* Form failed
* Signup/login started
* Payment started
* Payment completed
* Payment failed
* Search performed
* Filter used
* Media opened
* Admin action performed

Rules:

* Do not track sensitive data.
* Do not log secrets.
* Do not log full personal details unless absolutely required.
* Follow existing analytics patterns.
* Do not add analytics tools unless requested.

---

## 31. Privacy

Think through data privacy.

Check:

* What personal data is collected?
* Is it necessary?
* Who can access it?
* Is it exposed to the frontend?
* Is it sent to third parties?
* Is it stored securely?
* Is it logged?
* Is it shown in analytics?
* Is it included in emails?
* Can users see other users’ data?
* Can admins see only what they need?

Do not collect or expose more data than needed.

---

## 32. Error Handling

Handle:

* Network error
* Server error
* Validation error
* Permission error
* Not found
* Session expired
* Rate limit
* Database unavailable
* CMS unavailable
* Payment failure
* Upload failure
* Unknown error

Rules:

* User-facing errors should be understandable.
* Developer logs should be useful.
* Do not expose stack traces.
* Do not expose secrets.
* Do not silently swallow errors.
* Make recovery clear where possible.

---

## 33. Loading, Empty, Success & Failure States

Design states for:

* Initial loading
* Partial loading
* Empty content
* No search results
* Form submitting
* Form success
* Form failure
* Disabled action
* Unauthorized
* Not found
* Offline/failed request
* Deleted/unpublished content
* Payment pending
* Payment failed
* Payment success

Fallback UI should feel intentional, not like an afterthought.

---

## 34. Browser, Device & Environment Support

Consider:

* Chrome
* Safari
* Firefox
* Mobile Safari
* Android Chrome
* Desktop
* Mobile
* Tablet
* Slow devices
* Slow internet
* Touch screens
* Keyboard-only usage
* Reduced motion
* Dark mode if project supports it
* Light mode if project supports it

Do not rely on APIs unsupported by the project’s target browsers without fallback.

---

## 35. Internationalization & Formatting

If relevant, handle:

* Dates
* Times
* Timezones
* Currency
* Numbers
* Plurals
* Long translated text
* Right-to-left text if project supports it
* User locale
* Server timezone vs user timezone

Be careful with event times, deadlines, payment dates, and expiry logic.

---

## 36. Feature Flags & Admin Controls

If the feature may need to be turned on/off, consider:

* Feature flag
* CMS toggle
* Admin toggle
* Maintenance mode
* Registration open/closed
* Visibility setting
* Public/private setting
* Rollout percentage
* Internal-only preview

Make disabled states clear and safe.

---

## 37. Backward Compatibility

Ensure existing users/content/data still work.

Check:

* Old records without new fields
* Existing routes
* Existing API consumers
* Existing CMS documents
* Existing database rows
* Existing environment variables
* Existing tests
* Existing build process

Do not assume all old content has new fields.

---

## 38. Migration & Rollback

If migrations are needed:

* Explain migration purpose.
* Make migration safe.
* Avoid destructive changes unless required.
* Back up or preserve data where possible.
* Add defaults carefully.
* Backfill if needed.
* Document how to run migration.
* Document rollback plan if possible.
* Do not require manual production edits without documenting them.

For risky changes, include:

* Pre-deploy steps
* Deploy steps
* Post-deploy checks
* Rollback steps

---

## 39. Dependencies

Before adding a dependency, ask:

* Is it necessary?
* Can existing code solve this?
* Is the package maintained?
* Is it secure?
* Is it too large?
* Does it work with the current framework?
* Does it affect bundle size?
* Does it introduce licensing concerns?

Do not add dependencies for simple utilities.

---

## 40. Code Quality

Code should be:

* Simple
* Readable
* Typed where the project uses types
* Consistent with existing patterns
* Easy to maintain
* Not overly abstract
* Not duplicated unnecessarily
* Not clever for no reason

Rules:

* Reuse existing utilities.
* Keep components focused.
* Keep server logic separate from UI where appropriate.
* Name things clearly.
* Delete dead code.
* Avoid unrelated formatting churn.
* Avoid massive files when clean separation is better.
* Avoid premature abstraction.

---

## 41. Testing Strategy

Use the project’s existing testing setup.

Test relevant areas:

### UI

* Desktop
* Mobile
* Tablet
* Long text
* Missing content
* Media edge cases
* Empty state
* Error state

### Logic

* Valid action
* Invalid action
* Duplicate action
* Unauthorized action
* Forbidden state
* Status change
* Race condition if relevant

### Security

* Direct API call without permission
* Manipulated payload
* Accessing another user’s data
* Script input
* Oversized input
* Webhook verification if relevant
* Secret exposure check

### Reliability

* Slow network
* Failed request
* Refresh during action
* Back button behavior
* Multiple tabs
* Build succeeds
* Lint succeeds
* Existing pages still work

Run relevant commands:

```bash
[install command]
[dev command]
[lint command]
[test command]
[build command]
```

Use actual commands from the project.

---

## 42. Manual QA Checklist

Before calling the task complete, verify:

* Main happy path works.
* Empty state works.
* Error state works.
* Loading state works.
* Mobile layout works.
* Desktop layout works.
* Long content works.
* Missing optional data works.
* Invalid input is rejected.
* Unauthorized access is blocked.
* Duplicate actions are handled.
* Existing related pages still work.
* No console errors.
* No obvious layout shift.
* No horizontal overflow.
* No secrets exposed.
* Build/lint/tests pass where available.

---

## 43. Documentation

Update documentation if the task changes:

* Setup
* Environment variables
* CMS fields
* Database schema
* API behavior
* Admin workflow
* Deployment steps
* Migration steps
* Testing instructions
* Known limitations

Do not leave future maintainers guessing.

---

## 44. Agent Behavior Rules

The agent must:

* Research before coding.
* Prefer existing patterns.
* Think through edge cases.
* Make minimal safe changes.
* Avoid unrelated rewrites.
* Avoid adding dependencies unless justified.
* Avoid copying references exactly.
* Protect security and privacy.
* Validate server-side.
* Enforce permissions server-side.
* Handle failure states.
* Keep mobile in mind.
* Run available checks.
* Explain what changed clearly.

The agent must not:

* Say “done” without proof.
* Skip codebase research.
* Ignore security.
* Trust frontend-only checks.
* Break existing routes.
* Expose secrets.
* Hardcode dynamic data.
* Add random design patterns.
* Change global styles unnecessarily.
* Leave broken states unhandled.
* Make destructive database changes casually.
* Hide uncertainty.

---

## 45. Required Response Before Coding

Before coding, respond with:

1. Task size classification
2. Existing patterns found
3. Files likely to be changed
4. Data/model changes needed
5. Security and permission risks
6. UI and UX edge cases
7. Logic and state edge cases
8. Testing plan
9. Implementation plan

For tiny tasks, this can be brief.
For large tasks, this must be detailed.

---

## 46. Required Response After Coding

After implementation, respond with:

1. What was built
2. Files changed
3. Important decisions made
4. Edge cases handled
5. Security protections added
6. Validation added
7. Tests/checks run
8. Anything not completed
9. Risks or follow-ups
10. How to verify manually

Do not just say “completed.”

---

## 47. Acceptance Criteria

This task is complete only when:

* The requested functionality works.
* Existing codebase patterns are respected.
* UI edge cases are handled.
* User behavior edge cases are handled.
* Business logic is correct.
* Invalid states are blocked.
* Security risks are addressed.
* Permissions are enforced server-side.
* Data is validated server-side.
* Private data is not exposed.
* Mobile layout works.
* Accessibility is handled.
* Loading/empty/error states exist.
* Performance is not harmed.
* Existing functionality still works.
* Build/lint/tests pass where available.
* Final response explains changes clearly.

---

## 48. Task-Specific Details

Fill this section for the actual task.

### Feature / Fix

[Describe exact task.]

### Route / Location

[Route, page, component, file, or area.]

### Data Source

[CMS, database, API, static content, external service.]

### User Roles

[Who can use this.]

### Required Behavior

* [Behavior 1]
* [Behavior 2]
* [Behavior 3]

### Forbidden Behavior

* [Forbidden behavior 1]
* [Forbidden behavior 2]

### Design Notes

[Describe visual direction.]

### Logic Notes

[Describe important logic.]

### Security Notes

[Describe important security requirements.]

### Edge Cases

* [Edge case 1]
* [Edge case 2]
* [Edge case 3]

### Testing Notes

[Describe specific tests/checks needed.]

---

## 49. Compact Task Brief

Use this section when the task is small and does not need the full file repeated.

Task:

[One clear sentence.]

Context:

[Why it matters.]

Relevant files/areas:

[List files or areas if known.]

Requirements:

* [Requirement 1]
* [Requirement 2]
* [Requirement 3]

Edge cases:

* [Edge case 1]
* [Edge case 2]

Definition of done:

* [Done condition 1]
* [Done condition 2]
* [Done condition 3]

The agent should still follow the broader rules in this file where relevant.
