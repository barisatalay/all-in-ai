# Rust

## Detection signals
- `Cargo.toml`, `Cargo.lock`
- `rust-toolchain.toml`
- `src/main.rs`, `src/lib.rs`
- Workspace members in `Cargo.toml`, `crates/`

## Multi-module signals
- `[workspace]` with `members` in `Cargo.toml`
- Multiple `Cargo.toml` under `crates/` or `apps/`

## Before generating, analyze these sources
- Root `Cargo.toml`, `Cargo.lock`
- `rust-toolchain.toml` (if present)
- Workspace `Cargo.toml` in `crates/` or `apps/`
- `src/main.rs` / `src/lib.rs`

## Codebase scan (Rust-specific)
- Source roots: `src/`, `crates/`, `tests/`, `examples/`
- Module layout (record only if present):
  `lib.rs`, `main.rs`, `mod.rs`, `src/bin/*`
- Serde usage (record only if present):
  `#[derive(Serialize, Deserialize)]`
- Async/runtime (record only if present):
  `tokio`, `async-std`
- Web frameworks (record only if present):
  `axum`, `actix-web`, `warp`

## Mandatory output (Rust module CLAUDE.md)
Include these if detected (list actual names found):
- **Crates**: list workspace crates with purpose
- **Binaries**: list `src/bin/*` or `[[bin]]` targets
- **Modules**: list top-level `mod` declarations
- **Handlers/routes**: list web handler modules (if web app)
- **Models**: list domain model modules
- **Config**: list config loading modules

## Command sources
- README/docs or CI
- Repo scripts invoking `cargo`
- `cargo test`, `cargo run` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `src/`, `crates/`
- `tests/`, `examples/`, `benches/`
