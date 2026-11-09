# LilTech 2026 — Official Event Platform

<p align="center">
  <strong>One night. Two challenges. One platform to run it all.</strong>
</p>

<p align="center">
  The official digital platform for LilTech 2026 — managing team registration, QR check-in, Mini-CTF challenges, submissions, and live jury scoring.
</p>

---

## About LilTech 2026

**LilTech 2026** is a night-long technology competition organized by **GDG on Campus EPI** and **ISITCom Google Club**, taking place on **November 21–22, 2026**, at **Campus EPI, Sousse, Tunisia**.

The event features two parallel challenge tracks, each with its own jury and podium.

This repository contains the frontend platform designed to centralize the competition workflow and provide a unified experience for participants, jury members, and organizers.

## Platform Overview

The platform brings the entire competition into one digital environment:

- **Team Registration:** Team leaders register their teams and members.
- **Digital QR Badges:** Each participant receives a personal QR code.
- **QR Check-in:** Staff validate participant attendance at the event entrance.
- **Mini-CTF:** Teams solve a warm-up challenge to unlock their main challenge.
- **Challenge Access:** Participants access challenge briefs, requirements, resources, and evaluation criteria.
- **Project Submission:** Teams submit repository links, demos, presentation slides, and files before the deadline.
- **Live Jury Scoring:** Jury members evaluate teams during their presentations.
- **Administration Dashboard:** Organizers manage teams, attendance, challenges, submissions, announcements, and event phases.
- **Real-Time Updates:** Event progress and important information are synchronized across the platform.

## Event Timeline

| Time | Activity |
|---|---|
| 20:00 — November 21 | Official event launch and Mini-CTF unlock |
| 20:00–08:00 | Competition and project development |
| 08:00 — November 22 | Submission deadline |
| 09:00 | Team presentations and jury evaluation |
| 11:00 | Results and awards |

## How It Works

1. **Register:** A team leader registers the team.
2. **Receive badges:** Each participant receives an individual QR badge.
3. **Check in:** Staff scan participant QR codes at the entrance.
4. **Launch:** Organizers officially launch the competition.
5. **Solve:** Teams solve their Mini-CTF and submit the required flag.
6. **Unlock:** A correct flag unlocks the team's main challenge.
7. **Build:** Teams work on their challenge and prepare their deliverables.
8. **Submit:** Teams submit their work before the deadline.
9. **Present:** Teams pitch their projects to the jury.
10. **Evaluate:** Jury members score the teams through the platform.
11. **Celebrate:** Organizers publish the results and announce the winners.

## User Roles

| Role | Main responsibilities |
|---|---|
| Participant / Team | Registration, QR badge, Mini-CTF, challenge access, submissions |
| Staff | QR check-in and attendance validation |
| Jury | Challenge-specific team evaluation and scoring |
| Administrator | Event configuration, team management, challenge publishing, announcements, and results |

## Technology Stack

### Frontend
- React 18
- TypeScript
- Vite
- React Router
- Tailwind CSS

### Animation and User Experience
- GSAP
- GSAP ScrollTrigger
- GSAP SplitText
- GSAP Flip
- Lenis

### Data and State Management
- TanStack Query
- Zustand
- Zod

### Additional Tools
- QR Scanner
- QR Code Generator
- DOMPurify
- Marked
- Vite PWA

### Testing and Code Quality
- Vitest
- React Testing Library
- Playwright
- ESLint
- Prettier

## Architecture

The frontend is designed around a modular API layer.

It includes:
- A typed API client.
- A mock adapter for development and testing without a backend.
- A real API adapter designed to connect to the backend.
- Runtime response validation with Zod.
- Real-time event handling with automatic reconnection.

The mock implementation allows the frontend to be developed and demonstrated independently. The real backend can be integrated through configuration rather than rewriting the application.

> **Important:** This repository contains the frontend implementation. It does not claim to include the production backend.

## Project Structure

```text
liltech-2026-platform/
│
├── public/
│   ├── images/
│   ├── logos/
│   └── assets/
│
├── src/
│   ├── app/
│   ├── assets/
│   ├── components/
│   ├── config/
│   ├── features/
│   │   ├── auth/
│   │   ├── registration/
│   │   ├── check-in/
│   │   ├── participant/
│   │   ├── mini-ctf/
│   │   ├── challenges/
│   │   ├── submissions/
│   │   ├── jury/
│   │   ├── admin/
│   │   └── announcements/
│   ├── hooks/
│   ├── layouts/
│   ├── lib/
│   ├── pages/
│   ├── services/
│   ├── stores/
│   ├── styles/
│   ├── types/
│   └── main.tsx
│
├── docs/
│   ├── api-gaps.md
│   ├── assumptions.md
│   └── architecture.md
│
├── tests/
├── .env.example
├── .gitignore
├── index.html
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

*The structure above is the recommended organization; adapt it to the actual implementation.*

## Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm
- Git

### Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/liltech-2026-platform.git
```

Enter the project directory:

```bash
cd liltech-2026-platform
```

Install dependencies:

```bash
npm install
```

Create your environment file:

```bash
cp .env.example .env
```

Start the development server:

```bash
npm run dev
```

Build the production version:

```bash
npm run build
```

Run tests:

```bash
npm run test
```

*These commands assume the corresponding scripts are configured in `package.json`.*

## Environment Variables

Create a `.env` file based on `.env.example`.

Example:

```env
VITE_API_BASE_URL=http://localhost:3000/api
VITE_USE_MOCK_API=true
```

Use the mock API during frontend development. Set the real API configuration when the backend is ready.

Never commit private API keys, credentials, or production secrets.

## Design Philosophy

The visual identity follows the theme:

**The Night. From Dusk to Dawn.**

The public and participant experiences are designed to feel immersive and cinematic, while operational interfaces prioritize clarity, speed, accessibility, and reliability.

The platform also respects reduced-motion preferences and keeps essential workflows usable without animations.

## Security and Reliability

The frontend follows several important principles:

- API responses are validated at runtime.
- Mini-CTF flags are validated server-side; the correct flag must never be exposed in frontend code.
- Role-based interfaces are not treated as a replacement for backend authorization.
- Submissions rely on server timestamps and the official server clock.
- User-provided Markdown is sanitized before rendering.
- Environment secrets are not committed to the repository.
- Operational pages prioritize reliability over decorative animations.

## Documentation

Additional technical documentation is maintained in the `docs/` directory:

- `architecture.md` — application structure and frontend architecture.
- `api-gaps.md` — missing API details or requirements to clarify with the backend team.
- `assumptions.md` — documented implementation decisions and unresolved specifications.

## Event Information

| Detail | Information |
|---|---|
| Event | LilTech 2026 |
| Dates | November 21–22, 2026 |
| Venue | Campus EPI, Sousse, Tunisia |
| Organizers | GDG on Campus EPI & ISITCom Google Club |
| Competition format | Two parallel challenges |
| Evaluation | Separate juries and podiums |

## Contributors

Developed for the LilTech 2026 event by the project contributors and organizing teams.

Contributions, improvements, and technical feedback are welcome, subject to the repository's contribution guidelines.

## License

The license will be specified by the repository owners after confirming the project's distribution and usage permissions.

---

<p align="center">
  <strong>LilTech 2026</strong><br/>
  One night. Two challenges. One platform to run it all.
</p>
