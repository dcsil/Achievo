# Use Cases

## Jobs To Be Done (JTBD)

As part of our product use cases, we have the following 3 JTBDs:

### 1. Scheduling
As a student, I want to be able to organize all my to-dos in one place (including tests, assignments, and personal commitments) so that I can easily manage my schedule and stay on top of upcoming deadlines.

### 2. Notifications
As a student, I want to be reminded of my tasks and deadlines so that I can make sure I have them completed.

### 3. Gamification
As a student, I want to stay motivated on my school work so that I can continue keeping up with my tasks.

## Critical User Journeys (CUJs)

While our MVP is designed around 6 key CUJs, this semester’s development will focus on 3 that align with our core feature set — task completion gamification and task notifications.

The remaining CUJs will be included at a conceptual level to support storytelling and demonstrate the full product vision, but may not be fully implemented in this phase.

### 1. Task Notifications
**Description**: The user can receive notifications for upcoming deadlines and tasks. Clicking on a notification will bring them to their task list, where they can update progress and earn rewards.  

**JTBD**: Notifications & Keeping Track of Deadlines  

**User Path**:  
1. User navigates to the **Settings** tab.  
2. User clicks **“Allow Notifications”** in settings.  
3. User begins receiving notifications for deadlines and break reminders.  
4. User clicks a notification → views tasks, updates progress, and earns rewards.  

**UI/UX Mock-Up**:  

![CUJ #1 mockup](./cuj_mockups/cuj_figma_01.png)  

### 2. Task Completion & Rewards
**Description**: The user can mark tasks as complete either through Canvas or directly in the extension. Upon completion, they are rewarded with animations and in-game currency.  

**JTBD**: Gamification  

**User Path**:  
1. User completes a task by either:  
   - Clicking **“Complete”** in the extension  
   - Submitting it on Canvas  
2. User receives a reward animation.  
3. User sees in-game currency added to their balance.  

**UI/UX Mock-Up**:  

![CUJ #2 mockup](./cuj_mockups/cuj_figma_02.png)

### 3. Rewards Redemption
**Description**: The user can spend their earned in-game currency to unlock prizes. Unlocked prizes are added to their collection.  

**JTBD**: Gamification  

**User Path**:  
1. User opens the **Rewards**.  
2. User checks their collected prizes.  
3. User navigates to the **Store**.  
4. User spends in-game currency to unlock a prize.  
5. User is redirected back to **Rewards**, where the new prize is added.  

**UI/UX Mock-Up**:  

![CUJ #3 mockup](./cuj_mockups/cuj_figma_03.png)  

## Additional CUJs

### 4. Onboarding Quiz
**Description**: The user will complete a short onboarding quiz about their work-study habits and goals. Their responses will help the AI create a more personalized and effective schedule for them.

**JTBD**: Scheduling

**User Path**:
   1. User will Open chrome extension
   2. Sign up for account/link with Canvas for their account
   3. Quiz will be prompted if they are first time user
   4. Answer multiple choice questions like:
      - Do you prefer studying in the morning/night?
      - What are times you cannot do?
      - Let user block out class time, commute, meeting timeslots 
      - What are your goals for mental health?
   5. Once completed, the AI will better understand their preference, and understand better about the user.  

**UI/UX Mock-Up**:  

![CUJ #4 mockup](./cuj_mockups/cuj_04.png)

### 5. Schedule Generation
**Description**: The user uploads their syllabi, and the AI generates a schedule with both high-level and detailed task breakdowns. Users can export these as calendar files for easier integration into their workflow.  

**JTBD**: Scheduling

**User Path**:  
1. User uploads syllabi as a PDF file.  
2. AI extracts all relevant data and displays the schedule on the UI.  
3. User can export the schedule as an `.ics` file.  
4. User clicks a button to generate more detailed task breakdowns, such as:  
   - When to start working on an assignment  
   - Reminders to work out  
   - Breaks  
5. AI generates the detailed task breakdown and displays it on the UI.  
6. User can export the detailed breakdown as an `.ics` file.  

**UI/UX Mock-Up**:  

![CUJ #5 mockup](./cuj_mockups/cuj_05.png)  

### 6. Schedule Adjustment
**Description**: The user may have changes to their schedule that are not included in their syllabi. They can manually add events, and the AI will update the calendar accordingly, including shifting deadlines if needed.  

**JTBD**: Scheduling

**User Path**:  
1. User opens the Chrome extension and clicks on the **“Add” (+)** button.  
2. A pop-up appears asking the user to choose between:  
   - Uploading a syllabus  
   - Adding a new "to-do"
3. User selects **Add To-Do** to better describe their situation.  
4. User is brought to a separate page to manually add a new event to their calendar.  
5. User submits the desired change.  
6. AI updates the schedule accordingly, shifting deadlines if necessary.  
7. User is returned to the updated calendar view.  
8. User can export the updated calendar as an `.ics` file.  

**UI/UX Mock-Up**:  

![CUJ #6 mockup](./cuj_mockups/cuj_06.png)  

## Functional Requirements  
**Priority Features — Gamification & Notifications**
1. Users can earn in-game coins by completing tasks.
2. Users receive reminders as notifications for upcoming milestones and deadlines at defined intervals (e.g., 24 hours, 1 hour, 15 minutes before due time).
3. Users can use coins to purchase and open blind boxes. Each blind box contains a randomized collectible from a curated series of images, with a chance to unlock secret rewards such as animated GIFs.
4. Users can view their unlocked prizes on a dedicated page.
5. Allow user to sync with Canvas:
   - When a new task (assignment, quiz, etc.) is created in Canvas, it is automatically imported and added to the extension’s task list—users don’t have to enter it manually.
   - When a task is marked as completed in Canvas, its status is automatically updated as complete in the extension, ensuring users never need to update completion status twice.

**Deprioritized Feature — Scheduling**

1. The user can upload a syllabi, and the AI will automatically extract assignment deadlines and test dates from the document.
2. The user answers a series of questions tailored to their study habits and “hard no-s” (e.g., prefer to study between 6-9pm, club meeting from 7–10pm on Tuesdays, commute 9-10am daily).
3. The user can see their schedule (based on AI tailored output).
   - Calendar .ics file export
   - In-built task/breakdown calendar view of each task per course
   - Milestones (micro-deadlines)
4. The application allows users to adjust their schedule via settings, e.g., when an assignment due date changes.

## Non-Functional Requirements  

1. Performance:
   - Schedule generation finishes within 30 seconds for a syllabi up to 10MB in PDF form.
   - Each page and extension popup loads in ≤3 seconds.
   - Notifications fire within ±2 minutes of scheduled time; break reminders within ±30 seconds.
2. Usability:
   - User onboarding requires no more than 3 steps.
   - All key features accessible within 2 clicks from the main dashboard.
3. Quality & Maintainability:
   - Automated tests for all user-facing features.
   - Modular codebase with documentation and error logging.
