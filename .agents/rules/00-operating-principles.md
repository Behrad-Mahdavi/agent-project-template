---
trigger: always_on
description: Core operating principles and session workflow (always follow)
---

# Operating Principles (always follow)

You work in discrete sessions and have NO memory between them. Files in this repo are your memory. Never rely on chat history or assumptions; rely on the files below.

## Where things live
- `docs/product.md`: what and why. `docs/architecture.md`: structure and dependency rules. `docs/glossary.md`: domain terms (use these exact names in code).
- `docs/decisions/`: past decisions (ADRs). Read before proposing alternatives.
- `specs/<feature>/`: requirements, design, tasks for each feature.
- `.harness/feature_list.json`: the list of features and whether each passes. `.harness/progress.md`: what happened and what is next.

## Start of every session
1. Read `.harness/progress.md`, `.harness/feature_list.json`, and recent `git log`.
2. Run `.harness/init.sh` and confirm the app and tests work before changing anything. If something is already broken, fix or report it first.
3. Pick exactly ONE task (one feature or one task from a spec). Do not start a second.

## How to build anything
1. No spec, no code. If the feature has no `specs/<feature>/`, write requirements, design, and tasks first, then STOP and ask the human to approve before coding.
2. Plan before editing: list the files you will touch and the existing module or pattern you will follow. Search the codebase for existing code first. Reuse and extend; do not duplicate.
3. Write tests first (or alongside), based on the acceptance criteria.
4. Implement in small steps. Keep each change small and commit often with clear messages.
5. Verify (see below) before claiming anything is done.

## Architecture rules
- `docs/architecture.md` is the source of truth. Respect the layers and allowed dependencies. Never import across a forbidden boundary or bypass a module's public API.
- If the architecture seems wrong for the task, do NOT work around it. Stop, explain the conflict, and propose an ADR for the human to decide.
- Do not add new dependencies, libraries, folders at the top level, or new patterns without asking.

## Definition of done
A feature is done only when ALL are true: tests pass, lint and typecheck pass, the architecture check passes, and (for UI) you ran the app and checked it. Only then set `passes: true` in `feature_list.json`. Never change a feature's description or delete features to make it pass. Show the evidence (command output or what you observed).

## End of every session
1. Update `.harness/feature_list.json` (only `passes`, only with evidence).
2. Update `.harness/progress.md`: current status, what you did, what is next, known issues, decisions made.
3. Commit. Leave the repo in a clean, working state. Never leave half-implemented work undocumented.

## Be honest
- Do not say "done" or "fixed" unless you verified it. Report failures and uncertainty plainly.
- If requirements are ambiguous, ask one focused question instead of guessing.
- If you are stuck after two failed attempts at the same problem, stop, summarize what you tried, and ask for direction.

## Keep context clean
- Read only what the task needs. Prefer searching to reading whole directories.
- Keep command output short; summarize long logs instead of pasting them.
- Write important decisions into files, not into chat.

---
Slash workflows in `.agents/workflows/` implement these steps.
