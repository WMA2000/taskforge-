# TaskForge - Task Management System
https://via.placeholder.com/150x50?text=TaskForge
A modern task management system with authentication, CRUD operations, and real-time updates.

## Features
User Authentication (Login/Logout)

Task Management (Create, Read, Update, Delete)

Task Filtering (Search by title/description, status)

Responsive Design (Works on desktop & mobile)

MongoDB Database (Persistent storage)

## File Structure
```plaintext
taskforge/
├── models/               # Database models
│   └── Task.js           # Mongoose schema and queries
├── public/               # Static files
│   ├── css/              # Stylesheets
│   │   └── style.css     # Main CSS
│   └── js/               # Client-side scripts
│       └── main.js       # Frontend logic
├── routes/               # API routes
│   └── tasks.js          # All Express endpoints
├── views/                # EJS templates
│   ├── tasks.ejs         # Task dashboard
│   ├── add-task.ejs      # Task creation form
│   ├── edit-task.ejs     # Task editor
│   └── index.ejs         # Login page
├── middleware/           # Auth middleware
│   └── auth.js           # Session validation
├── .env.example          # Env template (rename to .env)
├── app.js                # Express setup
└── package.json          # Dependencies

```

## Setup Instructions

### 1. Prerequisites
Node.js (v18+)

MongoDB Atlas account (or local MongoDB)

Git (optional)

### 2. Installation
bash

# Clone repository (if using Git)
git clone https://github.com/yourusername/taskforge.git
cd taskforge

# Install dependencies
npm install


### 3. Configure Environment
Create a .env file:

env
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/task_forge?retryWrites=true&w=majority
SESSION_SECRET=your_random_secret_here
PORT=3000

### 4. Run the Application
bash
npm start
→ Access at: http://localhost:3000

### 5. Default Credentials
Email: tracking@system.org

Password: Password123


## Code Highlights

Authentication Flow (routes/tasks.js)

javascript

// Login route
router.post('/login', (req, res) => {
  if (email === ADMIN_EMAIL && password === ADMIN_PASSWORD) {
    req.session.user = { email, name: "Admin" }; // Store session
    res.redirect('/tasks');
  }
});


Task Model (models/Task.js)
javascript

const taskSchema = new mongoose.Schema({
  title: { type: String, required: true },
  status: { type: String, enum: ['Pending', 'In Progress', 'Completed'] },
  createdAt: { type: Date, default: Date.now }
});


Middleware (middleware/auth.js)
javascript


function ensureAuthenticated(req, res, next) {
  if (req.session.user) next(); 
  else res.redirect('/login');
}

## Deployment
Render.com (Recommended)
Upload ZIP or connect GitHub repo

Set environment variables in Render dashboard:

MONGODB_URI
SESSION_SECRET

## Deploy!

https://taskforge-pvop.onrender.com/

License

# TaskForge - Task Management System  

![TaskForge Banner](https://via.placeholder.com/1200x400?text=TaskForge+Banner)  
*A modern task manager with authentication, CRUD operations, and real-time updates.*  

[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js)](https://nodejs.org/)  
[![Express](https://img.shields.io/badge/Express-4.x-000000?logo=express)](https://expressjs.com/)  
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb)](https://www.mongodb.com/atlas)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  
[![Render](https://img.shields.io/badge/Deployed_on-Render-5f45bb?logo=render)](https://render.com)  

---
