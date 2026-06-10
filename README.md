# FFP Web (Financial Farm Planning)

Frontend application for the **Financial Farm Planning (FFP)** system — a platform for managing farm operations, crop lifecycle tracking, inventory, and harvest prediction.

This project is a **decoupled frontend client** built with React Router 7 and consumes a separate backend API (Hono + PostgreSQL + Prisma).

---

## 🧠 Overview

FFP Web handles the user interface layer for:

- Farm and field management
- Crop lifecycle tracking (plant → grow → harvest)
- Inventory tracking (inputs / outputs / stock)
- Planning and forecasting
- Operational dashboards
- Workflow-based farm activities

The backend is fully separated and acts as the **domain source of truth**.

---

## ⚙️ Tech Stack

- React 18+
- React Router 7
- TypeScript
- Vite
- Hono API (backend)
- PostgreSQL + Prisma (backend)
- React Query (recommended)
- Zod (validation)

---

## 🏗️ Architecture

Frontend and backend are fully decoupled:

```
Frontend (FFP Web)
    ↓ HTTP API
Backend (Hono API)
    ↓
PostgreSQL (Prisma)
```

### Design Principles

- Frontend = UI + state orchestration only
- Backend = business logic + domain rules
- API-first communication
- No shared server logic in frontend

---

## 🚀 Getting Started

### Install dependencies

```bash
bun install
```

or

```bash
npm install
```

---

### Run development server

```bash
bun run dev
```

App runs at:

```
http://localhost:5173
```

---

## 📁 Project Structure

```
app/
├── routes/        # Route pages (React Router)
├── components/    # Shared UI components
├── features/      # Domain modules (farm, crop, inventory)
├── services/      # API layer (Hono communication)
├── hooks/         # Custom React hooks
├── lib/           # Utilities
├── types/         # TypeScript types
└── styles/        # Global styles
```

---

## 🌾 Domain Modules

- Farm Management
- Crop Lifecycle Tracking
- Inventory System
- Planning & Forecasting
- Workforce / Activities
- Reporting & Analytics

Each module is isolated as a **feature-based unit**.

---

## 🔌 Backend Integration

Flow of data:

```
UI Action
  → Route Loader / Component
  → Service Layer
  → Hono API
  → Database (Prisma)
```

---

## 🧪 Development Rules

- Keep business logic in backend
- Keep frontend components pure
- API calls must go through `services/`
- Use React Router loaders only for orchestration
- Feature-based structure preferred over technical grouping

---

## 📦 Build

```bash
bun run build
```

---

## 🚢 Deployment

Can be deployed to:

- Vercel
- Cloudflare Pages
- Netlify
- Any static hosting + API backend

---

## 🎯 Goal

A structured, scalable frontend system for long-term farm operations management.

Frontend is not the source of truth — it is the visual layer of domain reality.
