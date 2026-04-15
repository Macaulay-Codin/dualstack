# DualStack Press Kit

---

## One Liner

Open source FastAPI and Next.js SaaS starter kit. 1,357 tests written first, 95 percent coverage, zero vulnerabilities. MIT licensed.

---

## What It Is

DualStack is a production ready starter kit for people who want to ship a SaaS without copying half broken boilerplate from their last project. Auth, payments, file uploads, real time events, monitoring. All there, all tested.

Every feature was test first. 863 backend tests, 494 frontend tests. Each integration point, each error path, each webhook race condition. Then the code to make them pass.

The result is something you can hand to a developer on day one. They can rip out whatever they dont need without wondering what breaks upstream.

---

## Source

GitHub: https://github.com/Macaulay-Codin/dualstack

---

## Numbers

| | |
|---|---|
| Backend tests | 863 |
| Frontend tests | 494 |
| Total tests | 1,357 |
| Coverage | 95 percent |
| Dependency vulnerabilities | 0 |
| Shared bundle size | 102 kB |
| Full deploy | 84 seconds |
| Authentication | Clerk (JWT via JWKS) |
| Payments | Stripe (Checkout, Portal, Webhooks) |
| Storage | S3 and R2 compatible, presigned URLs |
| Monitoring | Prometheus, Grafana, Alertmanager |
| Email | Resend, templates included |
| License | MIT |

---

## What It Actually Does

**Authentication.** Clerk on the frontend. Backend verifies every JWT against the JWKS endpoint with optional `aud` claim validation. Dev mode accepts an `X-User-ID` header for local testing. Production blocks it.

**Payments.** Stripe Checkout and Customer Portal wired end to end. Webhook handlers are idempotent. Plan enforcement is server side through an entitlements system, not frontend feature flags. Free, Pro, Enterprise tiers out of the box.

**File Uploads.** S3 and R2 compatible presigned URL flow. Content type allowlist blocks `text/html`, `image/svg+xml`, `application/javascript`, and `application/octet-stream`. Filenames are sanitized to strip path traversal attempts.

**Real Time.** WebSocket endpoint with JWT authentication and per user message routing. No broadcast leakage. Connection manager included.

**RBAC.** Role based access control with admin, user, and custom roles. Admin dashboard ships with the kit. User management, audit log viewer, health check detail page.

**Monitoring.** Prometheus scraping a protected `/metrics` endpoint. Grafana dashboards and Alertmanager routing all defined in Docker Compose. Kubernetes liveness and readiness probes built in.

**Background Jobs.** APScheduler for async task scheduling. Scoped to the backend process, swap for Celery when you need distributed workers.

**Email.** Resend integration with transactional templates. Infrastructure ready. You wire your own triggers.

**Generic CRUD Entity.** An Items module demonstrating the full pattern. Run `python scripts/rename.py --from item --to project` to rename everything at once. Class names, imports, routes, directories, Alembic migrations. One command.

---

## Stack

| Layer | Technology |
|-------|-----------|
| Backend | FastAPI, SQLAlchemy 2.0, Pydantic v2 |
| Frontend | Next.js 15 (App Router), React 18, TypeScript 5 |
| Database | SQLite by default, Turso ready, Postgres ready |
| Auth | Clerk (JWKS verification) |
| Payments | Stripe (Checkout, Portal, Webhooks) |
| Storage | S3 or R2 (presigned URLs) |
| Email | Resend |
| Styling | Tailwind CSS, shadcn/ui |
| State | React Query, Zustand |
| Real time | WebSocket (JWT authenticated) |
| Monitoring | Prometheus, Grafana, Alertmanager |
| Testing | pytest (863), Jest and Playwright (494) |
| Deployment | Docker backend, Vercel frontend |

---

## Built With PairCoder

DualStack was built using PairCoder's enforcement workflow. The 1,357 test suite is not afterthought coverage. Every feature started as a failing test. The webhook handlers, JWT verification, presigned URL generation, WebSocket auth, and RBAC enforcement all have deterministic test coverage because the enforcement layer required it before any code shipped.

The kit is the proof of the method. You dont have to trust the claim. Read the tests.

---

## The Problem

Every SaaS project starts the same way. Clone the last one. Strip the domain logic. Try to remember which auth fixes landed in the previous repo and which ones didnt. Chase down the webhook bug that bit you three projects ago because it never got written up. Ship the same half broken boilerplate with the same bugs inherited from the one before.

DualStack replaces that pattern with a tested foundation. The auth flow is verified. The payment webhook is idempotent. The file upload endpoint rejects the classes of content that get you in trouble. The RBAC system actually enforces roles instead of decorating them.

You start with a known good base and add your domain on top.

---

## Quickstart

```bash
git clone https://github.com/Macaulay-Codin/dualstack
cd dualstack
make setup
make dev
```

Frontend at http://localhost:3000. API at http://localhost:8000. Grafana at http://localhost:3001. You bring Clerk and Stripe keys. The kit brings everything else.

---

## Screenshots

_Screenshot capture pending. Run `make dev`, log in, exercise the flows below, drop captures here._

1. **Landing Page** `press-01-landing.png`
2. **Dashboard** `press-02-dashboard.png`
3. **Items CRUD** `press-03-items.png`
4. **Billing Portal Entry** `press-04-billing.png`
5. **Admin User Management** `press-05-admin.png`
6. **Grafana Dashboard** `press-06-grafana.png`

---

## Quote

"I stopped writing features and spent a month writing tests first. The kit is the proof." Kevin Masterson

---

## Team

- **Kevin Masterson** Creator, lead developer

---

## Contact

- **Reddit:** u/macaulay_codin
- **X:** @paircoder
- **GitHub:** https://github.com/fivedollarfridays
- **Subreddit:** r/PairCoder

---

## License

MIT

---

_Last updated: 2026-04-15_
