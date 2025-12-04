## MVP Development Justification 

### Initial Hypothesis 

#### Core Problem  
Students struggle to manage their academic schedules effectively, often missing deadlines or feeling overwhelmed by the cognitive load of tracking assignments, tests, and personal commitments across multiple courses. This disorganization leads to stress, last-minute cramming, and reduced academic performance.

#### Initial Product Vision 
Achievo began as an ambitious Chrome extension designed to transform student productivity through AI-powered scheduling and gamification. Our initial vision encompassed six comprehensive Critical User Journeys (CUJs):

- **Personalized Onboarding Quiz** - Collect user preferences about study habits, goals, and availability
- **AI Schedule Generation** - Parse syllabi PDFs to extract deadlines and generate detailed task breakdowns
- **Manual Task Creation** - Allow users to add non-syllabus commitments with AI-assisted rescheduling
- **Smart Notifications** - Remind users of upcoming deadlines and tasks
- **Task Completion & Rewards** - Track completion via Canvas integration or manual marking, reward with in-game currency
- **Reward Redemption** - Allow users to spend currency on prizes in a gamified store

#### Key Assumptions About Users
- Students wanted a highly automated setup process, and would be willing to complete onboarding quizzes and provide detailed preferences upfront.

- Students preferred uploading syllabi as their main way of inputting deadlines, and would trust the AI to extract accurate dates and generate microdeadlines without much verification.

- Students expected deep integration with existing academic tools, especially Canvas, and would rely on automatic task completion tracking.

- Gamification would be a strong primary motivator, where even simple rewards (e.g., static images, currency) would meaningfully increase engagement.

- Students wanted a single platform for all academic and personal tasks, and would adopt Achievo as their central productivity hub.

#### Initial Technical Approach
- **Database**: Databricks SQL Warehouse for structured data storage
- **AI Processing**: Vertex AI for intelligent syllabus parsing and scheduling
- **Frontend**: Chrome Extension built with HTML, CSS, JavaScript
- **Backend**: Flask + Python
- **Integrations**: Canvas API for automatic assignment tracking

### Key Learnings & Pivots

## Key Learnings & Pivots
### Pivot 1 — Scope Reduction After Testing Feasibility (A5)

**Critical Insight:**
Early development showed that implementing all six CUJs was unrealistic within the semester. Features like onboarding, syllabus parsing, and AI-generated breakdowns required extensive engineering and testing time.

**Assumptions Challenged:** Assumed all six CUJs were essential for an MVP

**Resulting Pivot:** We reduced the MVP to three core CUJs: Notifications, Task Completion & Rewards, and Reward Redemption.
This let us deliver polished functionality without spreading development across too many incomplete features.

### Pivot 2 — Switching from Vertex AI to Gemini API (A5)

**Critical Insight:** Vertex AI’s OAuth setup and cloud configuration slowed prototyping much more than expected.

**Assumptions Challenged:** Assumed an enterprise-level AI stack was needed immediately

**Resulting Pivot:** We moved to the Gemini API (via AI Studio), which used simple API-key authentication and enabled rapid iteration while still supporting future migration back to Vertex.

### Pivot 3 — UI/UX Refinements from First User Research (A6)

**Critical Insight:** The first usability test revealed navigation difficulties, skepticism toward AI-generated microdeadlines, and insufficient gamification depth.

**Assumptions Challenged:**
- Assumed hamburger menus were efficient for quick navigation
- Assumed users would trust AI-generated schedules without transparency
- Assumed simple static gamification (just having images) was enough to motivate

**Resulting Pivot:**
- Simplified navigation and exposed high-frequency actions
- Shifted focus toward improving AI accuracy and clarity
- Looked into deeper gamification features (mouse customization) 

### Pivot 4 — UI/UX Refinements from Second User Research (A8)

**Critical Insight:** A Life Sciences student emphasized personalization, flexible task creation, stronger incentives, and the need for wellness-oriented features.

**Assumptions Challenged:**
- Assumed basic task creation UX was sufficient
- Assumed static images were engaging enough rewards
- Assumed productivity features alone met user needs

**Resulting Pivot:**
- Improved Add Task UX with clearer time and note inputs
- Added mental health break notifications
- Logged Phase II features such as themes, virtual pets, mini-games, Pomodoro timers, and cross-platform support

