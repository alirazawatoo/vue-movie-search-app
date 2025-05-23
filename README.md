# JibbleGroup

Movie search web app built with **Vue 3** (Composition API), **TypeScript**, **Quasar**, and **Pinia**. It queries the public [jsonmock Hackerrank movies API](https://jsonmock.hackerrank.com/api/movies/search) by title, supports **pagination**, and handles **loading**, **empty**, and **error** states. Styles use **Sass** (no Tailwind).

## What’s in the repo

- **UI**: Quasar layout, search field with debounced search, results table, pagination, banners for errors.
- **State**: Pinia store with abort-aware `fetch` calls to avoid race conditions when the query or page changes quickly.
- **API**: Typed client with HTTPS-only origin and validated JSON responses.
- **Tests**: Vitest for the API client, store, and app shell; Playwright e2e tests with a mocked search API for stable CI-style runs.

## Requirements

- **Node.js** `^20.19.0` or `>=22.12.0` (see `package.json` `engines`).

## Run locally

Install dependencies (this repo includes `package-lock.json`; use **npm** unless you prefer another tool and regenerate its lockfile):

```sh
npm install
```

Start the Vite dev server (default [http://localhost:5173](http://localhost:5173)):

```sh
npm run dev
```

Type-check only:

```sh
npm run type-check
```

Production build (runs type-check in parallel with the Vite build):

```sh
npm run build
```

Serve the production build locally:

```sh
npm run preview
```

Lint (Oxlint + ESLint):

```sh
npm run lint
```

Format `src/` with Prettier:

```sh
npm run format
```

## Tests

### Unit tests (Vitest)

Watch mode (default):

```sh
npm run test:unit
```

Single non-watch run (e.g. CI or one-off):

```sh
npm run test:unit -- --run
```

### End-to-end tests (Playwright)

Install browsers once (or after upgrading `@playwright/test`):

```sh
npx playwright install
```

Run all configured browser projects:

```sh
npm run test:e2e
```

Run only Chromium (faster local feedback):

```sh
npm run test:e2e -- --project=chromium
```

`playwright.config.ts` starts the dev server automatically for e2e unless you override that behavior.

## Optional tooling

- **VS Code** with the [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) extension is a good match for `.vue` + TypeScript.
