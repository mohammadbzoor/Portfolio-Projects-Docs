<div align="center">

# Portfolio Web Application

### A modern full-stack portfolio web application built with React.js and Firebase

A dynamic portfolio platform featuring authentication, protected routes, admin dashboard, notes management, PDF viewing, and Firebase Hosting deployment.

<br />

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Visit%20Website-brightgreen?style=for-the-badge)](https://profaile-19e99.web.app/)
[![React](https://img.shields.io/badge/React.js-18.3.1-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)](https://react.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Backend-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)](https://firebase.google.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

</div>

---

## Overview

**Portfolio Web Application** is a full-stack web application designed to present personal information, projects, certificates, files, and notes through a clean and interactive user interface.

The project goes beyond a traditional static portfolio. It includes Firebase Authentication, protected routes, Firestore database integration, PDF viewing, admin-only access, and dynamic content management.

This project represents one of my early real-world full-stack web applications, started during my development journey in **February 2025**.

---

## Live Demo

<div align="center">

### [View Live Website](https://profaile-19e99.web.app/)

</div>

---

## Features

| Feature              | Description                                          |
| -------------------- | ---------------------------------------------------- |
| Responsive UI        | Modern and responsive portfolio interface            |
| Authentication       | Login and registration using Firebase Authentication |
| Protected Routes     | Restricts access to private pages                    |
| Admin Dashboard      | Admin-only section for managing dynamic content      |
| Notes Management     | Create, update, and manage notes                     |
| Projects Showcase    | Display portfolio projects in a structured layout    |
| Certificates Section | Showcase certificates and achievements               |
| PDF Viewer           | View PDF files directly inside the application       |
| Firebase Integration | Uses Firestore, Authentication, Storage, and Hosting |
| React Router         | Smooth navigation between pages                      |
| Reusable Components  | Organized and scalable React component structure     |

---

## Tech Stack

<div align="center">

### Frontend

![React](https://img.shields.io/badge/React.js-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge\&logo=css3\&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-38B2AC?style=for-the-badge\&logo=tailwind-css\&logoColor=white)

### Backend & Cloud Services

![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firestore](https://img.shields.io/badge/Firestore-Database-orange?style=for-the-badge\&logo=firebase\&logoColor=white)
![Firebase Auth](https://img.shields.io/badge/Firebase%20Auth-Authentication-yellow?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firebase Hosting](https://img.shields.io/badge/Firebase%20Hosting-Deployed-brightgreen?style=for-the-badge\&logo=firebase\&logoColor=black)

### Tools & Libraries

![React Router](https://img.shields.io/badge/React%20Router-Routing-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)
![React Icons](https://img.shields.io/badge/React%20Icons-Icons-blue?style=for-the-badge)
![React PDF Viewer](https://img.shields.io/badge/React%20PDF%20Viewer-PDF%20Support-red?style=for-the-badge)
![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge\&logo=git\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge\&logo=github\&logoColor=white)

</div>

---

## Project Structure

```bash
src/
├── components/
│   ├── aboutMe/
│   ├── admin/
│   ├── certificate/
│   ├── content/
│   ├── dataForm/
│   ├── login-and-regsister/
│   ├── navbar/
│   ├── note/
│   └── sliderHome/
│
├── pages/
│   ├── admin.js
│   ├── authentication.js
│   ├── files.js
│   ├── home.js
│   ├── notes.js
│   └── project.js
│
├── image/
├── style/
├── utils/
│
├── App.js
├── App.css
└── index.js
```

---

## Main Pages

| Page                | Description                                                                           |
| ------------------- | ------------------------------------------------------------------------------------- |
| Home Page           | Displays personal information, featured content, certificates, and project highlights |
| Projects Page       | Showcases portfolio projects in a structured and user-friendly layout                 |
| Files Page          | Provides PDF file viewing support and access to file-based content                    |
| Notes Page          | Protected page that allows authenticated users to manage notes                        |
| Admin Dashboard     | Restricted dashboard for managing portfolio data and dynamic content                  |
| Authentication Page | Handles user login and registration using Firebase Authentication                     |

---

## Key Functionalities

### Authentication System

The application includes login and registration functionality using Firebase Authentication. Protected routes are implemented to restrict access to private sections such as notes and admin pages.

### Admin Access Control

The admin dashboard includes restricted access to ensure that only authorized users can manage portfolio content and update sensitive data.

### Notes Management

Users can create, update, and manage notes, with data stored and handled using Firebase Firestore.

### Dynamic Content Management

Portfolio sections such as projects, certificates, and personal content are structured to support dynamic updates and future scalability.

### File and PDF Handling

The application supports displaying PDF files inside the web application and managing file-based content through Firebase services.

---

## Installation and Setup

### 1. Clone the source repository

> The source code repository may be private. If access is available, clone it using:

```bash
git clone https://github.com/mohammadbzoor/Portfolio-.git
```

### 2. Navigate to the project directory

```bash
cd Portfolio-
```

### 3. Install dependencies

```bash
npm install
```

### 4. Start the development server

```bash
npm start
```

### 5. Build for production

```bash
npm run build
```

---

## Firebase Configuration

To run this project locally, create a Firebase project and enable the following services:

* Firebase Authentication
* Firestore Database
* Firebase Storage
* Firebase Hosting

Then add your Firebase configuration inside the project.

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

> Important: Do not expose private keys or sensitive environment variables in public repositories.

---

## Development Highlights

* Designed and implemented a responsive portfolio interface using React.js
* Built reusable components for portfolio sections and UI structure
* Integrated Firebase Authentication for login and registration
* Implemented protected routes for private pages
* Created an admin dashboard for managing dynamic content
* Used Firestore to store and manage application data
* Added PDF viewing support for file-based content
* Deployed the project using Firebase Hosting

---

## What I Learned

Through this project, I practiced and improved my skills in:

* Building full-stack web applications with React and Firebase
* Creating reusable React components
* Managing routing using React Router
* Implementing Firebase Authentication
* Working with Firestore Database
* Handling protected routes
* Building admin-only sections
* Managing dynamic portfolio content
* Displaying PDF files inside a web application
* Deploying applications using Firebase Hosting
* Organizing a real-world frontend project structure

---

## Future Improvements

* Improve the overall UI/UX design
* Add dark mode support
* Add advanced admin controls
* Improve Firebase security rules
* Add search and filtering for projects
* Add analytics for portfolio visits
* Optimize loading speed and performance
* Refactor components for better scalability

---

## Repository Status

This documentation is public, while the source code repository may remain private depending on project requirements, privacy, or deployment configuration.

The project represents one of my early real-world full-stack web applications, started during my development journey in **February 2025**.

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
