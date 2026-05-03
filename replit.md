# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Hosts the Agrawal Packaging Systems website — a packaging machinery company website for a Chennai-based manufacturer.

## Artifacts

- **agrawal-packaging** (`artifacts/agrawal-packaging/`) — React + Vite frontend, served at `/`
- **api-server** (`artifacts/api-server/`) — Express 5 API, served at `/api`
- **mockup-sandbox** (`artifacts/mockup-sandbox/`) — Canvas design prototyping, served at `/__mockup`

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite + Tailwind CSS v4 + shadcn/ui + Wouter
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Agrawal Packaging Site Structure

### Pages
- `/` — Home (hero, products, services, industries, CTA)
- `/about` — Company story, values, stats
- `/products` — Product listing (Form Fill Seal, Pick Fill Seal, Band Sealers, Bottle Filling, Compact Units, Additional Machinery)
- `/services` — All services (AMC, Line Integration, Consultancy, Retrofitting, etc.)
- `/industries` — Industries served (12 sectors)
- `/get-a-quote` — **ONLY** shows the Enquiry Form (distinct from Contact Us)
- `/contact` — **ONLY** shows Contact Info + Google Maps location (distinct from Get a Quote)
- `/blog` — Blog posts
- `/our-reach` — Pan-India service network
- Footer mixes both Enquiry Form + Contact Info

### Key Design Decisions
- **Get a Quote** (CTA button, orange): links to `/get-a-quote` — shows ONLY enquiry form
- **Contact Us** (nav link): links to `/contact` — shows ONLY contact info + map location tag
- Footer: combines both sections for quick access
- Phone & WhatsApp: **+91 8939663466**
- Floating WhatsApp button on all pages

### Contact Details
- Phone/WhatsApp: +91 8939663466
- Email: info@agrawalpackaging.com
- Address: Industrial Area, Chennai, Tamil Nadu – 600 001

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
