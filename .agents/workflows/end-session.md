# End Session Workflow

<!-- Workflow for cleanly concluding an agent session. Usable as a slash command. -->

1. Update `.harness/feature_list.json`—mark features as `passes: true` only if backed by passing test evidence.
2. Update `.harness/progress.md` with current status, tasks completed, next prioritized items, and any new decisions or issues.
3. Verify working directory status with `git status` to ensure no unintended files remain untracked.
4. Commit session changes with an informative commit message summarizing session progress.
