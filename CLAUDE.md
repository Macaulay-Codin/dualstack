# Claude Code Instructions

> DualStack — FastAPI + Next.js SaaS Starter Kit

## Architecture

- **Backend**: FastAPI (Python 3.13), SQLAlchemy 2.0, Pydantic v2
- **Frontend**: Next.js 15, React 18, TypeScript
- **Database**: SQLite (Turso-ready)
- **Auth**: Clerk (JWT + JWKS)
- **Payments**: Stripe
- **Storage**: S3/R2-compatible presigned URLs

## Conventions

- Follow TDD: write tests before implementation
- Max file length: 300 lines (tests: 400)
- Max function length: 50 lines
- All request/response models use Pydantic v2
- Frontend state: React Query + Zustand
- UI components: shadcn/ui + Tailwind CSS

## Key Paths

| Path | Purpose |
|------|---------|
| `backend/app/core/` | Infrastructure (config, db, errors, logging) |
| `backend/app/items/` | Generic CRUD entity (copy for new modules) |
| `backend/tests/` | pytest test suite |
| `frontend/src/app/` | Next.js pages |
| `frontend/src/components/` | React components |
| `monitoring/` | Prometheus + Grafana Docker stack |
