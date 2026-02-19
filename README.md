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
```
npm install
```
3. Create a .env file
```
DATABASE_URL="file:./prisma/dev.db"
NEXTAUTH_SECRET="mysecret"
NEXTAUTH_URL="http://localhost:3000"
```
4. Initialize the database
```
npx prisma generate
npx prisma db push
```
5. Run the development server
```
npm run dev
```
Visit:
👉 http://localhost:3000

🛡️ Setting Up the Flask Admin Dashboard (MySQL)
1. Start MySQL

Open MySQL Workbench and ensure the server is running.

2. Create a Schema

Example:
```
fresh_footwear
```
3. Import All 12 Tables

Use files in:
```
/database/
```
n MySQL Workbench:

Server → Data Import
OR

File → Run SQL Script

4. Update admin/db.py
```
db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="YOUR_PASSWORD",
    database="fresh_footwear"
)
```
5. Run Admin Dashboard
```
python admin_app.py
```
Open:
```
http://127.0.0.1:5000
```
Login

Username: admin
Password: 123456

🧩 System Interaction
Frontend

- Uses SQLite for rendering pages and local logic.

Backend

- Uses MySQL for:

- Product storage

- User data

- Checkout functionality

- Confirmed checkout writes into MySQL.

🔒 Environment Variables
| Variable        | Used By | Description                 |
| --------------- | ------- | --------------------------- |
| DATABASE_URL    | Next.js | SQLite database path        |
| NEXTAUTH_SECRET | Next.js | Session encryption key      |
| NEXTAUTH_URL    | Next.js | Base URL for authentication |

MySQL credentials are configured inside admin/db.py.

👥 Group

| Member         | Role                 |
| -------------- | -------------------- |
| Nadeem Almalki | Product Owner        |
| Daniel Cao     | Full Stack Developer |
| Hani Imran     | Full Stack Developer |
| Jimmy Lin      | Cloud Developer      |
| Jake Lloyd     | Front-End Developer  |
| Evan Morris    | Cloud Developer      |


