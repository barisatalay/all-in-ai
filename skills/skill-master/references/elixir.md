# Elixir/Erlang

## Detection signals
- `mix.exs`
- `mix.lock`
- `config/config.exs`
- `lib/`, `test/` directories

## Multi-module signals
- Umbrella app (`apps/` directory)
- Multiple `mix.exs` in subdirs
- `rel/` for releases

## Pre-generation sources
- `mix.exs` (dependencies, config)
- `config/*.exs` (configuration)
- `rel/config.exs` (releases)

## Codebase scan patterns

### Source roots
- `lib/`, `apps/*/lib/`

### Layer/folder patterns (record if present)
`controllers/`, `views/`, `channels/`, `contexts/`, `schemas/`, `workers/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Phoenix Controller | `use *Web, :controller`, `def index` | phoenix-controller |
| Phoenix LiveView | `use *Web, :live_view`, `mount/3` | phoenix-liveview |
| Phoenix Channel | `use *Web, :channel`, `join/3` | phoenix-channel |
| Ecto Schema | `use Ecto.Schema`, `schema "` | ecto-schema |
| Ecto Migration | `use Ecto.Migration`, `create table` | ecto-migration |
| Ecto Changeset | `cast/4`, `validate_required` | ecto-changeset |
| Context | `defmodule *Context`, `def list_*` | phoenix-context |
| GenServer | `use GenServer`, `handle_call` | genserver |
| Supervisor | `use Supervisor`, `start_link` | supervisor |
| Task | `Task.async`, `Task.Supervisor` | elixir-task |
| Oban Worker | `use Oban.Worker`, `perform/1` | oban-worker |
| Absinthe | `use Absinthe.Schema`, `field :` | graphql-schema |
| ExUnit Test | `use ExUnit.Case`, `test "` | exunit-test |

## Mandatory output sections

Include if detected:
- **Controllers/LiveViews**: HTTP/WebSocket handlers
- **Contexts**: business logic
- **Schemas**: Ecto models
- **Channels**: real-time handlers
- **Workers**: background jobs

## Command sources
- `mix.exs` aliases
- README/docs, CI
- Common: `mix deps.get`, `mix test`, `mix phx.server`
- Only include commands present in repo

## Key paths
- `lib/*/`, `lib/*_web/`
- `priv/repo/migrations/`
- `test/`
- `config/`
