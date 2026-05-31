<div align="center">

# Time4Study - Study Planner

### A smart study planning and productivity web application built with React, Vite, and Firebase

A modern web application designed to help students organize study schedules, create personalized study plans, track daily progress, manage upcoming exams, and stay consistent through achievements and productivity insights.

<br />

[![React](https://img.shields.io/badge/React.js-19.1.1-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-Build%20Tool-646CFF?style=for-the-badge\&logo=vite\&logoColor=white)](https://vitejs.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Backend-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)](https://firebase.google.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3.8-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)](https://getbootstrap.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4.1.14-38B2AC?style=for-the-badge\&logo=tailwind-css\&logoColor=white)](https://tailwindcss.com/)

</div>

---

## Overview

**Time4Study** is a study planning web application built to help students manage their study time more effectively.

The application allows users to create personalized study plans based on their major, study level, daily available study hours, subject difficulty, exam dates, and preferred study schedule. It also provides a dashboard for tracking daily tasks, study streaks, weekly progress, upcoming exams, and learning achievements.

The project focuses on solving a real student productivity problem: **how to organize study time efficiently and consistently.**

---

## Project Idea

Many students struggle with planning their study time, balancing multiple subjects, tracking exam deadlines, and staying consistent.

Time4Study helps users by turning study goals into structured daily tasks, providing visual progress tracking, and offering an organized dashboard that keeps the student focused on what needs to be done next.

---

## Features

| Feature              | Description                                                                        |
| -------------------- | ---------------------------------------------------------------------------------- |
| User Authentication  | Login and registration using Firebase Authentication                               |
| Study Plan Generator | Creates personalized study plans based on user inputs                              |
| Study Capacity Setup | Allows users to define major, study level, daily study hours, and difficulty level |
| Subjects Management  | Users can add subjects with estimated study hours and exam dates                   |
| Schedule Preferences | Users can choose preferred study days, times, break duration, and schedule type    |
| Dashboard            | Displays today’s tasks, progress statistics, streaks, and upcoming exams           |
| Daily Tasks          | Shows study tasks with time, duration, subject, and priority                       |
| Task Completion      | Users can mark tasks as completed                                                  |
| Study Streak         | Tracks consecutive study days to motivate consistency                              |
| Weekly Progress      | Shows weekly completion progress                                                   |
| Upcoming Exams       | Displays nearby exams and days remaining                                           |
| Task Importer        | Allows importing study tasks using structured JSON                                 |
| Plan Manager         | Users can update and manage their study plans                                      |
| Reports              | Displays daily and weekly study progress                                           |
| Achievements         | Motivational badge system for study consistency                                    |
| ChatBot              | Provides study-related support and guidance                                        |
| Profile Page         | Allows users to view and update account information                                |
| Firebase Integration | Stores user data, plans, tasks, exams, and activities                              |
| Responsive UI        | Built for desktop, tablet, and mobile screens                                      |

---

## Tech Stack

<div align="center">

### Frontend

![React](https://img.shields.io/badge/React.js-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge\&logo=vite\&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-38B2AC?style=for-the-badge\&logo=tailwind-css\&logoColor=white)

### Backend & Cloud Services

![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firebase Auth](https://img.shields.io/badge/Firebase%20Auth-Authentication-yellow?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firestore](https://img.shields.io/badge/Firestore-Database-orange?style=for-the-badge\&logo=firebase\&logoColor=white)
![Firebase Storage](https://img.shields.io/badge/Firebase%20Storage-Cloud%20Storage-blue?style=for-the-badge\&logo=firebase\&logoColor=white)
![Firebase Analytics](https://img.shields.io/badge/Firebase%20Analytics-Analytics-orange?style=for-the-badge\&logo=firebase\&logoColor=black)

### Libraries & Tools

![React Router](https://img.shields.io/badge/React%20Router-7.9-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)
![Lucide React](https://img.shields.io/badge/Lucide%20React-Icons-black?style=for-the-badge)
![Font Awesome](https://img.shields.io/badge/Font%20Awesome-Icons-528DD7?style=for-the-badge\&logo=fontawesome\&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-Code%20Quality-4B32C3?style=for-the-badge\&logo=eslint\&logoColor=white)
![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge\&logo=git\&logoColor=white)

</div>

---

## Main Modules

| Module               | Description                                                |
| -------------------- | ---------------------------------------------------------- |
| Authentication       | Handles user login, registration, and profile-based data   |
| Study Plan Generator | Creates study plans based on student capacity and subjects |
| Dashboard            | Shows daily progress, tasks, streaks, and upcoming exams   |
| Plan Manager         | Allows users to update and manage study plans              |
| Daily Plans          | Displays daily study schedules and task progress           |
| Reports              | Shows productivity insights and progress summaries         |
| Achievements         | Motivates users through badges and streak-based progress   |
| ChatBot              | Provides study support and guidance                        |
| Profile              | Manages user profile and account information               |

---

## Study Plan Generator Flow

The study plan generator is divided into three main steps:

### 1. Study Capacity

Users define their personal study capacity:

* Major
* Study level
* Daily study hours
* Difficulty level

### 2. Subjects and Exams

Users add subjects with study requirements:

* Subject name
* Estimated study hours
* Exam date

### 3. Schedule Preferences

Users customize how they prefer to study:

* Preferred study days
* Preferred study times
* Break duration
* Schedule type

---

## Dashboard Features

The dashboard is the main productivity center of the application.

It includes:

* Today’s study tasks
* Completed tasks counter
* Study streak
* Weekly progress
* Days remaining until exams
* Next task reminder
* Upcoming exams
* Task importer
* Task completion tracking

---

## Task Importer

The project includes a task importer that allows users to import study tasks using structured JSON data.

Example:

```json
[
  {
    "time": "13:00",
    "subject": "Database Systems - Review Chapter 5",
    "duration": 60,
    "priority": "high"
  },
  {
    "time": "14:15",
    "subject": "Operating Systems - Practice Problems",
    "duration": 60,
    "priority": "normal"
  }
]
```

This feature makes it easier to quickly add a full study schedule without manually entering each task one by one.

---

## Firebase Data Structure

```text
Firestore Database Structure:

users/
├── {uid}/
│   ├── email
│   ├── name
│   ├── major
│   └── createdAt

plans/
├── {uid}/
│   └── current/
│       ├── capacity/
│       │   ├── major
│       │   ├── studyLevel
│       │   ├── dailyHours
│       │   └── difficultyLevel
│       │
│       ├── subjects/
│       │   ├── name
│       │   ├── estimatedHours
│       │   └── examDate
│       │
│       ├── schedulePrefs/
│       │   ├── preferredDays
│       │   ├── preferredTimes
│       │   ├── breakDuration
│       │   └── scheduleType
│       │
│       ├── tasks/
│       │   ├── id
│       │   ├── date
│       │   ├── time
│       │   ├── subject
│       │   ├── duration
│       │   ├── priority
│       │   └── completed
│       │
│       └── exams/
│           ├── id
│           ├── name
│           ├── examDate
│           └── subject

activities/
├── {uid}/
│   └── activity records
```

---

## User Flow

```text
Register / Login
   ↓
Home Page
   ↓
Create Study Plan
   ↓
Set Study Capacity
   ↓
Add Subjects and Exams
   ↓
Choose Schedule Preferences
   ↓
Dashboard
   ↓
Track Tasks, Progress, Exams, and Achievements
```

---

## Installation and Setup

### 1. Clone the source repository

> The source code repository may be private. If access is available, clone it using:

```bash
git clone YOUR_REPOSITORY_LINK
```

### 2. Navigate to the project directory

```bash
cd time4study-study-planner
```

### 3. Install dependencies

```bash
npm install
```

### 4. Add environment variables

Create a `.env` file and add your Firebase configuration:

```env
VITE_API_KEY=YOUR_API_KEY
VITE_AUTH_DOMAIN=YOUR_AUTH_DOMAIN
VITE_PROJECT_ID=YOUR_PROJECT_ID
VITE_STORAGE_BUCKET=YOUR_STORAGE_BUCKET
VITE_MESSAGING_SENDER_ID=YOUR_MESSAGING_SENDER_ID
VITE_APP_ID=YOUR_APP_ID
VITE_MEASUREMENT_ID=YOUR_MEASUREMENT_ID
```

### 5. Start the development server

```bash
npm run dev
```

### 6. Build for production

```bash
npm run build
```

---

## Development Highlights

* Built a study planning workflow using React and Firebase
* Designed a multi-step study plan generator
* Implemented user authentication and profile-based study data
* Built a dashboard for tasks, streaks, progress, and exams
* Added task completion tracking and study streak logic
* Designed a JSON-based task importer
* Structured Firestore collections for users, plans, tasks, exams, and activities
* Built responsive UI using Bootstrap and Tailwind CSS
* Used Vite for fast development and optimized builds
* Added a ChatBot feature to support student guidance

---

## What I Learned

Through this project, I practiced and improved my skills in:

* Building productivity-focused web applications
* Creating multi-step forms and user flows
* Managing user-specific data with Firebase
* Designing Firestore data structures
* Building dashboard-based interfaces
* Tracking progress and user activity
* Working with React Router
* Combining Bootstrap and Tailwind CSS
* Using Vite with React
* Building real-world student-focused software solutions

---

## Future Improvements

* Add smarter study plan generation logic
* Add calendar integration
* Add push notifications and reminders
* Add advanced reports and charts
* Add exam priority calculation
* Add Pomodoro timer
* Add study session history
* Add downloadable study plans
* Add dark mode
* Add multi-language support
* Improve Firebase security rules
* Add unit and integration tests

---

## Repository Status

This documentation is public, while the source code repository may remain private depending on project requirements or deployment configuration.

This project represents a real-world productivity and education web application focused on study planning, task tracking, exam preparation, and student consistency.

---

## Author

<div align="center">

### Mohammed AL Bzoor

**Full Stack Developer | React & AI Automation Engineer**

[![GitHub](https://img.shields.io/badge/GitHub-mohammadbzoor-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammed%20AL%20Bzoor-0A66C2?style=for-the-badge\&logo=linkedin)](https://www.linkedin.com/in/mohammadbzoor)
[![Portfolio](https://img.shields.io/badge/Portfolio-Live%20Website-brightgreen?style=for-the-badge)](https://profaile-19e99.web.app/)

</div>

---

## License

This documentation is available for portfolio and project presentation purposes.
