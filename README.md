# TourTravel (working name)

SaaS ERP for tour & travel agencies — Chris & Mulyadi, Batam.
Built on Arthasee's core (event bus, tenant scoping, auth), licensed from Langit.

Design: "Tour & Travel ERP — Design v0.1" (Claude Docs).

## Run locally

Ports are chosen so it runs next to Arthasee: backend **8001**, frontend **3001**.

    # backend
    cd backend
    source .venv/bin/activate
    python manage.py runserver 8001

    # frontend (second terminal)
    cd frontend
    npm run dev          # http://localhost:3001

    # tests
    cd backend && python manage.py test

## What's here (v0 scaffold)

- `apps/core` — TenantScopedModel, TenantScopedAPIView, Outbox + event bus (from Arthasee)
- `apps/authentication` — CustomUser (owner / super_admin), JWT login (from Arthasee)
- `apps/organizations` — Organization = one travel agency (slimmed)
- `/api/health/` — health check

Not yet: the accounting engine (ported as its own step), and the travel modules.
