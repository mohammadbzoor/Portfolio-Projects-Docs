<div align="center">

# Tesla Coffee — Digital Menu, POS Cashier & Restaurant Management System

### A cloud-native cafe & restaurant operations suite built with React 19 and Firebase

An integrated SaaS-style platform that combines a customer-facing digital storefront with a full point-of-sale cashier terminal, live inventory CMS, order management, and real-time financial analytics — built to run an actual cafe's daily operations end to end.

<br />

[![Repository](https://img.shields.io/badge/View%20Repository-GitHub-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor/TeslaCoffee)
[![React](https://img.shields.io/badge/React-19.1.0-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)](https://react.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-v12.14.0-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)](https://firebase.google.com/)
[![React Router](https://img.shields.io/badge/React%20Router-v7.6.2-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)](https://reactrouter.com/)
[![Framer Motion](https://img.shields.io/badge/Framer%20Motion-12.19.1-0055FF?style=for-the-badge\&logo=framer\&logoColor=white)](https://www.framer.com/motion/)

</div>

---

## Overview

**Tesla Coffee** is an integrated management ecosystem built to streamline end-to-end cafe and restaurant operations. Rather than a static digital menu, the platform combines customer self-ordering with a complete administrative and point-of-sale toolkit, all synced in real time through Firebase.

The system is split into two connected experiences:

* **Customer Storefront** — a live, filterable digital menu with cart and WhatsApp checkout
* **Admin & Operations Suite** — a touch-optimized POS cashier, inventory CMS, order tracking, and daily financial reporting

This project was built as a real-world, production-style SaaS system to practice complex state management, serverless architecture, role-based access control, and operational tooling beyond a typical storefront.

---

## Features

| Feature                      | Description                                                                                     |
| ----------------------------- | ------------------------------------------------------------------------------------------------- |
| Touch-Optimized POS Cashier   | Large touch-friendly product tiles, table assignment, kitchen notes, and instant order injection  |
| Printable POS Invoices        | Built-in invoice rendering engine formatted for thermal printers or standard paper receipts       |
| Live Inventory & Category CMS | Real-time CRUD for menu items with in-browser image cropping before upload to Firebase Storage    |
| Promotional Pricing Engine    | Dual-price fields with automatic discount badges and savings percentages                          |
| Real-Time Order Management    | Live Firestore-powered order tracking with status transitions (Pending → In Progress → Completed) |
| Daily Financial Analytics     | Automatic daily sales aggregation with revenue, order counts, and active table stats              |
| Excel Export                  | One-click export of live order data into `.xlsx` spreadsheets for bookkeeping and auditing        |
| Customer Digital Storefront   | Debounced search, live category filtering, and a persistent cart saved to local storage           |
| WhatsApp Order Dispatch       | Encodes cart items, notes, and table info into a WhatsApp message sent directly to the business    |
| Role-Based Access Control     | Firebase Authentication separating Admin, Staff, and Customer access levels                       |

---

## Tech Stack

<div align="center">

### Frontend

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![React Router](https://img.shields.io/badge/React%20Router-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer%20Motion-0055FF?style=for-the-badge\&logo=framer\&logoColor=white)

### Backend & Database

![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firestore](https://img.shields.io/badge/Firestore-Realtime%20Database-orange?style=for-the-badge\&logo=firebase\&logoColor=white)
![Firebase Auth](https://img.shields.io/badge/Firebase%20Auth-RBAC-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)
![Firebase Storage](https://img.shields.io/badge/Firebase%20Storage-Media%20CDN-FFCA28?style=for-the-badge\&logo=firebase\&logoColor=black)

### Libraries & Tools

![react-easy-crop](https://img.shields.io/badge/react--easy--crop-Image%20Cropping-blue?style=for-the-badge)
![xlsx](https://img.shields.io/badge/xlsx-Excel%20Export-green?style=for-the-badge)
![React Icons](https://img.shields.io/badge/React%20Icons-FontAwesome-528DD7?style=for-the-badge)

</div>

---

## Core Functional Modules

### 1. POS Cashier Terminal
A dedicated `/admin-dashboard` view built for counter staff — rapid order entry, table assignment, custom kitchen notes, live cart calculations, and printable invoices generated on the spot.

### 2. Product & Category CMS
Live, real-time CRUD for menu items and categories, with an in-browser image cropping pipeline so managers can frame product photos before they're pushed to Firebase Storage.

### 3. Order Lifecycle & Table Management
Real-time order streaming via Firestore listeners, with status toggles, line-item adjustments, and bulk or single-order purge utilities.

### 4. Financial Intelligence & Reporting
Live KPI cards (revenue, completed vs. pending orders, active tables) plus a daily aggregation engine and one-click Excel export for bookkeeping.

### 5. Customer Storefront
A dark, branded ordering experience with instant search, category filtering, a persistent cart, and a WhatsApp-based checkout flow — no payment gateway required to place an order.

---

## Data Models

### Menu Item (`menuItems` collection)
```typescript
interface MenuItem {
  id: string;
  title: string;
  price: number;
  newPrice?: number;       // Discounted offer price
  category: string;
  section?: string;        // 'offers' | 'regular'
  imgUrl: string;
  description?: string;
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

### Order (`orders` collection)
```typescript
interface Order {
  id: string;
  tableNumber?: string;
  notes?: string;
  items: Array<{ id: string; name: string; price: number; quantity: number }>;
  total: number;
  status: "pending" | "in-progress" | "completed";
  createdAt: Timestamp;
}
```

---

## Project Structure

```bash
TeslaCoffee/
├── README.md
└── coffee/                          # Core React 19 application
    ├── firebase.json                # Firebase Hosting & CDN config
    ├── package.json
    ├── public/
    └── src/
        ├── App.js
        ├── components/
        │   ├── admin/
        │   │   ├── cashier/         # POS terminal components
        │   │   ├── ProductManagement.js
        │   │   ├── CategoryManager.js
        │   │   ├── OrdersTable.js
        │   │   ├── DailySummaryTable.js
        │   │   ├── StatsCards.js
        │   │   └── InvoicePrintView.js
        │   ├── auth/                 # Login, registration, route guards
        │   └── ...                   # Storefront components (Navbar, CardList, etc.)
        ├── pages/
        │   ├── Home.js
        │   ├── cart.js
        │   ├── offers.js
        │   └── AdminDashboard.js
        ├── firebase/
        │   └── firebese.js
        └── utils/
            ├── AuthContext.js
            ├── CartContext.js
            ├── adminStats.js
            ├── orderHelpers.js
            └── exportOrdersToExcel.js
```

---

## Installation and Setup

### 1. Clone the repository
```bash
git clone https://github.com/mohammadbzoor/TeslaCoffee.git
cd TeslaCoffee/coffee
```

### 2. Install dependencies
```bash
npm install
```

### 3. Configure Firebase
Add your project credentials in `coffee/src/firebase/firebese.js`:
```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.firebasestorage.app",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

### 4. Run the development server
```bash
npm start
```
The app runs at `http://localhost:3000`.

### 5. Build & deploy
```bash
npm run build
firebase deploy
```

---

## Development Highlights

* Designed a dual-experience platform (customer storefront + admin operations) sharing one Firebase backend
* Built a touch-optimized POS cashier flow for real counter use, including printable invoices
* Implemented an in-browser image cropping pipeline before uploading product photos to Cloud Storage
* Built a daily sales aggregation engine and Excel export utility for financial reporting
* Implemented role-based access control across Admin, Staff, and Customer flows
* Used Framer Motion for interaction polish across both storefront and admin views

---

## What I Learned

Through this project, I practiced and improved my skills in:

* Structuring a multi-role, production-style SaaS application
* Designing real-time, serverless architecture with Firestore listeners
* Managing complex shared state across a storefront and an internal admin suite
* Implementing client-side image processing and Excel generation
* Building operational tooling (POS, invoicing, reporting) beyond a typical CRUD app

---

## Future Improvements

* Add online payment integration alongside the WhatsApp checkout flow
* Add a kitchen display screen synced with live order status
* Add multi-branch / multi-location support
* Add push notifications for new incoming orders
* Improve Firestore security rules and role granularity
* Add multilingual (Arabic/English) support across the storefront

---

## Repository Status

This project's source code is public. The full technical README — including architecture diagrams and complete data schemas — is available in the live repository linked below.

---

## Author

<div align="center">

### Mohammed AL Bzoor

**Full Stack Developer | React & AI Automation Engineer**

[![GitHub](https://img.shields.io/badge/GitHub-mohammadbzoor-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammed%20AL%20Bzoor-0A66C2?style=for-the-badge\&logo=linkedin)](https://www.linkedin.com/in/mohammadbzoor)
[![Repository](https://img.shields.io/badge/Repository-TeslaCoffee-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor/TeslaCoffee)

</div>

---

## License

This documentation is available for portfolio and project presentation purposes.
