# Epistle — Real-Time Chat Application

A full-stack, real-time chat application built with the MERN stack and Socket.IO. Features one-on-one messaging, a personal AI chatbot powered by Google Gemini, image sharing via AWS S3, email verification, and a fully responsive dark/light UI.

---

## Features

- **Real-time messaging** via Socket.IO with typing indicators and seen receipts
- **OTP login & email verification** via Gmail SMTP
- **Personal AI chatbot** powered by Google Gemini with streaming responses
- **Image sharing** via AWS S3 with optional captions
- **Reply, star, delete** messages (for me or everyone)
- **Pin conversations**, block/unblock users, clear chat history
- **Online/offline presence** and in-app push notifications
- **Dark / Light / System** theme toggle
- Fully **responsive** for desktop and mobile

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 19, TypeScript, Vite, Tailwind CSS v4, shadcn/ui, React Router v7 |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB (Mongoose) |
| **Real-time** | Socket.IO |
| **Authentication** | JWT, bcryptjs |
| **AI** | Google Gemini (`@google/genai`) |
| **File Storage** | AWS S3 (pre-signed POST uploads) |
| **Email** | Nodemailer (Gmail SMTP) |

---

## Getting Started

### Prerequisites

- Node.js ≥ 20
- MongoDB (local or [MongoDB Atlas](https://www.mongodb.com/atlas))

### 1. Clone the repo

```bash
git clone https://github.com/your-username/epistle.git
cd epistle
```

### 2. Set up the Backend

```bash
cd backend
cp .env.example .env
npm install
npm run dev
```

Fill in `backend/.env`:

```env
MONGO_URI=mongodb://localhost:27017/
MONGO_DB_NAME=epistle
JWT_SECRET=your_long_random_secret

# Email (Gmail SMTP)
EMAIL=your_gmail@gmail.com
PASSWORD=your_gmail_app_password   # use a Gmail App Password, not your real password

# Google Gemini (AI chatbot)
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-2.0-flash

# AWS S3 (profile pictures & image sharing)
AWS_BUCKET_NAME=your_bucket
AWS_ACCESS_KEY=your_access_key
AWS_SECRET=your_secret_key

FRONTEND_URL=http://localhost:5173
```

Backend runs on **http://localhost:5500**

### 3. Set up the Frontend

```bash
cd frontend
cp .env.example .env
npm install
npm run dev
```

`frontend/.env`:
```env
VITE_API_URL=http://localhost:5500
```

Frontend runs on **http://localhost:5173**

---

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `MONGO_URI` | ✅ | MongoDB connection string |
| `MONGO_DB_NAME` | ✅ | Database name |
| `JWT_SECRET` | ✅ | Secret for signing JWT tokens |
| `EMAIL` | ❌ | Gmail address for sending emails |
| `PASSWORD` | ❌ | Gmail App Password |
| `GEMINI_API_KEY` | ❌ | Google Gemini API key (AI chatbot) |
| `GEMINI_MODEL` | ❌ | Gemini model name (default: `gemini-2.0-flash`) |
| `AWS_BUCKET_NAME` | ❌ | S3 bucket for image uploads |
| `AWS_ACCESS_KEY` | ❌ | AWS access key |
| `AWS_SECRET` | ❌ | AWS secret key |
| `FRONTEND_URL` | ✅ | Frontend URL (used in email links) |
| `VITE_API_URL` | ✅ | Backend URL (baked into frontend bundle) |

---

## Scripts

### Backend

| Command | Description |
|---|---|
| `npm run dev` | Start dev server with hot-reload (nodemon) |
| `npm start` | Start production server |
| `npm run seed:users` | Seed test users |
| `npm run delete:users` | Remove seeded test users |

### Frontend

| Command | Description |
|---|---|
| `npm run dev` | Start Vite dev server |
| `npm run build` | Type-check + production build |
| `npm run preview` | Preview production build locally |

---


