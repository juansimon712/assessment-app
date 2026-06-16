# Chess Assessment Portal

A web app for chess coaches to evaluate students during demo classes. Tracks student level, topics known/covered, and manages admissions.

## Features

- **Assessment Form** — Submit demo class evaluations with conditional sections for Beginner / Intermediate / Advanced levels
- **Admin Dashboard** — View all submissions, search/filter, click for full details, update lead status
- **Analytics** — Real charts showing submissions by level, language, interest, and status
- **Chess Topic Lists** — Pre-built topic checkboxes for Beginner (19 topics) and Intermediate (23 topics)
- **Dark Mode** — Theme toggle with localStorage persistence
- **Responsive** — Works on mobile and desktop

## Tech Stack

- **Backend:** Node.js, Express, better-sqlite3
- **Frontend:** Plain HTML/CSS/JS (no framework)
- **Auth:** bcrypt + express-session

## Quick Start

```bash
npm install
node server.js
```

Open http://localhost:3000. Register as the first user (auto-admin).

## API Endpoints

| Method | Path | Auth | Description |
|--------|------|------|-------------|
| POST | /api/register | No | Register (first user is admin) |
| POST | /api/login | No | Login |
| GET | /api/slots | No | List demo slots 1–26 |
| GET | /api/topics/:level | No | Topics for Beginner/Intermediate/Advanced |
| POST | /api/assessments | No | Submit assessment |
| GET | /api/assessments | Yes | List all submissions |
| GET | /api/assessments/:id | Yes | Get full assessment details |
| PATCH | /api/assessments/:id/status | Yes | Update lead status |
| GET | /api/analytics/summary | Yes | Aggregated analytics data |
| GET | /api/analytics/over-time | Yes | Submissions over time |
