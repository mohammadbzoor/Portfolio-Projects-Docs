<div align="center">

# Restaurant Management System

### A modern restaurant menu and ordering web application built with React.js and Firebase

A full-stack restaurant web application that allows users to browse menu items, search and filter products, view offers, add items to the cart, and interact with a modern restaurant ordering experience.

<br />

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Visit%20Website-brightgreen?style=for-the-badge)](https://projectm-f5389.web.app/)
[![React](https://img.shields.io/badge/React.js-19.1.0-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)](https://react.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Backend-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)](https://firebase.google.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-UI-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)](https://getbootstrap.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

</div>

---

## Overview

**Restaurant Management System** is a modern web application designed for restaurants and food businesses. The project provides a smooth customer-facing interface for browsing food items, filtering categories, viewing special offers, and managing cart selections.

The application is built with **React.js** and integrates with **Firebase** for storing and managing menu data. It focuses on creating a practical restaurant ordering experience with responsive design, dynamic content, reusable components, and a clean user flow.

This project was developed as a real-world web application to practice frontend development, Firebase integration, state management, routing, UI design, and product-focused problem solving.

---

## Live Demo

<div align="center">

### [View Live Website](https://projectm-f5389.web.app/)

</div>

---

## Features

| Feature               | Description                                                                                                     |
| --------------------- | --------------------------------------------------------------------------------------------------------------- |
| Home Page             | Displays a modern landing page with slider, featured menu items, offers, about section, and contact information |
| Full Menu Page        | Shows all menu items in an organized and responsive layout                                                      |
| Category Filtering    | Allows users to filter products by category such as pizza, drinks, desserts, and more                           |
| Search Functionality  | Enables users to search for menu items by name or number                                                        |
| Offers Page           | Displays discounted products with old and new prices                                                            |
| Add Menu Item         | Provides a form to add new products with title, description, image, price, and category                         |
| Shopping Cart         | Allows users to add products to the cart and view selected items                                                |
| Cart Counter          | Shows the number of cart items directly in the navigation bar                                                   |
| Responsive Design     | Works across desktop, tablet, and mobile screens                                                                |
| Firebase Integration  | Stores and manages product data using Firebase                                                                  |
| Local Storage Support | Keeps cart data available locally for better user experience                                                    |
| Smooth UI Animations  | Uses motion and carousel libraries to improve interaction                                                       |

---

## Tech Stack

<div align="center">

### Frontend

![React](https://img.shields.io/badge/React.js-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![React Bootstrap](https://img.shields.io/badge/React%20Bootstrap-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge\&logo=css3\&logoColor=white)

### Backend & Database

![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firestore](https://img.shields.io/badge/Firestore-Database-orange?style=for-the-badge\&logo=firebase\&logoColor=white)

### Libraries & Tools

![React Router](https://img.shields.io/badge/React%20Router-Routing-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer%20Motion-Animations-black?style=for-the-badge\&logo=framer\&logoColor=white)
![React Slick](https://img.shields.io/badge/React%20Slick-Carousel-blue?style=for-the-badge)
![FontAwesome](https://img.shields.io/badge/FontAwesome-Icons-528DD7?style=for-the-badge\&logo=fontawesome\&logoColor=white)
![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge\&logo=git\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge\&logo=github\&logoColor=white)

</div>

---

## Main Pages

| Page          | Route     | Description                                                                           |
| ------------- | --------- | ------------------------------------------------------------------------------------- |
| Home          | `/`       | Main landing page with slider, featured products, offers, about, and contact sections |
| Menu          | `/menu`   | Displays all menu products with filtering and search                                  |
| Add Menu Item | `/add`    | Form for adding new food items                                                        |
| Cart          | `/cart`   | Shows selected cart items and total price                                             |
| Offers        | `/offers` | Displays discounted and special offer products                                        |

---

## Main Components

| Component | Description                                                                        |
| --------- | ---------------------------------------------------------------------------------- |
| Navbar    | Main navigation bar with logo, links, search field, social links, and cart counter |
| Slider    | Dynamic image carousel displayed on the home page                                  |
| Category  | Category filter for menu items                                                     |
| CardList  | Displays products as interactive cards                                             |
| About     | Shows information about the restaurant or project                                  |
| Contact   | Displays contact section or contact form                                           |
| Gallery   | Shows visual content and product images                                            |
| Footer    | Contains footer links and contact information                                      |

---

## State Management

### Cart Context

The project uses a cart context to manage cart state globally across the application.

Main responsibilities include:

* Tracking the number of cart items
* Updating cart count after cart actions
* Keeping cart data available through LocalStorage
* Sharing cart state between components

---

## Key Functionalities

### Menu Browsing

Users can browse available food products through a clean and responsive menu interface.

### Product Filtering

The menu page supports category-based filtering, making it easier for users to browse specific food types.

### Product Search

Users can search for menu items by product name or number.

### Cart Management

Users can add items to the cart, view selected products, and manage their order selections.

### Offers Display

Products with discounts can be shown with both old and new prices, making special offers visually clear.

### Add Product Form

The application includes a form for adding menu items with product title, description, image URL, price, old price, category, and offer-related options.

---

## Project Structure

```bash
restaurant-management-system/
├── README.md
└── menu/
    ├── package.json
    ├── public/
    └── src/
        ├── App.js
        ├── index.js
        ├── pages/
        │   ├── Home.js
        │   ├── Cart.js
        │   ├── MenuForm.js
        │   └── Offers.js
        ├── components/
        │   ├── Navbar/
        │   ├── Category/
        │   ├── CardList/
        │   ├── slider/
        │   ├── footer/
        │   ├── about/
        │   ├── Gallery/
        │   ├── Contact/
        │   └── heder/
        ├── utils/
        │   ├── CartContext.js
        │   ├── functionFirebase.js
        │   └── functionMenu.js
        └── style/
```

---

## Installation and Setup

### 1. Clone the source repository

> The source code repository may be private. If access is available, clone it using:

```bash
git clone YOUR_REPOSITORY_LINK
```

### 2. Navigate to the project folder

```bash
cd restaurant-management-system/menu
```

### 3. Install dependencies

```bash
npm install
```

### 4. Configure Firebase

Create a Firebase project and add your Firebase configuration inside the project.

### 5. Start the development server

```bash
npm start
```

### 6. Build for production

```bash
npm run build
```

---

## Firebase Configuration

To run this project locally, create a Firebase project and enable the required database services.

Example Firebase configuration:

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

* Built a complete restaurant menu and cart workflow
* Designed a responsive food ordering interface
* Implemented category filtering and product search
* Created reusable React components for product cards, navigation, slider, and sections
* Integrated Firebase for storing and managing menu data
* Used LocalStorage to persist cart-related data
* Improved user interaction using animation and carousel libraries
* Deployed the project using Firebase Hosting

---

## What I Learned

Through this project, I practiced and improved my skills in:

* Building real-world React applications
* Creating responsive user interfaces
* Managing state using Context API
* Handling cart logic and local storage
* Working with Firebase as a backend service
* Structuring reusable components
* Building search and filter functionality
* Designing restaurant and e-commerce-style user flows
* Deploying applications using Firebase Hosting

---

## Future Improvements

* Add authentication for restaurant admins
* Add advanced dashboard analytics
* Add order status tracking
* Add online payment integration
* Add product categories management
* Add notifications for new orders
* Improve Firebase security rules
* Improve SEO and performance
* Add multilingual support
* Add role-based access control

---

## Repository Status

This documentation is public, while the source code repository may remain private depending on project requirements or deployment configuration.

This project represents a real-world restaurant web application focused on menu browsing, cart management, offers, and food ordering workflows.

---

## Author

<div align="center">

### Mohammed AL Bzoor

**Full Stack Developer | React & AI Automation Engineer**

[![GitHub](https://img.shields.io/badge/GitHub-mohammadbzoor-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammed%20AL%20Bzoor-0A66C2?style=for-the-badge\&logo=linkedin)](https://www.linkedin.com/in/mohammadbzoor)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-Restaurant%20App-brightgreen?style=for-the-badge)](https://projectm-f5389.web.app/)

</div>

---

## License

This documentation is available for portfolio and project presentation purposes.
