
## Functional and Dynamic MVP Documentation

Our core CUJs that have been fully implemented are the following:

### 1. Task Notifications:
- The user should receive hourly notifications to stay on top of tasks
- The user should not receive Chrome Notifications if they currently have the extension open and in focus
- The user should be able turn on and off notifications in the Settings Page or during onboarding
- _Note: In-app notifications is part of CUJ 7_

### 2. Manual User Task Completion & Rewards
- User can click a task to complete it in in the Dashboard (Home Page) or Todo Page
- Once the user clicks complete, the task is marked as complete and they are automatically awarded coins
- If the user completes the last task in an assignment, they should receive coins for completing the assignment too
- The user should receive coins even upon completion of an overdue task. Currently, there is no logic for increasing or decreasing coin amounts based on completion time.

### 3. Rewards Redemption
- The user should be able to see their coin balance in the header at anytime
- When the user accumulates enough coins, they can buy blind boxes in the Rewards Page
- When a user buys a blind box, it should randomly output a prize and update their collection
- The user can see their current collection in the Rewards Page
- The user can equip any prize as their cursor. The cursor should show when hovering in the extension only.

-- 

For other CUJs, we’ve started the development of them:

### 4. Onboarding Quiz
- When the user creates a new account, after filling in profile information, they should automatically be directed to start the onboarding quiz
- **Static**: the user should be able to select their interests
- **Static**: the user should be able to sync to their Canvas account
- The user should be able to enable or disable notifications
- The user should be able to see an overview about our extension and then be redirected to the dashboard 

### 5. Schedule Generation
- The user should be able to upload their timetable (with various constraints) and our extension should parse and display their courses and classes for the selected semester
- _Note: the parsing in this MVP is not done by Gemini AI_
- **Static**: the user should be able to upload their syllabus and our extension should parse and display their assignments and tasks for that course

### 6. Schedule Adjustment
- The user can add their own tasks or assignments and add the following fields
  - Task Type
  - Name
  - Course
  - Start Date and Time
  - End Date and Time
- The user can use templates to help schedule better

### 7. Canvas Task Completion & Rewards
- **Static**: The user should be able to sync with Canvas
- **Static**: The user can see in the header if they are connected to Canvas or not
- **Static**: The in app notifications should update when a user completes an assignment on Canvas

### 8. Profile Creation and Customization
- The user can create a new profile
- The user can log into any existing profile
- In the Settings Page, the user can edit their profile. They can edit the following fields (the rest are static):
  - Profile picture
  - Name
  - Canvas Domain
  - Canvas API Key
- The profile information should be displayed and automatically refreshed on change or navigation to new page










