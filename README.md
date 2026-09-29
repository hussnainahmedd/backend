<div align="center">

# 📦 Stock Management Backend

[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![JWT](https://img.shields.io/badge/Auth-JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)](https://jwt.io/)

The REST API behind a stock/inventory management system — JWT-secured item CRUD backed by MongoDB, with an automatic change-history ledger. One `app.js` server, no fluff.

</div>

![Project preview](assets/hero.webp)

---

## ✨ Features

- **🔐 JWT authentication** — `POST /api/login` issues a 24-hour token; every other endpoint requires `Authorization: Bearer <token>`.
- **📦 Full inventory CRUD** — list (newest first), fetch one, create, update, and delete items with `name`, `category`, `quantity`, and `price`.
- **📜 Automatic history ledger** — every add, update, and delete is recorded with a timestamp; `GET /api/history` returns the last 100 events.
- **✅ Real input validation** — required fields, non-negative quantity/price, and MongoDB ObjectId checks before any DB call.
- **🖥️ Companion frontend serving** — serves a static frontend from `../frontend` (`login.html` at `/`, `index.html` for the rest).
- **🔌 MongoDB-first startup** — the server only listens once the database connection is open, and shuts down gracefully on `SIGINT`.

## 📡 API Reference

| Method | Endpoint | Auth | Description |
|:------:|----------|:----:|-------------|
| `POST` | `/api/login` | ❌ | Verify credentials, get a JWT |
| `GET` | `/api/items` | ✅ | All items, newest first |
| `GET` | `/api/items/:id` | ✅ | One item by ID |
| `POST` | `/api/items` | ✅ | Create an item |
| `PUT` | `/api/items/:id` | ✅ | Update an item |
| `DELETE` | `/api/items/:id` | ✅ | Delete an item |
| `GET` | `/api/history` | ✅ | Last 100 inventory events |

## 🛠️ Tech Stack

| Technology | Role |
|:-----------|:-----|
| **Node.js** | JavaScript runtime |
| **Express.js 5** | Routing and middleware |
| **MongoDB + Mongoose 8** | NoSQL storage with strict schemas |
| **jsonwebtoken** | Token generation and verification |
| **dotenv** | Environment configuration |

Also in `package.json`: `bcryptjs`, `cookie-parser`, `cors`, `express-rate-limit`, `helmet` — dependencies kept around for auth hardening and rate limiting.

## 🚀 Getting Started

**1. Clone and install**

```bash
git clone https://github.com/hussnainahmedd/backend.git
cd backend
npm install
```

**2. Add your `.env`**

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/stock_management
SECRET_KEY=your_super_secret_jwt_key
```

**3. Run it**

```bash
npm start
```

> ⚠️ **Heads up:** `app.js` imports `./config/db` and `./models/{Item,history}` — make sure those files are present in your project folder before starting, or the server won't boot.

## 📂 Project Structure

```
backend/
├── app.js            # Server, routes, auth middleware, error handling
├── package.json      # Dependencies and scripts
└── README.md         # You are here
```

---

<div align="center">

Built by [Hussnain Ahmad](https://github.com/hussnainahmedd) — a CS undergrad at Air University, Islamabad, learning backend engineering by building real things.

</div>
