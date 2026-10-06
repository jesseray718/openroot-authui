# OpenRoot Auth UI

Next.js authentication system for the OpenRoot ecosystem: JWT auth via jose
middleware, drizzle sqlite registration/login persistence, and
login/register/logout/dashboard UI. Smoke-tested end-to-end
(register 307 / login 200 / protected redirect 307).

Extracted from jesseray718/openroot on 2026-10-06 per issue #118 (decision:
extract), preserving original commit history via git filter-repo.

## Files

- app/ — Next.js app router pages and API routes
- smoke_auth_v1.sh — end-to-end auth smoke test (register, login, token, protected route)
- seal_auth_v1.sh — session seal script
- Root JS configs (package.json, tsconfig, biome, etc.)

## Setup

    npm install
    cp .env.local.example .env.local   # if present; otherwise create
    npm run dev                        # serves on :3000

## Standing items

- Known deliberate vuln hold: next@14.2.35 (documented in smoke_auth_v1.sh)
- .env.local is gitignored; JWT_SECRET must be set locally — rotate if the
  old secret ever appeared in logs
