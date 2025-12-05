# Lituus Foundation Website

## Quick Commands

```bash
npm run dev       # Astro dev server at localhost:3000
npm run build     # Build static site to ./dist/
npm run preview   # Build + test with Wrangler (Workers runtime)
npm run deploy    # Build + deploy to Cloudflare Workers
npm run cf-typegen # Generate Cloudflare type definitions
```

## Project Overview

- **Framework**: Astro 5.16.4
- **Deployment**: Cloudflare Workers (full-stack capable)
- **Build Output**: `./dist/` with Worker entry at `./dist/_worker.js/index.js`
- **Current State**: Minimal template, early-stage foundation website

## Architecture

This is a **Cloudflare Workers + Astro** project configured for full-stack deployment:

- **Static Content**: Astro generates HTML/CSS/JS to `./dist/`
- **Worker Script**: `./dist/_worker.js/index.js` serves assets and can handle dynamic routes
- **Assets Binding**: Static files served via Workers Assets binding
- **Image Optimization**: Cloudflare Image Service enabled
- **Local Testing**: `platformProxy` enabled in Astro config

## Project Structure

```
src/
  ├── pages/
  │   └── index.astro (file-based routing)
  ├── components/ (reusable Astro components)
  ├── env.d.ts (Cloudflare runtime types)
public/
  ├── favicon.svg
  └── .assetsignore (excludes _worker.js from assets)
```

## Key Configuration Files

- **wrangler.jsonc**: Workers configuration with Assets binding
- **astro.config.mjs**: Cloudflare adapter with Image Service
- **tsconfig.json**: TypeScript strict mode
- **src/env.d.ts**: Cloudflare runtime type definitions

## Astro + Workers Patterns

### Static Components (Zero JS)
- `.astro` files render to static HTML by default
- Use for content, layouts, page structure
- No JavaScript sent to browser for these components

### Interactive Components (Optional)
- Import UI frameworks (React, Vue, Svelte) as "islands"
- Requires `client:*` directive (e.g., `client:idle`)
- Props must be serializable (no functions)
- Use sparingly for better performance

### Server Routes (Full-Stack)
- Create `.astro` files with `export const GET()`, `export const POST()`, etc.
- Access Cloudflare runtime via `Astro.locals`
- Can add KV, D1, R2 bindings to `wrangler.jsonc` as needed

## Styling & Components

Not yet defined. Decisions needed:
- CSS approach (Tailwind, CSS modules, plain CSS, etc.)
- Component library or custom
- Dark mode strategy
- Design system/tokens

## Development Workflow

1. Create `.astro` files in `src/pages/` for routes
2. Create reusable `.astro` components in `src/components/`
3. Run `npm run dev` for local development
4. Test with Workers runtime using `npm run preview`
5. Deploy with `npm run deploy`

## Constraints & Decisions

- Static-first approach: Generate what you can at build time
- Workers for edge serving and optional server logic
- TypeScript strict mode enforced
- Observability enabled for production
- No framework components added yet (pure Astro)
