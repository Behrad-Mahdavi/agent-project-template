# New Feature Workflow

<!-- Workflow for developing a new feature from specification to commit. Usable as a slash command. -->

1. Create a new specification directory under `specs/<feature-name>/` by copying `specs/_template/` and filling out `requirements.md` and `design.md`.
2. Break down the design into small, verifiable items in `specs/<feature-name>/tasks.md` and present the plan to the human developer.
3. Wait for human approval of the specification and task plan before modifying any code.
4. Write failing tests first that define and assert the expected feature behavior.
5. Implement minimal code to satisfy the tests while respecting architecture boundaries.
6. Run the verification workflow (`.agents/workflows/verify.md`) to confirm all checks pass.
7. Commit changes with a clean, conventional commit message referencing the feature.
