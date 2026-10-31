# Review Workflow

<!-- Workflow for independent code review. Usable as a slash command. -->

1. Inspect the complete working diff using `git diff HEAD` (or compare against the base branch).
2. Evaluate the diff against the corresponding spec in `specs/` and boundary rules in `docs/architecture.md`.
3. Check for architectural violations, leaked abstractions, unhandled edge cases, and missing tests.
4. List all identified issues grouped by severity (Critical, Warning, Suggestion).
5. Do not edit code or apply fixes during this review step.
