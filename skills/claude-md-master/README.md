# claude-md-master

Master skill for the CLAUDE.md lifecycle: create, update, and improve files
using repo-verified data, with multi-module support and stack-specific rules.

## Overview
- Goal: produce accurate, concise `CLAUDE.md` files from real repo data
- Scope: root + meaningful modules, with stack-specific detection
- Safeguards: no secrets, no filler, explicit approval before writes

## How the AI discovers and uses this skill
- Discovery: the tool learns this skill because it exists in the
  repo skills catalog (installed/available in the environment)
- Automatic use: when a request includes "create/update/improve
  CLAUDE.md", the tool selects this skill as the best match
- Manual use: the operator can explicitly invoke `/claude-md-master`
  to force this workflow
- Run behavior: it scans repo docs/config/source, proposes changes,
  and waits for explicit approval before writing files

## Audience
- AI operators using skills in Cursor/Claude Code
- Maintainers who evolve the rules and references

## What it does
- Generates or updates `CLAUDE.md` with verified, repo-derived content
- Enforces strict safety and concision rules (no secrets, no filler)
- Detects multi-module repos and produces module-level `CLAUDE.md`
- Uses stack-specific references to capture accurate patterns

## When to use
- A user asks to create, improve, update, or standardize `CLAUDE.md`
- A repo needs consistent, verified guidance for AI workflows

## Inputs required (must be analyzed)
- Repo docs: `README.md`, `docs/*` (if present)
- Build/config files relevant to detected stack(s)
- Runtime/config: `Dockerfile`, `.env.example`, `config/*` (if present)
- CI: `.github/workflows/*`, `.gitlab-ci.yml`, `.circleci/*` (if present)
- Source roots to extract real structure, types, annotations, naming

## Output
- Root `CLAUDE.md` (always)
- Module `CLAUDE.md` for meaningful modules (build config + `src/`)
- Concise update report listing created/updated files and backups

## Workflow (high level)
1. Locate existing `CLAUDE.md` variants and detect first vs. subsequent run
2. Identify stack(s) and multi-module structure
3. Read relevant docs/configs/CI for real commands and workflow
4. Scan source roots for structure, key types, annotations, patterns
5. Generate root + module files, avoiding duplication via `@/CLAUDE.md`
6. Request explicit approval before applying updates
7. Apply changes and print the update report

## Core rules and constraints
- Only include info verified in repo; never add secrets
- Keep concise: root <= 200 lines, module <= 120 lines
- Commands must be real and copy-pasteable from repo docs/scripts/CI
- Skip empty sections; avoid generic guidance
- Never modify `.claude.local.md`
- Avoid code examples in Do/Do Not sections

## Multi-module policy (summary)
- Always create root `CLAUDE.md`
- Create module-level files only for meaningful modules
- Skip tooling-only dirs (e.g., `buildSrc`, `gradle`, `scripts`, `tools`)
- Business modules get their own file when >5 files or own README

## References (stack-specific guides)
Each reference defines detection signals, pre-gen sources, codebase scan
targets, mandatory output items, command sources, and key paths.

- `references/android.md` — Android/Gradle
- `references/ios.md` — iOS/Xcode/Swift
- `references/react-web.md` — React web apps
- `references/react-native.md` — React Native
- `references/node.md` — Node tooling (generic)
- `references/python.md` — Python
- `references/java.md` — Java/JVM
- `references/dotnet.md` — .NET (C#/F#)
- `references/go.md` — Go
- `references/rust.md` — Rust
- `references/flutter.md` — Dart/Flutter
- `references/ruby.md` — Ruby/Rails
- `references/php.md` — PHP (Laravel/Symfony/CI/Phalcon)
- `references/elixir.md` — Elixir/Erlang
- `references/cpp.md` — C/C++
- `references/generic.md` — Fallback when no stack matches

## Extending the skill
- Add a new `references/<stack>.md` using the same template
- Keep detection signals and mandatory outputs specific and verifiable
- Do not introduce unverified commands or generic advice

## Quality checklist
- Every rule references actual types/paths from the repo
- No placeholders remain
- No secrets included
- Commands are real and copy-pasteable
- Report-first rule respected; references are one level deep
