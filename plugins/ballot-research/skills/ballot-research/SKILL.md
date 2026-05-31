---
name: ballot-research
description: Research and compare the candidates and measures on a voter's ballot so they can make informed choices, then produce a clean ballot-ordered voter guide. Use this skill whenever the user shares a ballot (photos or a sample ballot), asks who is running for an office, asks about candidates, propositions, measures, bonds, or judges on their ballot, wants a side-by-side candidate comparison, asks "how should I vote" or "who should I vote for", wants races mapped to their own stated priorities, or wants a voter guide they can keep or share — even if they don't use the words "skill" or "ballot." Always prefer this skill over answering election questions from memory, because candidates, officeholders, and measures change every cycle and must be researched fresh.
---

# Ballot Research — Voter Guide Builder

Help a voter understand their ballot end to end: identify every contest, research each candidate and measure from **authoritative nonpartisan sources**, lay out the meaningful differences in consistent side-by-side tables, optionally map each race to the **voter's own stated priorities**, and deliver it in ballot order as a document they can keep or share.

## Non-negotiable principles

1. **Neutrality.** Present candidates and measures factually and even-handedly. Never steer the voter toward a party or ideology. The skill adapts to *whatever* priorities the voter states — it has no built-in lean. When you note how a race maps to the voter's priorities, label it explicitly as *their* criteria, show the opposing consideration too, and never present it as your endorsement.
2. **Research fresh, every time.** Officeholders, candidates, endorsements, ratings, and measures change each cycle and routinely post-date training data. Always search; never answer from memory. Treat surprising-but-sourced results (an incumbent losing, a candidate dropping out) as plausible.
3. **Authoritative sources only.** Lead with official election authorities and nonpartisan guides. See `references/sources.md`. Avoid campaign spin and partisan blogs except clearly labeled as a candidate's own statement or a named endorsement.
4. **Cite and paraphrase.** Attribute claims to their source; paraphrase rather than copy. For contested or critical claims (disciplinary records, controversies), name the outlet and frame opinion as opinion.
5. **Always point to the official record.** Close by directing the voter to their official sample ballot / registrar site to verify, and note this is research to inform their own decision, not legal or formal voting advice.
6. **Protect privacy.** Don't ask for or store sensitive voter data (full address beyond what's needed for the district, ID numbers, party registration unless volunteered). A ZIP or county is enough to find the right ballot.

## Workflow

### 1. Establish context
Gather (ask if not provided):
- **Where**: ZIP / city / county / state — needed to pull the correct ballot and districts.
- **Which election** and **date**.
- **The voter's own priorities**, in their words (e.g., lower taxes, environment, public safety, specific issues). This is optional but lets you add a "how this maps to your priorities" note per race. If they don't offer any, keep the guide purely factual.
- **The ballot itself**: photos of an official/sample ballot are ideal. If none, pull the official sample ballot from the registrar (see sources) using their location.

If the voter has already decided some races (e.g., marked a photo), record those as-is and focus research on the undecided ones.

### 2. Enumerate every contest in ballot order
List all races and measures top to bottom, page by page, exactly as they appear. Keeping ballot order is what makes the guide usable while voting. Mark which are already decided vs. open.

### 3. Research each contest
Search **per candidate and per measure** — a single combined query returns shallow results. Use the source hierarchy in `references/sources.md`. For each race gather: who's running, current role, background, party preference/lean (where it's a real fact), key positions, notable news or controversies, major endorsements, and any official ratings.

Scale effort to the office: top-of-ticket and contested seats deserve the deepest research; uncontested or minor races get a short note. If a candidate is genuinely low-profile and the record is thin, **say so** rather than padding.

### 4. Build the comparison tables
Use the templates in `references/comparison-templates.md`. Pick the right one:
- **Candidate races** (executive, legislative, etc.) → candidate-dossier table.
- **Judicial races** → judicial table. These are officially nonpartisan; lead with the **bar-association rating** and **prosecutor/defense/quasi-judicial background**, not partisan framing. Don't invent a party lean for a judge.
- **Ballot measures / propositions / bonds** → measure table: plain-language "what it does," the **cost / tax impact**, who supports and opposes it, and the core tradeoff.

### 5. (Optional) Map to the voter's priorities
If the voter gave priorities, add a short, clearly-labeled note per open race: which option(s) align with *each* stated priority and where the priorities pull in different directions. Always surface the strongest counter-consideration. Never collapse this into a single "vote for X" command — the voter decides.

### 6. Deliver in ballot order
Produce the guide as a saved document (Markdown by default) organized page-by-page in ballot order, so the voter can keep it, follow it while voting, and share it. End with the "verify on your official sample ballot" reminder and the not-legal-advice note.

## Output structure

Use this shape (adapt headings to the actual ballot):

```
# Voter Guide — [Election name & date] — [Location]
[How to use; neutrality note; "Lean/alignment columns reflect YOUR stated priorities, not endorsements"; top-two/primary mechanics if relevant]

## [Ballot section / page]
### [Office or Measure]
[comparison table from the template]
[optional: "How this maps to your priorities" note]
...

## Sources & verification
[nonpartisan sources used + link to official sample ballot; not-legal-advice line]
```

## Reference files
- `references/sources.md` — Where to find authoritative, nonpartisan ballot and candidate information (official election authorities, nonpartisan guides, judicial evaluations, campaign-finance lookups), with notes on adapting per state. Read this before researching.
- `references/comparison-templates.md` — The exact table templates for candidate races, judicial races, and ballot measures, plus the "map to priorities" pattern. Read this before building tables.
