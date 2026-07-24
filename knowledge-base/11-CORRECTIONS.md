# Corrections

Every documentation correction this reconstruction made or identified,
in two sections: applied directly to the source file, and identified
but left for a future pass.

## Part 1 — Applied this pass (2026-07-24)

Scope discipline: only small, mechanical, high-confidence corrections
of a factual claim against verified reality were applied directly —
matching "minimize documentation churn... prefer documentation fixes
over structural changes." Everything larger, riskier, code-behavior-
related, or requiring a judgment call is in Part 2 instead.

### `CrystalCore.OS-the-Crystal-Architecture-Archive/STATUS.md`

- **Archived-status claims (4 occurrences)** — before: "The-Crystal-
  Vision (archived 2026-07-18, read-only)," and equivalent phrasing for
  `crystalcore`, `crystal-vision`, and a fourth reference in the Built
  section. After: corrected to reflect that live GitHub metadata shows
  `archived:false` for all three, with the more accurate framing that
  whether to archive them is an open decision the umbrella's own
  charter records as undecided, not a settled fact.
- **`crystal-vision`'s "one true blank"** — before: "contents never
  audited by any ledger pass." After: resolved with a summary of this
  session's full audit (functional static demo, v0.5.1, Apache-2.0, no
  network calls, no secrets, two cosmetic defects).
- **`teraustralis-final.html`** — before: listed under "Running," with
  a "location unknown" note. After: removed from Running (a file
  confirmed absent everywhere no longer clears that section's bar);
  Known Unknowns updated to state it was searched for by filename,
  content, and git history across all six repositories and found
  nowhere — resolved absent, not merely unlocated.
- **Repo 3's CI claim** — before: "no CI." After: corrected to state
  `ci.yml` exists and runs on push; `deploy.yml` exists but GitHub
  Pages source hasn't been switched on yet (pending manual step).
- Added: a pointer line to `knowledge-base/00-INDEX.md`.

### `TerAustralis-Incognita/STATUS.md`

- **"Dormant by drift"** — before: "publish-packages.yml... and
  test-packages.yml... Dormant by drift rather than by decision." After:
  "not dormant, removed outright at Stage 2 (commit `60a20df`)... after
  confirming neither had ever had a git tag to fire on. Removal was a
  decision, not drift" — resolving a direct contradiction with the same
  repository's own `Migration-Plan.md`.
- **`teraustralis-final.html`** — before: "Presumed to live in an
  archived repo; unresolved this session." After: resolved absent,
  matching the system ledger's correction above.
- Added: a pointer line to the Archive repo's knowledge base.

### `TerAustralis-Incognita/docs/architecture/SystemMap.md`

- **The "Consequences" paragraph** — before: stated `ci.yml`/
  `deploy.yml` fail against absent paths and the CNAME points at an
  absent site — true when written (2026-07-23, 13:47 UTC), false within
  hours. After: rewritten to state Stage 2's resolution (same day),
  citing `Migration-Plan.md`, and to note what's still actually true
  (self-tests and demo commands remain unrunnable from a fresh clone,
  because `src/`/`tests/` are genuinely still not in this repository).
- **`starline` path reference** in the directory tree — before:
  `starline (P2P exchange)`. After: `consent_transport (P2P exchange;
  starline/ is a deprecated alias)`.

### `TerAustralis-Incognita/docs/governance/Roadmap.md`

- Added four missing dated entries to "Recently landed" — ADR-0006,
  ADR-0008, ADR-0009, ADR-0010 — matching what `CHANGELOG.md` already
  recorded in full but this page omitted entirely.

### `TerAustralis-Incognita/docs/README.md`

- Added a new "Root-level reference documents" section indexing the
  nine `docs/*.md` files that existed but were never listed
  (`ATTRIBUTIONS.md`, `DBT_WAREHOUSE_INTEGRATION.md`,
  `HUGGINGFACE_INTEGRATION.md`, `ADVANCED_UNCERTAINTY_METHODS.md`,
  `EMOTIONAL_INTELLIGENCE_BLUEPRINT.md`, `RESTRUCTURING_COMPLETE.md`,
  `FIRST_RELEASE.md`, `PUBLISHING.md`, `COMMERCIAL_LICENSING_GUIDE.md`)
  — a gap a prior architecture-survey session had already flagged and
  which remained unfixed until this pass.

### `TerAustralis-Incognita/docs/architecture/CrystalCore.md` and `docs/architecture/crystal-core/Runtime-Glossary.md`

- Same `starline/` → `consent_transport/` path correction as
  `SystemMap.md`, in both files.

### `TerAustralis-Incognita-Code/STATUS.md`

- **"No CI at all"** (Built section) — before: "this repo has no CI at
  all." After: corrected — both `ci.yml` and `deploy.yml` exist and
  run; the actual remaining gap (GitHub Pages source not switched on)
  stated precisely.
- **Lumina test-suite claim** — before: "Overclaim, or suites that
  never made the import? Unresolved." After: "Resolved 2026-07-24:
  confirmed overclaim — the other three suites do not exist anywhere in
  this repository." (`vision/README.md` itself deliberately left
  uncorrected — see Part 2.)
- **Second "No CI" claim** (Known unknowns) — same correction as above,
  cross-referenced.
- Added: a pointer line to the Archive repo's knowledge base.

### `TerAustralis-Incognita-Code/core/README.md`

- The component table's `crystal-core/` row listed "Starline P2P
  (`starline/`)" as a separate item from "Consent Transport
  (`consent_transport/`)" — collapsed into one accurate entry noting
  `starline/` is a deprecated alias, not a second component.

