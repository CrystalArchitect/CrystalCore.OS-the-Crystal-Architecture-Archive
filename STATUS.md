# STATUS

Last updated: 2026-07-24

This file describes the state of the system, not the ambition of
the system.

## Running
Executes, or can be opened and used by someone other than me.

- teraustralis-final.html — renders in a browser. Deployment
  unconfirmed.

## Built, not currently running
Code exists and ran previously. No machine to run it on at present.

- CrystalCore Python package (Clementine on Ollama) — in the
  archived The-Crystal-Vision repo (crystalcore-app/). Ran on my
  previous laptop; that hardware is gone. Not a code fault.

## Exists as a document
Written, readable, no execution involved. Real work — just not
software.

- Symbolic Lexicon v0.1
- Master Structure v0.2 (registers, document tree)
- Timeline + Evolution Map v0.1
- Sovereign Node Mesh framework v1.1

## Designed, not built
Specified in enough detail that someone could build it. Nobody has.

- Archive workflows
- Knowledge graph
- Visual artifact indexing
- Agent integration layer

## Concept only
Named. Not specified.

- Expanded Crystal Architecture models
- Interface designs
- Additional symbolic systems

## Known unknowns

- What technical form should CrystalCore.OS take, if any?
- Which parts need software rather than documents?
- Which workflows produce measurable value? Untested.
- Did the working crystalcore/ package actually get pushed before
  the laptop was lost? Resolved 2026-07-24: yes. crystalcore
  v0.13.4 (all 12 modules, ollama.py included) is in the archived
  The-Crystal-Vision repo at crystalcore-app/crystalcore/, last
  pushed 2026-07-17. Seven modules were rescued from .pyc
  bytecode before the machine was reset; the raw snapshot and its
  RECOVERY-STATUS.md sit alongside in local-snapshot-2026-07-17/.
  Re-verified 2026-07-24 on fresh hardware: the package imports
  cleanly and 19 of 20 offline tests pass (the one failure is a
  stale "0.13.3" version assertion, not a code fault). Not
  pushed: Clementine's local memory and profiles, gitignored by
  design. There is no repo named CrystalcoreOS; the crystalcore
  repo (Songline pack) never contained the package.
