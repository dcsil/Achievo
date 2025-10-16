
# ADR 008: Pytest 

**Date:** 2025-10-15 \
**Status:** Accepted

## Context  
Our project requires robust testing to ensure the reliability of both backend and frontend components. To streamline our testing process and ensure consistent results, we need a reliable framework that supports unit, integration, and coverage reporting. After evaluating several options, we decided to use pytest, a popular testing framework in the Python ecosystem, known for its ease of use, flexibility, and extensive plugin ecosystem. Additionally, code coverage reporting is crucial to ensure that our tests are comprehensive and that any potential issues are identified early. 

## Decision  
We will use pytest for unit testing and integration testing of the backend. We will integrate pytest-cov to generate code coverage reports, which will help us track test coverage and improve the effectiveness of our tests. These reports will be generated as part of our CI pipeline to ensure continuous quality assurance.

## Consequences 
- **Positive:**  
  - Ease of Use: pytest is simple to set up and provides powerful features like fixtures, parameterized tests, and detailed output.
  - Code Coverage: pytest-cov provides an easy way to track test coverage and identify areas of the codebase that require more testing.
  - Integration with CI: pytest integrates seamlessly with our CI/CD pipeline (GitHub Actions), ensuring tests are automatically triggered and coverage is tracked continuously.
  - Extensibility: pytest has a wide range of plugins and extensions for additional functionality, such as parallel test execution and detailed reporting.

- **Negative:**
  - Learning Curve: Although pytest is user-friendly, it may require a learning period for team members who are not familiar with it.
  - Manual Configuration: Some advanced features (e.g., custom coverage thresholds or test reporting) might require additional configuration or scripting. 

## Alternatives Considered  
- **Option A: Unittest**  
  - Pros: Built-in Python library, no need for external dependencies.
  - Cons: Less flexible and more verbose compared to pytest. Limited coverage reporting capabilities.
    
- **Option B: Nose2**  
  - Pros: Easy to set up with built-in support for plugins and coverage reporting.
  - Cons: Less widely used than pytest, meaning fewer resources and community support.
  

## References  
- [pytest Documentation](https://docs.pytest.org/en/stable/)
- [pytest-cov Plugin](https://pytest-cov.readthedocs.io/en/latest/）
