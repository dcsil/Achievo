# ADR 006: Python Flask 

**Date:** 2025-09-30  
**Status:** Proposed  

## Context  
Our project requires a backend that can integrate with Databricks, Vertex AI, the Canvas API, and a Chrome extension. Since much of the documentation and tooling for these integrations is provided in Python, it made sense to align our backend language with this ecosystem. Our team also has strong proficiency in Python, making it a natural fit.  

## Decision  
We will use Python Flask for the backend, leveraging its lightweight framework to build and scale APIs that connect our Chrome extension, Databricks SQL Warehouse, and other services.  

## Consequences 
- **Positive:**  
  - Python ecosystem provides strong library support for data parsing, ML, and API integrations (pandas, scikit-learn, NLP tools).  
  - Familiarity within the team, including one member with direct Flask experience, reduces learning curve.  
  - Flask is flexible and lightweight, allowing us to avoid unnecessary overhead. 

- **Negative:**  
  - Flask is minimalistic compared to larger frameworks, meaning some features (e.g., advanced authentication or structure) may require manual setup.  

## Alternatives Considered  
- **Option A: TypeScript (Node.js/Express)**  
  - Pros: Strong performance for concurrent tasks, same language across frontend and backend.  
  - Cons: Less direct integration with AI/ML libraries and Databricks + limited team expertise.  

## References  
- [Flask Documentation](https://flask.palletsprojects.com/)  
- [Pandas Documentation](https://pandas.pydata.org/docs/)  
- [scikit-learn Documentation](https://scikit-learn.org/stable/documentation.html)  
- [Databricks Developer Tools](https://docs.databricks.com/en/dev-tools/index.html)  
- [Canvas LMS API Docs](https://canvas.instructure.com/doc/api/)  