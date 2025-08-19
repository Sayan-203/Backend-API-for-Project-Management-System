# Project Camp Backend

**Project Camp Backend** is a RESTful API service for collaborative project management. It provides secure user authentication, role-based access control, and features for managing projects, tasks, subtasks, notes, and file attachments. This backend is designed to support team collaboration in an efficient and secure way.

---

## 🚀 Features

### 🔐 Authentication & Authorization
- User registration with email verification  
- Secure login with **JWT tokens** (access + refresh)  
- Password reset and change password functionality  
- Role-based access control (**Admin, Project Admin, Member**)  

### 📂 Project Management
- Create, update, and delete projects (Admin only)  
- View project details and member count  
- Manage team members: invite, update roles, remove  

### ✅ Task & Subtask Management
- Create, update, and delete tasks (Admin & Project Admin)  
- Assign tasks to team members with status tracking (**Todo, In Progress, Done**)  
- Create and manage subtasks with completion tracking  

### 📝 Project Notes
- Add, update, and delete notes (Admin only)  
- View project notes for collaboration  

### 📎 File Attachments
- Upload multiple file attachments to tasks  
- Secure file handling with **Multer**  

### 📊 System Health
- Health check endpoint for monitoring API status  

---

## 🛠 Tech Stack
- **Backend Framework**: Node.js, Express.js  
- **Database**: MongoDB (or PostgreSQL, if used)  
- **Authentication**: JWT (Access & Refresh Tokens), Role-Based Access Control  
- **File Handling**: Multer  
- **Utilities**: CORS, Nodemailer (for email services)  

---

## 📡 API Endpoints (v1)

### Authentication
- `POST /api/v1/auth/register` – Register new user  
- `POST /api/v1/auth/login` – User login  
- `POST /api/v1/auth/logout` – Logout (secured)  
- `POST /api/v1/auth/change-password` – Change password  
- `POST /api/v1/auth/refresh-token` – Refresh token  
- `GET /api/v1/auth/verify-email/:verificationToken` – Verify email  
- `POST /api/v1/auth/forgot-password` – Request reset link  
- `POST /api/v1/auth/reset-password/:resetToken` – Reset password  

### Projects
- `GET /api/v1/projects/` – List projects  
- `POST /api/v1/projects/` – Create project  
- `GET /api/v1/projects/:projectId` – Project details  
- `PUT /api/v1/projects/:projectId` – Update project (Admin only)  
- `DELETE /api/v1/projects/:projectId` – Delete project (Admin only)  
- `POST /api/v1/projects/:projectId/members` – Add members (Admin only)  

### Tasks
- `GET /api/v1/tasks/:projectId` – List tasks  
- `POST /api/v1/tasks/:projectId` – Create task  
- `PUT /api/v1/tasks/:projectId/t/:taskId` – Update task  
- `DELETE /api/v1/tasks/:projectId/t/:taskId` – Delete task  

### Subtasks
- `POST /api/v1/tasks/:projectId/t/:taskId/subtasks` – Create subtask  
- `PUT /api/v1/tasks/:projectId/st/:subTaskId` – Update subtask  
- `DELETE /api/v1/tasks/:projectId/st/:subTaskId` – Delete subtask  

### Notes
- `GET /api/v1/notes/:projectId` – List notes  
- `POST /api/v1/notes/:projectId` – Create note  
- `PUT /api/v1/notes/:projectId/n/:noteId` – Update note  
- `DELETE /api/v1/notes/:projectId/n/:noteId` – Delete note  

### Health Check
- `GET /api/v1/healthcheck` – API health status  

---

## ⚡ Installation & Setup

1. Clone the repository  
