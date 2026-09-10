CanvasLite - Open-Source Graphic Design Tool

📌 Introduction

CanvasLite is a self-hosted, open-source graphic design tool similar to Canva. It allows users to create, edit, and save custom designs with an easy-to-use interface. Built using React and Fabric.js, it provides a modern, flexible, and efficient design experience.

Features
🎨 Drag-and-Drop Canvas Editor
🖍️ Add and Edit Text with Custom Fonts
🖼️ Upload and Manipulate Images
🔺 Predefined Shapes (Rectangles, Circles, Triangles, etc.)
😊 Sticker Library (Emojis & SVG Stickers)
🎨 Change Object Colors and Background Colors
🔄 Undo & Redo Actions
🗑️ Delete Selected Objects
💾 Save and Download Designs as PNG
🔗 Backend API for Saving Projects
🛠 User Authentication (Signup/Login)


🏗️ Tech Stack
Frontend: React, Fabric.js, React Icons
Backend: Node.js, Express
Database: MongoDB
Image Processing: Sharp


🛠️ Installation & Setup
### 1️⃣ Clone the Repository
git clone https://github.com/Yashwanthgouda/CanvasLite.git
cd CanvasLite

### 2️⃣ Install Dependencies
#### Frontend:

cd frontend
npm install


#### Backend:

cd ../backend
npm install


### 3️⃣ Start the Application
#### Run Backend:

cd backend
npm start


#### Run Frontend:

cd frontend
npm start




📌 Future Enhancements

✅ Custom Templates
✅ Collaborative Editing
✅ Export as PDF & SVG
✅ More Stickers & Shapes
✅ Dark Mode Support

🤝 Contributing
Contributions are welcome! Feel free to fork the repo, create a new branch, and submit a pull request.

📃 License
This project is licensed under the MIT License.

## 🚀 Coolify Self-Host Deployment

This repo now includes production Docker files so you can deploy it to your self-hosted Coolify instance in a few clicks.

### What changed
- `backend/Dockerfile` — Node.js 20 slim runtime
- `frontend/Dockerfile` — multi-stage React build served by nginx, `/api` proxied to backend
- `docker-compose.yml` — single public entrypoint (frontend), internal backend + MongoDB
- `env.example` — local, self-hosted MongoDB by default (no cloud DB required)

### Steps
1. Fork or clone the repository and set the secrets in Coolify:
   - `JWT_SECRET` — strong random string
   - `MONGO_URI` — `mongodb://mongo:27017/canvaslite` (local container) or your own MongoDB URI
   - `REACT_APP_API_URL` — `/api` when using Coolify domain for the frontend
2. In Coolify: **Project → + New Resource → Docker Compose**
3. Select the repo and branch, set compose file path to `docker-compose.yml`
4. Add your domain in the resource settings (e.g. `canvaslite.192.168.1.101.nip.io`).
5. Deploy.

### Notes
- Do **not** commit `.env` to git; add the values in Coolify Environment tab.
- The backend is **not** exposed publicly; all API calls go through `/api` on the frontend domain.
- If you want the backend on its own subdomain instead, remove the `/api` nginx proxy block and expose `backend` separately.
