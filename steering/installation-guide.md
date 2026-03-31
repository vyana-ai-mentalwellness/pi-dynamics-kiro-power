# Installation Guide

## Quick Start

```bash
cd .kiro
./pi-dynamics/install.sh /path/to/your/project

# Or install to current directory
./pi-dynamics/install.sh

# Or install globally
./pi-dynamics/install.sh ~
```

The installer uses non-destructive copy — it will not overwrite existing files.

## What Gets Installed

| Source | Destination | What |
|--------|-------------|------|
| `pi-dynamics/agents/*.json` | `.kiro/agents/` | 16 CLI agent configs |
| `pi-dynamics/agents/*.md` | `.kiro/agents/` | 16 IDE agent configs |
| `pi-dynamics/skills/*/SKILL.md` | `.kiro/skills/pi-dynamics-*/` | 18 skills |
| `pi-dynamics/steering/*.md` | `.kiro/steering/pi-dynamics-*.md` | 16 steering files |
| `pi-dynamics/hooks/*.kiro.hook` | `.kiro/hooks/pi-dynamics-*.kiro.hook` | 10 IDE hooks |
| `pi-dynamics/scripts/*.sh` | `.kiro/scripts/` | 2 shell scripts |
| `pi-dynamics/docs/*.md` | `.kiro/docs/` | 3 documentation files |

## Project Structure

```
.kiro/pi-dynamics/
├── agents/           # 16 agents (JSON + MD)
├── skills/           # 18 skills (each with SKILL.md)
├── steering/         # 16 steering files
├── hooks/            # 10 IDE hooks + README
├── scripts/          # quality-gate.sh, format.sh
├── docs/             # longform, shortform, security guides
├── settings/         # mcp.json.example
├── install.sh        # Installer script
└── README.md         # Full documentation
```

## Customization

All files are yours after installation. The installer never overwrites.

- Agent prompts: `.kiro/agents/*.json` or `.kiro/agents/*.md`
- Skill workflows: `.kiro/skills/*/SKILL.md`
- Steering rules: `.kiro/steering/*.md`
- Hooks: `.kiro/hooks/*.kiro.hook` (set `"enabled": false` to disable)
- Scripts: `.kiro/scripts/*.sh`

## Sharing with Your Team

1. Zip `.kiro/pi-dynamics/` and share — recipients drop it in `.kiro/` and run `install.sh`
2. Add as a git submodule in `.kiro/`
3. Install this power from the Kiro Powers panel for documentation reference
