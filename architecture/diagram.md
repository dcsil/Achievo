## Architecture Diagram
<img width="1222" height="722" alt="image" src="https://github.com/user-attachments/assets/cbb0e11b-bdfd-42d4-b29c-c863a52c4252" />

## Tech Stack Summary

- Languages and Frameworks:
  - **Frontend**: HTML, CSS, Typescript + React, Jest (testing), React Testing Library (testing)
  - **Backend**: Python, Flask, pytest (testing)
- Other tools:
  - **Database**: Databricks SQL Warehouse
  - **AI**: Gemini API provided by Google AI Studio
  - **Course Information API**: Canvas API

Why all our tech stack choices were chosen are justified in our [ADRs](adrs/README.md).

## User data flow steps
1. In the Chrome extension, user enters syllabus/task data or task data is grabbed from Canvas via the Canvas API
2. Syllabus data is sent to Gemini API via HTTPS request. Data is processed using Vertex AI. Schedule and tasks are outputed via json format and displayed on the Chrome Extension.
3. Any task/schedule data is stored in our Databricks SQL Warehouse. Any specific Google Chrome data is stored in chrome.storage.
4. When tasks are displayed later on in the Chrome Extension, data is grabbed from the Databricks SQL Warehouse via HTTPS request.
5. When tasks are completed, the task data is updated in the Databricks SQL Warehouse via HTTPS request. 
