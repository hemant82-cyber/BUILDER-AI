# 🚀 Builder AI - AI-Powered Full-Stack Website Generator

An enterprise-grade MERN Stack application featuring Natural Language AI Prompt Generation, Secure Cookie-Based Authentication, and Live Sandbox Preview.

[![React](https://img.shields.io/badge/REACT-18-blue?style=for-the-badge&logo=react)](https://react.dev)
[![Node.js](https://img.shields.io/badge/NODE.JS-V18+-green?style=for-the-badge&logo=node.js)](https://nodejs.org)
[![Express.js](https://img.shields.io/badge/EXPRESS.JS-4.18-lightgrey?style=for-the-badge&logo=express)](https://expressjs.com)
[![MongoDB](https://img.shields.io/badge/MONGODB-ATLAS-darkgreen?style=for-the-badge&logo=mongodb)](https://www.mongodb.com)
[![Vite](https://img.shields.io/badge/VITE-5.0-yellow?style=for-the-badge&logo=vite)](https://vitejs.dev)

---

## 📌 Table of Contents

* 📖 [About Builder AI](#-about-builder-ai)
* ✨ [Core Features](#-core-features)
* 🛠️ [Tech Stack](#️-tech-stack)
* 📂 [Directory Structure](#-directory-structure)
* ⚡ [Quick Start Guide](#-quick-start-guide)
  * [1. Prerequisites](#1-prerequisites)
  * [2. Installation](#2-installation)
  * [3. Environment Setup](#3-environment-setup)
  * [4. Run Application](#4-run-application)
* 📬 [API Reference](#-api-reference)
* 📜 [Available Scripts](#-available-scripts)
* 🤝 [Contributing & License](#-contributing--license)

---

## 📖 About Builder AI

Builder AI is an end-to-end, production-ready AI development companion bridging the gap between natural language ideas and live web applications. 

The platform enables users to enter descriptive text prompts and watch as an AI agent dynamically structures code, manages components, and handles deployment workflows. Complete with secure token-based cookie authentication (`httpOnly` & `sameSite: none`), real-time tracking, and automated project saving, Builder AI empowers developers to spin up fully functional React and Node.js solutions instantly.

---

## ✨ Core Features

### 🔐 1. Authentication & Security
* **JWT Cookie Authorization:** Secure session management using JSON Web Tokens stored securely via `httpOnly` cookies with cross-origin support.
* **Password Hashing:** Industry-standard `bcryptjs` password encryption protocols.
* **Secure Logout:** Complete cookie clearing and token invalidation protocols ensuring clean session termination.

### 🤖 2. AI Code Generation & Management
* **Natural Language to Code:** Real-time generation of modular component code, styles, and file architectures from prompt inputs.
* **Project Dashboard:** Comprehensive management hub to track, view, and organize generated web applications.
* **Live Sandbox Preview:** Built-in code execution and rendering engine to visualize layouts instantly.

---

## 🛠️ Tech Stack

| Layer | Technology | Description |
| :--- | :--- | :--- |
| **Frontend** | React.js / Vite | Declarative UI component library and next-gen build tool |
| | React Router DOM | Client-side multi-page routing solution |
| | Axios | Promise-based HTTP client with credential/cookie support |
| **Backend** | Node.js | Asynchronous event-driven JavaScript runtime |
| | Express.js | Fast, unopinionated REST API web framework |
| | Mongoose | Elegant MongoDB object modeling (ODM) |
| **Database** | MongoDB / Atlas | NoSQL Document Database for persistent project states |
| **Security** | JSONWebToken (JWT) | Secure session token management via cookies |
| | Bcryptjs | Password hashing mechanism |

---

## 📂 Directory Structure

```text
BUILDER-AI/
├── package.json                      # Root scripts & orchestration
├── client/                           # React + Vite Frontend
│   ├── public/                       # Static public assets
│   ├── src/
│   │   ├── components/               # Reusable UI components (Header, Footer, etc.)
│   │   ├── context/                  # React Context state management
│   │   ├── pages/                    # Core view pages (Home, Login, Register, Builder)
│   │   ├── App.jsx                   # Main routing structure & protected routes
│   │   └── main.jsx                  # Application entry point
│   └── vite.config.js                # Vite bundler configuration
│
└── server/                           # Express + Node Backend
    ├── controllers/                  # Business logic (auth, project controllers)
    ├── middleware/                   # JWT verification & security middlewares
    ├── models/                       # Mongoose schemas (User, Project)
    ├── routes/                       # Express routing layers
    └── server.js                     # Express app initialization & server entry point
```

---

## ⚡ Quick Start Guide

### 1. Prerequisites

Ensure you have the following installed on your local system:

* **Node.js** (v16.0.0 or higher)
* **npm** (v8.0.0 or higher)
* **MongoDB** (Local instance running on `mongodb://localhost:27017` OR a free **MongoDB Atlas URI**)

---

### 2. Installation

Clone the repository and install root dependencies:

```bash
git clone https://github.com/hemant82-cyber/BUILDER-AI.git
cd BUILDER-AI
```

Install all dependencies for both client and server:

```bash
npm install
```

---

### 3. Environment Setup

Navigate to the `server/` directory and configure your `.env` file (you can copy `.env.example` if you create one):

```bash
cd server
touch .env
```

Fill in your configuration details inside `server/.env`:

```env
# Database Connection String
MONGO_URI=mongodb://localhost:27017/builder_ai_db

# JWT Security Key
JWT_SECRET=super_secret_jwt_key_2026

# Server Configuration
PORT=5000
NODE_ENV=development
```

---

### 4. Run Application

From the root directory, launch both frontend and backend concurrently in development mode:

```bash
npm run dev
```

* 🌐 **Frontend URL:** `http://localhost:5173`
* ⚙️ **Backend API Base:** `http://localhost:5000`

---

## 📬 API Reference

### 🔐 Authentication Routes (`/api/auth`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/auth/register` | Public | Register a new user account |
| `POST` | `/api/auth/login` | Public | Authenticate user & issue HTTP-only JWT cookie |
| `POST` | `/api/auth/logout` | Private | Clear auth cookies and terminate session |
| `GET` | `/api/auth/me` | Private | Retrieve currently authenticated user profile |

### 🛠️ Project & Builder Routes (`/api/projects`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/projects` | Private | Submit prompt and trigger AI generation |
| `GET` | `/api/projects` | Private | Fetch all saved projects for logged-in user |
| `DELETE` | `/api/projects/:id` | Private | Delete an existing project |

---

## 📜 Available Scripts

In the root directory, you can run:

| Command | Description |
| :--- | :--- |
| `npm run dev` | Runs both client (`:5173`) and server (`:5000`) concurrently |
| `npm run build` | Builds the client production bundle |
| `npm run start` | Starts production servers |

---

## 🤝 Contributing & License

Contributions are always welcome! Feel free to open an Issue or submit a Pull Request.

Distributed under the MIT License. See `LICENSE` for more information.

**Author:** Hemant Pandey  
**GitHub:** [@hemant82-cyber](https://github.com/hemant82-cyber)
