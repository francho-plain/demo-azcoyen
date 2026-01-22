# Copilot Instructions for AI Agents

## Overview
This is a monorepo for a task management app with:
- **Frontend**: Vue 3.5+ (Vuetify) in `/frontend`
- **Backend**: Django + Django REST Framework in `/backend`
- **Database**: Postgres (Dockerized)
- **Orchestration**: Docker Compose
- **Documentation & Tasks**: `/docs` (see `TASK.md` for atomic, tracked tasks)

## Architecture & Data Flow
- The frontend (Vue) communicates with the backend (Django REST API) via HTTP (CORS enabled).
- The backend persists data in a Postgres DB, all services run in containers via `docker-compose`.
- No authentication is required for MVP.

## Developer Workflows
- **Build/Run All**: Use `docker-compose up --build` from the repo root to start all services.
- **Frontend**: Vue app in `/frontend`, use standard Vue CLI commands for local dev if needed.
- **Backend**: Django app in `/backend`, use `manage.py` for migrations, createsuperuser, etc.
- **Database**: Data is persisted in `/db-data` (mounted volume).
- **Conventional Commits**: Enforced via commitlint/husky (see root config).
- **Tasks**: All project tasks are tracked in `/docs/TASK.md` and must be checked off and committed as completed.
- **Terminal Usage**: Always use a clean terminal session when running commands to avoid environment issues.

## Project Conventions
- **Monorepo**: All code (frontend, backend, infra) lives in a single repo, top-level folders.
- **Atomic Tasks**: Each user story (US-#) is tracked in `/docs/TASK.md` and must be implemented as an atomic, independent unit of work. When a task is completed, it MUST be immediately marked as `[x]` in `/docs/TASK.md` and a commit must be made reflecting the completion of that task.
- **Commits**: Use [Conventional Commits](https://www.conventionalcommits.org/) for all changes. Each completed task should have its own commit.
- **Docker**: All services must be runnable via `docker-compose` for local/dev/test.
- **Quality**: Linters and formatters (eslint/prettier for JS, black/flake8 for Python) are required.

## Key Files & Directories
- `/frontend`: Vue 3.5+ app (Vuetify, axios for API calls)
- `/backend`: Django + DRF app (tasks model, API, migrations)
- `/docs/TASK.md`: Task tracking (MUST update as you complete work)
- `/README.md`: High-level project overview
- `/docker-compose.yml`: Service orchestration

## Patterns & Examples
- **API**: All task operations (CRUD) are exposed via REST endpoints in Django.
- **Frontend**: State managed locally, API calls via axios, UI styled with Vuetify.
- **Testing**: Each component (frontend/backend) should have basic tests (unit/integration).

## Integration Points
- **Frontend <-> Backend**: All communication via REST API (CORS enabled on backend).
- **Backend <-> DB**: Django ORM, Postgres connection via Docker Compose networking.

---
For any new feature, update `/docs/TASK.md` and follow the atomic commit workflow. See existing files for structure and conventions.
