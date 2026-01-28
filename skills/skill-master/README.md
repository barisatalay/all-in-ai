# skill-master

Analyzes codebase patterns to discover missing skills and generate/update
`SKILL.md` files in `.claude/skills/` with real, repo-derived examples.

## Overview
- Goal: keep project skills aligned with actual code patterns
- Scope: discover, generate, and update skills across platforms
- Safeguards: backups, versioning, and write-scope limits

## How the AI discovers and uses this skill
- Triggers when users ask to analyze missing skills, generate skills,
  or sync/update existing skills
- Detection signals: `.claude/skills/` presence and platform build files
- Uses stack references to choose the right pattern detectors

## Audience
- AI operators using skills in Cursor/Claude Code
- Maintainers who evolve skill templates and references

## Capabilities
- Scan codebase for architecture patterns (e.g., ViewModel, Repository)
- Compare detected patterns with existing skills
- Auto-generate `SKILL.md` with real, anonymized examples
- Smart updates with version tracking and source markers

## Modes
### Discover Mode
- Outputs a gap analysis report of detected patterns vs. existing skills

### Generate Mode
- Creates new `SKILL.md` files from detected patterns
- Adds a source marker and version; backs up on first update

## Usage (quick path)
- Ask: “analyze project for missing skills”
- Ask: “generate skills from codebase patterns”
- Ask: “sync/update existing skills”

## Inputs required
- Build/config files for platform detection
- Source roots to extract patterns and conventions
- `.ruler/*.md` rules (if present)

## Output
- Gap analysis report (Discover Mode)
- Generated/updated `SKILL.md` files (Generate Mode)
- Marker with sources and version info

## Safety constraints (must follow)
- Never write outside `.claude/skills/`
- Always backup on first modification
- Preserve user customizations on updates
- Avoid secrets and business-specific details

## References (platform guides)
- `references/android.md` — Android/Gradle
- `references/ios.md` — iOS/Xcode/Swift
- `references/react-web.md` — React web apps
- `references/react-native.md` — React Native
- `references/node.md` — Node tooling
- `references/python.md` — Python
- `references/java.md` — Java/JVM
- `references/dotnet.md` — .NET (C#/F#)
- `references/go.md` — Go
- `references/rust.md` — Rust
- `references/flutter.md` — Dart/Flutter
- `references/ruby.md` — Ruby/Rails
- `references/php.md` — PHP
- `references/elixir.md` — Elixir/Erlang
- `references/cpp.md` — C/C++
- `references/generic.md` — Fallback when no stack matches
