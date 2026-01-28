# Generic/Unknown Stack

Fallback reference when no specific platform is detected.

## Detection signals
- No specific build/config files found
- Mixed technology stack
- Documentation-only repository

## Multi-module signals
- Multiple directories with separate concerns
- `packages/`, `modules/`, `libs/` directories
- Monorepo structure without specific tooling

## Pre-generation sources
- `README.md` (project overview)
- `docs/*` (documentation)
- `.env.example` (environment vars)
- `docker-compose.yml` (services)
- CI files (`.github/workflows/`, etc.)

## Codebase scan patterns

### Source roots
- `src/`, `lib/`, `app/`

### Layer/folder patterns (record if present)
`api/`, `core/`, `utils/`, `services/`, `models/`, `config/`, `scripts/`

### Generic pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Entry Point | `main.*`, `index.*`, `app.*` | entry-point |
| Config | `config.*`, `settings.*` | config-file |
| API Client | `api/`, `client/`, HTTP calls | api-client |
| Model | `model/`, `types/`, data structures | data-model |
| Service | `service/`, business logic | service-layer |
| Utility | `utils/`, `helpers/`, `common/` | utility-module |
| Test | `test/`, `tests/`, `*_test.*`, `*.test.*` | test-file |
| Script | `scripts/`, `bin/` | script-file |
| Documentation | `docs/`, `*.md` | documentation |

## Mandatory output sections

Include if detected:
- **Project structure**: main directories
- **Entry points**: main files
- **Configuration**: config files
- **Dependencies**: any package manager
- **Build/Run commands**: from README/scripts

## Command sources
- `README.md` (look for code blocks)
- `Makefile`, `Taskfile.yml`
- `scripts/` directory
- CI workflows
- Only include commands present in repo

## Key paths
- `src/`, `lib/`
- `docs/`
- `scripts/`
- `config/`

## Notes

When using this generic reference:
1. Scan for any recognizable patterns
2. Document actual project structure found
3. Extract commands from README if available
4. Note any technologies mentioned in docs
5. Keep output minimal and factual
