# Node Tooling (generic)

## Detection signals
- `package.json`
- `package-lock.json`, `pnpm-lock.yaml`, `yarn.lock`
- `.nvmrc`, `.node-version`
- `tsconfig.json`
- `.npmrc`, `.yarnrc.yml`
- `next.config.*`, `nuxt.config.*`
- `nest-cli.json`, `svelte.config.*`, `astro.config.*`

## Multi-module signals
- `pnpm-workspace.yaml`, `lerna.json`, `nx.json`, `turbo.json`, `rush.json`
- Root `package.json` with `workspaces`
- Multiple `package.json` under `apps/`, `packages/`

## Before generating, analyze these sources
- Root `package.json` and workspace config (`pnpm-workspace.yaml`, `lerna.json`,
  `nx.json`, `turbo.json`, `rush.json`)
- `apps/*/package.json`, `packages/*/package.json` (if monorepo)
- `tsconfig.json` or `jsconfig.json`
- Framework config: `next.config.*`, `nuxt.config.*`, `nest-cli.json`,
  `svelte.config.*`, `astro.config.*` (if present)

## Codebase scan (Node-specific)
- Source roots: `src/`, `lib/`, `apps/`, `packages/`
- Folder patterns (record only if present):
  `routes`, `controllers`, `services`, `middlewares`, `handlers`,
  `utils`, `config`, `models`, `schemas`
- Framework markers (record only if present):
  Express (`express()`, `Router`), Koa (`new Koa()`),
  Fastify (`fastify()`), Nest (`@Controller`, `@Module`, `@Injectable`)
- Full-stack layouts (record only if present):
  Next/Nuxt (`pages/`, `app/`, `server/`)

## Mandatory output (Node module CLAUDE.md)
Include these if detected (list actual names found):
- **Routes/pages**: list route files or page components
- **Controllers/handlers**: list controller or handler files
- **Services**: list service classes or modules
- **Middlewares**: list middleware files
- **Models/schemas**: list data models or validation schemas
- **State management**: list store setup (Redux, Zustand, etc.)
- **API clients**: list external API client modules

## Command sources
- `package.json` scripts
- README/docs or CI
- `npm|yarn|pnpm` script usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `src/`, `lib/`
- `tests/`
- `apps/`, `packages/` (monorepos)
- `pages/`, `app/`, `server/`, `api/`
- `controllers/`, `services/`
