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
bash
taskforge/
│
├── models/               # Database models
│   └── Task.js           # Mongoose schema for tasks
│
├── public/               # Static assets
│   ├── css/              # Stylesheets
│   │   └── style.css     # Main CSS file
│   └── js/               # Client-side scripts
│       └── main.js       # (Optional) Frontend logic
│
├── routes/               # Application routes
│   └── tasks.js          # All Express routes (login, tasks CRUD)
│
├── views/                # EJS templates
│   ├── tasks.ejs         # Main dashboard (task list)
│   ├── add-task.ejs      # Add new task form
│   ├── edit-task.ejs     # Edit existing task
│   └── index.ejs         # Login page
│
├── middleware/           # Custom middleware
│   └── auth.js           # Authentication checks
│
├── .env                  # Environment variables (MONGODB_URI, etc.)
├── app.js                # Main application entry point
└── package.json          # Dependencies and scripts

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
[MIT License - Free for personal and commercial use.](https://via.placeholder.com/150x50?text=TaskForge
A modern task management system with authentication and real-time task tracking.

https://img.shields.io/badge/Node.js-18%252B-green
https://img.shields.io/badge/License-MIT-blue.svg
https://img.shields.io/badge/Database-MongoDB_Atlas-brightgreen
https://img.shields.io/badge/Deploy-Render-5f45bb
https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
