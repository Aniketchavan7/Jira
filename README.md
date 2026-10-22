# Jira Software Clone (Full-Stack)

A modern, fast, full-stack Jira clone built with **React 19**, **Vite**, **TypeScript**, **Tailwind CSS**, and an **Express / Node.js** REST backend with persistent JSON storage.

---

## 🚀 Features

- **Interactive Kanban Board**:
  - Drag-and-drop issue movement across workflow stages (`TO DO`, `IN PROGRESS`, `IN REVIEW`, `DONE`).
  - Optimistic UI updates with instant backend synchronization.
  - Column issue counters and quick-add actions.
  - Sprint scope switcher (All Sprints, Active Sprint, Backlog).
- **Sprint Planning & Backlog**:
  - Visual backlog management with drag/move to planned sprints.
  - Active sprint indicator, 1-click sprint start & sprint completion.
  - Story point capacity breakdown (To Do, In Progress, Done).
- **Roadmap & Timeline**:
  - Progress percentage bars for each sprint and release goal.
  - Issue commitment overview.
- **Analytics & Agile Reports**:
  - Real-time KPI metrics (Total issues, Delivery rate, In-Progress flow, High-priority count).
  - Issue status distribution charts.
  - Work item breakdown (Stories, Tasks, Bugs).
  - Team workload & throughput per engineer.
- **Comprehensive Issue Detail Modal**:
  - Inline title and description editing.
  - Status transition selector.
  - Assignee and reporter management with user avatars.
  - Priority selector (Highest, High, Medium, Low, Lowest).
  - Story points estimation.
  - Sub-task checklist with completion progress bar.
  - Activity & comments thread with relative timestamps.
  - Label tags manager.
- **Global Search & Keyboard Shortcuts**:
  - Instant filter by ticket key, summary, description, or labels.
  - `Ctrl + K` / `Cmd + K`: Focus search bar.
  - `C`: Quick-create issue from anywhere.
  - Filter by assignee avatar and issue type.
- **Persistent Backend & REST API**:
  - Auto-seeded with realistic Jira tickets, epics, sprints, and team members.
  - Data stored in `server/data/jira-data.json`.
  - 1-click "Reset Data" button in top nav.

---

## 🛠️ Quick Start

### 1. Development Mode (Frontend + Backend with Hot Reload)

Runs Vite on port `3000` (with `/api` proxy) and Express API on port `3001`:

```cmd
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### 2. Production Mode (Single Unified Server)

Builds the frontend and serves both client and API on port `3001`:

```cmd
npm run build
npm start
```

Open [http://localhost:3001](http://localhost:3001) in your browser.

---

## 📡 REST API Reference

| Endpoint | Method | Description |
| :--- | :--- | :--- |
| `/api/projects` | `GET` | List all projects |
| `/api/projects/:id` | `GET` | Get single project |
| `/api/issues` | `GET` | List all issues (optional `?projectId=...`) |
| `/api/issues` | `POST` | Create a new issue |
| `/api/issues/:id` | `PATCH` | Update issue fields |
| `/api/issues/:id` | `DELETE` | Delete an issue |
| `/api/issues/reorder` | `POST` | Batch update issue order/status |
| `/api/issues/:id/comments` | `POST` | Add a comment |
| `/api/issues/:id/subtasks` | `POST` | Add a subtask |
| `/api/issues/:id/subtasks/:subtaskId/toggle` | `PATCH` | Toggle subtask checkbox |
| `/api/sprints` | `GET` | List sprints |
| `/api/sprints` | `POST` | Create a sprint |
| `/api/sprints/:id` | `PATCH` | Update sprint status / dates |
| `/api/users` | `GET` | List users |
| `/api/reset` | `POST` | Reset database to seed data |
