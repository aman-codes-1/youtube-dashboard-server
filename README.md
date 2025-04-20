# 🎬 YouTube Dashboard

A full-stack dashboard for managing YouTube video metadata, comments, replies, and personal notes — powered by the YouTube Data API v3.

## 🔗 Live URLs

- **Frontend:** https://youtube-dashboard-mauve.vercel.app
- **Backend:** https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0

## Deployment

- **Frontend:** **Vercel** - https://vercel.com
- **Backend:** **Choreo** - https://choreo.dev

Built using:

- ⚛️ React (Frontend)
- 🧠 Node.js + Express (Backend)
- 🍃 MongoDB (Database)
- 🔐 Google OAuth 2.0 (Authentication)
- 📺 YouTube Data API v3

---

## 🚀 Features

- Google Login using OAuth2
- Fetch video metadata (title, description, stats)
- Edit video title and description
- Post comments and replies to videos
- View and delete comments
- Add and manage private notes per video
- Clean dashboard UI to manage YouTube content

---

## 📦 Installation

### 1. Clone the repositories & Install dependencies

```bash
# Frontend
git clone https://github.com/your-username/youtube-dashboard.git
npm install
```

```bash
# Backend
https://github.com/aman-codes-1/youtube-dashboard-server.git
npm install
```

---

## ⚙️ Environment Variables

### 📁 client/.env

```env
PORT=3001
REACT_APP_SERVER_URI=https://reactchatter.in
REACT_APP_GOOGLE_CLIENT_ID=your_google_client_id
```

### 📁 server/.env

```env
PORT=4000
CLIENT_URI=https://youtube-dashboard-mauve.vercel.app
MONGO_URI=mongodb://localhost:27017/ytdashboard
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
OAUTH_REDIRECT_URI=https://youtube-dashboard-mauve.vercel.app/oauth2callback
```

---

## ▶️ Run the Application

### 1. Start Backend

```bash
npm run dev
```

### 2. Start Frontend

```bash
npm start
```

---

## 📘 API Endpoints

### 📹 YouTube Video

GET (Get video details (title, stats)): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/youtube/video/:videoId
PUT (Update video title/description): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/youtube/video/:videoId

---

### 💬 Comments

GET (List all comments ): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/youtube/video/:videoId/comments
POST (Post a new comment): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/youtube/video/:videoId/comment
POST (Post a reply to a comment): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/youtube/comment/:commentId/reply
DELETE (Delete a comment or reply): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/youtube/comment/:commentId

---

### 📝 Notes

GET (Get all notes for a video): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/notes/:videoId
POST (Add a note for a video): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/notes
DELETE (Delete a note by ID): https://457ff6c3-a744-4089-be94-97eaef8c3d72-dev.e1-us-east-azure.choreoapis.dev/default/youtube/v1.0/api/notes/:id

---

## 🗃️ Database Schema

### 📄 `Note`

```js
{
  _id: ObjectId,
  videoId: String,
  text: String,
  createdAt: {
    type: Date,
    default: Date.now
  }
}
```

> 🔒 Notes are stored privately and are not shared to YouTube.

---

## ✅ Tech Stack

| Area         | Tech                               |
|--------------|------------------------------------|
| Frontend     | React, Axios                       |
| Backend      | Node.js, Express.js                |
| Database     | MongoDB + Mongoose                 |
| Auth         | Google OAuth 2.0                   |
| APIs         | YouTube Data API v3                |

---

## 🔐 OAuth Configuration

Set up your **OAuth 2.0 credentials** in Google Cloud Console:

- Add your client ID & secret to `.env` files
- Set `your_client_url` as your redirect URI for development

---

## 🛡️ Security Notes

- All tokens are stored in localStorage (no refresh token storage unless explicitly handled).
- CORS and cookie handling should be properly configured if deployed.

---

## 🤝 Contributions

Got a feature idea or found a bug?  
Pull requests and suggestions are welcome!
