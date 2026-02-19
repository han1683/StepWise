# StepWise  
Fresh Footwear E-Commerce Platform  

StepWise is a locally hosted full-stack web application designed as an online shoe store.  
Users can browse products, view details, and interact with the early foundations of a shopping experience.  

Developed for **CP317A – Software Engineering (Group XVIII).**

---

## 🛠️ Tech Stack

### Frontend
- Next.js 14 (App Router)
- React
- TailwindCSS
- Prisma ORM (SQLite)
- NextAuth.js
- TypeScript

### Admin Backend
- Python
- Flask
- MySQL
- Jinja2 Templates
- Manual SQL Imports

---

## 📌 Project Overview

StepWise uses a **hybrid architecture**:

### 1️⃣ Next.js Frontend
- Uses SQLite (`/prisma/dev.db`)
- Managed through Prisma ORM
- Handles:
  - Home page
  - Catalogue browsing
  - Product details
  - Authentication

### 2️⃣ Flask Admin Dashboard
- Uses MySQL
- Requires importing 12 database tables from `/database/`
- Handles:
  - Admin product management
  - User management
  - Checkout verification
  - Full database control

The two systems work together but use different database engines.

---

## ⚙️ Setting Up the Next.js Frontend (SQLite + Prisma)

### 1. Clone the repository
```bash
git clone https://github.com/ShadowMaster1453/StepWise.git
cd StepWise
```
2. Install dependencies
npm install

