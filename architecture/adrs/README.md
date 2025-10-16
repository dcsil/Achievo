# Architectural Decision Records (ADRs)

For any architectural/engineering decisions we make, we will create an ADR (Architectural Decision Record) to keep track of what decision we made and why. This allows us to refer back to decisions in the future and see if the reasons we made a choice still hold true. It also allows for others to more easily understand the code and reasoning behind our stack.

**ADRs will follow this process:**
- They will live in the repo, under `architecture/adrs/`
- They will be written in Markdown
- They will follow the naming convention `adr-NNN-<decision-title>.md`
- `NNN` will be a counter starting at `001`, keeping the records in chronological order

**The common sections each ADR should have are:**
- Title
- Date
- Status
- Context
- Decision
- Consequences  
- Alternatives Considered
- References

Reference: [Documenting Architecture Decisions (Cognitect Blog)](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)

---

## Current ADRs & Tech Stack Summary

Below is a summary of our current decisions, with links to full ADRs:

- **[ADR 001: Canvas API](adr-001-canvas-api.md)**  
  *Summary:* To reliably detect assignment submissions, we integrated with the official Canvas REST API. This ensures secure OAuth2 authentication, avoids fragile DOM scraping, and allows extensibility for future features like grades or reminders.  

- **[ADR 002: Chrome Extension](adr-002-chrome-extension.md)**  
  *Summary:* We chose to build a Chrome Extension for direct browser integration, enabling notifications, tab control, and easy access. This maximizes accessibility for students but limits us to Chrome users.  

- **[ADR 003: Frontend React + TypeScript](adr-003-frontend-react-ts.md)**  
  *Summary:* We use React with TypeScript for the frontend UI to achieve a scalable, reliable, and maintainable codebase with stronger type safety and developer tooling compared to plain JavaScript.

- **[ADR 004: Frontend HTML & CSS (Tailwind)](adr-004-frontend-html-css.md)**  
  *Summary:* TailwindCSS was selected for fast, consistent styling with responsive design out-of-the-box. It increases HTML verbosity but accelerates iteration and improves maintainability.  

- **[ADR 005: AI Provider](adr-005-ai-provider.md)**  
  *Summary:* For the MVP, we use the Google Gemini API (AI Studio) with simple task/event scheduling and deprioritize OR optimization, leaving a clear migration path to Vertex AI if advanced optimization is needed later.

- **[ADR 006: Databricks SQL Warehouse](adr-006-databricks-sql-warehouse.md)**  
  *Summary:* We chose a SQL warehouse in Databricks for relational data integrity, scalability, and strong query performance. Its UI, AI agent, and documentation make it practical for both learning and production use.  

- **[ADR 007: Python Flask Backend](adr-007-python-flask.md)**  
  *Summary:* We use Python/Flask for the backend due to strong ecosystem support (Canvas API, Databricks, Gemini AI integrations), team proficiency, and lightweight API development. Flask’s flexibility reduces overhead and accelerates development.  

- **[ADR 008: Pytest](adr-008-pytest.md)**  
  *Summary:* We adopted pytest for unit and integration testing, with pytest-cov for code coverage reporting, ensuring automated, reliable testing and continuous quality assurance through CI integration.
