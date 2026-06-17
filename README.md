<div align="center">

# ⚙️ Stock Management API (Backend)

### _Robust RESTful API for Inventory Management_

[![Node.js](https://img.shields.io/badge/Node.js-18.x-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-4.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![JWT](https://img.shields.io/badge/Auth-JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)](https://jwt.io/)

<br/>

```
    ╔══════════════════════════════════════════════════════╗
    ║                                                      ║
    ║        [ CLIENT ] ──(HTTP JSON)──▶ [ EXPRESS API ]   ║
    ║                                         │            ║
    ║                                     (Mongoose)       ║
    ║                                         ▼            ║
    ║                                   [ MONGODB DB ]     ║
    ║                                                      ║
    ║        Secure. Fast. Ready for your frontend.        ║
    ╚══════════════════════════════════════════════════════╝
```

<br/>

> 🛠️ This repository contains the standalone **Node.js / Express backend** designed to power a Stock Management System. It features secure **JWT authentication**, robust MongoDB data models for items and history, and a fully functional RESTful API architecture.

---

[Features](#-features) •
[API Endpoints](#-api-reference) •
[Tech Stack](#-tech-stack) •
[Setup](#-quick-start)

</div>

---

## ✨ Features

- **🔐 JWT Authentication**: Secures all inventory routes. Requires a valid token via the `Authorization: Bearer <token>` header.
- **📦 Inventory CRUD**: Complete API to Create, Read, Update, and Delete stock items.
- **📜 History Tracking**: Maintains a ledger of inventory changes via the dedicated `History` model.
- **🛡️ Secure Middleware**: Implements routing best practices, JSON body parsing, and environment variable configuration via `dotenv`.
- **🍃 MongoDB Integration**: Utilizes `mongoose` for strict schemas and easy NoSQL interactions.

---

## 📡 API Reference

Below are the primary endpoints provided by `app.js`.

| Method | Endpoint | Auth Required | Description |
|:---:|:---|:---:|:---|
| `POST` | `/api/login` | ❌ No | Authenticates user credentials and returns a JWT |
| `GET` | `/api/items` | ✅ Yes | Retrieves all inventory items sorted by creation date |
| `POST` | `/api/items` | ✅ Yes | Adds a new item to the inventory database |
| `PUT` | `/api/items/:id` | ✅ Yes | Updates details (e.g., quantity) of an existing item |
| `DELETE` | `/api/items/:id` | ✅ Yes | Removes an item from the system |

---

## 🛠️ Tech Stack

<div align="center">

| Technology | Purpose |
|:---|:---|
| **Node.js** | Core JavaScript runtime engine |
| **Express.js** | Web framework handling HTTP routing and middleware |
| **MongoDB Atlas / Local** | NoSQL Database storage |
| **Mongoose** | Object Data Modeling (ODM) for MongoDB |
| **jsonwebtoken** | Token generation and verification for secure API access |
| **dotenv** | Environment variable configuration and secret management |

</div>

---

## 🚀 Quick Start

### Prerequisites
- **Node.js** (v14 or higher)
- **MongoDB** (Local instance or Atlas connection string)

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/hussnainahmedd/backend.git
cd backend
```

**2. Install dependencies**
```bash
npm install
```

**3. Configure Environment Variables**
Create a `.env` file in the root directory:
```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/stock_management
SECRET_KEY=your_super_secret_jwt_key
```

**4. Start the Development Server**
```bash
npm run dev
# OR
npm start
```
*The server will start, establish a connection to MongoDB, and listen on the configured port.*

---

## 📂 Project Structure

```
backend/
│
├── app.js                 # 🚀 Main entry point & route definitions
├── package.json           # 📦 Project metadata and scripts
├── package-lock.json      
│
├── config/                # ⚙️ Configuration files
│   └── db.js              # MongoDB connection setup
│
├── middleware/            # 🛡️ Custom Express middleware
│   └── auth.js            # (If separated) JWT verification logic
│
└── models/                # 📊 Mongoose database schemas
    ├── Item.js            # Defines the structure of a stock item
    └── history.js         # Defines the structure of inventory logs
```

---

<div align="center">

**⭐ Star this repo if you found it useful!**

Built with 💻 Node.js and 🍃 MongoDB.

</div>
