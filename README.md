# P2P Lending Platform — Deployment Guide

This project is a fullstack P2P lending platform repackaged from WordPress into:
- **Frontend**: Next.js
- **Backend**: Express.js
- **Deployment**: Vercel (Frontend), Render (Backend)

---

## 📁 Project Structure

```
p2p_lending_repackaged/
├── frontend/   # Next.js app
└── backend/    # Express API server
```

---

## ✅ Step 1: Deploy Frontend on Vercel

### A. Create a Vercel Account
- Go to https://vercel.com and sign up using GitHub or email.

### B. Push frontend/ to GitHub
```bash
cd frontend
git init
git remote add origin https://github.com/YOUR_USERNAME/p2p-lending-frontend.git
git add .
git commit -m "Initial commit"
git push -u origin master
```

### C. Deploy to Vercel
1. On the Vercel Dashboard, click **"New Project"**
2. Select your GitHub repo
3. Confirm:
   - Framework: Next.js
   - Build Command: `npm run build`
   - Output: `.next`
4. Click **Deploy**

### D. Add Environment Variables
In Vercel > Project > Settings > Environment Variables:
```
NEXT_PUBLIC_API_URL=https://your-backend-url.onrender.com
```

---

## ✅ Step 2: Deploy Backend on Render

### A. Create a Render Account
- Go to https://render.com and sign in with GitHub.

### B. Push backend/ to GitHub
```bash
cd backend
git init
git remote add origin https://github.com/YOUR_USERNAME/p2p-lending-backend.git
git add .
git commit -m "Initial backend commit"
git push -u origin master
```

### C. Deploy on Render
1. Click **“New Web Service”**
2. Select your `p2p-lending-backend` repo
3. Settings:
   - Runtime: Node
   - Build Command: `npm install`
   - Start Command: `node index.js`
4. Click **Create Web Service**

### D. Add Environment Variable (Optional)
In Render > Environment tab:
```
PORT=5000
```

Your API base URL will look like:  
`https://p2p-lending-backend.onrender.com`

---

## 🧪 Step 3: Test the App

### Visit Frontend:
`https://your-project-name.vercel.app`

### Visit Backend:
`https://your-backend-name.onrender.com`

---

## 🧼 Notes
- All backend endpoints live at `/api/...` (e.g., `/api/login`)
- Add a database (e.g., Firebase or MongoDB) for storing loan/user data
- Use Logs tabs on both platforms for debugging