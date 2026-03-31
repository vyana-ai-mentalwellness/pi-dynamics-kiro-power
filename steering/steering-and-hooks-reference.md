# Steering Files & Hooks Reference

## Steering Files (16 total)

Steering files provide always-on rules and context that shape how the agent works with your code.

### Auto-Loaded (always active)

| File | Description |
|------|-------------|
| `coding-style.md` | Core coding style rules: immutability, file organization, error handling, code quality standards. |
| `security.md` | Security best practices: mandatory checks, secret management, security response protocol. |
| `testing.md` | Testing requirements: 80% coverage minimum, TDD workflow, test types (unit, integration, E2E). |
| `development-workflow.md` | Development process, PR workflow, and collaboration patterns. |
| `git-workflow.md` | Git commit conventions, branching strategies, version control best practices. |
| `patterns.md` | Common design patterns and architectural principles. |
| `performance.md` | Performance optimization guidelines and profiling strategies. |
| `lessons-learned.md` | Project-specific patterns and learnings. Edit to capture your team's conventions. |

### File-Match (loaded when editing matching files)

| File | Pattern | Description |
|------|---------|-------------|
| `typescript-patterns.md` | `*.ts, *.tsx` | TypeScript-specific patterns, type safety, best practices. |
| `python-patterns.md` | `*.py` | Python-specific patterns, type hints, best practices. |
| `golang-patterns.md` | `*.go` | Go-specific patterns, concurrency, best practices. |
| `swift-patterns.md` | `*.swift` | Swift-specific patterns and best practices. |

### Manual (invoked with `#` in chat)

| File | Invoke With | Description |
|------|-------------|-------------|
| `dev-mode.md` | `#dev-mode` | Development context mode for focused implementation. |
| `review-mode.md` | `#review-mode` | Code review context mode for thorough reviews. |
| `research-mode.md` | `#research-mode` | Research context mode for exploration and learning. |

### Creating Custom Steering Files

Add a markdown file to `.kiro/steering/` with YAML frontmatter:

```yaml
---
inclusion: auto        # auto | fileMatch | manual
description: Brief explanation
fileMatchPattern: "*.ts"  # required if inclusion is fileMatch
---

Your rules here...
```

---

## IDE Hooks (10 total)

Hooks automate agent actions based on IDE events. Toggle on/off in the Agent Hooks panel.

| Hook | Trigger | Action | Description |
|------|---------|--------|-------------|
| `quality-gate` | `userTriggered` | `runCommand` | Runs build, type check, lint, and tests via `quality-gate.sh`. |
| `typecheck-on-edit` | `fileEdited` (*.ts, *.tsx) | `askAgent` | Checks for type errors when TypeScript files are edited. |
| `console-log-check` | `fileEdited` (*.js, *.ts, *.tsx) | `askAgent` | Flags console.log statements to prevent debug code leaking. |
| `tdd-reminder` | `fileCreated` (*.ts, *.tsx) | `askAgent` | Reminds to write tests first when creating new files. |
| `git-push-review` | `preToolUse` (shell) | `askAgent` | Reviews git push commands before execution. |
| `code-review-on-write` | `postToolUse` (write) | `askAgent` | Triggers code review after file modifications. |
| `auto-format` | `fileEdited` (*.ts, *.tsx, *.js) | `askAgent` | Checks formatting and fixes inline without spawning a terminal. |
| `extract-patterns` | `agentStop` | `askAgent` | Suggests patterns to add to lessons-learned.md after work completes. |
| `session-summary` | `agentStop` | `askAgent` | Provides a summary of work completed in the session. |
| `doc-file-warning` | `preToolUse` (write) | `askAgent` | Warns before modifying documentation files. |

### Scripts Used by Hooks

| Script | Description |
|--------|-------------|
| `quality-gate.sh` | Detects package manager and runs build, type check, lint, tests. Skips gracefully if tools missing. |
| `format.sh` | Detects formatter (biome or prettier) and auto-formats the specified file. |
