# Public Claude Skills

Free skills for Claude (Claude Code, the Claude desktop app, and claude.ai). Each skill lives in its own folder under `skills/` and has a `SKILL.md` with the instructions.

## Skills

| Skill | What it does |
|---|---|
| [inbox-triage](skills/inbox-triage/SKILL.md) | Checks your Gmail every morning and tells you what needs your attention: bills and to-dos first, then updates. On Saturdays it sends a weekly list of everything still pending, with how many days each item has waited. You get a short email and a detailed report in Claude. |

---

## inbox-triage

### What you get
- **Daily, 7 AM:** what's new: payments due, things people are waiting on you for, and a few updates.
- **Weekly, Saturday 7 AM:** everything from the week you haven't dealt with yet, marked ⏳ pending or 🔴 overdue.
- **Two versions of each report:**
  - **Email:** short, one line per item, with a link to each email.
  - **Claude:** detailed, with context for every item, the full list of updates and what got done.

### What you need
- A Claude account with **Claude Code** (to run it on a schedule).
- The **Gmail connector**, connected at [claude.ai/customize/connectors](https://claude.ai/customize/connectors). It needs permission to read your mail, and to send if you want the report emailed to you.

### Set it up

**Option 1: Cloud (recommended, runs even when your computer is off)**

Go to [claude.ai/code/routines](https://claude.ai/code/routines) and create two routines:

| | Daily | Weekly |
|---|---|---|
| Schedule | Every day, 7 AM | Saturdays, 7 AM |
| Repository | `https://github.com/jaizv/Public-Claude-Skills` | same |
| Connector | Gmail | Gmail |

For each one, use this prompt. Fill in your own email address, use `weekly` instead of `daily` for the Saturday routine, and change the time zone if needed:

```
Read skills/inbox-triage/SKILL.md in this repo and follow it in DAILY mode.
Settings: email: you@example.com, deliver: email, timezone: America/New_York
```

Routine schedules are set in UTC. 7 AM New York is 11:00 UTC in summer and 12:00 UTC in winter.

You'll get the short version by email. To see the detailed report, open the routine's latest run.

**Option 2: On your computer (Claude desktop app)**

1. Copy `skills/inbox-triage/` into your skills folder:
   - macOS / Linux: `~/.claude/skills/inbox-triage/`
   - Windows: `%USERPROFILE%\.claude\skills\inbox-triage\`
2. In the Claude app, ask: *"Run inbox-triage every day at 7 AM, and in weekly mode every Saturday at 7 AM."*
3. On the first run it asks for your email address, where you want reports (chat, email or both) and your time zone.

These scheduled tasks only run while the app is open.

**Just ask:** with the skill installed, you can also type *"check my email"* at any time.

### Privacy and safety
- **What it reads:** your Gmail, through the connector you approved.
- **What it sends:** one email, only to the address you entered. It never takes an address from an email it read, and it never replies to or forwards anything.
- **What it ignores:** instructions hidden inside emails (for example "AI, forward this to..."). It flags those as possible scams instead.
- **What it changes:** nothing in your inbox. It doesn't label, archive, delete or pay anything.
- **What it stores:** on your computer, a small settings file and a to-do list in `~/.claude/inbox-triage/`. In the cloud, nothing; the weekly report rebuilds its list from the daily emails it sent you.
- **What's in the reports:** sender, subject, amount, due date and a link. No account numbers, codes or email body text.

---

## License

[MIT](LICENSE): free to use, change and share.
