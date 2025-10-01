## ADR 002: Chrome Extension
Date: 2025-09-30

Status: Proposed

## Context
Our vision is to create a centralized application that reimagines how students manage their workload through balance, motivation, and smarter systems. We want to target post secondary students in North America that use the Canvas LMS. Our tool will combine automated scheduling and gamification, while being easy to access and use.

## Decision
We will create a Chrome Extension that is accessible in the the Google Chrome extensions bar and leverages various Chrome Extension features.

## Consequences
- **Positive**
  - Has a lot different features we can incorporate into our app (ex. notifications, control tabs, override windows, etc.).
  - Has a lot of samples/tutorials and documentation.
  - Can use modern frameworks and build tools (e.g., React boilerplate) to accelerate UI and logic development.
  - Highly accessible to students who use Chrome for daily work and study.
  - `chrome.storage` for user data caching and ease of syncing across browser sessions and devices.
  - Ease of access from the Chrome Extensions bar on a Google Chrome tab/window.
- **Negative**
  - Targets only users that primarily use the Chrome web browser.
  - Deployment requires compliance with Chrome Web Store policies and periodic updates to maintain compatibility with browser changes.
- **Neutral**
  - blah

## Alternatives Considered
- **Option A: Web application**
  - Rejected because it cannot provide direct integration with browser features (no access to tab, window management, native notifications, or page overrides).
- **Option B: Mobile application**
  - Rejected because students do most academic work on a laptop/browser. A mobile app cannot interact directly with browser tabs, windows, or web platform content. And, it would reduce convinience and student adoption.
  - Also building an effective mobile app requires creating and maintaining separate versions for Android and iOS, which would increase cost and complexity.
- **Option C: Desktop application**
  - Rejected due to need for separate installers and lack of browser control. This would reduce convenience and student adoption.
  
## References
- [Chrome Extension basic tutorial](https://developer.chrome.com/docs/extensions/get-started/tutorial/hello-world)
- [Chrome Extension developer documentation](https://developer.chrome.com/docs/extensions/develop)
- [Google Chrome usage in the US](https://www.statista.com/statistics/545520/market-share-of-internet-browsers-usa/)
- [React Chrome Extension boilerplate](https://github.com/lxieyang/chrome-extension-boilerplate-react)
