# Nexus Studios

AI-powered Creator Intelligence OS for YouTube creators.

## Purpose

Nexus Studios is an AI-powered creator intelligence platform designed for YouTube creators. This repository establishes the clean technical foundation for future product development without implementing product features yet.

## Architecture

This monorepo organizes the foundation into a small set of focused areas:

- `apps/web` — Next.js web application shell
- `apps/worker` — Node.js background worker service
- `packages/db` — Drizzle ORM + PostgreSQL setup
- `packages/contracts` — shared TypeScript interfaces
- `packages/config` — environment validation
- `packages/core` — reusable business logic
- `packages/logger` — structured logging
- `packages/queue` — queue abstraction
- `docs` — architecture and ADR documentation

This is intentionally minimal and extensible. Core feature work will be added later by other agents without modifying the underlying foundation.

## Folder Structure

```text
nexus-studios/
├── apps/
│   ├── web/
│   └── worker/
├── packages/
│   ├── ai/
│   ├── config/
│   ├── contracts/
│   ├── core/
│   ├── db/
│   ├── logger/
│   ├── queue/
│   ├── youtube/
│   └── ...
├── docs/
│   ├── adr/
│   └── architecture/
├── .github/
│   └── workflows/
├── .env.example
├── .gitignore
├── README.md
├── package.json
├── pnpm-workspace.yaml
├── tsconfig.base.json
├── tsconfig.json
├── turbo.json
├── vitest.config.ts
├── pnpm-lock.yaml (generated after install)
└── ...
```

## Prerequisites

- Node.js 18+
- pnpm 9+
- PostgreSQL-compatible database for local development

## Installation

```bash
git clone https://github.com/Sauritx/nexus-studios.git
cd nexus-studios
pnpm install
```

## Environment Setup

Copy the example environment file before starting development:

```bash
cp .env.example .env.local
```

Then fill values for your local environment. This repository intentionally does not include real secrets or production credentials.

Required variables:

- `DATABASE_URL`
- `DIRECT_DATABASE_URL`
- `GOOGLE_CLIENT_ID`
- `GOOGLE_CLIENT_SECRET`
- `GOOGLE_REDIRECT_URI`
- `YOUTUBE_API_KEY`
- `ENCRYPTION_KEY`
- `AI_PROVIDER`
- `OPENAI_API_KEY`
- `ANTHROPIC_API_KEY`
- `QUEUE_DATABASE_URL`
- `NEXT_PUBLIC_APP_URL`
- `NODE_ENV`

See `.env.example` for placeholder values.

## Development Commands

```bash
pnpm dev
pnpm build
pnpm lint
pnpm typecheck
pnpm test
pnpm db:generate
pnpm db:migrate
pnpm db:studio
```

## Important Scope Boundaries

This foundation intentionally does not implement:

- YouTube OAuth
- YouTube API integration
- AI agents
- niche detection
- analytics
- discovery
- scoring
- autopilot
- dashboards
- production database schema
- full UI

These will be added later as product features.

## Contributing

Keep feature work aligned with the monorepo structure and the repository's strict TypeScript foundation. Add tests for any new logic and prefer shared packages over app-local duplication.

---

Nexus Studios — foundation for creator intelligence workflows.
