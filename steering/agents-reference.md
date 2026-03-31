# Agents Reference

Pi Dynamics includes 16 specialized agents. Each agent is available in two formats:
- **IDE (Markdown)** — `.md` files for Kiro IDE automatic selection or explicit invocation
- **CLI (JSON)** — `.json` files for `kiro-cli` via `/agent swap`

## Agent Catalog

| Agent | Description |
|-------|-------------|
| `planner` | Expert planning specialist for complex features and refactoring. Read-only tools for safe analysis. |
| `code-reviewer` | Senior code reviewer ensuring quality and security. Reviews for CRITICAL security issues, code quality, React/Next.js patterns, and performance. |
| `tdd-guide` | Test-Driven Development specialist enforcing write-tests-first methodology. Ensures 80%+ test coverage. |
| `security-reviewer` | Security vulnerability detection and remediation. Flags secrets, SSRF, injection, unsafe crypto, and OWASP Top 10. |
| `architect` | Software architecture specialist for system design, scalability, and technical decisions. Read-only tools. |
| `build-error-resolver` | Build and TypeScript error resolution. Fixes build/type errors with minimal diffs, no architectural changes. |
| `doc-updater` | Documentation and codemap specialist. Updates codemaps, READMEs, and generates docs. |
| `refactor-cleaner` | Dead code cleanup and consolidation. Removes unused code, duplicates, and refactors safely. |
| `go-reviewer` | Go code review specialist. Reviews for idiomatic patterns, error handling, concurrency, and performance. |
| `go-build-resolver` | Go build error resolution. Fixes Go compilation errors, dependency issues, and build problems. |
| `python-reviewer` | Python code review specialist. Reviews for PEP 8, type hints, error handling, and best practices. |
| `database-reviewer` | Database and SQL specialist. Reviews schema design, queries, migrations, and database security. |
| `e2e-runner` | End-to-end testing specialist. Creates and maintains E2E tests using Playwright or Cypress. |
| `harness-optimizer` | Test harness optimization. Improves test performance, reliability, and maintainability. |
| `loop-operator` | Verification loop operator. Runs comprehensive checks and iterates until all pass. |
| `chief-of-staff` | Executive assistant for project management, coordination, and strategic planning. |

## Usage

### In Kiro IDE
- Agents are available via `/` menu or automatic selection based on context
- Kiro's native Spec session has built-in planner, designer, and architect capabilities

### In CLI
```bash
kiro-cli --agent planner
# Swap mid-session:
> /agent swap code-reviewer
```

## File Locations

After installation:
- IDE agents: `.kiro/agents/*.md`
- CLI agents: `.kiro/agents/*.json`
