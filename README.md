# Ballot Research

A reusable, **politically neutral** [Claude Skill](https://support.claude.com/en/articles/12512180-use-skills-in-claude) — packaged here as a [Claude Code plugin](https://code.claude.com/docs/en/plugin-marketplaces) — that helps a voter understand their ballot end to end. It identifies every contest, researches each candidate and measure from **authoritative nonpartisan sources**, lays out the meaningful differences in consistent side-by-side tables, optionally maps each race to the **voter's own stated priorities**, and delivers it in ballot order as a guide you can keep or share.

## What you can ask

Once it's set up (see **Install** below), just describe your ballot in plain language:

- *"Here are photos of my sample ballot — build me a voter guide."*
- *"What's on my ballot? I'm in [ZIP / county] for the [date] election."*
- *"Compare the candidates for [office] in my area."*
- *"Map my ballot to my priorities: [e.g. lower taxes, environment, public safety]."*

It works the same on every supported platform; only the one-time setup differs.

## Install

**Which Claude are you using?**

- **Claude web app or desktop app** → use **[Option B](#option-b--claudeai--claude-desktop-upload-the-skill)** (upload the skill zip). The `/plugin` commands below do **not** work in the consumer app.
- **Claude Code (the CLI)** → use **Option A** (plugin marketplace) below.
- **ChatGPT** → see **[`chatgpt/`](chatgpt/)** for a paste-ready instructions block (Project, one-off chat, or Custom GPT).

### Option A — Claude Code (as a plugin marketplace)

```shell
/plugin marketplace add Woland2k/ballot-research
/plugin install ballot-research@ballot-research
```

Then just describe your ballot in any session (the skill is model-invoked and loads when relevant), or run it directly with `/ballot-research:ballot-research`.

### Option B — claude.ai / Claude desktop (upload the skill)

The `/plugin` commands above are **Claude Code (CLI) only**. To use this in the Claude web or desktop app, upload the prebuilt skill zip:

1. Download **[`ballot-research-skill.zip`](https://github.com/Woland2k/ballot-research/releases/latest/download/ballot-research-skill.zip)** (latest release asset — a stable link that always serves the newest version).
2. **Enable code execution first** — Settings → **Capabilities** → turn on **Code execution / file creation**. The Skills upload option won't appear until this is on. *(On Team/Enterprise, an org owner must enable both "Code execution and file creation" and "Skills" in Organization settings before members can upload.)*
3. Go to **Customize → Skills**, click **+** → **+ Create skill** → **Upload a skill**.
4. Select the zip. It's then available — the skill is model-invoked, so just describe your ballot in any chat and it loads when relevant.

Works on all plans (including Free) once code execution is enabled. Uploaded skills are private to your account.

> The zip already contains the skill folder at the correct level (`ballot-research/SKILL.md` inside). To rebuild it yourself, zip the folder `plugins/ballot-research/skills/ballot-research/`.
>
> Menu paths move as the product updates; if it looks different, see [Use Skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

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