### `TerAustralis-Incognita-Code/core/crystal-core/SECURITY.md`

- Same `starline/` → `consent_transport/` correction.

### `TerAustralis-Incognita-Code/core/crystal-core/README.md`

- **Sibling-repository list** — before: named three repositories
  ("the-crystal-vision," "crystal-vision," "teraaustralis-incognita")
  that don't match current reality — none spelled or scoped like
  anything that exists today, and none mentioning this repository's own
  actual name. After: corrected against the umbrella's fresh
  "Repositories, today" section — all six current repositories named
  correctly, with CrystalBridge's actual location corrected (it lives
  in this repository, not the umbrella, as the original text implied).

### Four Code-repo module READMEs

`core/crystalcore/README.md` was not touched (its stale `src/apps/`
and `src/profiles/` references are code-comment-adjacent documentation
tightly coupled to `bridge.py`'s actual bug — see Part 2). The
following four each had their own stale, pre-split `src/apps/...` path
references corrected to the real current paths:
- `vision/apps/voicebox/README.md` — one path.
- `vision/apps/crystal-interface/README.md` — two paths (the `cd`
  instruction, and the relative path to the real pipeline).
- `vision/apps/vision-web/README.md` — four paths (the surface table,
  the `cd` instruction, and two entries in "Related").

---

## Part 2 — Identified, not applied

Each with a one-line reason it's left for a future, separate pass.

| Finding | File(s) | Why not applied here |
|---|---|---|
| `bridge.py`'s Lumina-path resolves to a nonexistent directory (`core/apps/` instead of `vision/apps/`); `recall`/`teach`/`message` crash at runtime | `TerAustralis-Incognita-Code/core/crystalcore/bridge.py` | Code-behavior fix, not a documentation fix — out of scope for a documentation-only reconstruction. |
| `gate.py`'s docstring claims four consent checks; only two (approval, permission) are implemented | Same file, `gate.py` | Same as above — fixing this "right" means either building the missing checks or downgrading a security claim, both real engineering decisions, not doc edits. |
| No requirements/toml/cfg file declares the `mcp` package `bridge.py` imports | `TerAustralis-Incognita-Code` (repo-wide) | Packaging/dependency fix, not documentation. |
| 96 files carry `SPDX-License-Identifier: Apache-2.0` headers under a CC BY-NC-ND 4.0 root `LICENSE` | `TerAustralis-Incognita-Code`, 96 files | Mechanically identical to a fix ADR-0008 already executed once, in the umbrella (97 files) — but sized for its own dedicated, scripted pass, not folded into this session's line-edit budget. |
| ADR-0007 and ADR-0011's own "Consequences" sections describe states later resolved same-day | `docs/adr/ADR-0007.md`, `ADR-0011.md` | Protected by the project's own precedent: accepted ADRs are left as unedited historical record (explicitly stated for ADR-0001/0002 in `ADR-0007.md`'s own text). |
| The PR template's Belt-Three checkboxes don't match `CONTRIBUTING.md`'s canonical three-label table (merges Story+Vision, adds an undocumented fourth category) | `.github/PULL_REQUEST_TEMPLATE.md` | Process/template redesign, not a factual correction. |
| `docs/governance/Review-Process.md`'s CI checklist describes a Python-based CI (`compileall`, four self-tests, `pytest`) that no longer exists — actual `ci.yml` runs only markdown lint and a link check | `TerAustralis-Incognita/docs/governance/Review-Process.md` | Not in this pass's directly-scoped file list; flagged here for a future pass. |
| `CONTRIBUTING.md`'s "Reality note" says CI currently fails for path reasons — CI was retargeted, not left failing | `TerAustralis-Incognita/CONTRIBUTING.md` | Same as above. |
| `vision/README.md` itself still claims four Lumina test suites | `TerAustralis-Incognita-Code/vision/README.md` | STATUS.md now correctly flags this as a confirmed overclaim; the overclaiming file itself was deliberately left for a separate pass, stated explicitly in the STATUS.md correction. |
| `crystal-interface/README.md` and `vision-web/README.md` carry the same stale sibling-repository lists as `core/crystal-core/README.md` (only that one file was corrected) | Both files | Out of this pass's specifically-scoped correction list; same fix pattern, future pass. |
| `vision-web/README.md`'s "Related" section links `docs/architecture/Full-Stack-v0.5.md` — a path that doesn't exist locally in this repository (docs live in the umbrella) | Same file | A cross-repository reference-format question, not a simple prefix swap like the other paths in this file. |
| The Crystal Runtime specification trio disagrees with itself about implementation readiness across three documents | `Crystal-Runtime-Specification-v0.3.md`, `Runtime-Module-Interfaces.md`, `Runtime-Testing-Specifications.md` | A judgment call about which of three progressively-differing claims is "true" — not a mechanical correction; documented in `03-ARCHITECTURE.md` instead. |
| Whether PR #1 (Code repo) should be formally closed, and whether its orphaned `src/runtime/` is worth salvaging | `TerAustralis-Incognita-Code`, PR #1 | Not a documentation question at all — a maintainer decision. Recorded in `07-HISTORY.md`. |
| Whether `mythos/crystalcore-os`'s ~2,300 lines of ML code should be reclassified out of "Vision-layer" | `TerAustralis-Incognita/mythos/crystalcore-os/`, and everywhere it's described | A classification decision, not a factual correction — this archive preserves the project's own stated classification while flagging the tension (`05-KNOWLEDGE-MODEL.md`). |
