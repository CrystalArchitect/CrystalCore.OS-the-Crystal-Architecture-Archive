# Corrections

Every documentation correction this reconstruction made or identified,
in two sections: applied directly to the source file, and identified
but left for a future pass.

## Part 0 — Applied 2026-07-28 (portfolio review pass)

### The archive covered 6 of 11 repositories

- **`knowledge-base/02-REPOSITORY-MAP.md` and `00-INDEX.md`** — before:
  "all six repositories" / "the six-repository CrystalArchitect
  portfolio." After: eleven. `CrystalCore.OS`, `CrystalCore-AERIS`,
  `crystalcore-os-aeris-vault12`, `teraustralis-incognita-v2`, and
  `teraustralis-v2-presentation` were absent from the map entirely.

  This is only partly an omission. Four of the five did not exist when
  the reconstruction ran on 2026-07-24 — the three terminal repos were
  created 2026-07-29 (+1000) and `teraustralis-v2-presentation` on
  2026-07-28. The genuine miss is `teraustralis-incognita-v2`, created
  2026-07-24 14:14 UTC, which existed on the day and was not surveyed.

  The original six-repository statements were left standing and the new
  material added as its own Statement, so that what the archive asserted
  on 2026-07-24 remains readable as a claim about 2026-07-24. Correcting
  by accretion rather than by overwrite is the same discipline
  `10-PROVENANCE.md` applies to everything else here.

- **Standing risk this exposes.** The ledger has no trigger that fires
  when a repository is created. It was re-run only because a review
  happened to be commissioned. Whatever replaces that — a scheduled
  re-survey, or a rule that a new repository is not real until the map
  names it — is an open decision, recorded here rather than resolved.

### `02-REPOSITORY-MAP.md` — vault12 described from a stale clone

- Before: `crystalcore-os-aeris-vault12` listed as "`index.html`,
  `logo.jpg`, and a README", and grouped with `CrystalCore.OS` and
  `CrystalCore-AERIS` as one of "the three single-page terminal
  repositories ... variants of one another." After: recorded as the
  **specification home for Starline edge nodes and the Consent Token**,
  carrying seven technical documents.

  The clone this was measured from was taken at 20:45 UTC; the seven
  specifications landed on that repository's `main` afterwards
  (head `a09943c`). So the archive described a specification repository
  as a web page — a claim outliving the evidence it was drawn from,
  which is the precise failure this archive exists to prevent.

  Corrected in place with the error left visible and the re-read dated,
  rather than rewritten to look as though it had always been right.

- **Added, not merely corrected:** a Statement comparing the vault12
  specification against the running `consent_transport` implementation.
  They are the same protocol at the transport layer and diverge at the
  consent layer — Noise IK matches the spec exactly, while Consent
  Tokens, expiry, scope, and propagatable revocation are specified and
  not built. Filed on the maturity ladder accordingly.

- **Standing risk, same shape as the eleven-repository miss above.** Both
  errors have one cause: a clone read once and then trusted. Nothing in
  this archive's method re-reads a source before a claim about it is
  published. Recorded here rather than resolved.

### `README.md` (this repository)

- Before: 49 bytes — the repository name as an H1, no trailing newline,
  no content, in the repository that holds the portfolio's knowledge
  base and system ledger. After: a real front door pointing at
  `knowledge-base/00-INDEX.md`, `STATUS.md`, and the review reports.

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

---

## Part 5 — Applied 2026-07-28

**→ Status superseded, see Part 9.** The fixes described below were
never merged; the maintainer closed the PR carrying them. The finding
stands, the applied-status does not.

One new defect, in a class this archive had not previously audited for:
a **truth-label failure in shipped UI**, rather than in documentation.
Found in `CrystalCore-AERIS`, which no prior pass had examined.

### `CrystalCore-AERIS/index.html` and `website/index.html`

