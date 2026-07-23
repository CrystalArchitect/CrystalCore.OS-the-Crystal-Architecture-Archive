# STATUS

Last updated: 2026-07-24

This file describes the state of the system, not the ambition of
the system.

## Running
Executes, or can be opened and used by someone other than me.

- teraustralis-final.html — renders in a browser. Deployment
  unconfirmed. 2026-07-24 (multi-repo pass): the file is not in either
  TerAustralis repo, the umbrella's archive/ included — if it survives
  anywhere it is in an archived repo, none of which were attached to
  that session. Its location is now a known unknown; the render claim
  stands on the original verification.
- Crystal Core self-tests (four suites, 51/51) and Lumina core tests
  (16/16) — pass on a fresh clone of TerAustralis-Incognita-Code,
  verified 2026-07-24. Detail in that repo's STATUS.md.
- The two demo shells, the engine's own interface page, and the
  story-library prototype render in a headless browser, verified
  2026-07-24 — see the per-repo ledgers.

## Built, not currently running
Code exists and ran previously. No machine to run it on.

- CrystalCore Python package (Clementine on Ollama) — confirmed
  on GitHub in the archived The-Crystal-Vision repo at
  crystalcore-app/crystalcore/. Has tests, requirements.txt,
  .env.example. Ran on my previous laptop; that hardware is
  gone. Code is safe. Needs a machine with Python + Ollama.

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
  four core suites and Lumina's core tests pass on a fresh clone; no
  CI; the site source builds but nothing deploys it. Has its own
  STATUS.md.
- CrystalCore.OS-the-Crystal-Architecture-Archive — the system
  ledger. This file.
- The-Crystal-Vision (archived 2026-07-18, read-only) — holds
  crystalcore v0.13.4 at crystalcore-app/crystalcore/ (verified
  2026-07-24: imports cleanly, 19/20 offline tests) and the raw
  laptop snapshot with RECOVERY-STATUS.md. Mirrors of that material
  also sit in the umbrella's archive/.
- crystalcore (Songline pack; archived 2026-07-18, read-only) —
  never contained the package in any commit (full-history search,
  2026-07-24).
- crystal-vision (archived 2026-07-18, read-only, private) — contents
  never audited by any ledger pass. The one true blank on this list.

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
- Where teraustralis-final.html actually lives. Not in either
  TerAustralis repo (2026-07-24 search, archives included); the
  archived repos were not attached to that session to check. Until
  someone looks there, the ledger's oldest "Running" line rests on
  the original render alone.
