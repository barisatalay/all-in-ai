# .NET (C#/F#)

## Detection signals
- `*.csproj`, `*.fsproj`
- `*.sln`
- `global.json`
- `appsettings.json`
- `Program.cs`, `Startup.cs`

## Multi-module signals
- Multiple `*.csproj` files
- Solution with multiple projects
- `src/`, `tests/` directories with projects

## Pre-generation sources
- `*.csproj` (dependencies, SDK)
- `*.sln` (project structure)
- `appsettings.json` (config)
- `global.json` (SDK version)

## Codebase scan patterns

### Source roots
- `src/`, `*/` (per project)

### Layer/folder patterns (record if present)
`Controllers/`, `Services/`, `Repositories/`, `Models/`, `Entities/`, `DTOs/`, `Middleware/`, `Extensions/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Controller | `[ApiController]`, `ControllerBase`, `[HttpGet]` | aspnet-controller |
| Service | `I*Service`, `class *Service` | dotnet-service |
| Repository | `I*Repository`, `class *Repository` | dotnet-repository |
| Entity | `class *Entity`, `[Table]`, `[Key]` | ef-entity |
| DTO | `class *Dto`, `class *Request`, `class *Response` | dto-pattern |
| DbContext | `: DbContext`, `DbSet<` | ef-dbcontext |
| Middleware | `IMiddleware`, `RequestDelegate` | aspnet-middleware |
| Background Service | `BackgroundService`, `IHostedService` | background-service |
| MediatR Handler | `IRequestHandler<`, `INotificationHandler<` | mediatr-handler |
| SignalR Hub | `: Hub`, `[HubName]` | signalr-hub |
| Minimal API | `app.MapGet(`, `app.MapPost(` | minimal-api |
| gRPC Service | `*.proto`, `: *Base` | grpc-service |
| EF Migration | `Migrations/`, `AddMigration` | ef-migration |
| Unit Test | `[Fact]`, `[Theory]`, `xUnit` | xunit-test |
| Integration Test | `WebApplicationFactory`, `IClassFixture` | integration-test |

## Mandatory output sections

Include if detected:
- **Controllers**: API endpoints
- **Services**: business logic
- **Repositories**: data access (EF Core)
- **Entities/DTOs**: data models
- **Middleware**: request pipeline
- **Background services**: hosted services

## Command sources
- `*.csproj` targets
- README/docs, CI
- Common: `dotnet build`, `dotnet test`, `dotnet run`
- Only include commands present in repo

## Key paths
- `src/*/`, project directories
- `tests/`
- `Migrations/`
- `Properties/`
