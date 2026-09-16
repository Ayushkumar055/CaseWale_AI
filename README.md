# ⚖️ CaseWale AI

### AI-Powered Legal Assistant for Indian Law

CaseWale AI is a full-stack web application designed to simplify legal research and case management for users navigating the Indian legal system.

The platform combines an **AI-powered legal question-answering system using Google's Gemini API** with practical case-management tools, allowing users to ask legal questions, manage cases, prepare document drafts, and track hearings and important case events from a single platform.

> **Built as part of an internship project at AstraTech AI.**

---

## 🎯 Problem Statement

Legal research often requires navigating complex statutes, case laws, and legal procedures using multiple disconnected tools.

CaseWale AI aims to provide a **single, lightweight platform** where users can get AI-assisted answers to legal questions while also organising their case-related information.

---

## 💡 What CaseWale AI Provides

CaseWale AI brings together two major capabilities:

### 🤖 AI-Assisted Legal Research

Users can ask legal questions in natural language and receive AI-generated responses through the Google Gemini API.

### 📁 Case Management

Users can manage ongoing legal matters, create document drafts, and keep track of hearings and important case events.

---

## ✨ Key Features

* 🤖 **Ask AI** — Ask legal questions using natural language.
* 📂 **Case Management** — Create and manage individual case records.
* 📝 **Drafts** — Create and manage legal document drafts.
* 📅 **Calendar** — Track hearings and important case events.
* 🔐 **Authentication** — Token-based user authentication.
* 🌓 **Theme Toggle** — Switch between dark and light themes.
* 💾 **Persistent Data** — Case and event information is stored through Prisma.
* 🇮🇳 **Indian Legal Focus** — Designed around legal queries related to the Indian legal system.

---

## 🔄 How It Works

```text
                    ┌─────────────────────┐
                    │       USER          │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      FRONTEND       │
                    │   HTML / CSS / JS   │
                    └──────────┬──────────┘
                               │
                         HTTP / REST API
                               │
                               ▼
                    ┌─────────────────────┐
                    │   EXPRESS BACKEND   │
                    │      Node.js        │
                    └───────┬─────┬───────┘
                            │     │
                 ┌──────────┘     └──────────┐
                 ▼                           ▼
        ┌─────────────────┐        ┌─────────────────┐
        │   PRISMA ORM    │        │   GEMINI API    │
        │                 │        │   AI Engine     │
        └────────┬────────┘        └─────────────────┘
                 │
                 ▼
        ┌─────────────────┐
        │     DATABASE    │
        │ Cases / Events  │
        └─────────────────┘
```

The frontend communicates with the Express backend through HTTP requests.

The backend handles application logic and routes requests either to the database through Prisma or to the Gemini API for AI-generated responses.

---

## 🛠️ Technology Stack

| Layer           | Technology                    |
| --------------- | ----------------------------- |
| Frontend        | HTML, CSS, Vanilla JavaScript |
| Backend         | Node.js, Express.js           |
| ORM             | Prisma                        |
| Database        | Prisma-supported database     |
| AI Engine       | Google Gemini API             |
| Authentication  | Token-based authentication    |
| Package Manager | npm                           |
| Development     | Nodemon                       |

### Why This Stack?

The project uses a lightweight full-stack architecture that allows rapid development while keeping the application simple to maintain.

**Express + Node.js** handles the backend and REST APIs, **Vanilla JavaScript** keeps the frontend lightweight, while **Prisma** provides structured database access. Google's **Gemini API** powers the AI functionality.

---

## 📂 Project Structure

```text
CaseWale-AI/
│
├── casewale-frontend/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── package.json
│
├── precedent-backend/
│   ├── prisma/
│   │   └── schema.prisma
│   ├── routes/
│   ├── controllers/
│   ├── middleware/
│   ├── package.json
│   └── ...
│
└── README.md
```

> The exact folder contents may vary as the project continues to evolve.

---

# ⚙️ Getting Started

## Prerequisites

Make sure the following are installed on your system:

* **Node.js**
* **npm**
* A configured database supported by the project's Prisma setup
* **Google Gemini API key**

You can verify Node.js and npm with:

```bash
node --version
npm --version
```

---

# 🚀 Installation

## 1. Clone the Repository

```bash
git clone https://github.com/sandip2810-bhp/CaseWale-AI.git
```

Move into the project directory:

```bash
cd CaseWale-AI
```

---

## 2. Setup the Backend

Navigate to the backend:

```bash
cd precedent-backend
```

Install dependencies:

```bash
npm install
```

---

## 3. Configure Environment Variables

Create a `.env` file inside the backend directory.

