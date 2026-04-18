# 🍴 ZestyFlow

### A full-stack food ordering web application — browse, cart, order, track.

[![HTML](https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS](https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)](https://jwt.io/)



---

## 📖 Overview

**ZestyFlow** is a seamless, end-to-end food ordering platform that enables users to browse food items, manage their cart, place orders, download bills, track order history, and cancel orders — all secured with JWT-based authentication.

---

## ✨ Features

- 🔐 **User Authentication** — Signup & Login with JWT-based security
- 👤 **Secure Account Management** — Protected user profile and session handling
- 🛒 **Cart Management** — Add and remove items from cart (persisted via `localStorage`)
- 📦 **Order Placement** — Place orders with auto-generated bill download
- 📋 **Order History** — Track all past and current orders
- ❌ **Order Cancellation** — Cancel orders within a 2-minute window
- 🔒 **Protected Routes** — Backend middleware guards authenticated endpoints
- 🗄️ **MongoDB Integration** — Persistent data storage for users and orders
- 🌐 **REST API Architecture** — Clean, structured API endpoints

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | HTML, CSS, JavaScript |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB |
| **Authentication** | JWT (JSON Web Token) |

---

## 📂 Project Structure

```
food-order/
│
├── backend/
│   ├── middleware/
│   │   └── auth.js              # JWT verification middleware
│   │
│   ├── models/
│   │   ├── User.js              # User schema
│   │   └── Order.js             # Order schema
│   │
│   ├── routes/
│   │   ├── auth.js              # Auth routes (signup, login, me)
│   │   └── orders.js            # Order routes (place, fetch, cancel)
│   │
│   ├── server.js                # Express server entry point
│   └── .env                     # Environment variables
│
├── pages/
│   ├── login.html
│   └── signup.html
│
├── account.html
├── cart.html
├── orders.html
├── index.html
└── README.md
```

---

## 🔐 Authentication Flow

```
User Signup / Login
      │
      ▼
JWT Token Generated (Backend)
      │
      ▼
Token Stored in localStorage (Frontend)
      │
      ▼
Protected Routes Verified via Middleware
      │
      ▼
Authenticated Access to Orders & Account
```

---

## 📦 Order Management

### Place an Order
1. Browse food items on the home page
2. Add desired items to the cart
3. Cart data is saved in `localStorage`
4. Proceed to checkout — order is sent to the backend via REST API
5. Order is stored in MongoDB with total price and `placed` status
6. Auto-generated bill is available for download

### Cancel an Order
- Orders can be cancelled **within 2 minutes** of placement
- Status transitions: `placed` → `cancelled`
- Authorization check ensures **only the order owner** can cancel

---

## 🔌 REST API Reference

### Authentication

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/signup` | Register a new user |
| `POST` | `/api/auth/login` | Login and receive JWT token |
| `GET` | `/api/auth/me` | Get authenticated user details |

### Orders

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/orders` | Place a new order |
| `GET` | `/api/orders/me` | Fetch order history for logged-in user |
| `PATCH` | `/api/orders/:id/cancel` | Cancel an order (within 2 minutes) |

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/zestyflow.git
cd zestyflow
```

### 2. Install Backend Dependencies

```bash
cd backend
npm install
```

### 3. Configure Environment Variables

Create a `.env` file inside the `backend/` folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
CLIENT_ORIGIN=http://127.0.0.1:3000
JWT_SECRET=yourSecretKey
```

### 4. Start the Backend Server

```bash
node server.js
```

### 5. Launch the Frontend

Open `index.html` using **Live Server** (VS Code extension or any local HTTP server).

---

## 🚀 Future Improvements

- [ ] 💳 Payment Gateway Integration (Razorpay / Stripe)
- [ ] 📍 Live Order Tracking
- [ ] 🛠️ Admin Dashboard
- [ ] 🍽️ Restaurant Panel
- [ ] 📧 Email Notifications
- [ ] 📱 Progressive Web App (PWA) Support

---

## 👩‍💻 Author

Developed by **Soumi Das**

---


⭐ If you found this project helpful, please consider giving it a star!



