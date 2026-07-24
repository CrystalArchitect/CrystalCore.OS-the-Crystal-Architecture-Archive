# Repository Map

The canonical map of all six repositories: what each owns, how they
relate, and where the seams between them are.

## Statement

Six repositories exist. One is public; five are private. The public
repository holds no application code — it is canon, governance, and
mythos only.

**Status: Implemented** (verified directly against live GitHub metadata,
not assumed from any document).

### Evidence
- GitHub API, queried directly 2026-07-24: `TerAustralis-Incognita` —
  `"private":false`, `"visibility":"public"`, `has_pages:true`,
  `has_discussions:true`, `pull_request_creation_policy:
  "collaborators_only"` (public read, closed contribution). The other
  five — `TerAustralis-Incognita-Code`,
  `CrystalCore.OS-the-Crystal-Architecture-Archive`, `The-Crystal-
  Vision`, `crystalcore`, `crystal-vision` — all `"private":true`.

### Historical Notes
The system ledger (`STATUS.md` in this repository) previously described
`The-Crystal-Vision`, `crystalcore`, and `crystal-vision` as "archived
2026-07-18, read-only." Live GitHub metadata shows `archived:false` for
all three, confirmed 2026-07-24. Corrected in this repository's
`STATUS.md`; see `11-CORRECTIONS.md`. Whether to formally archive them
is an open decision the umbrella's own governance charter records as
undecided — not a settled fact any document simply got wrong. See "Open
decisions" below.

### Cross References
`04-GOVERNANCE.md`, `07-IP` content in `04-GOVERNANCE.md`.

---

## Statement

The canonical, current per-repository map, quoted from the umbrella's
own governance charter, rewritten 2026-07-24 (hours before this
reconstruction) from a same-day survey of all six repositories:

**The living system:**

| Repository | Role |
|---|---|
| `TerAustralis-Incognita` | The umbrella: governance, ADRs, architecture docs, research, provenance mirrors under `archive/`, and `mythos/` — the canon home (Codex, Apocryphon, The First Remembering, the crystalcore-os terminal). |
| `TerAustralis-Incognita-Code` (private) | The software, per Migration-Plan Stages 1–2: `core/` (engine — protocol pack with Clementine, CrystalBridge, mesh stub, SDK) and `vision/` (application — Lumina, voicebox, demo shells, the site source). Full CI; carries the Pages deploy and `CNAME`. |
| `CrystalCore.OS-the-Crystal-Architecture-Archive` | The system ledger: one fleet-wide `STATUS.md` — state, receipts, known unknowns across all repositories. Deliberately small (now also holds this knowledge base). |

**Frozen provenance** — checkpointed 2026-07-17 (the laptop hand-off),
deliberately left unarchived, never edited; their code lives on as
ancestors of the `-Code` tree:

| Repository | Was | Lives on as |
|---|---|---|
| `The-Crystal-Vision` (tag `vision-safe-2026-07-17`) | Codex site + Clementine companion; holds the complete crystalcore v0.13.4 bytecode rescue and the laptop snapshot | Ancestor of Lumina's embedded framework (which forked the earlier 0.7.0 line — see "Open decisions") |
| `crystalcore` (tag `crystalcore-safe-2026-07-17`) | The Songline protocol pack | Direct ancestor of `core/crystal-core` (Songline Bus → Starline Weaver) |
| `crystal-vision` | Static demo shell (Grok build) | Direct ancestor of `vision/apps/crystal-interface` |

**Status: Implemented** (this table's every row was independently
re-verified during this reconstruction, not merely copied).

### Evidence
- `TerAustralis-Incognita/docs/governance/Project-Boundaries.md`,
  "Repositories, today" section — added via merged PR #58
  (2026-07-24T03:57:10Z).
- Provenance tags fetched and directly confirmed to exist:
  `vision-safe-2026-07-17` on `The-Crystal-Vision`,
  `crystalcore-safe-2026-07-17` on `crystalcore`.

