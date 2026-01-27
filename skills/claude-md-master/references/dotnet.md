# .NET (C# / F#)

## Detection signals
- `*.sln`
- `*.csproj`, `*.fsproj`, `*.vbproj`
- `global.json`
- `Directory.Build.props`, `Directory.Build.targets`
- `nuget.config`
- `Program.cs`
- `Startup.cs`
- `appsettings*.json`

## Multi-module signals
- `*.sln` with multiple project entries
- Multiple `*.*proj` files under `src/` and `tests/`
- `Directory.Build.*` managing shared settings across projects

## Before generating, analyze these sources
- `*.sln`, `*.csproj` / `*.fsproj` / `*.vbproj`
- `Directory.Build.props`, `Directory.Build.targets`
- `global.json`, `nuget.config`
- `Program.cs` / `Startup.cs`
- `appsettings*.json`

## Codebase scan (.NET-specific)
- Source roots: `src/`, `tests/`, project folders with `*.csproj`
- Layer folders (record only if present):
  `Controllers`, `Services`, `Repositories`, `Domain`, `Infrastructure`
- ASP.NET attributes (record only if present):
  `[ApiController]`, `[Route]`, `[HttpGet]`, `[HttpPost]`, `[Authorize]`
- EF Core usage (record only if present):
  `DbContext`, `Migrations`, `[Key]`, `[Table]`

## Mandatory output (.NET module CLAUDE.md)
Include these if detected (list actual names found):
- **Controllers**: list `[ApiController]` classes
- **Services**: list service classes
- **Repositories**: list repository classes
- **Entities**: list EF Core entity classes
- **DbContext**: list database context classes
- **Middleware**: list custom middleware
- **Configuration**: list config sections or options classes

## Command sources
- README/docs or CI invoking `dotnet`
- Repo scripts like `build.ps1`, `build.sh`
- `dotnet run`, `dotnet test` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `src/`, `tests/`
- `appsettings*.json`
- `Controllers/`, `Models/`, `Views/`, `wwwroot/`
