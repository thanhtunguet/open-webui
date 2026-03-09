# Style & Conventions

## Frontend (TypeScript / Svelte)
- **Formatter**: Prettier
  - useTabs: true
  - singleQuote: true
  - trailingComma: none
  - printWidth: 100
  - endOfLine: lf
  - prettier-plugin-svelte for .svelte files
- **Linter**: ESLint with TypeScript and Svelte plugins
- **Framework**: SvelteKit (Svelte 5 with runes syntax)
- **Styling**: TailwindCSS v4

## Backend (Python)
- **Formatter**: Black (excludes .venv/ and /venv/)
- **Linter**: Pylint
- **Framework**: FastAPI + Pydantic v2
- **ORM**: SQLAlchemy 2.0 + Alembic (migrations), Peewee (legacy)
- **Async**: aiohttp, aiofiles
- Type hints are used throughout Python code (Pydantic models)
- No strict docstring requirement observed

## Naming Conventions
- Frontend: camelCase for variables/functions, PascalCase for components/types
- Backend: snake_case for Python (PEP8)
- File names: kebab-case for Svelte components, snake_case for Python
