## ADR 001: Canvas API
Date: 2025-09-30

Status: Proposed

## Context
We need a reliable way to detect when a student has submitted an assignment in Canvas, so the extension can:
- Show a congratulatory popup.
- Mark the assignment as completed in the student’s task list.

## Decision
We will integrate with the official Canvas REST API to detect assignment submissions and update the extension state.

## Consequences
- **Positive**
  - Reliable and supported by Canvas (less likely to break than DOM scraping).
  - Secure authentication flow (OAuth2).
  - Easier to extend later (grades, due dates, reminders).
- **Negative**
  - Requires OAuth setup and token management in the extension.
  - Possible delays if API is polled too infrequently.
  - Rate limits may restrict real-time feedback.
- **Neutral**
  - Users must grant API access once (login flow).
  - Extension logic shifts from DOM observation to API polling or webhook simulation.

## Alternatives Considered
- **Option A: DOM scraping**
  - Chrome extension watching for changes directly in the Canvas web page’s HTML (Document Object Model)
  - Rejected because it’s brittle, can break when Canvas UI updates, and may violate ToS.
- **Option B: Manual task tracking**
  - Students would manually mark tasks as complete, and the extension would store this state in local storage.
  - Rejected because it eliminates the automatic sync benefit — users would need to update tasks twice (once in Canvas and once in the extension), which reduces convenience and the core value of the feature.

## References
- [Canvas API documentation](https://canvas.instructure.com/doc/api/)