Add the environment variables required by your local configuration, including the database connection and Gemini API credentials.

Example:

```env
DATABASE_URL="your_database_connection_string"
GEMINI_API_KEY="your_gemini_api_key"
```

> **Never commit your `.env` file or API keys to GitHub.**

---

## 4. Setup Prisma

Generate the Prisma client:

```bash
npx prisma generate
```

Apply the database migrations:

```bash
npx prisma migrate dev
```

If the project is being connected to an existing database, make sure the database connection configured in `.env` is correct before running migrations.

---

## 5. Start the Backend

Run the backend development server:

```bash
npm run dev
```

The backend runs on:

```text
http://localhost:3001
```

---

# 🖥️ Setup the Frontend

Open another terminal.

From the project root:

```bash
cd casewale-frontend
```

Install dependencies:

```bash
npm install
```

Start the frontend:

```bash
npm start
```

The frontend runs on:

```text
http://localhost:3000
```

---

# 🔐 Authentication

CaseWale AI uses a token-based authentication system to manage user sessions.

The authentication flow allows users to:

1. Register / log in.
2. Receive an authentication token.
3. Use the token for authenticated API requests.
4. Access protected application functionality.

The backend validates authentication information before processing protected requests.

---

# 🤖 AI Integration

The **Ask AI** module uses Google's **Gemini API** as the external AI engine.

The general flow is:

```text
User's Legal Question
        ↓
Frontend
        ↓
Express API
        ↓
Gemini API
        ↓
AI Generated Response
        ↓
Frontend
```

This allows users to interact with the system using natural-language legal questions rather than relying only on traditional keyword-based searches.

---

# 📅 Case & Calendar Management

CaseWale AI provides dedicated case-management functionality.

### Cases

Users can maintain information related to individual legal cases.

### Case Events

Important events such as hearings can be associated with cases through the `CaseEvent` model.

### Calendar

The calendar interface provides a way to view and organise important case-related dates.

---

# 📝 Drafts

The Drafts module provides a workspace for preparing and managing legal document drafts.

This allows users to keep document preparation alongside their case-management workflow rather than relying entirely on separate tools.

---

# 🧪 Testing & Debugging

During development, several issues were identified and resolved, including:

### Gemini API Credential Issues

Invalid or stale Gemini API credentials caused AI requests to fail.

**Resolution:** API credentials were refreshed and the integration was tested again.

### Prisma Client Synchronisation

Changes to the `Case` and `CaseEvent` models caused Prisma Client synchronisation issues.

**Resolution:**

```bash
npx prisma generate
```

and database migration synchronisation were performed.

### Foreign Key Constraint Issues

A stale authentication token referenced invalid user data.

**Resolution:** Token and session handling was corrected.

### Theme Toggle

The dark/light theme button initially lacked the required click handler.

**Resolution:** The missing event listener was implemented.

---

# 📊 Current Project Status

CaseWale AI currently provides a functional local application with the following core capabilities:

* ✅ AI-powered legal Q&A
* ✅ Gemini API integration
* ✅ User authentication
* ✅ Case management
* ✅ Calendar / CaseEvent management
* ✅ Legal document drafts
* ✅ Dark / light theme
* ✅ Prisma database integration
* ✅ Express REST API
* ✅ Frontend-backend integration

The application has been tested and stabilised for local development.

---

# 🔮 Future Improvements

Planned improvements include:

* Question history and follow-up conversations
* Clickable citations for statutes and case law
* Jurisdiction-based responses
* Case activity timeline
* Linking drafts directly to cases
* Document preview
* Advanced case filters
* Hearing reminders
* Google Calendar integration
* Authentication rate limiting
* Automated Prisma generation during installation
* Dashboard statistics and analytics
* Global search across cases, drafts and AI conversations
* Improved mobile responsiveness

---

# ⚠️ Disclaimer

**CaseWale AI is an educational and technology project and should not be considered a substitute for professional legal advice.**

AI-generated information may contain inaccuracies or incomplete interpretations of law. Users should verify important legal information with qualified legal professionals and authoritative legal sources.

---

# 👨‍💻 Development Team

**Sandip Mandal**
**Ayush Kumar**
**Shantanu Sinha**
**Aakash Singh**

### Internship

**AstraTech AI**

### Mentor / Supervisor

**Mr. Aniket Kumar**

### Internship Duration

**18 May 2026 – 02 August 2026**

---

# 📚 References

* Google Gemini API
* Prisma ORM
* Express.js
* Node.js

---

## ⭐ Support

If you find this project interesting, consider giving the repository a ⭐ on GitHub.

---

**CaseWale AI — Bringing AI-assisted legal research and case management into one platform.**
