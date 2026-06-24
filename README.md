# Smart Food Hub — Smart Food Management & Student Resource Sharing

Smart Food Hub is a platform for managing surplus food, sharing student resources, and connecting donors, students, and NGOs.

This folder contains the authentication backend and frontend for the Food Sharing project.

Contents:
- `backend/` — Express server, MongoDB models, routes
- `frontend/` — Vite + React app

Quick start (development):

Backend:
```powershell
cd auth-system/backend
npm install
# create a .env with MONGO_URI and other secrets (see .env.example)
node server.js
```

Frontend:
```powershell
cd auth-system/frontend
npm install
npm run dev
```

Environment:
- Copy `backend/.env.example` → `backend/.env` and fill values (DO NOT commit real secrets).

Push to GitHub (example):
```bash
# from auth-system root
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/<your-username>/<repo-name>.git
git branch -M main
git push -u origin main
```

Replace `<your-username>` and `<repo-name>` with your values. Use GitHub Secrets for production env values.

Features: posting leftovers, request handling, swap marketplace, notifications (email/SMS), role-based access (students / NGOs / mess admins).

Tech: React, Vite, Node.js, Express, MongoDB, Mongoose, JWT.

