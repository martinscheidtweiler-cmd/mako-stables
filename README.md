# MaKo Stables

Mobile-first training planner for Martin & Kobe.

## Architecture

- Static installable PWA — served from the repository root by Vercel.
- Auth, horse profiles, plans and logs: **existing Optimus Supabase** project.
- AI interface is included, but **AI is not active** until the `mako-coach` Supabase Edge Function and an `OPENAI_API_KEY` secret are configured. Do not put any secret in this repository or in client JavaScript.
- Supabase's **publishable** (public) client key appears in the UI intentionally. Authorization is enforced by row-level security policies.

## Deploying with GitHub → Vercel

Import this repository as a **new** Vercel project called `mako-stables`.
- Framework preset: Other
- Root directory: `./`
- Build command: none
- Output: root (static website)
- Disable preview deployments if you want to minimize deploys.
- Import and deploy **once**. Subsequent pushes to production branch may trigger more deployments and associated usage; collect changes before pushing.

## Install on a phone

- iPhone: Open HTTPS URL in Safari → Share → Add to Home Screen.
- Android: Open HTTPS URL in Chrome → menu → Install app.

## Auth callbacks

Add the final app URL to existing Optimus Supabase → Authentication → URL Configuration → Redirect URLs; keep the existing Optimus URLs unchanged.

## Local preview

Run any small static HTTP server in this directory, e.g. `python3 -m http.server 8000`. Open http://localhost:8000 .