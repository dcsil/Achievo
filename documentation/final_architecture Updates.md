## Final Architecture Updates 

We updated our [Architecture Diagram](architecture/diagram.md) to better represent our MVP.

### Key Changes:
- Added: Render Deployment
- Out of MVP Scope: Canvas API, Google AI Studio

### New Diagram
<img width="1920" height="1080" alt="Main Application" src="https://github.com/user-attachments/assets/9ee6f8e4-d0c7-4d4f-8dd8-ba9323aa51c0" />

The final architecture of this system consists of a Python/Flask backend deployed on Render, a Supabase-managed PostgreSQL database, a Chrome Extension frontend built with TypeScript and React. Currently, input data is grabbed via text or file uploads. This data is transmitted as JSON or through HTTPS API requests to the frontend layer.

Beyond the MVP, we will use Google AI Studio for data processing and AI scheduling capabilities. Additionally, we will include another input data source: Canvas API. We’ve started exploring these functionalities already.

### Integration Components
Input Data: 
- Canvas API: Our initial API calls to the Canvas API are in [`services/canvas.py`](https://github.com/dcsil/achievo-app/blob/main/backend/app/services/canvas.py). But note that none of the data is actually used in the final MVP.
- User Input: There are many different places that require user input. This includes updating [profiles](https://github.com/dcsil/achievo-app/blob/main/frontend/src/pages/Settings/index.tsx), [login](https://github.com/dcsil/achievo-app/blob/main/frontend/src/pages/Login/index.tsx), [signup](https://github.com/dcsil/achievo-app/blob/main/frontend/src/pages/Signup/index.tsx), [uploading timetable](https://github.com/dcsil/achievo-app/blob/main/frontend/src/pages/Onboarding/steps/WelcomeStep.tsx), etc.. The user inputs data into specific areas in the frontend.

Frontend:
- Google Chrome Extension: All Chrome Extension setup related files, such as the manifest and service workers are stored in `frontend/public` and [`extensionUtils.ts`](https://github.com/dcsil/achievo-app/blob/main/frontend/src/utils/extensionUtils.ts). 
- Language and Framework: All files in `frontend` are written in Typescript and may use React as well, except the Google Chrome Extension specific files ([`service_worker.js`](https://github.com/dcsil/achievo-app/blob/main/frontend/public/service-worker.js) and [`manifest.json`](https://github.com/dcsil/achievo-app/blob/main/frontend/public/manifest.json)).
- Testing: All test files accompany the original files. They are named like: [original_name].test.tsx
- Calling Backend APIs: In the `src/api-contexts` folder are all the various API context files used to call the backend.

Backend:
- Language and Framework: All files in `backend` are written in Python and Flask is used for APIs.
- Testing: All tests can be found in `app/services`
- Sending information to Frontend: Requests from frontend are handled in [`main.py`](https://github.com/dcsil/achievo-app/blob/main/backend/app/main.py).
- Querying from Supabase: Querying and connecting to the Supabase database is done in the repositories in `backend/database`.

Database: 
- Supabase: Our cloud storage for any data. We query from it in our Backend.

Data Processing and AI Scheduling:
- Google AI Studio: Our initial API calls to the Google AI Studio are in [`read_syllabi.py`](https://github.com/dcsil/achievo-app/blob/main/backend/app/services/read_syllabi.py) and [`read_timetable.py`](https://github.com/dcsil/achievo-app/blob/main/backend/app/services/read_timetable.py). But note that none of the calls are actually used in the final MVP.
