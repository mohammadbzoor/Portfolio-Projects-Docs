<h1 align="center">🛒 E-Commerce REST API</h1>

<p align="center">
  <strong>A production-ready, full-featured E-Commerce backend built with Node.js, Express &amp; MongoDB</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-v24.14.0-339933?style=for-the-badge&logo=node.js&logoColor=white" />
  <img src="https://img.shields.io/badge/Express-v5.2.1-000000?style=for-the-badge&logo=express&logoColor=white" />
  <img src="https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=for-the-badge&logo=mongodb&logoColor=white" />
  <img src="https://img.shields.io/badge/JWT-Auth-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" />
  <img src="https://img.shields.io/badge/Stripe-Payments-635BFF?style=for-the-badge&logo=stripe&logoColor=white" />
  <img src="https://img.shields.io/badge/License-ISC-blue?style=for-the-badge" />
</p>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [API Endpoints](#-api-endpoints)
- [Security](#-security)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Project Structure](#-project-structure)
- [Author](#-author)

---

## 🚀 Overview

A robust, scalable RESTful API for a full E-Commerce platform. This backend handles everything from user authentication and product management to shopping carts, orders, and real-time Stripe payment processing via webhooks.

Built following best practices for **security**, **performance**, and **maintainability** — production-ready out of the box.

---

## ✨ Features

### 🔐 Authentication & Authorization
- JWT-based authentication with expiry control
- Role-based access control: `user`, `manager`, `admin`
- Secure password hashing with **bcryptjs** (12 salt rounds)
- Forgot password flow with **6-digit OTP** sent via email
- OTP verification & secure password reset
- Token invalidation on password change

### 🛍️ Product Management
- Full CRUD for Products, Categories, Subcategories, and Brands
- Image upload with on-the-fly **image processing & resizing** via Sharp
- Slug auto-generation for SEO-friendly URLs
- Product reviews & dynamic **ratings average** calculation

### 🛒 Shopping & Orders
- Shopping cart management (add, update, remove items)
- Coupon/discount code system
- Order creation (cash on delivery & online payment)
- **Stripe payment integration** with webhook support
- Order status management (admin/manager controls)

### 👤 User Profile
- Wishlist management (add/remove products)
- Multiple saved delivery addresses
- Profile image upload
- Soft delete for user accounts (`active` flag)

### ⚙️ Advanced API Features
- **Filtering** — filter by any field with `[gt]`, `[gte]`, `[lt]`, `[lte]` operators
- **Sorting** — multi-field sorting support
- **Field Limiting** — select only needed fields to reduce payload
- **Full-Text Search** — keyword search across products, categories, etc.
- **Pagination** — with `currentPage`, `numberOfPages`, `next`, and `prev` metadata

---

## 🛠 Tech Stack

| Category | Technology |
|---|---|
| **Runtime** | Node.js v24.14.0 |
| **Framework** | Express.js v5 |
| **Database** | MongoDB Atlas via Mongoose v9 |
| **Authentication** | JSON Web Tokens (JWT) |
| **Password Hashing** | bcryptjs |
| **Payment Gateway** | Stripe v22 |
| **Email Service** | Nodemailer (SMTP/Gmail) |
| **Image Processing** | Sharp |
| **File Uploads** | Multer |
| **Input Validation** | express-validator |
| **Security** | Helmet, HPP, CORS, Rate Limiting, XSS sanitization, NoSQL injection protection |
| **Logging** | Morgan |
| **Compression** | compression |
| **Linting** | ESLint (Airbnb config) + Prettier |
| **Dev Server** | Nodemon |

---

## 🏗 Architecture

The project follows a clean **MVC-inspired layered architecture**:

```
┌─────────────────────────────────────────────────┐
│                   Client / Frontend              │
└──────────────────────┬──────────────────────────┘
                       │ HTTP Requests
┌──────────────────────▼──────────────────────────┐
│              Security Middleware Layer            │
│   Helmet · CORS · Rate Limiter · HPP             │
│   XSS Sanitizer · NoSQL Injection Guard          │
└──────────────────────┬──────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────┐
│                  Routes Layer                    │
│    /api/v1/auth  /api/v1/products  /api/v1/...   │
└──────────────────────┬──────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────┐
│               Validators Middleware              │
│           express-validator schemas              │
└──────────────────────┬──────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────┐
│               Services Layer                    │
│   Business logic, CRUD, Factory handlers        │
└──────────────────────┬──────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────┐
│                 Models Layer                    │
│        Mongoose Schemas & Data Models           │
└──────────────────────┬──────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────┐
│              MongoDB Atlas Database              │
└─────────────────────────────────────────────────┘
```

---

## 📡 API Endpoints

Base URL: `http://localhost:8000/api/v1`

### 🔑 Authentication — `/api/v1/auth`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `POST` | `/signup` | Register a new user | Public |
| `POST` | `/login` | Login and receive JWT | Public |
| `POST` | `/forgotPassword` | Request password reset OTP | Public |
| `POST` | `/verifyResetCode` | Verify the OTP code | Public |
| `PUT` | `/resetPassword` | Set a new password | Public |

### 👥 Users — `/api/v1/users`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get all users | Admin |
| `GET` | `/:id` | Get user by ID | Admin |
| `POST` | `/` | Create user | Admin |
| `PUT` | `/:id` | Update user | Admin |
| `DELETE` | `/:id` | Delete user | Admin |
| `GET` | `/getMe` | Get logged-in user profile | User |
| `PUT` | `/updateMe` | Update own profile | User |
| `PUT` | `/changeMyPassword` | Change own password | User |
| `DELETE` | `/deleteMe` | Deactivate own account | User |

### 📦 Products — `/api/v1/products`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get all products (filter/sort/search/paginate) | Public |
| `GET` | `/:id` | Get product by ID | Public |
| `POST` | `/` | Create product | Admin / Manager |
| `PUT` | `/:id` | Update product | Admin / Manager |
| `DELETE` | `/:id` | Delete product | Admin |

### 🗂 Categories — `/api/v1/categories`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get all categories | Public |
| `GET` | `/:id` | Get category by ID | Public |
| `POST` | `/` | Create category | Admin / Manager |
| `PUT` | `/:id` | Update category | Admin / Manager |
| `DELETE` | `/:id` | Delete category | Admin |

### 🏷 Subcategories — `/api/v1/subcategories`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get all subcategories | Public |
| `POST` | `/` | Create subcategory | Admin / Manager |
| `PUT` | `/:id` | Update subcategory | Admin / Manager |
| `DELETE` | `/:id` | Delete subcategory | Admin |

### 🏢 Brands — `/api/v1/brands`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get all brands | Public |
| `GET` | `/:id` | Get brand by ID | Public |
| `POST` | `/` | Create brand | Admin / Manager |
| `PUT` | `/:id` | Update brand | Admin / Manager |
| `DELETE` | `/:id` | Delete brand | Admin |

### ⭐ Reviews — `/api/v1/reviews`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get all reviews | Public |
| `GET` | `/:id` | Get review by ID | Public |
| `POST` | `/` | Create review | User |
| `PUT` | `/:id` | Update review | User (owner) |
| `DELETE` | `/:id` | Delete review | User (owner) / Admin |

### ❤️ Wishlist — `/api/v1/wishlist`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get user wishlist | User |
| `POST` | `/` | Add product to wishlist | User |
| `DELETE` | `/:productId` | Remove from wishlist | User |

### 📍 Addresses — `/api/v1/addresses`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get user addresses | User |
| `POST` | `/` | Add new address | User |
| `DELETE` | `/:addressId` | Remove address | User |

### 🎟 Coupons — `/api/v1/coupons`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get all coupons | Admin / Manager |
| `GET` | `/:id` | Get coupon by ID | Admin / Manager |
| `POST` | `/` | Create coupon | Admin / Manager |
| `PUT` | `/:id` | Update coupon | Admin / Manager |
| `DELETE` | `/:id` | Delete coupon | Admin |

### 🛒 Cart — `/api/v1/carts`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `GET` | `/` | Get logged-in user cart | User |
| `POST` | `/` | Add product to cart | User |
| `PUT` | `/:itemId` | Update item quantity | User |
| `DELETE` | `/:itemId` | Remove item from cart | User |
| `DELETE` | `/` | Clear entire cart | User |
| `POST` | `/applyCoupon` | Apply a coupon to cart | User |

### 📋 Orders — `/api/v1/orders`

| Method | Endpoint | Description | Access |
|--------|----------|-------------|--------|
| `POST` | `/:cartId` | Create cash order | User |
| `GET` | `/` | Get all orders | Admin / Manager |
| `GET` | `/myOrders` | Get logged-in user orders | User |
| `PUT` | `/:id/pay` | Mark order as paid | Admin |
| `PUT` | `/:id/deliver` | Mark order as delivered | Admin |
| `GET` | `/checkout-session/:cartId` | Create Stripe checkout session | User |

### 💳 Stripe Webhook

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/webhook-checkout` | Handle Stripe payment webhook events |

---

## 🔒 Security

This API implements multiple layers of security:

| Mechanism | Library | Purpose |
|---|---|---|
| **Security Headers** | `helmet` | Sets secure HTTP headers |
| **Rate Limiting** | `express-rate-limit` | 100 requests / 15 min per IP |
| **CORS** | `cors` | Controls cross-origin access |
| **XSS Protection** | `xss` | Sanitizes user input to prevent XSS |
| **NoSQL Injection** | Custom Middleware | Removes `$` operators from requests |
| **Parameter Pollution** | `hpp` | Prevents HTTP parameter pollution |
| **Password Hashing** | `bcryptjs` | Hashes passwords with salt factor 12 |
| **JWT Expiry** | `jsonwebtoken` | Tokens expire after 90 days |
| **Request Size Limit** | Express built-in | Max 20KB JSON body |
| **Stripe Webhook Verification** | Stripe SDK | Verifies webhook signatures |

---

## 🏁 Getting Started

### Prerequisites

- **Node.js** >= v18 (v24 recommended)
- **npm** >= v9
- A **MongoDB Atlas** account (or local MongoDB instance)
- A **Stripe** account for payment processing
- A **Gmail** account for email services (with App Password enabled)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/mohammadbzoor/shopBackend.git

# 2. Navigate to the project directory
cd shopBackend

# 3. Install dependencies
npm install

# 4. Create your environment configuration file
cp config.env.example config.env
# Fill in your values — see the Environment Variables section below

# 5. Start the development server
npm run start:dev
```

The server will start on **http://localhost:8000** 🚀

### Running in Production

```bash
NODE_ENV=production npm start
```

---

## 🔧 Environment Variables

Create a `config.env` file in the root directory:

```env
# ─── Server ───────────────────────────────────────
PORT=8000
NODE_ENV=development        # or "production"

# ─── Database ─────────────────────────────────────
DB_URI=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/?appName=<AppName>

# ─── JWT ──────────────────────────────────────────
JWT_SECRET_KEY=your_super_secret_key_here
JWT_EXPIRE_TIME=90d

# ─── Base URL ─────────────────────────────────────
BASE_URL=http://localhost:8000

# ─── Email (Nodemailer / Gmail SMTP) ──────────────
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=465
EMAIL_USERNAME=your_email@gmail.com
EMAIL_PASSSWORD=your_gmail_app_password

# ─── Stripe ───────────────────────────────────────
STRIPE_SECRET=sk_test_your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=whsec_your_webhook_secret
```

> ⚠️ **Never commit your `config.env` file to version control.** Make sure it is listed in `.gitignore`.

---

## 📁 Project Structure

```
shopBackend/
│
├── 📄 server.js                    # Application entry point & Express setup
│
├── ⚙️  config/
│   └── database.js                 # MongoDB connection configuration
│
├── 🛣️  routes/
│   ├── index.js                    # Central route mounting
│   ├── authRoute.js
│   ├── userRoute.js
│   ├── productRoute.js
│   ├── categoryRoute.js
│   ├── subCategoryRoute.js
│   ├── brandRoute.js
│   ├── reviewRoute.js
│   ├── wishlistRoute.js
│   ├── addressRoute.js
│   ├── couponRoute.js
│   ├── cartRoute.js
│   └── orderRoute.js
│
├── 🗄️  models/
│   ├── userModle.js
│   ├── productModel.js
│   ├── categoryModel.js
│   ├── subCategoryModel.js
│   ├── brandModle.js
│   ├── reviewModle.js
│   ├── cartModel.js
│   ├── couponModel.js
│   └── orderModel.js
│
├── ⚙️  services/
│   ├── handlersFactory.js          # Generic CRUD factory handler
│   ├── authService.js
│   ├── userServices.js
│   ├── productServices.js
│   ├── categoryServices.js
│   ├── subCategoryServices.js
│   ├── brandServices.js
│   ├── reviewServices.js
│   ├── whishlistService.js
│   ├── addressService.js
│   ├── couponService.js
│   ├── cartService.js
│   └── orderServices.js
│
├── 🛡️  middlewares/
│   ├── errorMiddleware.js          # Global error handler
│   ├── uploadImageMiddlewere.js    # Multer file upload config
│   └── validatorMiddleware.js      # Validation result handler
│
├── 🔧  utils/
│   ├── apiError.js                 # Custom API error class
│   ├── apiFeaturss.js              # Filter · Sort · Paginate · Search · FieldLimit
│   ├── createToken.js              # JWT token generator
│   ├── sendEmail.js                # Nodemailer email utility
│   ├── sanitizeData.js             # Data sanitizer helpers
│   └── validators/                 # Field-level validation schemas
│
├── 🖼️  uploads/                    # Static files served by Express
│
├── 📄 config.env                   # Environment variables (never committed)
├── 📄 package.json
├── 📄 .eslintrc.json
└── 📄 .gitignore
```

---

## 🗺 Data Models Overview

### 👤 User
- Fields: `name`, `email` (unique), `password` (hashed), `phone`, `profileImg`
- Roles: `user` | `manager` | `admin`
- Embedded: `wishlist[]` (Product refs), `addresses[]`
- Reset flow: `passwordResetCode`, `passwordResetExpires`, `passwordResetVerified`

### 📦 Product
- Fields: `title`, `slug`, `description`, `price`, `priceAfterDiscount`, `quantity`, `sold`
- Media: `imageCover`, `images[]`
- Relations: `category`, `subcategories[]`, `brand`
- Computed: `ratingsAverage`, `ratingsQuantity`

### 🛒 Cart
- `cartItems[]`: `{ product, quantity, color, price }`
- `totalCartPrice`, `totalPriceAfterDiscount`, `coupon`

### 📋 Order
- `user`, `cartItems[]`, `shippingAddress`
- `paymentMethodType`: `card` | `cash`
- `totalOrderPrice`, `isPaid`, `paidAt`, `isDelivered`, `deliveredAt`

---

## 👨‍💻 Author

**Mohammed Bzoor**

- 📧 Email: [mohammedbzoor777@gmail.com](mailto:mohammedbzoor777@gmail.com)
- 🐙 GitHub: [@mohammadbzoor](https://github.com/mohammadbzoor)

---

<p align="center">
  Made with ❤️ using Node.js &amp; Express
</p>
