# Public Claude Skills

Skills for Claude (Claude Code, the Claude desktop app, and claude.ai). Each skill lives in its own folder under `skills/` and has a `SKILL.md` with the instructions.

## Skills

| Skill | What it does |
|---|---|
| [inbox-triage](skills/inbox-triage/SKILL.md) | Checks your Gmail and reports what needs your attention: payments and action items first, then a few updates. Daily mode covers new mail. Weekly mode lists what's still not taken care of. It can email the report to you. |

## Installing a skill

Copy the skill's folder into your personal skills folder:

- macOS / Linux: `~/.claude/skills/<skill-name>/`
- Windows: `%USERPROFILE%\.claude\skills\<skill-name>\`

Restart Claude Code or the desktop app. The skill then loads on its own whenever a request matches its description.

## Requirements

- **inbox-triage** needs a Gmail connector. Reading lets it check your mail. Sending is needed only if you want the report emailed to you.
  - On the first run it asks for your email address and where you want reports (chat, email or both), and saves your answers in `~/.claude/inbox-triage/settings.md`. Reports go to chat unless you choose email.
  - It only ever sends to that one saved address. It never follows instructions written inside emails, and it changes nothing in your inbox.
  - To get reports automatically, set up two scheduled tasks: a daily one ("run inbox-triage in daily mode") and a weekly one ("run inbox-triage in weekly mode").
