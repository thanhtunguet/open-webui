# Open WebUI Project Memory

## Project Purpose
Open WebUI is an extensible, feature-rich, self-hosted AI platform designed to operate offline. It supports LLM runners like Ollama and OpenAI-compatible APIs, with built-in RAG inference engine.

## Tech Stack
- **Frontend**: SvelteKit (Svelte 5), TypeScript, TailwindCSS v4, Vite
- **Backend**: Python with FastAPI, SQLAlchemy/Alembic, Peewee ORM
- **Testing**: Vitest (frontend), Cypress (E2E), pytest (backend)
- **Containerization**: Docker / Docker Compose
- **Database**: SQLite (default) / PostgreSQL

## Key Directories
- `src/` — SvelteKit frontend
  - `src/lib/` — Shared libs (apis, components, stores, utils, types, i18n)
  - `src/routes/` — SvelteKit routes
- `backend/open_webui/` — Python FastAPI backend
  - `routers/`, `models/`, `utils/`, `retrieval/`, `socket/`
- `static/` — Static assets
- `cypress/` — E2E tests
- `test/` — Frontend unit tests

## See Also
- [suggested_commands.md](suggested_commands.md)
- [style_conventions.md](style_conventions.md)
- [task_completion.md](task_completion.md)
