# Task Completion Checklist

When completing a coding task in this project:

## Frontend Changes
1. Run type check: `npm run lint:types`
2. Run ESLint: `npm run lint:frontend`
3. Format with Prettier: `npm run format`
4. Run unit tests: `npm run test:frontend`

## Backend Changes
1. Format with Black: `npm run format:backend`
2. Run pylint: `npm run lint:backend`
3. Run backend tests: `cd backend && python -m pytest`

## Both (Full lint)
```bash
npm run lint
```

## i18n Changes
```bash
npm run i18n:parse
```
