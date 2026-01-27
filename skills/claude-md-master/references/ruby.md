# Ruby / Rails

## Detection signals
- `Gemfile`, `Gemfile.lock`
- `Rakefile`
- `config.ru`
- `bin/rails` or `bin/rake`
- `config/application.rb`
- `config/routes.rb`

## Multi-module signals
- Multiple `Gemfile` or `.gemspec` files in subdirs
- `gems/`, `packages/`, or `engines/` with separate gem specs
- Multiple Rails apps under `apps/` (each with `config/application.rb`)

## Before generating, analyze these sources
- `Gemfile`, `Gemfile.lock`, and any `.gemspec`
- `config/application.rb`, `config/routes.rb`
- `Rakefile` / `bin/rails` (if present)
- `engines/`, `gems/`, `apps/` (if multi-app/engine setup)

## Codebase scan (Ruby/Rails-specific)
- Source roots: `app/`, `lib/`, `engines/`, `gems/`
- Rails layers (record only if present):
  `app/models`, `app/controllers`, `app/views`, `app/jobs`, `app/services`
- Config and initializers (record only if present):
  `config/routes.rb`, `config/application.rb`, `config/initializers/`
- ActiveRecord/migrations (record only if present):
  `db/migrate`, `ActiveRecord::Base`
- Tests (record only if present): `spec/`, `test/`

## Mandatory output (Ruby module CLAUDE.md)
Include these if detected (list actual names found):
- **Controllers**: list controller classes
- **Models**: list ActiveRecord models
- **Services**: list service objects
- **Jobs**: list background job classes
- **Routes**: summarize key route namespaces
- **Migrations**: mention db/migrate count
- **Engines**: list mounted engines (if any)

## Command sources
- README/docs or CI invoking `bundle`, `rails`, `rake`
- `Rakefile` tasks
- `bundle exec` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `app/`, `config/`, `db/`
- `app/controllers/`, `app/models/`, `app/views/`
- `spec/` or `test/`
