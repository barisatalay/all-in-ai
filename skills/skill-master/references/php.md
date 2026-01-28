# PHP

## Detection signals
- `composer.json`, `composer.lock`
- `public/index.php`
- `artisan` (Laravel)
- `spark` (CodeIgniter 4)
- `bin/console` (Symfony)
- `app/Config/App.php` (CodeIgniter 4)
- `ext-phalcon` in composer.json (Phalcon)
- `phalcon/devtools` (Phalcon)

## Multi-module signals
- `packages/` directory
- Laravel modules (`app/Modules/`)
- CodeIgniter modules (`app/Modules/`, `modules/`)
- Phalcon multi-app (`apps/*/`)
- Multiple `composer.json` in subdirs

## Pre-generation sources
- `composer.json` (dependencies)
- `.env.example` (env vars)
- `config/*.php` (Laravel/Symfony)
- `routes/*.php` (Laravel)
- `app/Config/*` (CodeIgniter 4)
- `apps/*/config/` (Phalcon)

## Codebase scan patterns

### Source roots
- `app/`, `src/`, `apps/`

### Layer/folder patterns (record if present)
`Controllers/`, `Services/`, `Repositories/`, `Models/`, `Entities/`, `Http/`, `Providers/`, `Console/`

### Framework-specific structures

**Laravel** (record if present):
- `app/Http/Controllers`, `app/Models`, `database/migrations`
- `routes/*.php`, `resources/views`

**Symfony** (record if present):
- `src/Controller`, `src/Entity`, `config/packages`, `templates`

**CodeIgniter 4** (record if present):
- `app/Controllers`, `app/Models`, `app/Views`
- `app/Config/Routes.php`, `app/Database/Migrations`

**Phalcon** (record if present):
- `apps/*/controllers/`, `apps/*/Module.php`
- `models/`, `views/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Laravel Controller | `extends Controller`, `public function index` | laravel-controller |
| Laravel Model | `extends Model`, `protected $fillable` | laravel-model |
| Laravel Migration | `extends Migration`, `Schema::create` | laravel-migration |
| Laravel Service | `class *Service`, `app/Services/` | laravel-service |
| Laravel Repository | `*Repository`, `interface *Repository` | laravel-repository |
| Laravel Job | `implements ShouldQueue`, `dispatch(` | laravel-job |
| Laravel Event | `extends Event`, `event(` | laravel-event |
| Symfony Controller | `#[Route]`, `AbstractController` | symfony-controller |
| Symfony Service | `#[AsService]`, `services.yaml` | symfony-service |
| Doctrine Entity | `#[ORM\Entity]`, `#[ORM\Column]` | doctrine-entity |
| Doctrine Migration | `AbstractMigration`, `$this->addSql` | doctrine-migration |
| CI4 Controller | `extends BaseController`, `app/Controllers/` | ci4-controller |
| CI4 Model | `extends Model`, `protected $table` | ci4-model |
| CI4 Migration | `extends Migration`, `$this->forge->` | ci4-migration |
| CI4 Entity | `extends Entity`, `app/Entities/` | ci4-entity |
| Phalcon Controller | `extends Controller`, `Phalcon\Mvc\Controller` | phalcon-controller |
| Phalcon Model | `extends Model`, `Phalcon\Mvc\Model` | phalcon-model |
| Phalcon Migration | `Phalcon\Migrations`, `morphTable` | phalcon-migration |
| API Resource | `extends JsonResource`, `toArray` | api-resource |
| Form Request | `extends FormRequest`, `rules()` | form-request |
| Middleware | `implements Middleware`, `handle(` | php-middleware |
| Unit Test | `extends TestCase`, `test*()`, `PHPUnit` | phpunit-test |
| Feature Test | `extends TestCase`, `$this->get(`, `$this->post(` | feature-test |

## Mandatory output sections

Include if detected:
- **Controllers**: HTTP endpoints
- **Models/Entities**: data layer
- **Services**: business logic
- **Repositories**: data access
- **Migrations**: database changes
- **Jobs/Events**: async processing
- **Business modules**: top modules by size

## Command sources
- `composer.json` scripts
- `php artisan` (Laravel)
- `php spark` (CodeIgniter 4)
- `bin/console` (Symfony)
- `phalcon` devtools commands
- README/docs, CI
- Only include commands present in repo

## Key paths

**Laravel:**
- `app/`, `routes/`, `database/migrations/`
- `resources/views/`, `tests/`

**Symfony:**
- `src/`, `config/`, `templates/`
- `migrations/`, `tests/`

**CodeIgniter 4:**
- `app/Controllers/`, `app/Models/`, `app/Views/`
- `app/Database/Migrations/`, `tests/`

**Phalcon:**
- `apps/*/controllers/`, `apps/*/models/`
- `apps/*/views/`, `migrations/`
