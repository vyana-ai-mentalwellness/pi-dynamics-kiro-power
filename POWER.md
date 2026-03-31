---
name: "pi-dynamics"
displayName: "Pi Dynamics — Complete developer tool kit for Kiro"
description: "Complete developer toolkit to Kiro. Includes 16 specialized agents, 18 skills, 16 steering files, 10 IDE hooks, and shell scripts for TDD, code review, security, and multi-language development workflows."
keywords: ["ecc", "everything-claude-code", "agents", "skills", "hooks", "steering", "tdd", "code-review", "security", "pi-dynamics"]
author: "Abhilash M"
---

# Pi Dynamics — Everything Claude Code for Kiro

## Overview

Pi Dynamics brings the workflows to Kiro. It packages 16 specialized agents, 18 invocable skills, 16 steering files, 10 IDE hooks, and utility scripts into a single installable toolkit.

The toolkit covers the full development lifecycle: planning, TDD, code review, security auditing, refactoring, documentation, database work, deployment, and multi-language support (TypeScript, Python, Go, Swift).

## Available Steering Files

This power organizes its content into focused guides. Use `readSteering` to load what you need:

- **agents-reference** — Full catalog of all 16 agents with descriptions, formats, and usage patterns
- **skills-reference** — Full catalog of all 18 skills with descriptions and invocation instructions
- **steering-and-hooks-reference** — All 16 steering files and 10 IDE hooks with trigger types and configuration
- **installation-guide** — Quick start, install script usage, customization, and project structure
- **workflows-and-examples** — 10 end-to-end workflow examples covering TDD, security, refactoring, deployment, and more

## Component Summary

| Component | Count | Description |
|-----------|-------|-------------|
| Agents | 16 | Specialized AI assistants (planner, code-reviewer, security-reviewer, tdd-guide, architect, etc.) |
| Skills | 18 | On-demand workflows (tdd-workflow, security-review, api-design, golang-patterns, etc.) |
| Steering Files | 16 | Always-on and conditional rules (coding-style, security, testing, language-specific patterns) |
| IDE Hooks | 10 | Automated triggers (quality-gate, typecheck-on-edit, tdd-reminder, extract-patterns, etc.) |
| Scripts | 2 | Shell utilities (quality-gate.sh, format.sh) |
| Docs | 3 | Longform guide, shortform guide, security guide |

## Recommended Workflow

1. Plan with the `planner` agent to break down complex features
2. Write tests first using the `tdd-workflow` skill
3. Review code with the `code-reviewer` agent
4. Audit security with the `security-reviewer` agent
5. Run the `quality-gate` hook before committing
6. Verify comprehensively with the `verification-loop` skill before PRs

## Installation

After installing this power, copy the `pi-dynamics` folder into your project's `.kiro/` directory and run:

```bash
cd .kiro/pi-dynamics
./install.sh /path/to/your/project
```

The installer uses non-destructive copy and will not overwrite existing files.

## Configuration

No MCP server required. All components are pure documentation, steering, and hook files that work natively in Kiro.

## Customization

All files are yours to modify after installation:
- Edit agent prompts in `.kiro/agents/*.json`
- Modify skill workflows in `.kiro/skills/*/SKILL.md`
- Adjust steering rules in `.kiro/steering/*.md`
- Toggle or edit hooks in `.kiro/hooks/*.kiro.hook`
- Customize scripts in `.kiro/scripts/*.sh`
