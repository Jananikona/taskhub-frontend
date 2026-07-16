# TaskHub (TaskFlow) — Frontend

A React-based task and team collaboration platform frontend, featuring real-time updates via WebSockets, project/task management, and team collaboration tools.

**Live demo:** [taskhub-frontend-five.vercel.app](https://taskhub-frontend-five.vercel.app/)

## Tech Stack

- **React** (Create React App / `react-scripts`)
- **socket.io-client** — real-time updates (online presence, project/task events)
- **React Context API** — global state (auth, sockets)
- Deployed on **Vercel**

## Project Structure

```
src/
├── pages/
│   ├── Board.jsx           # Kanban-style task board
│   ├── Dashboard.jsx       # User dashboard / overview
│   ├── Login.jsx           # Login screen
│   ├── MyTasks.jsx         # Tasks assigned to the current user
│   ├── Profile.jsx         # User profile management
│   ├── ProjectDetail.jsx   # Single project view
│   ├── Projects.jsx        # List of all projects
│   ├── Register.jsx        # Signup screen
│   └── Team.jsx            # Team management
├── App.jsx                 # Root component / routing
├── api.js                  # API client (auth, tasks, projects, etc.)
├── contexts.js             # AuthProvider + SocketProvider (global state)
├── index.js                # App entry point
└── styles.css               # Global styles
```

## Core Features

- **Authentication** — register/login with token-based sessions, persisted in `localStorage`
- **Real-time collaboration** — Socket.IO connection tracks online users and pushes live project/task updates
- **Project & task management** — create, view, and organize projects, boards, and individual tasks
- **Team management** — view and manage team members per project

## Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm

### Installation

```bash
git clone https://github.com/Jananikona/taskhub-frontend.git
cd taskhub-frontend
npm install
```

### Environment Variables

Copy `frontend-.env.example` to `.env` and fill in the values, e.g.:

```
REACT_APP_SOCKET_URL=https://your-backend-url.com
```

If not set, the app defaults to `https://new-stcp.onrender.com` for the Socket.IO connection.

### Running Locally

```bash
npm start
```

App runs at `http://localhost:3000` by default.

### Building for Production

```bash
npm run build
```

Outputs an optimized build to the `build/` directory.

## Deployment

This project is deployed on **Vercel**, connected to the `main` branch of this repository. Every push to `main` triggers an automatic build and deploy.

Make sure any required environment variables (like `REACT_APP_SOCKET_URL`) are also set in the Vercel project settings, since `.env` files are not committed to the repo.

## Backend

This is the frontend only. It expects a companion backend API (referenced via `api.js`) and a Socket.IO server for real-time features.

---

*This README was drafted based on the current repo structure — feel free to expand the Features and Backend sections with more specific details about your API endpoints and data models.*
