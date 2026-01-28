# Ruby/Rails

## Detection signals
- `Gemfile`
- `Gemfile.lock`
- `config.ru`
- `Rakefile`
- `config/application.rb` (Rails)

## Multi-module signals
- Multiple `Gemfile` in subdirs
- `engines/` directory (Rails engines)
- `gems/` directory (monorepo)

## Pre-generation sources
- `Gemfile` (dependencies)
- `config/database.yml`
- `config/routes.rb` (Rails)
- `.env.example`

## Codebase scan patterns

### Source roots
- `app/`, `lib/`

### Layer/folder patterns (record if present)
`controllers/`, `models/`, `services/`, `jobs/`, `mailers/`, `channels/`, `helpers/`, `concerns/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Rails Controller | `< ApplicationController`, `def index` | rails-controller |
| Rails Model | `< ApplicationRecord`, `has_many`, `belongs_to` | rails-model |
| Rails Migration | `< ActiveRecord::Migration`, `create_table` | rails-migration |
| Service Object | `class *Service`, `def call` | service-object |
| Rails Job | `< ApplicationJob`, `perform_later` | rails-job |
| Mailer | `< ApplicationMailer`, `mail(` | rails-mailer |
| Channel | `< ApplicationCable::Channel` | action-cable |
| Serializer | `< ActiveModel::Serializer`, `attributes` | serializer |
| Concern | `extend ActiveSupport::Concern` | rails-concern |
| Sidekiq Worker | `include Sidekiq::Worker`, `perform_async` | sidekiq-worker |
| Grape API | `Grape::API`, `resource :` | grape-api |
| RSpec Test | `RSpec.describe`, `it "` | rspec-test |
| Factory | `FactoryBot.define`, `factory :` | factory-bot |
| Rake Task | `task :`, `namespace :` | rake-task |

## Mandatory output sections

Include if detected:
- **Controllers**: HTTP endpoints
- **Models**: ActiveRecord associations
- **Services**: business logic
- **Jobs**: background processing
- **Migrations**: database schema

## Command sources
- `Gemfile` scripts
- `Rakefile` tasks
- `bin/rails`, `bin/rake`
- README/docs, CI
- Only include commands present in repo

## Key paths
- `app/controllers/`, `app/models/`
- `app/services/`, `app/jobs/`
- `db/migrate/`
- `spec/`, `test/`
- `lib/`
