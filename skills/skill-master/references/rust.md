# Rust

## Detection signals
- `Cargo.toml`
- `Cargo.lock`
- `src/main.rs` or `src/lib.rs`
- `target/` directory

## Multi-module signals
- `[workspace]` in `Cargo.toml`
- Multiple `Cargo.toml` in subdirs
- `crates/`, `packages/` directories

## Pre-generation sources
- `Cargo.toml` (dependencies, features)
- `build.rs` (build script)
- `rust-toolchain.toml` (toolchain)

## Codebase scan patterns

### Source roots
- `src/`, `crates/*/src/`

### Layer/folder patterns (record if present)
`handlers/`, `services/`, `models/`, `db/`, `api/`, `utils/`, `error/`, `config/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Axum Handler | `axum::`, `Router`, `async fn handler` | axum-handler |
| Actix Route | `actix_web::`, `#[get]`, `#[post]` | actix-route |
| Rocket Route | `rocket::`, `#[get]`, `#[post]` | rocket-route |
| Service | `impl *Service`, `pub struct *Service` | rust-service |
| Repository | `*Repository`, `trait *Repository` | rust-repository |
| Diesel Model | `diesel::`, `Queryable`, `Insertable` | diesel-model |
| SQLx | `sqlx::`, `FromRow`, `query_as!` | sqlx-model |
| SeaORM | `sea_orm::`, `Entity`, `ActiveModel` | seaorm-entity |
| Error Type | `thiserror`, `anyhow`, `#[derive(Error)]` | error-type |
| CLI | `clap`, `#[derive(Parser)]` | cli-app |
| Async Task | `tokio::spawn`, `async fn` | async-task |
| Trait | `pub trait *`, `impl * for` | rust-trait |
| Unit Test | `#[cfg(test)]`, `#[test]` | rust-test |
| Integration Test | `tests/`, `#[tokio::test]` | integration-test |

## Mandatory output sections

Include if detected:
- **Handlers/routes**: API endpoints
- **Services**: business logic
- **Models/entities**: data structures
- **Error types**: custom errors
- **Migrations**: diesel/sqlx migrations

## Command sources
- `Cargo.toml` scripts/aliases
- `Makefile`, README/docs
- Common: `cargo build`, `cargo test`, `cargo run`
- Only include commands present in repo

## Key paths
- `src/`, `crates/`
- `tests/`
- `migrations/`
- `examples/`
