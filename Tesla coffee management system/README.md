<div align="center">

# Tesla Coffee

### Digital Menu, POS Cashier & Cafe Management System

A cafe management system built with React 19 and Firebase. It combines a customer-facing digital menu with an admin dashboard that includes a POS cashier, order management, menu management, and daily sales reports. The interface is fully Arabic (RTL), with prices in Jordanian Dinar (JOD).

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Tesla%20Coffee-22C55E?style=for-the-badge&logo=googlechrome&logoColor=white)](https://teslacoffee-04.web.app/)
[![Repository](https://img.shields.io/badge/Repository-GitHub-181717?style=for-the-badge&logo=github)](https://github.com/mohammadbzoor/TeslaCoffee)
[![React](https://img.shields.io/badge/React-19.1.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-12.14.0-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com/)

</div>

---

## Overview

Tesla Coffee has two connected parts that share one Firebase backend:

- **Customer storefront:** a live, filterable digital menu with a cart and WhatsApp checkout
- **Admin dashboard:** a touch-friendly POS cashier, order tracking, menu and category management, and daily sales reports

**Live:** [teslacoffee-04.web.app](https://teslacoffee-04.web.app/)

---

## Features

| Feature | Description |
|---|---|
| POS cashier | Large product tiles, table number, kitchen notes, live total, and instant order creation |
| Printable invoices | Invoice view formatted for thermal printers or standard paper |
| Menu and category management | Add, edit, and delete items with in-browser image cropping before upload to Firebase Storage |
| Promotional pricing | Old and new price fields with automatic discount badges and savings percentage |
| Real-time orders | Live Firestore order stream with status changes (pending, in progress, completed) |
| Daily sales summary | Daily aggregation of revenue and order counts, with Excel export |
| Customer storefront | Debounced search, category filtering, and a cart saved in local storage |
| WhatsApp checkout | Cart items, notes, and table info are encoded into a WhatsApp message to the business |
| Authentication | Firebase Authentication with route guards for the admin area |
| Arabic RTL interface | Fully Arabic admin dashboard and storefront, with prices in JOD |

---

## Admin Dashboard

The admin dashboard is a single Arabic (RTL) page at `/admin-dashboard`. The cafe team moves between sections using tabs, so they can follow orders and sales without complex navigation.

| Tab | What it does |
|---|---|
| Overview | KPI cards: revenue, completed vs pending orders, and active tables |
| Orders | Live order stream from Firestore, status changes, line-item edits, and order cleanup |
| Cashier | Quick POS for creating table orders directly from the dashboard |
| Products | Add, edit, and delete menu items, with image cropping before upload |
| Categories | Manage the menu categories used by the cashier and the storefront |
| Daily Summary | Daily sales aggregation with revenue and order counts, with Excel export |
| Admin Tools | Maintenance utilities for managing data |

### Quick Cashier

The cashier is built for fast counter use:

- **Product grid:** large tiles with images and prices, filtered by category (hot coffee, cold coffee, hot drinks, soft drinks, cocktails, milkshakes, waffles) or by search
- **Current order panel:** table number, kitchen notes, live total, and buttons to create or clear the order
- **Instant creation:** the new order appears in the Orders tab through the same Firestore listeners, and an invoice can be printed

---

## Customer Storefront

A dark, branded ordering experience with instant search, category filtering, an offers page, and a persistent cart. Orders are sent through a WhatsApp checkout flow, so no payment gateway is needed to place an order.

---

## Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | React 19.1.0, React Router 7.6.2, Bootstrap, Framer Motion 12.19.1 |
| Backend and database | Firebase 12.14.0: Firestore, Authentication, Storage, Hosting |
| Libraries | react-easy-crop (image cropping), xlsx (Excel export), React Icons |

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
    ├── firebase.json                # Firebase Hosting config
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
        │   ├── auth/                # Login, registration, route guards
        │   └── ...                  # Storefront components (Navbar, CardList, etc.)
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

### 5. Build and deploy

```bash
npm run build
firebase deploy
```

---

## What I Learned

- Structuring a multi-section React application with a customer side and an admin side
- Building real-time features with Firestore listeners
- Managing shared state across the storefront and the admin dashboard
- Client-side image cropping and Excel generation
- Building operational tools (POS, invoices, reports) beyond a basic CRUD app

---

## Future Improvements

- Add online payment alongside the WhatsApp checkout
- Add a kitchen display screen synced with live order status
- Add multi-branch support
- Add push notifications for new orders
- Improve Firestore security rules and role granularity
- Add English language support

---

## Author

<div align="center">

### Mohammed AL Bzoor

**Full Stack Developer | React & AI Automation Engineer**

[![GitHub](https://img.shields.io/badge/GitHub-mohammadbzoor-181717?style=for-the-badge&logo=github)](https://github.com/mohammadbzoor)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammed%20AL%20Bzoor-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/mohammadbzoor)

</div>
