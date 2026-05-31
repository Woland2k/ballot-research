# Ballot Research

A reusable, **politically neutral** [Claude Skill](https://support.claude.com/en/articles/12512180-use-skills-in-claude) — packaged here as a [Claude Code plugin](https://code.claude.com/docs/en/plugin-marketplaces) — that helps a voter understand their ballot end to end. It identifies every contest, researches each candidate and measure from **authoritative nonpartisan sources**, lays out the meaningful differences in consistent side-by-side tables, optionally maps each race to the **voter's own stated priorities**, and delivers it in ballot order as a guide you can keep or share.

## Install

### Option A — Claude Code (as a plugin marketplace)

```shell
/plugin marketplace add Woland2k/ballot-research
/plugin install ballot-research@ballot-research
```

Then just describe your ballot in any session (the skill is model-invoked and loads when relevant), or run it directly with `/ballot-research:ballot-research`.

### Option B — claude.ai (upload the skill)

1. Download this repo (green **Code → Download ZIP**, or a Release asset).
2. Zip the inner skill folder `plugins/ballot-research/skills/ballot-research/` (the folder containing `SKILL.md`).
3. In Claude, go to **Settings → Capabilities → Skills**, upload the zip, and toggle it on.

> Settings paths move as the product updates; if it looks different, search "use skills" at support.claude.com.

## What's inside

```
.
├── .claude-plugin/
│   └── marketplace.json                 # marketplace catalog
└── plugins/
    └── ballot-research/
        ├── .claude-plugin/
        │   └── plugin.json              # plugin manifest
        └── skills/
            └── ballot-research/
                ├── SKILL.md             # the workflow + guardrails
                └── references/
                    ├── sources.md       # authoritative nonpartisan sources
                    └── comparison-templates.md  # candidate / judge / measure tables
```

## How it works

When you share a sample ballot (photos) or give your location and election, the skill walks Claude through: enumerating every contest in ballot order → researching each candidate/measure from official election authorities and nonpartisan guides → building side-by-side comparison tables (including bar-association ratings for judges) → optionally mapping each race to your stated priorities → delivering a ballot-ordered guide, with a reminder to verify on your official sample ballot.

## Design principle: neutral by default

This skill has **no built-in political lean.** It presents candidates and measures factually, adapts to whatever priorities the voter states, and always surfaces the opposing consideration. Any "how this maps to your priorities" note is explicitly the *voter's* criteria, never an endorsement. It's research to inform your own decision — not legal or formal voting advice.

## Trust

Skills can contain executable code, so install only from sources you trust. This one is **plain Markdown only — no scripts, nothing to execute.**

## License

MIT — see [LICENSE](LICENSE). Free to use, modify, and share; attribution appreciated, not required.
