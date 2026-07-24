# STATUS

Last updated: 2026-07-24

Full portfolio knowledge-base reconstruction this pass:
`knowledge-base/00-INDEX.md` (this repo).

This file describes the state of the system, not the ambition of
the system.

## Running
Executes, or can be opened and used by someone other than me.

- Crystal Core self-tests (four suites, 51/51) and Lumina core tests
  (16/16) — pass on a fresh clone of TerAustralis-Incognita-Code,
  verified 2026-07-24. Detail in that repo's STATUS.md.
- The two demo shells, the engine's own interface page, and the
  story-library prototype render in a headless browser, verified
  2026-07-24 — see the per-repo ledgers.

## Built, not currently running
Code exists and ran previously. No machine to run it on.

- CrystalCore Python package (Clementine on Ollama) — confirmed
  on GitHub in The-Crystal-Vision repo (not archived — see per-repo
  ledger below) at crystalcore-app/crystalcore/. Has tests,
  requirements.txt, .env.example. Ran on my previous laptop; that
  hardware is gone. Code is safe. Needs a machine with Python + Ollama.

## Exists as a document
Written, readable, no execution involved.

- Symbolic Lexicon v0.1
- Master Structure v0.2 (registers, document tree)
- Timeline + Evolution Map v0.1
- Sovereign Node Mesh framework v1.1

## Designed, not built
Specified enough that someone could build it. Nobody has.

- Archive workflows
- Knowledge graph
- Visual artifact indexing
- Agent integration layer

## Concept only
Named. Not specified.

- Expanded Crystal Architecture models
- Interface designs
- Additional symbolic systems

## Per-repo ledger
Added 2026-07-24. One line of state per repository; detail lives in
each repo's own STATUS.md where one exists.

- TerAustralis-Incognita (umbrella) — canon, governance, mythos,
  research. CI green with honestly shrunken scope; Pages deploys
  nothing since src/site moved out; the dbt warehouse is built, not
  running. Has its own STATUS.md.
- TerAustralis-Incognita-Code — the engine and the vision app. All
  four core suites and Lumina's core tests pass on a fresh clone; CI
  (ci.yml) runs those suites on push — corrected 2026-07-24, this line
  previously said "no CI." deploy.yml targets the site but GitHub
  Pages isn't switched on for that repo yet (manual admin step, still
  pending). Has its own STATUS.md.
- CrystalCore.OS-the-Crystal-Architecture-Archive — the system
  ledger. This file. Also now holds the full knowledge-base/
  reconstruction (see pointer above).
- The-Crystal-Vision (not archived — corrected 2026-07-24; live GitHub
  metadata shows archived:false, contradicting this line's prior
  "archived 2026-07-18, read-only." The umbrella's own 2026-07-24
  charter records whether to archive the three repos below as a
  deliberately open decision, not a settled fact) — holds crystalcore
  v0.13.4 at crystalcore-app/crystalcore/ (verified 2026-07-24: imports
  cleanly, 19/20 offline tests) and the raw laptop snapshot with
  RECOVERY-STATUS.md. Mirrors of that material also sit in the
  umbrella's archive/.
- crystalcore (Songline pack; not archived — same correction as above,
  was wrongly marked "archived 2026-07-18, read-only") — never
  contained the package in any commit (full-history search, 2026-07-24).
- crystal-vision (not archived — same correction, private) — audited
  2026-07-24: functional static Vercel demo, v0.5.1, Apache-2.0, zero
  network calls, zero secrets. Two minor cosmetic defects (a dead
  element-id reference, one footer link that 404s past the deploy
  tree). No longer the blank on this list — detail in
  knowledge-base/02-REPOSITORY-MAP.md.

## Known unknowns

- Which repo is canonical? Six have overlapping names. The
  Per-repo ledger above now maps what each one holds; naming the
  canonical one is a decision still to be made, not a fact to
  verify.
- What's in local-snapshot-2026-07-17/? Resolved 2026-07-24: the
  last capture from the lost laptop, preserved in
  The-Crystal-Vision — updated docs, clementine.py and
  clementine_web.py, two generations of the crystalcore/ package
  including the complete v0.13.4 bytecode rescue (see its
  RECOVERY-STATUS.md), the teraustralis.com.au site files, the
  seven-sisters pack, .env.example, and Windows launchers.
  Credentials and chat history were deliberately excluded.
- Does the package still run on a fresh machine? Partly verified
  2026-07-24: on a fresh Linux machine it imports cleanly and 19
  of 20 offline tests pass (the one failure is a stale version
  string in a test, not the code). A full Clementine session
  with Ollama is still untested.
- Which workflows produce measurable value? Untested.
- teraustralis-final.html — no longer listed under Running (moved
  here 2026-07-24). Full six-repo search this session — filename and
  content-grep, including archive/, local-snapshot directories, and
  git history — found zero copies anywhere in the portfolio.
  Confirmed absent, not merely unconfirmed-location; the original
  render observation isn't disproven, but nobody today can open or
  use this file. Detail in knowledge-base/07-HISTORY.md.
