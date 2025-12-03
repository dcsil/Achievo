## Architecture Diagram
<img width="1920" height="1080" alt="Main Application" src="https://github.com/user-attachments/assets/d590a890-39fe-4247-9d5e-8aa2f41108d1" />


## Tech Stack Summary

- Languages and Frameworks:
  - **Frontend**: HTML, CSS, Typescript + React, Jest (testing), React Testing Library (testing)
  - **Backend**: Python, Flask, pytest (testing)
- Other tools:
  - **Database**: Supabase Postgres Database
  - **AI (Beyond MVP)**: Gemini API provided by Google AI Studio
  - **Course Information API (Beyond MVP)**: Canvas API
  - **Deployment**: Render

Why all our tech stack choices were chosen are justified in our [ADRs](adrs/README.md).

## MVP user data flow steps:
1. In the Chrome extension, the user enters timetable/syllabus/task data.
2. A schedule is parsed and outputted from the timetable upload and everything is displayed on the Chrome Extension.
3. Any task/schedule data is stored in our Supabase Postgres Database.
4. Notifications are created using the Chrome APIs.
5. When tasks are displayed later on in the Chrome Extension, data is grabbed from the Supabase Postgres Database via HTTPS request.
6. When tasks are completed, the task data is updated in the Supabase Postgres Database via HTTPS request.
