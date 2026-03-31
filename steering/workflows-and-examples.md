# Workflows & Examples

10 end-to-end workflow examples showing how to combine agents, skills, hooks, and steering files.

## 1. Building a New Feature with TDD

```bash
# Plan the feature
kiro-cli --agent planner
> "I need to add user authentication with JWT tokens"

# Invoke TDD workflow
> /tdd-workflow
# Guides you through: unit tests → integration tests → E2E tests

# Review implementation
> /agent swap code-reviewer

# Security audit for auth code
> /agent swap security-reviewer

# Run quality gate before committing (click hook in Agent Hooks panel)
```

## 2. Code Review Workflow

```bash
kiro-cli --agent code-reviewer
> "Review the changes in src/api/users.ts"

# Comprehensive verification
> /verification-loop
# Runs: build → type check → lint → tests → security scan → diff review
```

## 3. Security-First Development

```bash
> /security-review
# Covers: input validation, auth, secrets, SQL injection, XSS, CSRF

> /agent swap security-reviewer
> "Analyze the API endpoints for vulnerabilities"
```

## 4. Language-Specific Development

```bash
# Go
kiro-cli --agent go-reviewer
> /golang-patterns

# Python
kiro-cli --agent python-reviewer
> /python-patterns

# Steering files auto-load for matching file types
```

## 5. Using Hooks for Automation

- `typecheck-on-edit` — saves .ts/.tsx → checks type errors inline
- `console-log-check` — saves .js/.ts/.tsx → flags console.log
- `tdd-reminder` — creates new .ts/.tsx → reminds to write tests first
- `extract-patterns` — agent stops → suggests patterns for lessons-learned.md
- `session-summary` — agent stops → summarizes work completed

## 6. Manual Context Modes

```bash
> #dev-mode        # Focused implementation
> #review-mode     # Thorough code review
> #research-mode   # Exploration and learning
```

## 7. Database Work

```bash
kiro-cli --agent database-reviewer
> /database-migrations
> /postgres-patterns
```

## 8. Building and Deploying

```bash
kiro-cli --agent build-error-resolver
> /docker-patterns
> /deployment-patterns
```

## 9. Refactoring and Cleanup

```bash
kiro-cli --agent refactor-cleaner
> /verification-loop
```

## 10. Documentation Updates

```bash
kiro-cli --agent doc-updater
# doc-file-warning hook prevents accidental doc changes
```
