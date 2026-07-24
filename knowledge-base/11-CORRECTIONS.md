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
| `bridge.py`'s Lumina-path resolves to a nonexistent directory (`core/apps/` instead of `vision/apps/`); `recall`/`teach`/`message` crash at runtime | `TerAustralis-Incognita-Code/core/crystalcore/bridge.py` | Code-behavior fix, not a documentation fix — out of scope for a documentation-only reconstruction. **→ Since resolved, see Part 3.** |
| `gate.py`'s docstring claims four consent checks; only two (approval, permission) are implemented | Same file, `gate.py` | Same as above — fixing this "right" means either building the missing checks or downgrading a security claim, both real engineering decisions, not doc edits. **→ Since resolved, see Part 3.** |
| No requirements/toml/cfg file declares the `mcp` package `bridge.py` imports | `TerAustralis-Incognita-Code` (repo-wide) | Packaging/dependency fix, not documentation. **→ Since resolved, see Part 3.** |
| 96 files carry `SPDX-License-Identifier: Apache-2.0` headers under a CC BY-NC-ND 4.0 root `LICENSE` | `TerAustralis-Incognita-Code`, 96 files | Mechanically identical to a fix ADR-0009 already executed once — its own text records batch-correcting 97 `src/*` files to `CC-BY-NC-ND-4.0`, later relocated to `core/`+`vision/` by the repo split — but sized for its own dedicated, scripted pass, not folded into this session's line-edit budget. **→ Since resolved, see Part 4.** |
| ADR-0007 and ADR-0011's own "Consequences" sections describe states later resolved same-day | `docs/adr/ADR-0007.md`, `ADR-0011.md` | Protected by the project's own precedent: accepted ADRs are left as unedited historical record (explicitly stated for ADR-0001/0002 in `ADR-0007.md`'s own text). |
| The PR template's Belt-Three checkboxes don't match `CONTRIBUTING.md`'s canonical three-label table (merges Story+Vision, adds an undocumented fourth category) | `.github/PULL_REQUEST_TEMPLATE.md` | Process/template redesign, not a factual correction. **→ Since resolved, see Part 4.** |
| `docs/governance/Review-Process.md`'s CI checklist describes a Python-based CI (`compileall`, four self-tests, `pytest`) that no longer exists — actual `ci.yml` runs only markdown lint and a link check | `TerAustralis-Incognita/docs/governance/Review-Process.md` | Not in this pass's directly-scoped file list; flagged here for a future pass. **→ Since resolved, see Part 4.** |
| `CONTRIBUTING.md`'s "Reality note" says CI currently fails for path reasons — CI was retargeted, not left failing | `TerAustralis-Incognita/CONTRIBUTING.md` | Same as above. **→ Since resolved, see Part 4.** |
| `vision/README.md` itself still claims four Lumina test suites | `TerAustralis-Incognita-Code/vision/README.md` | STATUS.md now correctly flags this as a confirmed overclaim; the overclaiming file itself was deliberately left for a separate pass, stated explicitly in the STATUS.md correction. **→ Since resolved, see Part 3.** |
| `crystal-interface/README.md` and `vision-web/README.md` carry the same stale sibling-repository lists as `core/crystal-core/README.md` (only that one file was corrected) | Both files | Out of this pass's specifically-scoped correction list; same fix pattern, future pass. **→ Partially resolved, see Part 4 — re-verification found `vision-web/README.md` did not actually have this defect; this row was itself imprecise.** |
| `vision-web/README.md`'s "Related" section links `docs/architecture/Full-Stack-v0.5.md` — a path that doesn't exist locally in this repository (docs live in the umbrella) | Same file | A cross-repository reference-format question, not a simple prefix swap like the other paths in this file. **→ Since resolved, see Part 4.** |
| The Crystal Runtime specification trio disagrees with itself about implementation readiness across three documents | `Crystal-Runtime-Specification-v0.3.md`, `Runtime-Module-Interfaces.md`, `Runtime-Testing-Specifications.md` | A judgment call about which of three progressively-differing claims is "true" — not a mechanical correction; documented in `03-ARCHITECTURE.md` instead. |
| Whether PR #1 (Code repo) should be formally closed, and whether its orphaned `src/runtime/` is worth salvaging | `TerAustralis-Incognita-Code`, PR #1 | Not a documentation question at all — a maintainer decision. Recorded in `07-HISTORY.md`. |
| Whether `mythos/crystalcore-os`'s ~2,300 lines of ML code should be reclassified out of "Vision-layer" | `TerAustralis-Incognita/mythos/crystalcore-os/`, and everywhere it's described | A classification decision, not a factual correction — this archive preserves the project's own stated classification while flagging the tension (`05-KNOWLEDGE-MODEL.md`). |

---

## Part 3 — Applied after this archive's first publication (2026-07-24)

Four Part 2 items were resolved the same day this archive first
published, and their rows above are annotated accordingly. The Part 2
table itself is preserved unchanged as the record of what the first
pass deliberately declined to do and why — this section records what
happened next, with evidence, per `12-CONTRIBUTING.md`'s dated-note
convention.

- **`bridge.py`'s Lumina path — fixed.** PR #8
  (`TerAustralis-Incognita-Code`, merged 2026-07-24) recomputes
  `LUMINA_PKG_DIR` from the repo root into
  `vision/apps/lumina/crystalcore/`. `recall`/`teach`/`message` no
  longer crash. A regression guard in the new
  `core/crystalcore/selftest.py` fails loudly if the path ever stops
  resolving.
- **`gate.py`'s docstring — corrected.** Same PR. The resolution
  chosen was "make the docstring true": it now states the two checks
  `check()` actually implements (approval, tool-permission) and
  records, in the docstring itself, that scope/provenance were
  documented as intended but never implemented — no surviving spec
  defines either, so building them remains an open maintainer design
  task, not something this fix invented. The one other file asserting
  the four-check claim (`vision/site/src/content/ARCHITECTURE.md`,
  "Reality (Built)" table) was corrected in the same PR.
- **The `mcp` dependency — declared.** Same PR. New
  `core/crystalcore/requirements-bridge.txt` (the filename the
  module's own README already instructed users to install), matching
  the sibling `requirements-consenttransport.txt` convention. CI now
  installs it and runs the CrystalBridge selftest on every push.
- **`vision/README.md`'s four-test-suite overclaim — fixed, by the
  maintainer independently.** PR #7 (`TerAustralis-Incognita-Code`,
  commit `08fa2cc`, merged 2026-07-24, shortly before PR #8): the
  README now states the one real core suite and marks the other three
  as not-yet-existing. Attributed accurately — this was the
  maintainer's own pass, not this archive's session.

---

## Part 4 — Applied in this pass (2026-07-24, later still)

Six more Part 2 rows resolved, plus one new, unscoped discovery this
pass made and resolved: a second knowledge base found living in the
umbrella's `docs/`, colliding with this archive's own canonical claim.

- **The 96 (now 97 — see below) stale SPDX headers, `TerAustralis-
  Incognita-Code` — fixed.** Reapplied the exact fix ADR-0009 already
  documented once: `SPDX-License-Identifier: Apache-2.0` →
  `SPDX-License-Identifier: CC-BY-NC-ND-4.0`, changing only the
  identifier value, on every affected line, across all three comment
  styles present (`#`, `//`, `<!-- -->`). Verified 97 → 0 stale
  occurrences and spot-checked diffs across `.py`/`.js`/`.svelte` files
  to confirm nothing else in any file changed. The 97th file was this
  archive's own prior-session addition, `core/crystalcore/selftest.py`,
  which had copied the stale pattern from its siblings without
  question — caught and fixed in the same sweep, not exempted for
  being this session's own work.
  **Precision on the count:** ADR-0009's original 97-file batch was
  scoped to `src/apps/`, `src/crystal-core/`, `src/crystalcore/`,
  `src/crystalcore-os/`, `src/node/`, `src/sdk/`, `src/site/` — all
  relocated to `core/`+`vision/` by the Stage 1/Stage 2 repo split.
  The umbrella's own remaining straggler
  (`mythos/crystalcore-os/crystalcore_os.py`, also fixed this pass) was
  never part of that batch — a different path (`mythos/`, not
  `src/crystalcore-os/`) — so it is an independent, never-remediated
  instance of the same defect class, not "the one file ADR-0009
  missed."
- **PR template ↔ `CONTRIBUTING.md` Belt-Three mismatch — reconciled.**
  `.github/PULL_REQUEST_TEMPLATE.md`'s merged "Story / Vision" checkbox
  split into two, matching `CONTRIBUTING.md`'s three canonical rows
  exactly. `CONTRIBUTING.md`'s table gained a fourth row, "Docs /
  governance / process," matching what the template already treated as
  a real, distinct category in practice — repository reality (the
  template's actual use) overriding stale documentation (the table),
  the same principle this whole reconstruction applies elsewhere.
- **`docs/governance/Review-Process.md` and `CONTRIBUTING.md`'s stale
  CI descriptions — corrected.** Both described a Python-based CI
  (`compileall`, four self-tests, `pytest`) that no longer runs in the
  umbrella at all — confirmed directly: `TerAustralis-Incognita`'s own
  `ci.yml` runs markdown-lint and a link-check only. Both now state
  this plainly and point at `TerAustralis-Incognita-Code`'s own
  `ci.yml` for the actual Python suites (5 self-tests, 2 pytest suites),
  since Stage 1/2 moved that code there. The dead
  `scripts/maintenance/check.sh` reference (confirmed absent from the
  umbrella entirely) was dropped from both in the same edit.
- **`vision/apps/crystal-interface/README.md`'s sibling-repository
  list — corrected.** Matched to the accurate six-repo block already
  written into `core/crystal-core/README.md` in the original pass.
  **`vision-web/README.md` needed no change** — re-verification found
  it never carried this defect (it has no sibling-repo-identity block
  at all, only a small in-repo app-surface table; its own path
  references were already corrected in Part 1). Part 2's row grouping
  these two files together was itself imprecise on this point — noted
  there directly rather than silently fixing a file that wasn't
  broken, per this archive's own standard for correcting itself.
- **`vision-web/README.md`'s dead `Full-Stack-v0.5.md` link — fixed.**
  Confirmed the file exists, but only in the umbrella repo. Converted
  the same-repo-relative path to a working cross-repo GitHub URL,
  matching the pattern `core/README.md` already established for the
  same kind of reference.

### The competing knowledge base — discovered and reconciled

While scoping this pass, found that umbrella PRs #60/#61 (merged,
branch `claude/repo-structure-boundaries-xddagp` — a different,
uncoordinated session, not this one) had created **seven new files
directly under `TerAustralis-Incognita/docs/`**: `ARCHITECTURE.md`,
`GOVERNANCE.md`, `REPOSITORIES.md`, `TECHNICAL-FINDINGS.md`,
`IP-LICENSING.md`, `OPEN-DECISIONS.md`, `TIMELINE.md`. These cover
nearly the same ground as this archive's own `knowledge-base/` — same
underlying evidence (the same ADRs, the Incognita Rule, the 2026-07-23
architecture survey), a different per-section template, a different
location — and `docs/README.md` (PR #61) indexed the set as "the
canonical knowledge base," the same word this archive's own
`00-INDEX.md` uses for itself. Two artifacts claiming the same role is
not a new problem for this project: it is a third instance of the
uncoordinated-parallel-session collision pattern this archive already
documents twice (the licensing chaos in `08-DESIGN-DECISIONS.md`; the
Crystal Runtime episode in `07-HISTORY.md`).

**Resolution:** this archive's own `knowledge-base/` remains canonical
when the two disagree — not a new judgment call, but this archive's
own prior, explicit decision (recorded in `00-INDEX.md` from the outset)
applied to a fact pattern that came later. Independent corroboration
arrived from an unrelated third source the same day: `REPO-ARCHAEOLOGY-
2026-07-24.md` (a git-object-level survey of all six repositories,
committed to this repository's root by yet another uncoordinated
session, branch `claude/repo-archaeology-prompt-b3niko`) states plainly
that no single repository is canonical for everything, but for this
specific role names this repository directly: *"System ledger /
meta-record → `CrystalCore.OS-the-Crystal-Architecture-Archive`...
documents the other five; no unique application content."* Both sets
are preserved, neither deleted: a dated reconciliation note was added to
`docs/README.md` and to the top of each of the 7 files, stating the
relationship and pointing back here. Reconciling the two into one
structure is future work, not done in this pass — recorded as a new
Part 2-style open item below rather than silently left implicit.

Everything else in Part 2 remains open as written, plus one addition:

| Finding | File(s) | Why not applied here |
|---|---|---|
| Two independently-built knowledge bases now coexist (this archive's `knowledge-base/`, and `TerAustralis-Incognita/docs/`'s 7-file set) — reconciled with pointer notes this pass, but not merged into one structure | `TerAustralis-Incognita/docs/*.md` (7 files), this archive's `knowledge-base/` | A real information-architecture decision (which document owns which content long-term) — bigger than a documentation correction, and not something to settle unilaterally given this archive's own repeated deference to maintainer judgment on structural questions. |