### Pivot 5 — Database Migration to Supabase (A8)

**Critical Insight:**
Databricks created unnecessary overhead for simple operations and slowed our backend workflow.

**Assumptions Challenged:** Assumed a large-scale data warehouse was the best long-term choice

**Resulting Pivot:** Migrating to Supabase (PostgreSQL) significantly reduced development friction and allowed faster iteration on core features.

### Pivot 6 — CUJ Restructuring & Scheduling Enhancements (A9)

**Critical Insight:** Our original CUJ structure didn’t reflect real user workflows, and user research highlighted that schedules needed to consider class timetables—not just deadlines.

**Assumptions Challenged:**
- Assumed task completion was a single flow
- Assumed only syllabus deadlines were needed for scheduling

**Resulting Pivot:**
- Split Task Completion into two CUJs (manual vs. Canvas-based)
- Added timetable processing to prevent double-booking
- Enhanced notifications with wellness reminders and hourly nudges

### Pivot 7 — Strategic Feature Deprioritization (A9)

**Critical Insight:**
Too many features reduced focus and slowed testing. User feedback showed quality and clarity mattered more than breadth.

**Assumptions Challenged:** Assumed adding more features early increased value

**Resulting Pivot:**
- Deferred advanced features (multi-syllabus upload, full onboarding quiz, virtual pets, streaks, .ics export, Pomodoro, cross-platform support) to Phase II/III.
- This ensured a stable, testable MVP aligned with core student pain points.


## Justification of Final MVP
### Why These Features Form the Final MVP

Our final MVP includes three fully implemented CUJs—Smart Notifications, Task Completion & Rewards, and Reward Redemption—supported by a stable backend, AI integration, and Chrome extension interface. These CUJs were prioritized because they directly test our core hypothesis:
Can smart notifications combined with gamified rewards help students stay organized and motivated?

All three CUJs address validated pain points discovered through A6 and A8 user research, competitive analysis, and feasibility testing. Features that did not contribute to hypothesis validation, or introduced high risk and low clarity of user need, were intentionally deferred.

### CUJ 1 — Smart Notifications

**Why It Was Prioritized:**
- Validated user need: Students consistently reported forgetting deadlines and wanting proactive reminders.
- Competitive gap: Tools like Syllabuddy require users to check calendars manually.
- Low-risk implementation: Chrome alarms API enabled fast, reliable integration.

### CUJ 2 — Task Completion & Rewards

**Why It Was Prioritized:**
- Motivation gap: User research confirmed that awareness alone isn’t enough—students need incentives to act.
- Student-requested engagement: A6 and A8 participants wanted interactive rewards, not static badges.
- Canvas automation: Reduces friction by rewarding completion without extra manual steps.

### CUJ 3 — Reward Redemption

**Why It Was Prioritized:**
- Completes the motivation loop: Turning points into collectibles gives students a reason to keep using the extension.
- Differentiation: No competitor offers an academic reward store or collectible system.
- User validation: Students explicitly asked for customizable and interactive rewards.

### Supporting Infrastructure

We built the technical foundation needed to deliver reliable end-to-end flows, including:
- Supabase PostgreSQL database (post-Databricks pivot for speed and reliability)

- Flask REST API with various core endpoints

- Gemini API for syllabus parsing and schedule generation

- Chrome extension frontend with React/TypeScript

- 77% backend test coverage + 89% frontend test converge, and full CI/CD pipeline

### Why Other Features Were Deferred
We excluded features like onboarding quizzes, calendar export, multi-syllabus upload, virtual pets, advanced AI rescheduling, and social systems because:

- They introduced high complexity or high error risk

- They did not directly test the core hypothesis

- User need was weak or unvalidated

- Implementing them would reduce quality of the core CUJs

Deferring these features allows us to gather usage data first and expand based on evidence.

### Why This MVP Is the Most Viable Solution

- **Directly addresses validated needs:** Awareness (notifications) and motivation (rewards).

- **Fully differentiates from competitors:** We combine scheduling support with gamified engagement.

- **Technically reliable:** High test coverage, stable APIs, and CI/CD reduce risk.

- **Focused and hypothesis-driven:** Three CUJs executed deeply are more valuable than six shallow features.

- **Sets up clear next steps:** Personalization, social features, and advanced AI can be built once core usage is validated.