- **"Starship telemetry" was not telemetry — relabelled.** The AERIS
  desktop presented a `◈ STARSHIP` window of stat rows (`Flight 13 /
  Intact`, `Ship 40 / Indian Ocean`, `Reusability / 62%`, `Mars Goal /
  Active`) and a `◈ NEWS FEED` window of four items, both styled as
  instrument readouts. Verified by search: the page contains **zero**
  `fetch`, `XMLHttpRequest`, `WebSocket`, or `EventSource` calls. Every
  value was a literal string in the markup. The word "telemetry" and the
  "feed" framing asserted live instrumentation that does not exist.

  After: window titles are `◈ STARSHIP — SNAPSHOT` and `◈ NEWS —
  SNAPSHOT`; each body carries a visible `.snapshot-note` reading
  "Static snapshot — not live telemetry / not a live feed. Reviewed
  2026-07." The terminal's `starship` command gained the same
  disclosure in place of its reusability figure. The marketing site's
  hero line and feature card ("STARSHIP TELEMETRY / Flight status,
  reusability odds, Mars commitment") became "STARSHIP MISSION BOARD /
  ...a recorded snapshot, not a live feed."

- **Prediction-market odds presented as instrumentation — removed.**
  The `Reusability 62%` stat row, the news item `POLY — Reusability odds
  62% (+4%)`, and the terminal's `Reusability: 62%` were three
  renderings of one prediction-market figure. The `(+4%)` delta in
  particular implies a tracked series. All three deleted rather than
  relabelled: a snapshot label makes a stale fact honest, but it cannot
  make an odds quote into a measurement.

- **`#news` fixed height removed (incidental).** `height: 200px` under
  `.window { overflow: hidden }` clipped the new snapshot note. Height
  now follows content, matching `#telemetry`'s existing behaviour.
  Confirmed by headless-Chromium render before and after.

**Scope held deliberately.** Three things were *not* done:

1. The real-world flight claims (`Flight 13 / Intact`, `Ship 40 /
   Indian Ocean`, the 2028 window) were neither verified nor corrected.
   This pass had no authority to check them and did not guess; marking
   them dated and static is what makes them safe, not editing their
   content.
2. No live data source was added. The page's zero-network-calls
   property is a feature — the same property a prior pass recorded
   approvingly for `crystal-vision` — and importing a feed to justify
   the old label would have been the wrong direction of fix.
3. The `id="telemetry"` element identifier and its `showWin('telemetry')`
   handler were left alone. Internal, not user-visible; renaming risked
   the taskbar for no truth gain.

**What was verified as sound, and bounded this correction.**
**[Superseded the same day — see Part 6. The "not a pattern" claim below
was wrong: the identical defect was then found in `CrystalCore.OS`,
which this pass had not examined. The sentence is left standing rather
than edited, because the error is the point.]** The same
sweep confirmed the *accurate* claims, so the defect is narrow and not
a pattern: the Mars clock is genuinely live and arithmetically correct
(`88775.244` s is the true sol length; epoch is Perseverance's
2021-02-18 landing; it read Sol 1933 on 2026-07-28, matching
independent calculation). The terminal's ten commands all exist. In
`TerAustralis-Incognita-Code`, `core/crystal-core/consent_transport/`
is a real `Noise_IK_25519_ChaChaPoly_SHA256` implementation on audited
`cryptography` primitives with no hand-rolled cipher work, and its
selftest passes 9/9 — including `test_denied_without_consent`,
`test_revocation_takes_effect_next_request`, and
`test_forged_fragment_is_rejected_by_receiver`. `discovery.py` is
genuinely serverless (LAN UDP broadcast, no rendezvous host) and
documents its own limits accurately.

**Provenance — why this surfaced now.** The defect was found while
checking an external AI-generated report ("CrystalCore.OS — AERIS /
VAULT 12 Exploration Report," attributed to Manus AI, dated
2026-07-28) that the maintainer supplied. That report repeated
"Starship telemetry" as fact and presented shipped code, mythos, and
aspiration in a single register with no layer distinction. This is the
label defect propagating outward: an external reader, human or machine,
inherits whatever confidence the artifact projects. The correction is
therefore in the artifact, not the report — the report was accurate
about what it saw.

---

## Part 6 — Applied 2026-07-28 (later the same day)

**→ Status superseded, see Part 9.** As with Part 5, the fixes below
were never merged. The finding — the same defect in a second
repository — stands.

Part 5 was wrong about its own scope. It called the AERIS truth-label
defect "narrow and not a pattern." Within the hour the identical defect
was found in `CrystalCore.OS` — a repository Part 5 had not examined,
in an earlier and more explicit form. Part 5's sentence is left in place
with a pointer here rather than quietly edited: a corrections ledger
that silently repairs its own misjudgements is worth less than one that
shows them.

### `CrystalCore.OS/index.html` and `README.md`

- **"STARSHIP TELEMETRY" — relabelled.** Where AERIS titled the window
  `◈ STARSHIP`, this one said `◈ STARSHIP TELEMETRY` outright, over the
  same static stat rows, with the same zero network calls. Now
  `◈ STARSHIP — SNAPSHOT` with a dated `.snapshot-note`, matching AERIS.
  The `◈ NEWS FEED` window received the same treatment.

- **A liveness claim in prose — removed.** The news item read
  `POLYMARKET — Starship reusability odds: 62% (up 4% this week)`.
  "This week" asserts a tracked series outright, which is a stronger
  false claim than any AERIS carried. Deleted, along with the
  `Polymarket Reusability / 62%` stat row and the figure in the
  terminal's `starship` and `news` commands.

- **The README contained its own disproof.** Under **Features**:
  "Starship Telemetry panel (Flight 13 status + Polymarket odds)."
  Under **Roadmap**: "Live Polymarket odds API." The odds cannot be
  live if making them live is future work. The Features line now
  describes what ships; the Roadmap line is untouched, being honest as
  stated future work.

- **Sol counter arithmetic — corrected.** Unrelated to the labelling,
  found in the same sweep. The counter divided elapsed time by
  `24.65 * 3600` s (88 740 s). A Martian sol is 88 775.244 s, so the
  clock ran 35.244 s/sol fast and had accumulated 0.77 sols of error
  since the 2021-02-18 epoch — enough to read **Sol 1934** on
  2026-07-28 while `CrystalCore-AERIS`, using the correct constant,
  read **Sol 1933**. Two sibling pages describing the same moment
  disagreed by a full sol, and the one the README markets as a "Live
  Mars Clock" was the wrong one. Now uses AERIS's constant; both agree.
  Verified by headless-Chromium render.

**Correction to Part 5's reasoning, not just its facts.** Part 5 cited
the correct sol arithmetic in AERIS as evidence *bounding* the defect —
"the accurate claims are accurate, therefore the problem is local."
That inference was unsound twice over. The sol constant was not a
project-wide invariant but a per-file literal, wrong in the sibling
file. And a defect verified absent in the one repository examined says
nothing about repositories not examined. Correct labelling in one
artifact is not evidence about another; only looking is.

**Standing scope note.** Four of the eight repositories then visible had
not been audited for this defect class (`crystal-vision`,
`The-Crystal-Vision`, `TerAustralis-Incognita`,
`TerAustralis-Incognita-Code`). This is recorded as unexamined, not as
clean. Per the reasoning above, no claim is made about them either way.

**Corrected 2026-07-28: the denominator was wrong.** "Eight" was this
session's clone count, not the portfolio. A GitHub API query for
`user:CrystalArchitect` returns **eleven**, so seven repositories are
unaudited for this defect class, not four — the three additions
(`crystalcore-os-aeris-vault12`, `teraustralis-incognita-v2`,
`teraustralis-v2-presentation`) were never in this session's scope and
could not be cloned, `add_repo` requiring an approval a non-interactive
session cannot obtain.

Worth naming plainly, because it is the third instance of one error in
this file. Part 6 established that a defect verified absent in the
repositories you examined says nothing about repositories you did not.
Part 9 reduced that to "only looking is." Then the very sentence stating
the rule counted its own scope from what happened to be mounted, and got
the denominator wrong. Knowing the rule is not the same as having a
number you can trust — a scope claim needs its source named, not just
its logic sound.

One of the three matters more than the other two.
`crystalcore-os-aeris-vault12` is **public**, and Part 0 records it as
carrying the Starline edge-node and Consent Token specifications. A
public specification repository is exactly where a decorative figure
read as a specification does the most damage, and it is precisely the
class of repository this defect has favoured. Unexamined, and flagged
as the one to look at first.

---

## Part 7 — Applied 2026-07-28 (origin of the Part 5/6 defect)

**→ Status partly superseded, see Part 9.** `CONCEPT-RENDERS.md` was
never merged and does not exist. The causal account of where the defect
came from is unaffected.

Parts 5 and 6 corrected the same mislabel in two repositories without
establishing where it came from. It came from the concept art.

The Grok render used as the AERIS build reference contains a panel
captioned `STARSHIP TELEMETRY`, complete with `VEHICLE SN-42`,
`VELOCITY 27.4 KM/S`, `POWER 82%` and an ECG trace. It was implemented
faithfully. Nobody introduced the defect; a render was handed over as a
build reference and, absent any statement to the contrary, its
decorative instrumentation was indistinguishable from a specification.

The full propagation, now closed: **render → `CrystalCore.OS` →
`CrystalCore-AERIS` → both READMEs → an external exploration report
that repeated "Starship telemetry" as fact → a suggested next feature,
"add a Starship telemetry panel with animated flight-status data."**
Four hops. Each one faithful to its input.

### `CrystalCore-AERIS/CONCEPT-RENDERS.md` — new

Records each reference render, what it shows, and which elements are set
dressing. Deliberately **not** a new convention: it follows the
table-plus-truth-label format `TerAustralis-Incognita/mythos/art/
README.md` already uses, whose `eight-sovereign-laws.jpeg` row was
already doing precisely this job ("a `0.1-alpha` experiment, but it is
unwired — the companion does not actually score sessions"). The pattern
existed; it had simply never been applied to the build references.

Two findings of substance beyond the telemetry block:

- **`HANDSHAKE: XX` contradicts the implementation.** The Starline
  render's Noise panel says XX; `consent_transport/noise.py` implements
  **IK** (`PROTOCOL_NAME = b"Noise_IK_25519_ChaChaPoly_SHA256"`, "IK
  pattern only"). Different handshake, different assumptions — IK means
  the initiator already holds the responder's static key, which is what
  the manual pairing step provides; XX means neither side does. The
  panel's other three lines (`ChaChaPoly`, `X25519`, `ED25519`) are all
  correct against the code, which is exactly what lends the wrong one
  its authority. Caught before implementation this time.
- **Register determines risk.** The Starline Expansion maps show the
  same network as the render above, drawn cartographically — compass
  roses, chart framing, no uptimes, no packet rates, nothing shaped
  like a reading. Same content, no defect surface. Recorded as the
  preferred reference format, which is a cheaper fix than labelling
  every future HUD.

Also logged there, unresolved by design: two node names in those maps
(**Sunwash Atolls**, **Cinderwake Chain**) appear in no repository and
are not among the Codex's Five Keys, while the map's other five map onto
them exactly. Recorded as render-only with canon status undecided — a
maintainer's call about the mythos, not a defect for this pass to
correct. **→ Since resolved, see Part 8.**

### Added to Part 2 — identified, not applied

| Finding | File(s) | Why not applied here |
|---|---|---|
| Stale pre-split path in the art gallery's truth label: cites `src/apps/lumina/crystalcore/sovereignty_scorer.py`, which does not exist. The file is at `vision/apps/lumina/crystalcore/sovereignty_scorer.py` after the Stage 1/2 split — the same defect class Part 1 corrected in six other files. The claim itself is **accurate**: verified this pass that `sovereignty_scorer` has zero references anywhere else in the Lumina app, so it is genuinely unwired. | `TerAustralis-Incognita/mythos/art/README.md` | One-line path fix, but in a repository this pass has otherwise not touched and against which no branch is open. Batching it with the next pass on that repository costs nothing; opening a fourth branch for one line does. |

---

## Part 8 — Applied 2026-07-28 (the open canon question, answered)

Part 7's one deliberately-open item is closed. The maintainer confirmed
**Sunwash Atolls** and **Cinderwake Chain** as canon Starline nodes the
same day.

Worth recording as a distinct case, because it inverts the pattern
Parts 5–7 documented. There, the render was ahead of nothing — it
carried decoration that the code then implemented as fact. Here the
render was ahead of the *code*: it drew two real nodes the
implementation did not yet have. Same divergence, opposite direction,
and only one of the two is a defect. The rule that separates them is
not "art must match code" but "each must say which it is."

### `TerAustralis-Incognita/mythos/crystalcore-os/crystalcore_os.py` and `mythos/CRYSTALCORE-OS.md`

- **Two nodes added, both key-bearing and both sealed** behind named
  keys — Magenta Key and Ember Key — making the First Gate a seven-key
  gate. Node order follows the chart outward from Earth, which
  renumbers the `visit <n>` shortcuts; saves are unaffected, since
  `keys_held` stores names rather than indices.

- **The count is now derived rather than written.** This is the part
  that matters beyond the mythos. The gate condition was already
  `len(keys_held) == len(nodes)` and absorbed the change for free; the
  prose did not. Four strings said "five" outright and the snapshot
  listing hardcoded `keys {n}/5` — every one of them became false the
  moment the list grew. They are now spelled from `len(self.nodes)` by
  a `_count_word()` helper, so the register survives and the number
  cannot go stale again.

  That is the same defect class as the sol constant in Part 6: a value
  written into a second place, then drifting from the first. Part 6
  corrected an instance; this removes the mechanism for one file.

- **The artwork now lags the map.**
  `mythos/art/starline-network-year-3000.jpeg` renders the original
  five nodes. Labelled in `CRYSTALCORE-OS.md` as an earlier state of
  the same map rather than left to contradict the ASCII chart
  silently. Regenerating it at seven nodes is a separate decision, not
  taken here.

Verified by playthrough against a throwaway `HOME`: sealed nodes refuse
entry without their named key, all seven yield keys, the First Gate
opens at 7/7, and no stale "five" survives outside the lookup table and
its explanatory docstring. Repository CI (markdownlint + link check)
passed — the first PR in this constellation to run any CI at all, four
of the other repositories having no `pull_request` workflow.

**Naming note — raised, and resolved the same day.** The key was first
given as `Ember Ley` — "Ley", not "Key". This pass recorded it verbatim
and flagged it rather than normalising it: in a project built on
songlines, starlines and lattices, a ley line of embers is a plausible
coinage, and an author's word is not a typo merely because a more
obvious word exists nearby. The maintainer confirmed it was a slip and
the key is **`Ember Key`**, now corrected in
`crystalcore_os.py`, `CRYSTALCORE-OS.md`, and here.

Worth keeping in the ledger even though the cautious reading turned out
wrong. Asking cost one exchange; guessing wrong in the other direction
would have written an invented coinage into the canon under the
maintainer's name, and nothing in the artifact would have revealed it.
The asymmetry, not the hit rate, is what justifies the flag.

---

## Part 9 — Applied 2026-07-28 (Parts 5–7 reclassified: found, not fixed)

Parts 5–7 were written and merged while their fixes sat in open pull
requests. The maintainer then closed those pull requests without
merging. The corrections never landed, and this file — merged to `main`
— went on describing them in the past tense as applied.

That is the defect this ledger exists to catch, occurring in the ledger
itself. A corrections record that claims corrections which do not exist
is worse than no record, because it retires a finding that is still
live.

**This is a status change, not a retraction.** Every finding in Parts
5–7 was verified and remains true. Only the applied-status was wrong.

### What is now false, and what replaces it

| Part 5–7 claimed | Reality on 2026-07-28 |
|---|---|
| `CrystalCore-AERIS`: window titles **are** `◈ STARSHIP — SNAPSHOT` and `◈ NEWS — SNAPSHOT`; the `.snapshot-note` disclosure exists | Not merged. Both windows still title static content as instrumentation. |
| `CrystalCore-AERIS`: the prediction-market odds figure was **removed** in all three places | Not merged. `Reusability 62%`, the `POLY … (+4%)` news item, and the terminal figure all remain. |
| `CrystalCore-AERIS`: `#news` fixed height **removed** (incidental) | Not merged. |
| `CrystalCore.OS`: same relabelling applied; sol constant **corrected** to `88775.244` | Not merged. The counter still divides by `24.65 * 3600`, running 35.244 s/sol fast — it read **Sol 1934** against `CrystalCore-AERIS`'s correct **Sol 1933**. |
| `CrystalCore-AERIS/CONCEPT-RENDERS.md` — **new** | Does not exist. The build-boundary record was never created. |

Parts 5–7 keep their text with a `→ Status superseded` pointer at the
head of each, following the precedent Part 6 set over Part 5: the
record shows what was believed and when, rather than being rewritten to
look correct in hindsight.

### Moved to Part 2 — identified, not applied

| Finding | File(s) | Why not applied |
|---|---|---|
| Static stat and news windows titled as live instrumentation, on a page with zero network calls | `CrystalCore-AERIS/index.html`, `website/index.html` | Fix was written and reviewed, then the PR was closed unmerged by the maintainer. A closed PR is a decision, not an oversight — this stays a live finding until the maintainer chooses otherwise, and is not to be re-opened unasked. |
| Same defect, earlier and more explicit form: window titled `STARSHIP TELEMETRY`, news item claiming odds "up 4% this week" | `CrystalCore.OS/index.html`, `README.md` | Same PR-closed reason. |
| Sol counter divides by `24.65 * 3600` s where a Martian sol is `88775.244` s — 35.244 s/sol fast, already a full sol adrift from its sibling page | `CrystalCore.OS/index.html` | Same PR-closed reason. Unlike the labelling above this is a plain arithmetic error, independent of any judgment about how the page should be framed. |
| No record marks which elements of the Grok build-reference renders are decoration rather than specification | `CrystalCore-AERIS` (file was to be `CONCEPT-RENDERS.md`) | Same PR-closed reason. Part 7's causal account of the propagation stands regardless; what is missing is the artifact that would stop it recurring. |

### What Part 8 is not

Part 8 is unaffected, and its status is earned rather than assumed.
Both halves of it merged on 2026-07-28: the seven-node canon in
`TerAustralis-Incognita#70`, and its extension to the web recreation in
`TerAustralis-Incognita-Code#29`. Part 8 is therefore the one entry in
this run whose "applied" is literally true, and — since the Code repo
owns the CNAME and publishes on merge — the live site at
`www.teraustralis.com.au/crystalcore-os` now shows seven nodes too.

This paragraph needed correcting twice while being written. It first
said *"Neither is merged at the time of writing"*; #70 merged within
the hour, and #29 merged while that sentence was being fixed. The rule
below, bitten twice by its own author inside one pass — which is the
right outcome, and the reason the wording now names merge commits and
dates rather than describing a PR's mood. **State what merged and
when. A sentence about what is currently open is written to rot.**

**A rule this pass earned.** An entry in this file should not say
"applied" while its change is in an unmerged pull request. Applied
means merged. Until then the honest word is *proposed* — Parts 5–8 were
all written in the past tense before their PRs landed, and three of
them turned out to be wrong.
