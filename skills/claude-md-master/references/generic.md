# Generic / Unknown Stack

Use this reference when no specific stack reference matches.

## Detection signals (common patterns)
- `README.md`, `CONTRIBUTING.md`
- `Makefile`, `Taskfile.yml`, `justfile`
- `Dockerfile`, `docker-compose.yml`
- `.env.example`, `config/`
- CI files: `.github/workflows/`, `.gitlab-ci.yml`, `.circleci/`

## Before generating, analyze these sources
- `README.md` - project overview, setup instructions, commands
- Build/package files in root (any recognizable format)
- `Makefile`, `Taskfile.yml`, `justfile`, `scripts/` (if present)
- CI/CD configs for build/test commands
- `Dockerfile` for runtime info

## Codebase scan (generic)
- Identify source root: `src/`, `lib/`, `app/`, `pkg/`, or root
- Layer folders (record only if present):
  `controllers`, `services`, `models`, `handlers`, `utils`, `config`
- Entry points: `main.*`, `index.*`, `app.*`, `server.*`
- Test location: `tests/`, `test/`, `spec/`, `__tests__/`, or co-located

## Mandatory output (generic CLAUDE.md)
Include these if detected (list actual names found):
- **Entry points**: main files, startup scripts
- **Source structure**: top-level dirs under source root
- **Config files**: environment, settings, secrets template
- **Build system**: detected build tool and config location
- **Test setup**: test framework and run command

## Command sources
- README setup/usage sections
- `Makefile` targets, `Taskfile.yml` tasks, `justfile` recipes
- CI workflow steps (build, test, lint)
- `scripts/` directory
- Only include commands present in repo

## Key paths to mention (only if present)
- Source root and its top-level structure
- Config/environment files
- Test directory
- Documentation location
- Build output directory
