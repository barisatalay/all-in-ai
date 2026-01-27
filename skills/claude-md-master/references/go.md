# Go

## Detection signals
- `go.mod`, `go.sum`, `go.work`
- `cmd/`, `internal/`
- `main.go`
- `magefile.go`
- `Taskfile.yml`

## Multi-module signals
- `go.work` with multiple module paths
- Multiple `go.mod` files in subdirs
- `apps/` or `services/` each with its own `go.mod`

## Before generating, analyze these sources
- `go.work`, `go.mod`, `go.sum`
- `cmd/`, `internal/`, `pkg/` layout
- `Makefile`, `Taskfile.yml`, `magefile.go` (if present)

## Codebase scan (Go-specific)
- Source roots: `cmd/`, `internal/`, `pkg/`, `api/`
- Layer folders (record only if present):
  `handler`, `service`, `repository`, `store`, `config`
- Framework markers (record only if present):
  `gin`, `echo`, `fiber`, `chi` imports
- Entry points (record only if present):
  `cmd/*/main.go`, `main.go`

## Mandatory output (Go module CLAUDE.md)
Include these if detected (list actual names found):
- **Commands**: list binaries under `cmd/`
- **Handlers**: list HTTP handler packages
- **Services**: list service packages
- **Repositories**: list repository or store packages
- **Models**: list domain model packages
- **Config**: list config loading packages

## Command sources
- README/docs or CI
- `Makefile`, `Taskfile.yml`, or repo scripts invoking Go tools
- `go test ./...`, `go run` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `cmd/`, `internal/`, `pkg/`, `api/`
- `tests/` or `*_test.go` layout
