# Suggested Commands

## Frontend Development
```bash
# Start dev server
npm run dev

# Build for production
npm run build

# Preview build
npm run preview
```

## Backend Development
```bash
# Start backend dev server
cd backend && ./dev.sh

# Or via run.sh at project root
./run.sh
```

## Linting & Formatting
```bash
# Lint all (frontend + types + backend)
npm run lint

# Lint frontend only
npm run lint:frontend

# Type-check frontend
npm run lint:types    # runs svelte-check

# Lint backend (pylint)
npm run lint:backend

# Format frontend (prettier)
npm run format

# Format backend (black)
npm run format:backend
```

## Testing
```bash
# Run frontend unit tests
npm run test:frontend

# Open Cypress E2E
npm run cy:open

# Run backend tests (pytest)
cd backend && python -m pytest
```

## i18n
```bash
# Parse and update i18n strings
npm run i18n:parse
```

## Docker
```bash
# Start via docker-compose
make install        # docker-compose up -d
make startAndBuild  # up -d --build
make stop
make start
make remove
```
