# Provenance

Git-history mechanics, and this reconstruction's own verification
methodology, transparently — including the one mistake it caught and
fixed in itself.

## Statement — Confirmed provenance tags

Two checkpoint tags exist, marking the frozen-provenance repositories'
hand-off point, and were fetched and independently confirmed to exist
during this reconstruction (not merely cited from a document):

- `vision-safe-2026-07-17` on `The-Crystal-Vision`.
- `crystalcore-safe-2026-07-17` on `crystalcore`.

**Status: Implemented** (verified by direct `git fetch --tags` and
`git tag -l`, this session).

### Evidence
- Direct shell commands, this session: `git fetch origin --tags` in
  each repository's local clone, followed by `git tag -l`, both tags
  returned.

### Historical Notes
None.

### Cross References
`02-REPOSITORY-MAP.md`.

---

## Statement — Migration provenance, exact

Both `core/` and `vision/` in `TerAustralis-Incognita-Code` were
imported from the umbrella repository's branch
`claude/crystalcore-boot-visual-jau1bk`, at commit `32692fd`. This
archive independently confirmed the branch/commit correspondence: the
umbrella repository's branch list shows `claude/crystalcore-boot-
visual-jau1bk` at sha `32692fd9b103bd11875fc362a6fcac01b4b65258` — the
7-character prefix matches exactly what both `core/README.md` and
`vision/README.md` in the Code repo cite as their import source.

**Status: Implemented.**

### Evidence
- `TerAustralis-Incognita-Code/core/README.md` and `vision/README.md`:
  "Imported from the umbrella repository's branch
  `claude/crystalcore-boot-visual-jau1bk` @ `32692fd`."
- GitHub API, `list_branches` on `TerAustralis-Incognita`: confirms the
  exact sha match.

### Historical Notes
None.

### Cross References
`07-HISTORY.md`.

---

## Statement — The same-day history rewrite

The umbrella repository's git history was mechanically rewritten on
2026-07-23 as part of executing the repository split. This is stated
directly by the project's own commit record, not inferred by this
reconstruction.

**Status: Historical.**

### Evidence
- Commit message, umbrella repo: "Survey correction: the repo split
  landed via a same-day history rewrite."
- Corroborating: the Crystal Runtime episode (`07-HISTORY.md`) — a
  commit confirmed to exist via GitHub's API is unreachable from the
  umbrella's current `main` via local `git log --all`, consistent with
  exactly this kind of rewrite having occurred after that commit
  merged.

### Historical Notes
Applies to every 2026-07-23 date cited in this archive: these are the
project's own claims about its history, not independently re-derivable
original chronology.

### Cross References
`07-HISTORY.md`.

---

## Statement — This reconstruction's verification methodology

Three parallel research agents performed full-text reads (ADRs and
governance documents; the Seven Sisters corpus and vision/philosophy
documents; formal architecture specifications and component READMEs
across both the umbrella and Code repositories) — never skimming,
always citing file:line. This was supplemented by direct verification:
full dated git history across all six repositories (re-checked when an
initial pull was found incomplete), live GitHub metadata for all six
repositories, every branch's actual pull-request status (fetched via
the API's single-PR endpoint, not just a list dump — see below), two
provenance tags fetched and confirmed, and a full commit-level
reconstruction of the Crystal Runtime episode.

**Status: Implemented** (this is a description of process, itself
checkable against the specific citations throughout this archive).

### Evidence
This archive's own citations, throughout.

### Historical Notes

**One self-caught mistake, corrected before being trusted, disclosed
here per this archive's own evidence standard:** an early pass at
checking pull-request status for several umbrella-repository branches
parsed a bulk `list_pull_requests` JSON dump with a script that
mis-read the `merged` field, concluding six branches were "closed,
unmerged" (i.e., abandoned). A direct, single-PR fetch
(`pull_request_read`, method `get`) on two of those six returned
`"merged":true` — contradicting the bulk-parse result. All six were
then re-checked individually via the reliable method; all six were in
fact merged, not abandoned. The bulk-list method was not used again for
anything load-bearing in this archive.

**A second, related catch:** this reconstruction's local clone of the
umbrella repository was found to be three merged pull requests behind
`origin/main` (missing PR #56, #57, #58) partway through the session —
discovered when a fetched pull request's metadata (`merged_at`
timestamp) postdated everything visible in the local clone's `git log`.
The local clone was fast-forwarded (`git merge --ff-only origin/main`)
and the affected content re-read directly before any of it was cited in
this archive. This matters concretely: PR #58 rewrote the exact
"Repositories, today" section this archive's `02-REPOSITORY-MAP.md`
quotes — had this gone uncaught, that document would have cited a
stale, already-superseded table.

Neither mistake reached this archive's final content. Both are recorded
because the project's own standard — "a model agreeing with you is not
evidence" — applies equally to this reconstruction's own process, and a
caught-and-fixed error disclosed is more credible than a process
presented as having been flawless throughout.

### Cross References
`00-INDEX.md` (the standard being upheld), `02-REPOSITORY-MAP.md`.

---

## Statement — The Crystal Runtime and PR #1 forensic evidence, raw

For independent re-verification: umbrella repo commit
`b09672d454d124b333abbeeb0c7265f6603c83dc` (PR #43, merged
2026-07-23T08:14:29Z). Code repo PR #1, branch
`claude/teraustralis-incognita-import-g63jm9`, base sha
`075f2ea2fb5bec98cff7ab30104711a670249ce9`, opened
2026-07-23T09:44:46Z, still open. Diff against `main`: 401 files
changed, 21,173 insertions(+), 1,130 deletions(-). Both facts are
independently reproducible by any reader with repository access, using
the exact commands below.

**Status: Implemented** (as a documented, reproducible methodology).

### Evidence
```
# Confirm the Crystal Runtime commit exists but is unreachable from main:
git log --all --oneline -- '*runtime*'   # (in the umbrella repo — returns nothing)
# vs. GitHub API: pull_request_read(method=get_commits, pullNumber=43)
#   → returns commit b09672d, with full file diff

# Confirm PR #1's unique content on the Code repo:
git fetch origin claude/teraustralis-incognita-import-g63jm9
git diff --stat main origin/claude/teraustralis-incognita-import-g63jm9
git ls-tree -r --name-only origin/claude/teraustralis-incognita-import-g63jm9 -- src/runtime/
git ls-tree -r --name-only origin/claude/teraustralis-incognita-import-g63jm9 -- packages/
```

### Historical Notes
None.

### Cross References
`07-HISTORY.md`.
