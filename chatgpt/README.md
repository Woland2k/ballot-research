# Using Ballot Research in ChatGPT

ChatGPT has no plugin/skill marketplace equivalent, so this folder ports the skill as a **paste-ready instructions block**. It's fully self-contained — the source hierarchy and comparison templates that the Claude skill keeps in separate reference files are **inlined** here, because a plain ChatGPT context has no separate "knowledge files."

## Option 1 — A Project (recommended for repeated use)

1. In ChatGPT, create a **Project** (left sidebar → **+ → New project**), name it e.g. *Ballot Research*.
2. Open the project's **Instructions** and paste the entire contents of **[`ballot-research-instructions.md`](ballot-research-instructions.md)**.
3. Make sure **web search** is available/on for your account — this skill *must* research fresh and will be wrong without it.
4. Start a chat inside the project and describe your ballot (location + election, or upload sample-ballot photos).

## Option 2 — One-off in any chat

Paste the contents of [`ballot-research-instructions.md`](ballot-research-instructions.md) as your first message, then add your ballot details below it. Works anywhere, nothing to set up, but you re-paste each new chat.

## Option 3 — Custom GPT (shareable)

If you have ChatGPT Plus/Team/Enterprise and want a shareable *Ballot Research* GPT:
- **Instructions** = the contents of [`ballot-research-instructions.md`](ballot-research-instructions.md) (trim the inlined reference sections if you hit the instruction-length limit).
- **Knowledge** = upload [`sources.md`](../plugins/ballot-research/skills/ballot-research/references/sources.md) and [`comparison-templates.md`](../plugins/ballot-research/skills/ballot-research/references/comparison-templates.md) instead of inlining them, and in the instructions say "consult your knowledge files for the source hierarchy and table templates."
- **Capabilities** = enable **Web Search**.

## Note

This is a port of the same neutral, research-fresh workflow as the Claude skill. The canonical source is [`SKILL.md`](../plugins/ballot-research/skills/ballot-research/SKILL.md); if you change the skill, mirror the change into `ballot-research-instructions.md` (see [`RELEASING.md`](../RELEASING.md)).