### Historical Notes
This section itself replaced an earlier version of the same file that
called `TerAustralis-Incognita-Code` "empty by design," stale since
Stage 1 landed the engine. This reconstruction's local clone of the
umbrella repository was briefly stale by three merged pull requests
(#56, #57, #58) mid-session; fast-forwarded and re-verified before this
content was trusted — see `10-PROVENANCE.md` for the full methodology
note.

### Cross References
`07-HISTORY.md`, `10-PROVENANCE.md`.

---

## Statement

The explicit, repeated dependency rule between the engine and the
application: **Crystal Vision may depend on Crystal Core; Crystal Core
never imports Crystal Vision.** The one apparent exception — CrystalBridge
reaching Lumina's memory — is explicitly framed as a runtime filesystem-
path coupling, not a module/package dependency.

**Status: Implemented** (stated identically, independently, in two
separate module READMEs within the same repository).

### Evidence
- `TerAustralis-Incognita-Code/core/README.md`: "Crystal Vision may
  depend on Crystal Core; Crystal Core never imports Crystal Vision.
  (CrystalBridge reaches Lumina's memory *by configured data path at
  runtime* — it serves the companion without importing it.)"
- `TerAustralis-Incognita-Code/vision/README.md`: near-identical
  wording, independently stated.

### Historical Notes
None.

### Cross References
`06-COMPONENTS.md` (CrystalBridge, Lumina entries).

---

## Statement

Canon reaches the public website through exactly one pipeline, which is
manual at one step and is explicitly flagged, by the project's own
governance charter, as a deliberate drift risk:

```
mythos/ (umbrella, canonical)
   → copied by hand into vision/site/src/content/ (Code repo)
   → built by deploy.yml → GitHub Pages → www.teraustralis.com.au
```

The site renders *copies*, not the canon directly — new canon is not
public until its copy step happens. This drift is live right now, not
theoretical: a new mythos file (`THE-FIRST-REMEMBERING.md`) is canonical
in the umbrella as of 2026-07-24 and has not yet been copied into the
site's content set.

**Status: Implemented** (the pipeline mechanism), **Unresolved** (the
specific current drift instance — "site copy of new canon" is one of
the project's own open decisions, see below).

### Evidence
- `TerAustralis-Incognita/docs/governance/Project-Boundaries.md`,
  "How canon reaches the public site" section (added 2026-07-24).
- `TerAustralis-Incognita-Code/CNAME` and
  `vision/site/static/CNAME` — both `www.teraustralis.com.au`, confirmed
  to exist; the umbrella repository has no `CNAME` file at all (moved
  out at Migration-Plan Stage 2).
- The domain itself is **not independently verifiable** from a session
  container — the egress proxy returns 403 on the CONNECT (domain not
  on the allowlist), confirmed directly this session, not merely
  inherited from an earlier claim of "egress blocked."

### Historical Notes
Pages/CNAME/`deploy.yml` all moved from the umbrella to
`TerAustralis-Incognita-Code` at Migration-Plan Stage 2 (2026-07-23). The
umbrella's own `SystemMap.md` described this move as still-broken for
several hours after it had already been resolved — corrected in this
pass, see `11-CORRECTIONS.md`. GitHub Pages source for
`TerAustralis-Incognita-Code` has not yet been switched to "GitHub
Actions" — a pending manual admin step with no API path available from
an agent session.

### Cross References
`06-COMPONENTS.md` (Site entry), `04-GOVERNANCE.md` (open decisions).

---

## Statement

The same brand/concept name is reused across the portfolio for
genuinely unrelated things, in two cases:

**"crystalcore"** names three unrelated things: (1) the companion Python
package family in `The-Crystal-Vision` (four version copies: 0.13.4
canonical, 0.13.4 bytecode-recovered, 0.12.0 reconstructed, 0.7.0
oldest), (2) the CrystalBridge MCP consent-gate package at
`TerAustralis-Incognita-Code/core/crystalcore/` (v0.1.0, unrelated
codebase), and (3) the standalone `crystalcore` repository's Seven
Sisters/Songline protocol-pack brand.

**"Clementine"** names two unrelated things: (1) the companion chat
persona, born in `The-Crystal-Vision` on 2026-07-15, later renamed
Lumina in the current lineage, and (2) the multi-AI message-bus/hub-
agent persona, born in the `crystalcore` repo on 2026-07-17 as the
"Clementine Singularity Bridge," later renamed Starline Weaver in the
current canon. Both original "Clementine" senses were renamed away in
the same 2026-07-21 rename sweep, to two *different* new names, because
they were always two different concepts that happened to share a first
name.

**Status: Historical** (both collisions are fully resolved in current
canon by the 2026-07-21 renames; the old names persist only in
un-updated, frozen-provenance repositories).

### Evidence
- `TerAustralis-Incognita/mythos/NAMES.md`: the governing rename
  document — "Starlines are the map. Dreamlines are the traveller of
  the map," and explicitly reserves "Songline" for Aboriginal culture
  only, not the software.
- Git commit evidence (umbrella repo, 2026-07-21): "lore: complete the
  persona sweep — Clementine (companion) → Lumina"; "rename the
  Songline Bus → Starline Weaver + Dreamline Narrator."
- `The-Crystal-Vision` commit (2026-07-15): "Refactor into the
  CrystalCore package; Clementine is its first persona" — confirms the
  framework was multi-persona-shaped from birth, with Clementine as
  persona #1.

### Historical Notes
The standalone `crystalcore` repository, created 2026-07-17, was never
updated past the pre-rename names — it is the only repository in the
portfolio still natively using "Clementine Singularity Bridge" and
"Songline Bus" throughout its own docs and code. This is presented as a
historical/provenance fact about a frozen repository, not a defect to
fix — that repository is deliberately checkpointed and unedited per the
umbrella's own charter.

### Cross References
`07-HISTORY.md`, `09-GLOSSARY.md`.

---

## Statement

The interface-demo concept and the Seven Sisters/protocol-pack content
each exist in two diverged copies across the portfolio, confirmed
non-identical by direct diff, not merely assumed to be duplicates:

- The crystal-vision interface demo: `crystal-vision/app.js` (546
  lines, newer, standalone repo) vs. `crystalcore/interface/app.js`
  (349 lines, older, inside the standalone Songline-pack repo).
- The Seven Sisters corpus: `TerAustralis-Incognita/research/
  seven-sisters/` vs. the standalone `crystalcore` repository's root
  markdown pack — mostly byte-identical, but `README.md` and three
  core path files differ in a consistent way: the `crystalcore` repo's
  copy keeps older, more grandiose framing ("Quantum Songline Weaver
  v∞.Δ+"), while the umbrella's reorganized copy explicitly downgrades
  to "a Vision-layer motif, not a claim."

**Status: Historical** (both are point-in-time forks, not actively
synchronized).

### Evidence
- Direct `diff` of `app.js`/`style.css` between `crystal-vision/` and
  `crystalcore/interface/`: all files differ.
- Direct `diff` of the Seven Sisters files between the two locations.

### Historical Notes
The editorial toning-down between the two Seven Sisters copies is
itself evidence of the project's own move toward more honest framing
over time — worth noting as a positive signal, not just a duplication
defect.

### Cross References
`03-ARCHITECTURE.md` (Seven Sisters section).

---

## Statement — Open decisions this map records rather than resolves

The umbrella's own governance charter states four open decisions
explicitly, and this archive preserves them as open — they are the
project's questions, not this archive's to answer:

- **Stage 3 repo count** — whether `core/`/`vision/` split into two
  repositories (Migration-Plan criteria; deliberately not decided).
- **0.13.4 lineage** — Lumina's framework forked the 0.7.0 line; the
  0.13.4 rescue's extras (SpaceXAI provider, `node.py`, `status.py`,
  CLI) sit unreconciled in `The-Crystal-Vision`.
- **Frozen repos' end state** — whether to GitHub-archive (read-only
  flag) the three provenance repos, or leave them as-is. Explicitly
  undecided — not a fact any prior STATUS.md simply got wrong when it
  called them "archived."
- **Site copy of new canon** — The First Remembering is canonical but
  not yet copied into the site content set.

**Status: Unresolved** (by design — these are the project's own stated
open questions).

### Evidence
- `TerAustralis-Incognita/docs/governance/Project-Boundaries.md`,
  "Open decisions this map records rather than resolves" section.

### Historical Notes
None — current as of 2026-07-24.

### Cross References
`04-GOVERNANCE.md`, `07-HISTORY.md`.
