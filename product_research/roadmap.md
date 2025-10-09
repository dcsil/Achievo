# Roadmap

This roadmap outlines our plan for building a Chrome extension that helps students organize their schedules, sync assignments from Canvas, and stay engaged through gamification. It is structured into short term (next month), medium term (1–6 months), and long term (6+ months) goals. The roadmap highlights overall outcomes, while detailed tasks are tracked as GitHub Issues.

## Short Term

**Duration:** Q4 2025

**Target Completion Date:** 10/31/2025

Goal: Deliver a functional MVP focused on core CUJs related to notifications and gamification, showcasing how users are motivated and rewarded for task completion.  

Other features such as syllabus upload, scheduling, and onboarding will use dummy data to support the overall user narrative. 

- Build the core extension scaffold (Chrome Extension, Typescript, HTML/CSS) and backend service (Flask + Databricks SQL Warehouse).
- Provide basic onboarding and syllabus upload with placeholder data to simulate workflow.
- Implement task list + schedule view using mock syllabus data.
- Enable gamification features: mark tasks as done to earn coins, view collections, and purchase items using coins.
- Add basic notification functionality: task reminders and motivational prompts.
- Establish infrastructure: tech stack decisions, CRUD APIs, Postman testing, database schema, and work delegation.
- Conduct 3–5 user interviews to validate notification and gamification experiences and refine MVP priorities.
 

## Medium Term

**Duration:** Q4 2025 - Q1 2026

**Target Completion Date:** 3/31/2026


Goal: Evolve from a dummy-data MVP into a functional alpha product with basic file uploads (including sorting/add functionality) and Canvas integration.  

This phase focuses on making previously simulated features fully functional while enhancing engagement and usability.

- Implement calendar view, enhanced home page, and profile updates.
- Transition from mock syllabus/schedule data to live data parsed from uploaded files.
- Expand authentication to support multiple users (login/signup), and linking with Canvas API.
- Add filter/sort functionality to schedules.
- Add manual event/task upload functionality.
- Strengthen testing coverage to 90% for backend and frontend.

## Long Term

**Duration:** Q2 2026 - Q3 2026

**Target Completion Date:** 8/1/2026

**Target Launch Date:** 8/2/2026


Goal: Advance from a functional alpha to a **public-ready product** with intelligent automation, analytics, and high-quality user experience for full launch.  

This phase emphasizes scalability, personalization, and polish leading up to public release.

- Add UI polish and animations to elevate gamification and overall user experience.
- Build an analytics dashboard to track task completion rates, streaks, and engagement metrics.
- Implement predictive scheduling: AI-driven study block and productivity recommendations.
- Personalize schedules using onboarding quiz data to adapt task pacing, break intervals, and workload balance.
- Develop advanced notifications with tiered reminders, personalized nudges, and re-engagement prompts.
- Introduce user quiz redo functionality to recalibrate preferences and update recommendations.
- Refine AI-powered task breakdown for more adaptive micro-deadlines and dynamic workload planning.
- Add `.ics` export for syncing schedules to external calendars (Google Calendar, Outlook).
- Optimize performance, scalability, and backend infrastructure for production readiness.
- Public launch: transition from beta to full release on the Chrome Web Store, with marketing emphasis on Canvas integration and personalized scheduling for the 2026–2027 academic year.

 
