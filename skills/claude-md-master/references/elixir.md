# Elixir / Erlang

## Detection signals
- `mix.exs`, `mix.lock`
- `config/config.exs`
- `lib/`, `test/`
- `apps/` (umbrella)
- `rel/`

## Multi-module signals
- Umbrella with `apps/` containing multiple `mix.exs`
- Root `mix.exs` with `apps_path`

## Before generating, analyze these sources
- Root `mix.exs`, `mix.lock`
- `config/config.exs`
- `apps/*/mix.exs` (umbrella)
- `lib/`, `test/`, `rel/`

## Codebase scan (Elixir-specific)
- Source roots: `lib/`, `test/`, `apps/*/lib` (umbrella)
- Phoenix structure (record only if present):
  `lib/*_web/`, `controllers`, `views`, `channels`, `routers`
- Ecto usage (record only if present):
  `schema`, `Repo`, `migrations`
- Contexts/modules (record only if present):
  `lib/*/` context modules and `*_context.ex`

## Mandatory output (Elixir module CLAUDE.md)
Include these if detected (list actual names found):
- **Contexts**: list context modules
- **Schemas**: list Ecto schema modules
- **Controllers**: list Phoenix controller modules
- **Channels**: list Phoenix channel modules
- **Workers**: list background job modules (Oban, etc.)
- **Umbrella apps**: list apps under umbrella (if any)

## Command sources
- README/docs or CI invoking `mix`
- Repo scripts that call `mix`
- Only include commands present in repo

## Key paths to mention (only if present)
- `lib/`, `test/`, `config/`
- `apps/`, `rel/`
