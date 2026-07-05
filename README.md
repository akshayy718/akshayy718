<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,08090A,00E6A7&height=220&section=header&text=DataVault&fontSize=80&fontColor=00E6A7&animation=fadeIn&fontAlignY=40&desc=Transform%20Spreadsheets%20Into%20QR-Powered%20Experiences&descAlignY=65&descSize=18&descColor=9CA3AF" width="100%"/>

</div>

<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=20&duration=3000&pause=800&color=00E6A7&center=true&vCenter=true&width=800&lines=Upload+a+CSV+%E2%86%92+Select+Data+%E2%86%92+Generate+QR+%E2%86%92+Share+Anywhere;PIN+Protection+%7C+Expiry+%7C+View+Limits+%7C+Live+Mode;48%2F48+Automated+Tests+Passing+%E2%9C%85;Rated+9%2F10+Technical+%7C+9%2F10+UI%2FUX+%7C+9%2F10+Portfolio+Value)](https://git.io/typing-svg)

</div>

<br/>

<div align="center">

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-datavault--gilt.vercel.app-00E6A7?style=for-the-badge&logo=vercel&logoColor=black)](https://datavault-gilt.vercel.app)
[![Backend](https://img.shields.io/badge/⚙️_Backend_API-Render-00E6A7?style=for-the-badge&logo=render&logoColor=black)](https://datavault-api-3j82.onrender.com/health)
[![GitHub](https://img.shields.io/badge/GitHub-akshayy718%2Fdatavault-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/akshayy718/datavault)

</div>

<div align="center">

![Next.js](https://img.shields.io/badge/Next.js%2014-000000?style=flat-square&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind%20CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer%20Motion-0055FF?style=flat-square&logo=framer&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat-square&logo=render&logoColor=black)

</div>

---

<div align="center">

## ✦ What is DataVault?

</div>

> **DataVault** is a production-grade SaaS platform that turns any spreadsheet into a premium, shareable experience via QR code — in seconds. Upload a CSV or Excel file, select exactly the data you want to share (rows, columns, cells, or ranges), configure security and limits, generate a real scannable QR code, and anyone who scans it sees a beautifully designed card — no login, no app download required.

<div align="center">

```
Upload CSV  →  Select Data  →  Configure Share  →  Generate QR  →  Recipient Scans  →  Premium Card
```

</div>

---

## 🏗️ Architecture

<div align="center">

```
┌─────────────────────────────────────────────────────────────────┐
│                        DATAVAULT SYSTEM                          │
│                                                                   │
│   ┌──────────────────────┐      ┌──────────────────────────┐    │
│   │   FRONTEND (Vercel)  │      │    BACKEND (Render)       │    │
│   │                      │      │                           │    │
│   │  Next.js 14 (SSR)    │◄────►│  FastAPI + SQLAlchemy    │    │
│   │  TypeScript          │      │  PostgreSQL + Alembic    │    │
│   │  Tailwind CSS        │      │  bcrypt + PyJWT          │    │
│   │  Framer Motion       │      │  qrcode + Pillow         │    │
│   │                      │      │  Groq AI (Llama 3.3)     │    │
│   │  6 Screens           │      │  45 API Endpoints        │    │
│   │  SSR Recipient Page  │      │  9 Backend Modules       │    │
│   └──────────────────────┘      └──────────────────────────┘    │
│                                           │                       │
│                              ┌────────────▼──────────┐           │
│                              │   PostgreSQL (Render)  │           │
│                              │   Users · Datasets     │           │
│                              │   Shares · Analytics   │           │
│                              └───────────────────────┘           │
└─────────────────────────────────────────────────────────────────┘
```

</div>

### How a request flows through the system

**For the recipient page (the most important flow):**

```
Phone scans QR
      │
      ▼
Vercel edge server receives request
      │
      ▼  (Server-Side Rendering — runs on Vercel's fast server)
Vercel fetches data from Render backend
      │
      ▼
Render returns share data (rows, columns, fields)
      │
      ▼
Vercel builds complete HTML page with data already inside
      │
      ▼
Phone receives finished page — displays instantly
(No slow JavaScript fetch on the phone)
```

This is why the recipient card loads fast on phones even though the backend is in Singapore — Vercel's server does the heavy lifting, the phone just displays the result.

---

## 🎨 Design System

<div align="center">

| Token | Value | Usage |
|-------|-------|-------|
| Background | `#08090A` | All page backgrounds |
| Primary | `#00E6A7` | Buttons, highlights, active states |
| Accent | `#5BE7FF` | Secondary highlights |
| Surface | `#0E0F11` | Cards, panels |
| Muted | `#9CA3AF` | Subtitles, labels |
| Font Headings | Inter Tight | All headings |
| Font Body | Inter | Body text |
| Font Numbers | Space Grotesk | Analytics, counts |

</div>

---

## 📱 Screens

<div align="center">

| Screen | Route | Description |
|--------|-------|-------------|
| **Auth** | `/auth` | Login · Register · Forgot password — 2-panel layout with animated product preview |
| **Dashboard** | `/dashboard` | Upload CSV · Interactive data table · 4 selection modes · AI assistant panel |
| **Share Creator** | `/share` | Configure PIN · expiry · limits · themes · live phone preview · QR generation |
| **Recipient View** | `/view/[token]` | Premium card for single person OR list view for multiple records — SSR |
| **Analytics** | `/analytics` | Real view counts · top shares · device breakdown — live backend data |
| **Select Studio** | `/select` | Alternative card-grid selection UI |

</div>

---

## ⚙️ Backend Modules

<div align="center">

| Module | What it does |
|--------|-------------|
| **Auth** | Register · login · JWT tokens (24h) · refresh tokens (7d) · bcrypt hashing · auto-refresh |
| **Datasets** | Upload CSV/XLSX · parse columns + rows · store in PostgreSQL · restore for persistence |
| **Shares** | Create shares · QR generation · PIN protection · expiry · max views · live vs snapshot mode |
| **Selection Engine** | Row · multi-row · single column · multi-column · cell · range — all correctly mapped to backend |
| **Analytics** | Per-share view counts · workspace totals · top shares ranking |
| **AI Copilot** | NL row filtering · duplicate detection · group suggestions from real data |
| **AI Key Strategy** | Platform key vs BYOK · Fernet encryption at rest |
| **Templates** | Create and version reusable card layouts |
| **Export Engine** | Export any share as CSV · PNG · PDF |

</div>

---

## 🔐 Security Features

<div align="center">

| Feature | Implementation |
|---------|----------------|
| **Password hashing** | bcrypt with salt rounds |
| **Authentication** | JWT access tokens (24h) + refresh tokens (7d) |
| **Token storage** | localStorage with auto-refresh on 401 |
| **Cross-user isolation** | All queries scoped to authenticated user's workspace |
| **PIN protection** | Shares can require a PIN — hashed with bcrypt |
| **CORS** | Production-hardened — only known Vercel domains allowed |
| **API docs** | Hidden in production (`/docs` returns 404) |
| **Database** | Parameterized queries via SQLAlchemy ORM — no SQL injection |
| **Secrets** | All keys in environment variables — zero hardcoded secrets |

</div>

---

## 🧪 Test Results

<div align="center">

```
═══════════════════════════════════════════════
  DataVault — Full System Test
═══════════════════════════════════════════════

  [1] AUTH
  ✓ Register (new account)
  ✓ Duplicate account blocked
  ✓ Login correct password
  ✓ Wrong password blocked
  ✓ /auth/me session restore
  ✓ Token refresh

  [2] UPLOAD
  ✓ Upload CSV
  ✓ Correct row count
  ✓ Correct column count
  ✓ Get rows (restore path)

  [3] SELECTION TYPES
  ✓ Create — Single row        recipient: kind=single n=1
  ✓ Create — Multiple rows     recipient: kind=multi  n=3
  ✓ Create — Single column     recipient: kind=multi  n=9
  ✓ Create — Multiple columns  recipient: all cols present
  ✓ Create — Cell              recipient: kind=single n=1
  ✓ Create — Range rows        recipient: kind=multi  n=3

  [4] SHARE OPTIONS
  ✓ Create PIN share
  ✓ PIN blocks access (401)
  ✓ Wrong PIN rejected (401)
  ✓ Correct PIN unlocks (200)
  ✓ Create max_views=2 share
  ✓ View 1 of 2 — allowed
  ✓ View 2 of 2 — allowed
  ✓ View 3 of 2 — blocked (410)
  ✓ Create expired share
  ✓ Expired share blocked (410)
  ✓ Create Live share
  ✓ Live share viewable + mode=live

  [5] QR CODE
  ✓ QR PNG accessible
  ✓ QR is real PNG (magic bytes verified)
  ✓ QR has valid file size

  [6] HEALTH
  ✓ Health endpoint (200)
  ✓ Has env field

  [7] ANALYTICS
  ✓ Analytics (200)
  ✓ Has total_shares
  ✓ Has total_views
  ✓ Has top_shares

  [8] REVOKE
  ✓ Viewable before revoke
  ✓ Revoke share
  ✓ Blocked after revoke (410)

  [9] SECURITY
  ✓ Cross-user dataset blocked (403)
  ✓ Search workspace-isolated

═══════════════════════════════════════════════
  48 PASSED  |  0 FAILED  |  48 TOTAL ✅
═══════════════════════════════════════════════
```

</div>

---

## 🚀 Getting Started

### Prerequisites

```bash
# Backend requirements
Python 3.11.9
PostgreSQL (or SQLite for local dev)

# Frontend requirements
Node.js 18+
npm
```

### Local Development

**1. Clone the repository**
```bash
git clone https://github.com/akshayy718/datavault.git
cd datavault
```

**2. Set up the backend**
```bash
cd apps/api

# Create virtual environment
python -m venv venv
venv\Scripts\activate    # Windows
source venv/bin/activate # Mac/Linux

# Install dependencies
pip install -r requirements.txt

# Copy environment file and fill in values
cp ../../.env.example .env

# Run database migrations
alembic upgrade head

# Start backend (runs on port 8000)
uvicorn app.main:app --reload
```

**3. Set up the frontend**
```bash
cd apps/web

# Install dependencies
npm install

# Create local env file
echo "NEXT_PUBLIC_API_URL=http://localhost:8000/api/v1" > .env.local

# Start frontend (runs on port 3000)
npm run dev
```

**4. Open the app**
```
http://localhost:3000
```

### Environment Variables

**Backend (`apps/api/.env`):**
```env
DATABASE_URL=sqlite:///./datavault_dev.db
JWT_SECRET=your-long-random-secret-here
AI_PROVIDER_API_KEY=your-groq-api-key
APP_ENV=development
RECIPIENT_APP_BASE_URL=http://localhost:3000
```

**Frontend (`apps/web/.env.local`):**
```env
NEXT_PUBLIC_API_URL=http://localhost:8000/api/v1
```

---

## 🌐 Deployment

| Service | Platform | URL |
|---------|----------|-----|
| **Frontend** | Vercel (free tier) | [datavault-gilt.vercel.app](https://datavault-gilt.vercel.app) |
| **Backend** | Render (free tier) | [datavault-api-3j82.onrender.com](https://datavault-api-3j82.onrender.com) |
| **Database** | Render PostgreSQL (free tier) | Internal connection |
| **Monitoring** | UptimeRobot (free) | Pings `/health` every 5 minutes |

---

## 📁 Project Structure

```
datavault/
├── apps/
│   ├── api/                    ← FastAPI backend
│   │   ├── app/
│   │   │   ├── core/           ← Config, security, settings
│   │   │   ├── db/             ← Database session and base model
│   │   │   ├── models/         ← SQLAlchemy database models
│   │   │   ├── routes/         ← API route handlers (45 endpoints)
│   │   │   ├── schemas/        ← Pydantic request/response schemas
│   │   │   ├── services/       ← Business logic (9 modules)
│   │   │   └── main.py         ← FastAPI app entry point
│   │   ├── migrations/         ← Alembic database migrations
│   │   ├── static/qr/          ← Generated QR code PNG files
│   │   ├── requirements.txt
│   │   └── start.sh            ← Render startup script
│   │
│   └── web/                    ← Next.js 14 frontend
│       ├── app/
│       │   ├── analytics/      ← Analytics dashboard
│       │   ├── api/unlock/     ← Vercel proxy for PIN unlock
│       │   ├── auth/           ← Login / Register
│       │   ├── dashboard/      ← Upload + data table + AI panel
│       │   ├── select/         ← Selection Studio
│       │   ├── share/          ← Share Creator
│       │   └── view/[token]/   ← Recipient View (SSR)
│       ├── components/
│       │   ├── layout/         ← Navbar
│       │   ├── share/          ← QR Panel, Share Options, Preview
│       │   ├── ui/             ← Button, Input, Toast
│       │   └── upload/         ← DropZone, DataPreview, AIPanel
│       ├── hooks/              ← useAuth, useFlow, usePersistedDataset
│       └── lib/
│           └── api.ts          ← API client with auto token refresh
│
└── infra/
    └── seed-data/              ← Demo CSV files for testing
```

---

## 🤝 Author

<div align="center">

**Akshay Santhosh**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/akshay-santhosh-435499208)
[![Gmail](https://img.shields.io/badge/Gmail-akshaysanthosh718-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:akshaysanthosh718@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-Live%20Site-00E6A7?style=for-the-badge&logo=vercel&logoColor=black)](https://akshay-portfolio-site-vert.vercel.app/)
[![GitHub](https://img.shields.io/badge/GitHub-akshayy718-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/akshayy718)

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,08090A,00E6A7&height=130&section=footer&animation=fadeIn" width="100%"/>

*Built with FastAPI · Next.js 14 · PostgreSQL · Deployed on Vercel + Render*

</div>
