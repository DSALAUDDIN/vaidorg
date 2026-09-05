# VAID — Volunteer Aid International

Production-oriented full-stack starter for the **Volunteer Aid International (VAID)** platform.

## Stack

- **Frontend:** Next.js App Router + TypeScript
- **Backend:** NestJS + TypeScript
- **Database:** PostgreSQL (Neon-ready)
- **ORM / schema:** Drizzle ORM
- **Authentication:** JWT issued by NestJS, stored by the Next.js app as an HTTP-only cookie
- **Authorization:** Role-based `ADMIN` / `VOLUNTEER`
- **Password security:** bcrypt (12 rounds)

The supplied Volunteer Aid logo and campaign artwork are used as the visual source of truth.

## Included product areas

### Public website
- Human-first VAID landing page
- Brand theme based on supplied green / red / blue / cream identity
- Impact areas
- Opportunity marketplace
- Volunteer, internship, emergency and remote opportunity types
- Location/type search filters

### Volunteer portal
- Volunteer registration
- Volunteer login
- My VAID dashboard
- Application history/status
- Upcoming schedule
- Verified service-hour total
- Certificate count
- PostgreSQL-backed data

### Admin portal
- Separate admin login
- Admin dashboard metrics
- Publish opportunities
- Review/update applications
- Assign volunteer schedule items
- Verify service hours
- Issue certificates
- Volunteer directory API

## Database tables

`users`, `volunteer_profiles`, `organizations`, `opportunities`, `applications`, `schedules`, `service_logs`, `certificates`

## Local setup

Create `backend/.env` from `backend/.env.example` and `frontend/.env.local` from `frontend/.env.example`.

Then run:

```bash
npm install
npm run db:migrate
npm run db:seed
npm run dev
```

- Public website: `http://localhost:3000`
- Volunteer login: `http://localhost:3000/login`
- Volunteer registration: `http://localhost:3000/register`
- Volunteer dashboard: `http://localhost:3000/dashboard`
- Admin login: `http://localhost:3000/admin/login`
- Admin panel: `http://localhost:3000/admin`
- NestJS API: `http://localhost:4000/api`

## Production

Recommended split:

- **Next.js:** Vercel
- **NestJS:** Railway / Render / VPS
- **PostgreSQL:** Neon

Never commit `.env`. Rotate any credential that has been shared outside your secret manager.
