# Project Guidelines

## Project Overview
- Mona Mayhem is an Astro v5 app with a Node adapter and server output.
- The main UI entry point is `src/pages/index.astro`.
- API endpoints live in `src/pages/api/**` and are implemented as Astro API routes.
- Treat `workshop/**` as reference material only; do not change it unless the user explicitly asks.

## Build and Dev Commands
- Install dependencies: `npm install`
- Start local dev server: `npm run dev`
- Build for production: `npm run build`
- Run production preview locally: `npm run preview`

## Architecture
- `astro.config.mjs` sets `output: 'server'` with `@astrojs/node` in standalone mode.
- `src/pages/**` defines routes by file-based routing.
- `src/pages/api/contributions/[username].ts` is a dynamic API route for contribution data.

## Astro Best Practices
- Keep page templates in `.astro` files and put server-side logic in frontmatter.
- Prefer small, focused routes and components; move shared logic into utility modules when added.
- Type API handlers with `APIRoute` and validate route params before using them.
- Return explicit HTTP status codes and JSON content types for API responses.
- Keep SSR behavior intentional: use `export const prerender = false` only for routes that must run on the server.
- Avoid embedding large CSS/JS blocks in pages when a dedicated file in `public/` or `src/` is clearer.

## Conventions
- Use TypeScript for API routes and keep response payloads predictable.
- Preserve existing formatting style in each file (tabs/spaces and quote style).
- Make minimal, targeted edits; avoid broad refactors unless requested.
