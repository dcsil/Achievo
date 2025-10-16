# ADR 009: Frontend Testing with Jest + React Testing Library

**Date:** 2025-10-15 \
**Status:** Accepted

## Context

We need a robust and developer-friendly testing setup for our React frontend. The testing framework should support both unit and integration testing, integrate smoothly with modern React features, and enable confident, maintainable testing practices.  

Jest provides an all-in-one testing framework for JavaScript and TypeScript applications, offering fast execution, built-in mocking, and integrated coverage reporting. React Testing Library (RTL) complements Jest by focusing on testing user behavior and component output rather than implementation details. Together, they form the de facto standard for testing React applications.

## Decision

We will use **Jest** as the main testing framework and **React Testing Library** for component testing. Jest will handle unit tests, mocks, and coverage reports, while RTL will be used for UI tests that focus on user interactions and accessibility.

## Consequences

- **Positive**
    - Tight integration with React and TypeScript ecosystems.  
    - Encourages user-focused tests instead of implementation-driven ones.  
    - Built-in mocking and snapshot testing for reliable component verification.  
    - Built-in code coverage reporting with no extra plugins required.  
    - Well-supported in CI/CD environments and developer tooling.

- **Negative**
    - Slightly slower execution for large test suites compared to lighter alternatives.  
    - Some learning curve when shifting to behavior-driven testing patterns.  

- **Neutral**
    - Primarily optimized for React applications; limited use outside that ecosystem.  
    - Configuration may vary slightly between Vite, CRA, or custom setups.

## Alternatives Considered

- **Option A: Vitest + Testing Library**
    - Pros: Faster due to Vite’s architecture; similar API to Jest.  
    - Rejected: Ecosystem still maturing; less stable documentation and plugin support.

- **Option B: Cypress (Component Testing Mode)**
    - Pros: Strong visual feedback and end-to-end testing capabilities.  
    - Rejected: Better suited for integration and E2E testing rather than unit tests.

## References

- [Jest Documentation](https://jestjs.io/docs/getting-started)  
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)  
