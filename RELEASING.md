# Releasing a new version

This repo ships two ways from the same source, and both are driven by one release:

- **Claude Code (CLI):** `/plugin marketplace add Woland2k/ballot-research` reads `.claude-plugin/marketplace.json` on the default branch.
- **Claude web / desktop:** users download the skill zip from the **latest GitHub Release** (the README links to `releases/latest/download/ballot-research-skill.zip`, which always serves the newest release — so the README link never changes).

## Steps

Replace `vX.Y.Z` below with the new version (e.g. `v1.1.0`).

### 1. Bump the version in two manifests

Keep these in sync:

- `plugins/ballot-research/.claude-plugin/plugin.json` → `"version"`
- `.claude-plugin/marketplace.json` → the plugin entry's `"version"`

### 2. Rebuild the skill zip

The zip must contain the skill folder at the top level (`ballot-research/SKILL.md` inside) — **not** the repo wrapper. Build it from the `skills/` directory:

```shell
cd plugins/ballot-research/skills
rm -f /tmp/ballot-research-skill.zip
zip -r -X /tmp/ballot-research-skill.zip ballot-research -x '*.DS_Store'
```

Sanity-check the structure (`SKILL.md` should be one level deep):

```shell
unzip -l /tmp/ballot-research-skill.zip
```

### 3. Commit the version bump

```shell
git add -A
git commit -m "Release vX.Y.Z"
git push origin main
```

### 4. Create the release with the zip attached

With the `gh` CLI:

```shell
gh release create vX.Y.Z /tmp/ballot-research-skill.zip \
  --repo Woland2k/ballot-research \
  --title "Ballot Research vX.Y.Z" \
  --notes "Prebuilt skill zip for the Claude web/desktop app. Upload it in Settings -> Capabilities -> Skills. Claude Code users: /plugin marketplace add Woland2k/ballot-research"
```

Or via the web UI: **Releases → Draft a new release → tag `vX.Y.Z` → attach `ballot-research-skill.zip` → Publish**.

The asset **must** be named `ballot-research-skill.zip` so the README's stable `releases/latest/download/...` link keeps working.

### 5. Verify

```shell
# Should 302-redirect to the new tag's asset
curl -s -o /dev/null -w "%{http_code} -> %{redirect_url}\n" \
  https://github.com/Woland2k/ballot-research/releases/latest/download/ballot-research-skill.zip
```

That's it. The README download link and the Claude Code marketplace command both pick up the new version automatically — no further edits needed.
