# 📚 Intelligent Library Management System (ILMS)

> A modern, AI-powered, full-stack library and academic research management platform designed with micro-portal architecture, intelligent RAG semantic search, automated background queues, and integrated payment processing.

---

## ✨ Standout & Most Excellent Highlights

### 🤖 1. AI-Powered RAG (Retrieval-Augmented Generation) Assistant
* **Semantic Search & Q&A**: Powered by **Google Gemini**, **Groq**, **LangChain**, and **Qdrant Vector Database**.
* **Smart Academic Inquiries**: Students can ask natural language questions across the library catalog and research papers to receive instant contextual answers, summaries, and source citations.

### ⚡ 2. Automated Waitlist Management & Background Queue System
* **BullMQ & Redis Message Queues**: Background queue workers handle book availability transitions seamlessly.
* **Instant Waitlist Promotion**: When an issued book is returned, the system automatically promotes the next eligible student in the waitlist queue and triggers real-time in-app and **Nodemailer** email notifications.

### 💳 3. Automated Fine Tracking & SSLCommerz Payment Gateway
* **Automated Cron Jobs**: Scheduled **node-cron** tasks track overdue books, calculate accrued fines dynamically, and update student accounts.
* **Secure Online Settlement**: Integrated **SSLCommerz** payment gateway with IPN callback verification, transaction history logging, and instant automated fine clearance upon payment confirmation.

### 📄 4. Digital Research Paper Repository & Access
* Dedicated digital repository for university research papers, publications, and journals.
* Features advanced search, categorized tagging, and direct digital reading access for students and faculty.

### 👥 5. Dual Dedicated Portals (Admin & Student)
* **Admin Management Portal**: Real-time dashboard for inventory management, physical book issue/return tracking, research paper approvals, transaction auditing, and fine management.
* **Student Discovery Portal**: Intuitive student hub with Google OAuth integration, interactive book catalog, reservation queue tracking, fine payment gateway, and notification center.

### 🛡️ 6. Enterprise-Grade Security & Performance
* **Authentication**: Multi-tier authentication with **JWT token rotation**, **Google OAuth 2.0**, and **Firebase Admin**.
* **Reliability & Protection**: Input validation with **Zod**, HTTP header hardening with **Helmet**, API rate limiting with **express-rate-limit**, and multi-level caching with **Redis** & **Node-Cache**.

---

## 🏗️ Architecture & Tech Stack

```
Intelligent Library Management System/
├── full-backend/                 # Node.js / Express REST API + BullMQ + RAG Engine
├── admin-portal(front-end)/      # Admin Portal (React 19, Vite, TanStack Query, Tailwind CSS v4)
└── student-portal(front-end)/    # Student Portal (React 19, Vite, TanStack Query, Motion)
```

| Layer | Technologies |
| :--- | :--- |
| **Backend Core** | Node.js (ESM), Express.js 5, Mongoose / MongoDB |
| **AI & Vector DB** | Google Generative AI (Gemini), Groq SDK, LangChain, Qdrant Client |
| **Queues & Caching** | BullMQ, Redis (ioredis / Upstash), Node-Cache, Node-Cron |
| **Payments & Comms** | SSLCommerz-LTS, Nodemailer |
| **Frontend Core** | React 19, TypeScript, Vite 6, React Router 7 |
| **State & UI** | TanStack React Query v5, Framer Motion, Tailwind CSS v4, DaisyUI, Lucide Icons |
| **Security & Auth** | JWT, Firebase Admin / Auth, BcryptJS, Helmet, Express Rate Limit, Zod |

---

## 🚀 Getting Started

### Prerequisites
* **Node.js**: `v18+` or `v20+`
* **MongoDB**: Local instance or MongoDB Atlas
* **Redis**: Local Redis server or Upstash Redis
* **Qdrant Vector DB**: Local or Cloud cluster (for RAG features)

---

### 1. Backend Server Setup
```bash
cd full-backend
npm install
cp .env.example .env     # Configure MongoDB, Redis, JWT secrets, Gemini API key, SSLCommerz credentials
npm run dev
```

### 2. Admin Portal Setup
```bash
cd "admin-portal(front-end)"
npm install
cp .env.example .env     # Set VITE_API_URL
npm run dev
```

### 3. Student Portal Setup
```bash
cd "student-portal(front-end)"
npm install
cp .env.example .env     # Set VITE_API_URL and Firebase config
npm run dev
```

---

## 🔒 Security & Environment
Never commit `.env` files containing sensitive credentials, API keys, or secret tokens. Always use `.env.example` as a template for local development.
