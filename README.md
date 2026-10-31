# Agent Project Template

Stack-agnostic template designed for AI-agent-driven development (Google Antigravity, Claude Code, Cursor).

## Why This Template Exists

Working with coding agents across sessions often suffers from context loss, ungrounded code generation, and architectural drift. This template establishes:

- **External Memory**: `.harness/progress.md` and `.harness/feature_list.json` maintain continuity across stateless agent sessions.
- **Spec-Driven Process**: Prompts the agent to write and verify specs before writing code, reducing hallucinations.
- **Consistent Workflows**: Standardized step-by-step procedures for each phase (session start, feature implementation, verification, review, session end).
- **Quality & Boundary Enforcement**: Text rules in `.agents/rules/` guide agent behavior, while `.archrules/` and `.github/workflows/ci.yml` provide hard enforcement. *Note: Text instructions reduce mistakes, but actual boundary enforcement requires configuring stack-specific lint/arch tools and CI checks.*

## Getting Started Checklist

1. [ ] **Product Definition**: Fill out `docs/product.md` with problem, users, and v1 scope (WHAT and WHY).
2. [ ] **Architecture**: Fill out `docs/architecture.md` with stack, layers, boundaries, and dependencies.
3. [ ] **Agent Instructions**: Fill out `AGENTS.md` with project one-liner, core commands, and do-not rules.
4. [ ] **Domain Terms**: Define key vocabulary in `docs/glossary.md`.
5. [ ] **Rules & Boundaries**: Customize `.agents/rules/` and set up boundary enforcement in `.archrules/`.
6. [ ] **CI & Tooling**: Configure `.github/workflows/ci.yml` and `.harness/init.sh`.
7. [ ] **First Feature**: Ask the agent to use workflow `new-feature` to draft the first spec in `specs/` and seed `.harness/feature_list.json`.
