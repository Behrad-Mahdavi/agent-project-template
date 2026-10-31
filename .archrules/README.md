# Architecture Boundary Rules

<!-- Configuration placeholder for import boundaries and architectural rule enforcement. -->

## Boundary Tooling
Place stack-specific architecture boundary configurations in this directory, for example:
- **TypeScript / JavaScript**: `.dependency-cruiser.js` or `eslint-plugin-import`
- **Python**: `import-linter` or `tach`
- **JVM**: `ArchUnit` configuration
- **Go**: `depguard` or `go-arch-lint`

Configure the corresponding command in `AGENTS.md` under `Commands -> Arch-Check`.
