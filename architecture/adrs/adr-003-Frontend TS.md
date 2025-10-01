## ADR 003: Frontend TS
Date: 2025-09-30

Status: Proposed

## Context
We need to build the frontend UI for the Chrome extension. Chrome extensions must be built with HTML, CSS, and JavaScript (or TypeScript compiled to JavaScript). Using TypeScript ensures stronger type consistency, making the codebase more reliable and maintainable as it grows.

## Decision
We will use TypeScript for the frontend, compiled down to JavaScript for the Chrome runtime.

## Consequences
- **Positive**
  - Type safety reduces common runtime errors.
  - Better developer experience with autocompletion and refactoring.
  - More maintainable and scalable for long-term development.
- **Negative**
  - Requires a build step (TS → JS).
- **Neutral**
  - Chrome still runs JavaScript; TypeScript is a development-time choice only.
  - Project setup includes a TypeScript toolchain.

## Alternatives Considered
- **Option A: Plain JavaScript**
  - Simpler setup (no compilation step).
  - Rejected because it increases risk of runtime errors and lowers maintainability.
- **Option B: Hybrid (JS with JSDoc typing)**
  - Adds lightweight type hints without a compiler.
  - Rejected because it provides weaker guarantees and less tooling support than full TypeScript.

## References
- [Chrome Extension Documentation](https://developer.chrome.com/docs/extensions)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
