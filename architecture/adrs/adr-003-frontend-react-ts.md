# ADR 003: Frontend with React + TypeScript

**Date:** 2025-10-15 \
**Status:** Accepted

## Context

We need to build the frontend UI for the Chrome extension. Chrome extensions must be built with HTML, CSS, and JavaScript (or TypeScript compiled to JavaScript). Modern UI development benefits greatly from component-based frameworks like React. Using React with TypeScript ensures a scalable, maintainable, and type-safe frontend architecture.

## Decision

We will use **React with TypeScript** for building the frontend UI, compiling down to JavaScript for the Chrome runtime.

## Consequences

- **Positive**
    - Component-based design improves readability and reusability.
    - Type safety from TypeScript reduces common runtime errors.
    - Powerful developer experience with autocompletion, refactoring, and React tooling.
    - High maintainability and scalability for long-term development.
- **Negative**
    - Requires a build step (TypeScript/React JSX → JavaScript).
    - Slightly larger bundle size due to React runtime.
- **Neutral**
    - Chrome still runs JavaScript; React and TypeScript are development-time choices.
    - Project setup includes a React/TypeScript toolchain (e.g., Vite, Webpack, or Create React App).


## Alternatives Considered

- **Option A: Plain JavaScript**
    - Simpler setup (no compilation step).
    - Rejected: increases risk of runtime errors and lowers maintainability.
- **Option B: Hybrid (JS with JSDoc typing)**
    - Adds lightweight type hints without a compiler.
    - Rejected: weaker guarantees and less tooling support than full TypeScript.
- **Option C: TypeScript without React**
    - No framework (vanilla JS/TS).
    - Rejected: less efficient for building complex, interactive UIs required by the extension.


## References

- [Chrome Extension Documentation](https://developer.chrome.com/docs/extensions)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [React Documentation](https://react.dev/)
