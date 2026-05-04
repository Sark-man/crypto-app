# Full-Stack Crypto App – Interim Assessment

> ⚠️ **Disclaimer**: This is a student project built for educational purposes only. It is not affiliated with, endorsed by, or associated with Coinbase, Inc. Do not enter real personal information or passwords.

---

## 🚀 Live Links

- **Frontend**: https://sark-crypto-app.netlify.app
- **Backend**: https://crypto-app-backend-y4e9.onrender.com

---

## 📋 Overview

A full-stack cryptocurrency platform built with React, Node.js, Express, and MongoDB. Features JWT-based authentication, a protected profile page, and dynamic crypto data fetched from a custom REST API.

---

## 🛠️ Tech Stack

- **Frontend**: React.js, Tailwind CSS, React Router
- **Backend**: Node.js, Express.js
- **Database**: MongoDB Atlas
- **Authentication**: JWT (HTTP-only cookies)
- **Deployment**: Netlify (frontend), Render (backend)

---

## 🔐 Authentication (JWT-Based)

### Register — `POST /api/auth/register`
Creates a new user account with name, email, and password. Password is hashed with bcrypt before storing in MongoDB.

### Login — `POST /api/auth/login`
Authenticates user with email and password. Returns a JWT token stored in an HTTP-only cookie and redirects to homepage on success.

### Logout — `POST /api/auth/logout`
Clears the JWT cookie and ends the session.

---

## 👤 Protected Profile Page — `GET /api/users/profile`

Displays the logged-in user's name, email, account ID, and member since date. Redirects unauthenticated users to the login page.

---

## 💰 Crypto API Endpoints

### `GET /api/crypto`
Returns all cryptocurrencies stored in the database, sorted newest first.

### `GET /api/crypto/gainers`
Returns cryptocurrencies with a positive 24h change, sorted highest to lowest.

### `GET /api/crypto/new`
Returns the most recently added cryptocurrencies, sorted newest to oldest.

### `POST /api/crypto`
Adds a new cryptocurrency. Required fields:
- `name` — e.g. Bitcoin
- `symbol` — e.g. BTC
- `price` — e.g. 97500
- `change24h` — e.g. 2.5 or -1.3
- `image` — URL to coin image (optional)

---

## 📁 Backend Structure
crypto-app/
├── server.js
├── models/
│   ├── User.js
│   └── Crypto.js
├── controllers/
│   ├── authController.js
│   ├── userController.js
│   └── cryptoController.js
├── routes/
│   ├── authRoutes.js
│   ├── userRoutes.js
│   └── cryptoRoutes.js
└── middleware/
└── authMiddleware.js
---

## ⚙️ Running Locally

### Backend
```bash
cd crypto-app
npm install
npm run dev
```

### Frontend
```bash
npm install
npm run dev
```

### Environment Variables
Create a `.env` file in `crypto-app/`:
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
JWT_EXPIRE=7d
NODE_ENV=development
CLIENT_URL=http://localhost:5173
PORT=5000
---

> This project was built for educational purposes as part of a full-stack web development assessment.