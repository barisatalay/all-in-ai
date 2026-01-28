# all-in-ai

A curated collection of AI agent skills covering codebase analysis,
skill generation, and CLAUDE.md lifecycle workflows.

## Overview
- Focus: repeatable, repo-verified documentation and skill generation
- Scope: multi-platform detection with stack-specific references
- Format: each skill is a self-contained folder with `SKILL.md`

## Skills
| Skill | Purpose | When to use |
| --- | --- | --- |
| `claude-md-master` | Create/update `CLAUDE.md` files with repo-verified content | When asked to create, improve, or standardize `CLAUDE.md` |
| `skill-master` | Discover patterns and generate/update `SKILL.md` files | When asked to analyze missing skills or sync skills |

## Usage
- Choose a skill under `skills/`
- Read its `README.md` and `SKILL.md` for triggers, inputs, and rules
- Apply in your agent environment according to that skill's instructions

## Repository structure
- `skills/<skill-name>/SKILL.md` (required)
- `skills/<skill-name>/README.md` (usage and context)
- `skills/<skill-name>/references/` (stack-specific guides)

## Supported stacks (via references)
Android, iOS, React Web, React Native, Node, Python, Java/JVM, .NET, Go, Rust,
Flutter, Ruby, PHP, Elixir, C/C++, and a generic fallback.

## License
MIT. See `LICENSE`.