<div align="center">

# Online Quiz Platform

### A modern quiz management web application built with React.js and Firebase

An interactive online quiz platform that allows users to browse and solve quizzes, while admins can create, manage, and edit quizzes through protected admin features.

<br />

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Visit%20Website-brightgreen?style=for-the-badge)](https://singup-12a91.web.app/)
[![React](https://img.shields.io/badge/React.js-18.2.0-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)](https://react.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Backend-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)](https://firebase.google.com/)
[![SCSS](https://img.shields.io/badge/SCSS-Styling-CC6699?style=for-the-badge\&logo=sass\&logoColor=white)](https://sass-lang.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

</div>

---

## Overview

**Online Quiz Platform** is a React-based web application designed for creating, managing, and solving online quizzes.

The platform includes user authentication, role-based access control, protected routes, admin-only quiz management, quiz solving pages, and Firebase integration for authentication and database operations.

The project was developed to practice building real-world educational web applications using **React.js**, **Firebase Authentication**, **Firestore**, **React Router**, **Context API**, and modern UI styling with **SCSS**.

---

## Live Demo

<div align="center">

### [View Live Website](https://singup-12a91.web.app/)

</div>

---

## Features

| Feature             | Description                                                                     |
| ------------------- | ------------------------------------------------------------------------------- |
| User Authentication | Users can log in and access the platform securely using Firebase Authentication |
| Admin Role Access   | Admin users can access protected quiz management features                       |
| Quiz Listing        | Displays available quizzes for users                                            |
| Quiz Solving        | Users can open a quiz, answer questions, and view quiz content                  |
| Add Quiz            | Admins can create new quizzes through a dedicated form                          |
| Edit Quiz           | Admins can update existing quiz content                                         |
| Admin Dashboard     | Admin-only area for managing quizzes and platform content                       |
| Protected Routes    | Restricts access to specific pages based on authentication and role             |
| Context API         | Shares user, admin, loading, and error states across the app                    |
| Firebase Firestore  | Stores quiz data and admin-related information                                  |
| SEO Support         | Includes meta tags, sitemap, manifest, and structured data support              |
| PWA Support         | Includes web app manifest for installable app behavior                          |

---

## Tech Stack

<div align="center">

### Frontend

![React](https://img.shields.io/badge/React.js-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![SCSS](https://img.shields.io/badge/SCSS-CC6699?style=for-the-badge\&logo=sass\&logoColor=white)
![Styled Components](https://img.shields.io/badge/Styled%20Components-CSS--in--JS-DB7093?style=for-the-badge\&logo=styledcomponents\&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)

### Backend & Cloud Services

![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firebase Auth](https://img.shields.io/badge/Firebase%20Auth-Authentication-yellow?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firestore](https://img.shields.io/badge/Firestore-Database-orange?style=for-the-badge\&logo=firebase\&logoColor=white)
![Firebase Hosting](https://img.shields.io/badge/Firebase%20Hosting-Deployed-brightgreen?style=for-the-badge\&logo=firebase\&logoColor=black)

### Libraries & Tools

![React Router](https://img.shields.io/badge/React%20Router-Routing-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)
![React Firebase Hooks](https://img.shields.io/badge/React%20Firebase%20Hooks-Firebase%20Integration-orange?style=for-the-badge)
![Monaco Editor](https://img.shields.io/badge/Monaco%20Editor-Code%20Editor-blue?style=for-the-badge)
![MathJax](https://img.shields.io/badge/MathJax-Math%20Rendering-1D6F42?style=for-the-badge)
![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge\&logo=git\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge\&logo=github\&logoColor=white)

</div>

---

## Main Pages

| Page            | Route                | Description                           |
| --------------- | -------------------- | ------------------------------------- |
| Quiz List       | `/`                  | Displays available quizzes            |
| Authentication  | `/authenticate`      | Handles user login and authentication |
| Add Quiz        | `/addQuiz`           | Admin-only page for creating quizzes  |
| Show Quiz       | `/showQuiz/:id`      | Displays a specific quiz for users    |
| Admin Dashboard | `/admin`             | Admin-only management area            |
| Edit Quiz       | `/edit-quiz/:quizId` | Admin-only page for editing quizzes   |

---

## Main Components

| Component       | Description                                        |
| --------------- | -------------------------------------------------- |
| Navbar          | Main navigation bar for the application            |
| Auth Form       | Handles login and authentication interface         |
| Quiz Form       | Form used to create or edit quiz content           |
| Quiz Data       | Displays quiz information and questions            |
| Show Quiz Data  | Handles quiz display and answer flow               |
| Admin           | Admin management component                         |
| Loading Spinner | Displays loading state while data is being fetched |
| Navbar Quiz     | Navigation component for quiz-related pages        |

---

## Application Flow

```text
User Login
   ↓
Firebase Authentication
   ↓
Check Admin Status from Firestore
   ↓
MainContext Provider
   ↓
Render Pages Based on Authentication and Role
```

---

## State Management

### Main Context

The project uses React Context API to share global application state across components.

The shared state includes:

* Current user data
* Admin status
* Loading state
* User ID
* Selected tab
* Error messages

This helps avoid unnecessary prop drilling and keeps authentication and permission-related data available throughout the application.

---

## Security and Access Control

The platform includes multiple security-focused features:

* Firebase Authentication for secure login
* Admin role checking through Firestore
* Protected routes for admin-only pages
* Environment variables for Firebase configuration
* `.env` file excluded from GitHub using `.gitignore`
* Route-level access control for sensitive pages

---

## SEO and PWA Support

The project includes several enhancements for search engines and installable web app behavior:

* SEO meta tags
* Open Graph tags for social sharing
* Twitter Card metadata
* Canonical URL
* Structured Data using JSON-LD
* Sitemap file
* Robots file
* Web app manifest
* Favicon and app icons

---

## Project Structure

```bash
reactQuiz/
├── public/
│   ├── index.html
│   ├── m7md.ico
│   ├── manifest.json
│   ├── robots.txt
│   └── sitemap.xml
│
├── src/
│   ├── App.js
│   ├── App.scss
│   ├── index.js
│   ├── index.scss
│   │
│   ├── pages/
│   │   ├── authenticate.js
│   │   ├── quizs.js
│   │   ├── showQuiz.js
│   │   └── addQuiz.js
│   │
│   ├── components/
│   │   ├── navbar/
│   │   ├── authForm/
│   │   ├── QuizForm/
│   │   ├── quizData/
│   │   ├── showQuizData/
│   │   ├── Admin/
│   │   ├── LoadingSpinner/
│   │   └── navbarQuiz/
│   │
│   ├── utils/
│   │   ├── context.js
│   │   ├── firebaseConfig.js
│   │   ├── firebaseFunction.js
│   │   ├── checkRouter.js
│   │   ├── useWindowSize.js
│   │   └── hooks/
│   │
│   └── style/
│       └── authenticate.scss
│
├── package.json
├── firebase.json
├── jsconfig.json
└── .gitignore
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
cd reactQuiz
```

### 3. Install dependencies

```bash
npm install
```

### 4. Add environment variables

Create a `.env` file and add your Firebase configuration:

```env
REACT_APP_API_KEY=YOUR_API_KEY
REACT_APP_AUTH_DOMAIN=YOUR_AUTH_DOMAIN
REACT_APP_PROJECT_ID=YOUR_PROJECT_ID
REACT_APP_STORAGE_BUCKET=YOUR_STORAGE_BUCKET
REACT_APP_MESSAGING_SENDER_ID=YOUR_MESSAGING_SENDER_ID
REACT_APP_APP_ID=YOUR_APP_ID
REACT_APP_MEASUREMENT_ID=YOUR_MEASUREMENT_ID
```

### 5. Start the development server

```bash
npm start
```

### 6. Build for production

```bash
npm run build
```

---

## Development Highlights

* Built a quiz platform with authentication and admin permissions
* Implemented protected routing for admin-only pages
* Used Firebase Authentication for user login
* Used Firestore to store quiz data and user roles
* Managed global authentication and permission state using Context API
* Added support for code-based questions using Monaco Editor
* Added support for mathematical content using MathJax
* Improved SEO using metadata, sitemap, robots file, and structured data
* Deployed the application using Firebase Hosting

---

## What I Learned

Through this project, I practiced and improved my skills in:

* Building educational web applications with React
* Managing authentication with Firebase
* Creating role-based access control
* Protecting routes based on user permissions
* Managing global state with Context API
* Working with Firestore database
* Structuring scalable React components
* Building admin dashboards
* Improving SEO for React applications
* Preparing a React project for Firebase Hosting

---

## Future Improvements

* Improve quiz result analytics
* Add quiz categories and difficulty levels
* Add user profiles and quiz history
* Add timer functionality for quizzes
* Add certificate generation after quiz completion
* Add advanced admin dashboard statistics
* Add better validation for quiz creation
* Add dark mode
* Improve mobile UI/UX
* Add multilingual support

---

## Repository Status

This documentation is public, while the source code repository may remain private depending on project requirements or deployment configuration.

This project represents a real-world educational web application focused on quizzes, admin control, authentication, and Firebase-based data management.

---

## Author

<div align="center">

### Mohammed AL Bzoor

**Full Stack Developer | React & AI Automation Engineer**

[![GitHub](https://img.shields.io/badge/GitHub-mohammadbzoor-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammed%20AL%20Bzoor-0A66C2?style=for-the-badge\&logo=linkedin)](https://www.linkedin.com/in/mohammadbzoor)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-Quiz%20Platform-brightgreen?style=for-the-badge)](https://singup-12a91.web.app/)

</div>

---

## License

This documentation is available for portfolio and project presentation purposes.
