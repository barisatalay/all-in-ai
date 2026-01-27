# PHP

## Detection signals
- `composer.json`, `composer.lock`
- `public/index.php`
- `artisan`, `spark`, `bin/console` (framework entry points)
- `phpunit.xml`, `phpstan.neon`, `phpstan.neon.dist`, `psalm.xml`
- `config/app.php`
- `routes/web.php`, `routes/api.php`
- `config/packages/` (Symfony)
- `app/Config/` (CI4)
- `ext-phalcon` in composer.json (Phalcon)
- `phalcon/ide-stubs`, `phalcon/devtools` (Phalcon)

## Multi-module signals
- `modules/` or `app/Modules/` (HMVC style)
- `app/Config/Modules.php`, `app/Config/Autoload.php` (CI4)
- Multiple PSR-4 roots in `composer.json`
- Multiple `composer.json` under `packages/` or `apps/`
- `apps/` with subdirectories containing `Module.php` or `controllers/`

## Before generating, analyze these sources
- `composer.json`, `composer.lock`
- `config/` and `routes/` (framework configs)
- `app/Config/*` (CI4)
- `modules/` or `app/Modules/` (if HMVC)
- `phpunit.xml`, `phpstan.neon*`, `psalm.xml` (if present)
- `bin/worker.php`, `bin/console.php` (CLI entry points)

## Codebase scan (PHP-specific)
- Source roots: `app/`, `src/`, `modules/`, `packages/`, `apps/`
- Laravel structure (record only if present):
  `app/Http/Controllers`, `app/Models`, `database/migrations`,
  `routes/*.php`, `resources/views`
- Symfony structure (record only if present):
  `src/Controller`, `src/Entity`, `config/packages`, `templates`
- CodeIgniter structure (record only if present):
  `app/Controllers`, `app/Models`, `app/Views`, `app/Config/Routes.php`,
  `app/Database/Migrations`
- Phalcon structure (record only if present):
  `apps/*/controllers/`, `apps/*/Module.php`, `models/`
- Attributes/annotations (record only if present):
  `#[Route]`, `#[Entity]`, `#[ORM\\Column]`

## Business module discovery
Scan these paths based on detected framework:
- Laravel: `app/Services/`, `app/Domains/`, `app/Modules/`, `packages/`
- Symfony: `src/` top-level directories
- CodeIgniter: `app/Modules/`, `modules/`
- Phalcon: `src/`, `apps/*/`
- Generic: `src/`, `lib/`

For each path:
- List top 5-10 largest modules by file count
- For each significant module (>5 files), note its purpose if inferable from name
- Identify layered patterns if present: `*/Repository/`, `*/Service/`, `*/Controller/`, `*/Action/`

## Module-level CLAUDE.md signals
Scan these paths for significant modules (framework-specific):
- `src/` - Symfony, Phalcon, custom frameworks
- `app/Services/`, `app/Domains/` - Laravel domain-driven
- `app/Modules/`, `modules/` - Laravel/CI4 HMVC
- `packages/` - Laravel internal packages
- `apps/` - Phalcon multi-app

Create `<path>/<Module>/CLAUDE.md` when:
- Threshold: module has >5 files OR has own `README.md`
- Skip utility dirs: `Helper/`, `Exception/`, `Trait/`, `Contract/`, `Interface/`, `Constants/`, `Support/`
- Layered structure not required; provide module info regardless of architecture

### Module CLAUDE.md content (max 120 lines)
- Purpose: 1-2 sentence module description
- Structure: list subdirectories (Service/, Repository/, etc.)
- Key classes: main service/manager/action classes
- Dependencies: other modules this depends on (via use statements)
- Entry points: main public interfaces/facades
- Framework-specific: ServiceProvider (Laravel), Module.php (Phalcon/CI4)

## Worker/Job detection
- `bin/worker.php` or similar worker entry points
- `*/Job/`, `*/Jobs/`, `*/Worker/` directories
- Queue config files (`queue.php`, `rabbitmq.php`, `amqp.php`)
- List job classes if present

## API versioning detection
- `routes_v*.php` or `routes/v*/` patterns
- `controllers/v*/` directory structure
- Note current/active API version from route files or config

## Mandatory output (PHP module CLAUDE.md)
Include these if detected (list actual names found):
- **Controllers**: list controller directories/classes
- **Models**: list model/entity classes or directory
- **Services**: list service classes or directory
- **Repositories**: list repository classes or directory
- **Routes**: list route files and versioning pattern
- **Migrations**: mention migrations dir and file count
- **Middleware**: list middleware classes
- **Views/templates**: mention view engine and layout
- **Workers/Jobs**: list job classes if present
- **Business modules**: list top modules from detected source paths by size

## Command sources
- `composer.json` scripts
- README/docs or CI
- `php artisan`, `bin/console` usage in docs/scripts
- `bin/worker.php` commands
- Only include commands present in repo

## Key paths to mention (only if present)
- `app/`, `src/`, `apps/`
- `public/`, `routes/`, `config/`, `database/`
- `app/Http/`, `resources/`, `storage/` (Laravel)
- `templates/` (Symfony)
- `app/Controllers/`, `app/Views/` (CI4)
- `apps/*/controllers/`, `models/` (Phalcon)
- `tests/`, `tests/acceptance/`, `tests/unit/`
