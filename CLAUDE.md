# skills-lab

A workspace for building and testing Claude Code skills. Skills built here graduate to global scope (`c:\Users\USER\.claude\skills\`) once proven, so they're usable from any project — this project is the lab, not necessarily the final home. Default to promoting a validated skill/pattern globally without waiting to be asked, once it's actually been exercised successfully here.

## Active skills

- **`skill-builder`** (project-scoped, stays here) — guides creating/auditing/optimizing Claude Code skills. Use this before hand-writing a new `SKILL.md`.
- **`lordgen-pitch`** (graduated to global, `c:\Users\USER\.claude\skills\lordgen-pitch\`) — grounds a client pitch + illustration brief for one named profession in real Q&A/friction detail instead of generic or imagined copy, then by default renders the illustration, builds a branded 2-page PDF, and emails it as a self-addressed review copy. Portable pitch-PDF template lives at `lordgen-pitch/assets/pitch-template.html`.
- **`tool-scout`** (global, `c:\Users\USER\.claude\skills\tool-scout\`) — identifies API keys/MCP connectors any task needs, always leads with free-tier/open-source options, and is self-improving (`catalogue.md` grows instead of re-researching). Picks the research tool (Perplexity/Firecrawl/WebSearch) automatically per its own priority order — this shouldn't need reminding.

## Cross-project dependencies

`lordgen-pitch` reaches outside whichever project it's invoked from for shared LordGen agency context, since that context doesn't belong duplicated per-project:

- `c:\Users\USER\Downloads\Lordgen AI Post Reference\reference.md` — the trade friction table (shared with the `lordgen-post` skill).
- `c:\Users\USER\Lordgen AI Skill builder\references\offers.md` — LordGen's offer catalogue (currently a stub — no confirmed pricing/scope).
- `c:\Users\USER\Lordgen AI Skill builder\references\human-in-the-loop.md` — the approval-gating policy `lordgen-pitch` follows (client-facing drafts are Yellow tier: draft freely, never auto-send).
- `c:\Users\USER\Newsletter Demo\` — shared Gmail OAuth (`credentials.json`/`token.json`) reused by `lordgen-pitch/scripts/send_pitch_email.py`.
- `tool-scout` (global) — free-tier/open-source tool research, shared across all projects, not just this one.

**If any of those paths don't exist on the current machine**, ask the user for the correct location rather than silently skipping the grounding step that depends on them.

## Output convention

Skills that produce artifacts (currently just `lordgen-pitch`) save them to `output/<slug>/` in the invoking project's root, not inside the skill's own directory — this project's `output/` holds the pitches built here so far.

## Standing preferences (LordGen initiative)

- Skills/patterns validated here should be promoted to global scope proactively, not on request.
- Tool selection (which research/render/send tool to use) should happen automatically per `tool-scout`'s priority order — don't wait to be told to use Perplexity, Firecrawl, etc.
- Missing credentials/MCP connectors should be surfaced and requested proactively (placeholder `.env` created + value asked for in the same turn), not discovered mid-failure.
- LordGen is moving toward production use — hold execution to a high reliability bar (verify actual output, e.g. real page counts/rendered images, not just that a command exited 0).
