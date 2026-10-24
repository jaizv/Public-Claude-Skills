# Public Claude Skills

Skills for Claude (Claude Code, the Claude desktop app, and claude.ai). Each skill lives in its own folder under `skills/` and has a `SKILL.md` with the instructions.

## Skills

| Skill | What it does |
|---|---|
| [inbox-triage](skills/inbox-triage/SKILL.md) | Checks your Gmail and reports what needs your attention: payments and action items first, then updates. Read-only. |

## Installing a skill

Copy the skill's folder into your personal skills folder:

- macOS / Linux: `~/.claude/skills/<skill-name>/`
- Windows: `%USERPROFILE%\.claude\skills\<skill-name>\`

Restart Claude Code or the desktop app. The skill then loads on its own whenever a request matches its description.

## Requirements

- **inbox-triage** needs a Gmail connector so Claude can search and read your threads.
