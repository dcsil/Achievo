## Architecture Diagram

<img width="1157" height="668" alt="image" src="https://github.com/user-attachments/assets/a5e34e9f-39bf-467c-8ded-7a5eac33299b" />

## User data flow steps
1. In the Chrome extension, user enters syllabus/task data or task data is grabbed from Canvas via the Canvas API
2. Syllabus data is sent to Vertex AI via HTTPS request. Data is processed using Vertex AI. Schedule and tasks are outputed via json format and displayed on the Chrome Extension.
3. Any task/schedule data is stored in our Databricks SQL Warehouse. Any specific Google Chrome data is stored in chrome.storage.
4. When tasks are displayed later on in the Chrome Extension, data is grabbed from the Databricks SQL Warehouse via HTTPS request.
5. When tasks are completed, the task data is updated in the Databricks SQL Warehouse via HTTPS request. 
