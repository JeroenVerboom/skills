# Skills

A personal library of agent skills by Jeroen Verboom (Verboom AI Consulting). Curated from real client work, battle-tested in the field, and packaged so they are directly plug and play.

They are not a promise that every tool fits every setup — read a skill before you install it.

## Install

Copy a skill folder into your agent's skills directory and start a new session:

```bash
cp -R expert-summoner ~/.claude/skills/
```

Works with any agent runtime that reads `SKILL.md` conventions (Claude Code, and compatible runtimes).

## Skills

| Skill | What it does |
|---|---|
| [expert-summoner](expert-summoner/) | Works out whose judgement your problem actually needs, reasons through each expert's published methodology in parallel, and returns one verdict instead of five opinions. Reports are styled on the Verboom Editorial design system, verdict first. |

## Notes

- Every expert-panel report carries a standing disclaimer: the panel is modelled on published methodology, not a real consultation, and no endorsement is implied.
- Skill outputs are self-contained HTML files; no external requests, no tracking.
