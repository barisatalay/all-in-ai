# Go

## Detection signals
- `go.mod`
- `go.sum`
- `main.go`
- `cmd/`, `internal/`, `pkg/` directories

## Multi-module signals
- `go.work` (workspace)
- Multiple `go.mod` files
- `cmd/*/main.go` (multiple binaries)

## Pre-generation sources
- `go.mod` (dependencies)
- `Makefile` (build commands)
- `config/*.yaml` or `*.toml`

## Codebase scan patterns

### Source roots
- `cmd/`, `internal/`, `pkg/`

### Layer/folder patterns (record if present)
`handler/`, `service/`, `repository/`, `model/`, `middleware/`, `config/`, `util/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| HTTP Handler | `http.Handler`, `http.HandlerFunc`, `gin.Context` | http-handler |
| Gin Route | `gin.Engine`, `r.GET(`, `r.POST(` | gin-route |
| Echo Route | `echo.Echo`, `e.GET(`, `e.POST(` | echo-route |
| Fiber Route | `fiber.App`, `app.Get(`, `app.Post(` | fiber-route |
| gRPC Service | `*.proto`, `pb.*Server` | grpc-service |
| Repository | `type *Repository interface`, `*Repository` | data-repository |
| Service | `type *Service interface`, `*Service` | service-layer |
| GORM Model | `gorm.Model`, `*gorm.DB` | gorm-model |
| sqlx | `sqlx.DB`, `sqlx.NamedExec` | sqlx-usage |
| Migration | `goose`, `golang-migrate` | db-migration |
| Middleware | `func(*Context)`, `middleware.*` | go-middleware |
| Worker | `go func()`, `sync.WaitGroup`, `errgroup` | worker-goroutine |
| Config | `viper`, `envconfig`, `cleanenv` | config-loader |
| Unit Test | `*_test.go`, `func Test*(t *testing.T)` | go-test |
| Mock | `mockgen`, `*_mock.go` | go-mock |

## Mandatory output sections

Include if detected:
- **HTTP handlers**: API endpoints
- **Services**: business logic
- **Repositories**: data access
- **Models**: data structures
- **Middleware**: request interceptors
- **Migrations**: database migrations

## Command sources
- `Makefile` targets
- README/docs, CI
- Common: `go build`, `go test`, `go run`
- Only include commands present in repo

## Key paths
- `cmd/`, `internal/`, `pkg/`
- `api/`, `handler/`
- `migrations/`
- `config/`
