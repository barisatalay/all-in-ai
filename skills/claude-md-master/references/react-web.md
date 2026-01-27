# React (Web)

## Detection signals
- `package.json`
- `src/`, `public/`
- `vite.config.*`, `next.config.*`, `webpack.config.*`
- `tsconfig.json`
- `turbo.json`
- `app/` or `pages/` (Next.js)

## Multi-module signals
- `pnpm-workspace.yaml`, `lerna.json`, `nx.json`, `turbo.json`
- Root `package.json` with `workspaces`
- `apps/` and `packages/` each with `package.json`

## Before generating, analyze these sources
- Root `package.json` and workspace config (`pnpm-workspace.yaml`, `lerna.json`,
  `nx.json`, `turbo.json`)
- `apps/*/package.json`, `packages/*/package.json` (if monorepo)
- `vite.config.*`, `next.config.*`, `webpack.config.*`
- `tsconfig.json` / `jsconfig.json`

## Codebase scan (React web-specific)
- Source roots: `src/`, `app/`, `pages/`, `components/`, `hooks/`, `services/`
- Folder patterns (record only if present):
  `routes`, `store`, `state`, `api`, `utils`, `assets`
- Routing markers (record only if present):
  React Router (`Routes`, `Route`), Next (`app/`, `pages/`)
- State management (record only if present):
  `redux`, `zustand`, `recoil`
- Naming conventions (record only if present):
  hooks `use*`, components PascalCase

## Mandatory output (React web module CLAUDE.md)
Include these if detected (list actual names found):
- **Pages/routes**: list page components or route files
- **Components**: list shared component directories
- **Hooks**: list custom hooks
- **Services/API**: list API client modules
- **State management**: list store setup (Redux, Zustand, etc.)
- **Utils**: list utility modules

## Command sources
- `package.json` scripts
- README/docs or CI
- Only include commands present in repo

## Key paths to mention (only if present)
- `src/`, `public/`
- `app/`, `pages/`, `components/`
- `hooks/`, `services/`
- `apps/`, `packages/` (monorepos)
