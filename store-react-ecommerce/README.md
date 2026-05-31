<div align="center">

# StoreReact - E-Commerce Web Application

### A modern e-commerce web application built with React.js and Firebase

A full-stack online store application that supports user authentication, product browsing, cart management, admin product control, real-time updates, and Firebase-based backend services.

<br />

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Visit%20Website-brightgreen?style=for-the-badge)](https://mohammadbzoor-9490e.firebaseapp.com/)
[![React](https://img.shields.io/badge/React.js-18.3-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)](https://react.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Backend-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)](https://firebase.google.com/)
[![SCSS](https://img.shields.io/badge/SCSS-Styling-CC6699?style=for-the-badge\&logo=sass\&logoColor=white)](https://sass-lang.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

</div>

---

## Overview

**StoreReact** is a modern e-commerce web application built with **React.js** and **Firebase**.

The project provides a complete online store experience, including user authentication, product browsing, cart management, admin-based product management, real-time database updates, and responsive UI design.

It was developed as a real-world full-stack web application to practice frontend development, Firebase integration, authentication flows, role-based access, state management, and e-commerce user experience.

---

## Live Demo

<div align="center">

### [View Live Website](https://mohammadbzoor-9490e.firebaseapp.com/)

</div>

---

## Features

| Feature                 | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| User Authentication     | Users can register and log in using Firebase Authentication  |
| User Roles              | Supports normal users and admin users                        |
| Product Store           | Displays available products in a clean store interface       |
| Product Filtering       | Allows products to be filtered dynamically                   |
| Product Cards           | Shows product details using reusable product card components |
| Shopping Cart           | Users can add products to the cart                           |
| Cart Management         | Users can view, update, and remove cart items                |
| Admin Panel             | Admins can add, edit, and delete products                    |
| Product Management      | Admin users can manage their own products                    |
| Real-Time Updates       | Uses Firebase real-time listeners to update data instantly   |
| Global State Management | Uses Context API to share user, cart, role, and product data |
| Responsive Design       | Works across desktop, tablet, and mobile screens             |
| Loading States          | Uses loading spinners for better user experience             |

---

## Tech Stack

<div align="center">

### Frontend

![React](https://img.shields.io/badge/React.js-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![SCSS](https://img.shields.io/badge/SCSS-CC6699?style=for-the-badge\&logo=sass\&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)
![React Icons](https://img.shields.io/badge/React%20Icons-Icons-blue?style=for-the-badge)

### Backend & Cloud Services

![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firebase Auth](https://img.shields.io/badge/Firebase%20Auth-Authentication-yellow?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firestore](https://img.shields.io/badge/Firestore-Database-orange?style=for-the-badge\&logo=firebase\&logoColor=white)
![Firebase Hosting](https://img.shields.io/badge/Firebase%20Hosting-Deployed-brightgreen?style=for-the-badge\&logo=firebase\&logoColor=black)

### Libraries & Tools

![React Router](https://img.shields.io/badge/React%20Router-7.1-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)
![React Firebase Hooks](https://img.shields.io/badge/React%20Firebase%20Hooks-Firebase%20Integration-orange?style=for-the-badge)
![React Loader Spinner](https://img.shields.io/badge/React%20Loader%20Spinner-Loading%20UI-blue?style=for-the-badge)
![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge\&logo=git\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge\&logo=github\&logoColor=white)

</div>

---

## Main Pages

| Page                | Description                                            |
| ------------------- | ------------------------------------------------------ |
| Authentication Page | Handles user login and registration                    |
| Store Page          | Displays products and allows users to browse the store |
| Cart Page           | Shows products added to the cart                       |
| Add Product Page    | Admin-only page for adding new products                |

---

## Main Components

| Component     | Description                               |
| ------------- | ----------------------------------------- |
| Navbar        | Main navigation bar with dynamic links    |
| Login Form    | Handles user login inputs                 |
| Register Form | Handles new user registration             |
| Product Card  | Displays product information in the store |
| Cart Card     | Displays cart item details                |
| Product Form  | Used by admins to add or update products  |

---

## Application Flow

```text
User Register / Login
   ↓
Firebase Authentication
   ↓
Fetch User Data and Role
   ↓
Load Store Products
   ↓
User Browses Products
   ↓
User Adds Products to Cart
   ↓
Cart Data Updates in Firestore
```

---

## Admin Flow

```text
Admin Login
   ↓
Verify Admin Role
   ↓
Access Product Management Page
   ↓
Add / Edit / Delete Products
   ↓
Products Update in Firestore
   ↓
Store UI Updates Automatically
```

---

## State Management

The application uses **React Context API** to share important data across the application.

Shared state includes:

* Current user data
* Username
* User role
* Admin status
* Cart products
* Filtered products
* Store data

This helps keep the application organized and reduces unnecessary prop drilling between components.

---

## Firebase Integration

The project uses Firebase for backend functionality, including:

* User authentication
* Firestore database
* User role management
* Product storage
* Cart storage
* Real-time updates
* Firebase Hosting deployment

Real-time updates are handled using Firebase listeners, allowing product and cart data to update immediately when changes happen in the database.

---

## Project Structure

```bash
store/
├── src/
│   ├── pages/
│   │   ├── authenticate.js
│   │   ├── store.js
│   │   ├── cart.js
│   │   └── addproduct.js
│   │
│   ├── components/
│   │   ├── navbar/
│   │   ├── login-form/
│   │   ├── register-form/
│   │   ├── product-card/
│   │   ├── cart-card/
│   │   └── product-form/
│   │
│   ├── utils/
│   │   ├── firebaseConfig.js
│   │   ├── firebaseFunctions/
│   │   └── context.js
│   │
│   ├── styles/
│   ├── App.js
│   └── index.js
│
└── package.json
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
cd store
```

### 3. Install dependencies

```bash
npm install
```

### 4. Add Firebase configuration

Create a Firebase project and add your Firebase configuration inside the project.

Example:

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

* Built a complete e-commerce user flow using React
* Implemented Firebase Authentication for login and registration
* Added user role handling for admins and normal users
* Created reusable product and cart components
* Built cart management functionality connected to Firestore
* Added admin product management features
* Used Context API for global state management
* Integrated Firebase real-time updates
* Styled the interface using SCSS
* Deployed the application using Firebase Hosting

---

## What I Learned

Through this project, I practiced and improved my skills in:

* Building e-commerce applications with React
* Managing authentication with Firebase
* Creating role-based access control
* Working with Firestore database
* Managing cart logic and product state
* Building reusable React components
* Handling real-time database updates
* Structuring scalable React projects
* Using Context API for shared application state
* Deploying React applications using Firebase Hosting

---

## Future Improvements

* Add product categories and advanced filtering
* Add product search
* Add checkout workflow
* Add payment integration
* Add order history
* Add user profile page
* Add admin dashboard analytics
* Add product images upload using Firebase Storage
* Improve UI/UX design
* Improve Firebase security rules
* Add dark mode
* Add unit and integration tests

---

## Repository Status

This documentation is public, while the source code repository may remain private depending on project requirements or deployment configuration.

This project represents a real-world e-commerce web application focused on authentication, product management, cart functionality, admin control, and Firebase-based backend services.

---

## Author

<div align="center">

### Mohammed AL Bzoor

**Full Stack Developer | React & AI Automation Engineer**

[![GitHub](https://img.shields.io/badge/GitHub-mohammadbzoor-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammed%20AL%20Bzoor-0A66C2?style=for-the-badge\&logo=linkedin)](https://www.linkedin.com/in/mohammadbzoor)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-StoreReact-brightgreen?style=for-the-badge)](https://mohammadbzoor-9490e.firebaseapp.com/)

</div>

---

## License

This documentation is available for portfolio and project presentation purposes.
