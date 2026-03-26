# 🧠 GrindSquad

> **DSA prep, but make it social.** GrindSquad is a squad-based platform where friend groups crush DSA problems together — share problems from LeetCode/GFG/Codeforces, compete on leaderboards, duel each other 1v1, and track your weaknesses before placement season hits.

---

## ✨ Features

- 🔗 **Problem Sharing** — Paste any LeetCode / GFG / Codeforces link. Problem card auto-populates with title, difficulty, and tags.
- 👥 **Squads** — Create private invite-only groups or join public ones. Your crew, your leaderboard.
- 🏆 **Live Leaderboard** — Points for solving, streak bonuses, difficulty multipliers. Rankings update in real time.
- ⚔️ **1v1 Duels** — Challenge a squadmate to the same problem. First to mark solved wins.
- 💬 **Discussion Threads** — Share approaches, drop spoiler-hidden hints, react with custom emojis.
- 📊 **Weakness Analytics** — Radar chart of your topic coverage. See exactly where you're falling behind.
- 🔥 **Streaks** — Daily solve streaks with animated flames. Don't break the chain.

---

## 🛠️ Tech Stack

| Layer | Tech |
|---|---|
| Frontend | Next.js 14, TypeScript, Tailwind CSS, Framer Motion |
| Backend | Node.js, Express, Prisma ORM |
| Database | PostgreSQL via Supabase |
| Cache / Leaderboard | Redis via Upstash |
| Auth | Clerk |
| Realtime | Socket.io |
| Frontend Deploy | Vercel |
| Backend Deploy | Railway |
| Email | Resend |

---

## 📁 Project Structure

```
grindsquad/
├── client/          # Next.js 14 frontend
├── server/          # Node.js + Express backend
├── .github/         # CI/CD workflows
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js 20+
- PostgreSQL (or a Supabase account)
- Redis (or an Upstash account)
- A Clerk account for auth

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_ORG/grindsquad.git
cd grindsquad
```

### 2. Setup the backend
```bash
cd server
cp .env.example .env       # fill in your secrets
npm install
npx prisma migrate dev     # run DB migrations
npm run dev                # starts on port 4000
```

### 3. Setup the frontend
```bash
cd client
cp .env.example .env.local  # fill in your secrets
npm install
npm run dev                 # starts on port 3000
```

---

## 🔐 Environment Variables

### `server/.env`
```env
DATABASE_URL=             # Supabase PostgreSQL connection string
DIRECT_URL=               # Supabase direct URL (for migrations)
REDIS_URL=                # Upstash Redis URL
REDIS_TOKEN=              # Upstash Redis token
CLERK_SECRET_KEY=         # From Clerk dashboard
JWT_SECRET=               # Random secret for JWT signing
PORT=4000
CLIENT_URL=http://localhost:3000
```

### `client/.env.local`
```env
NEXT_PUBLIC_API_URL=http://localhost:4000
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=   # From Clerk dashboard
CLERK_SECRET_KEY=                    # From Clerk dashboard
NEXT_PUBLIC_SOCKET_URL=http://localhost:4000
```

---

## 🌿 Git Workflow

```
main          ← production only. Never commit directly.
  └── dev     ← integration branch. Merge features here.
        ├── feat/auth
        ├── feat/squad-creation
        ├── feat/problem-feed
        └── feat/duels
```

**Commit convention:** `feat:`, `fix:`, `chore:`, `refactor:`, `docs:`

**PR rule:** No PR sits unreviewed for more than 24 hours.

---

## 🗺️ Roadmap

- [x] Repo setup
- [ ] Auth + user profiles
- [ ] Squad creation + invite system
- [ ] Problem sharing feed + link scraper
- [ ] Mark as solved + points engine
- [ ] Live leaderboard (Redis)
- [ ] 1v1 Duels (Socket.io)
- [ ] Discussion threads
- [ ] Analytics dashboard (radar chart + heatmap)
- [ ] Weekly digest emails
- [ ] Public squad discovery page

---

## 👥 Team

| Name | Role |
|---|---|
| You | Frontend, UI/UX |
| Antigravity | Backend, Infrastructure |

---

## 📄 License

MIT
