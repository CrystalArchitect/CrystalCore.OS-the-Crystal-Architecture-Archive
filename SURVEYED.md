# Surveyed

The commit of each repository that this archive's claims were read from.

This file exists because of a specific failure, twice in one session.
On 2026-07-28 this archive stated that the portfolio had six
repositories, and described `crystalcore-os-aeris-vault12` as
"`index.html`, `logo.jpg`, and a README." Both were true of the clones
they were read from. Neither was true by the time anyone read them.
Nothing in the method re-read a source before publishing a claim about
it, so a four-hour-old clone produced an archive that read as current
and was not.

A stale claim and a wrong claim are indistinguishable to a reader. This
file makes the difference visible: every claim here is a claim about a
named commit, and `.github/scripts/check-freshness.py` reports which of
those commits have since moved.

**Staleness is not an error.** The portfolio moves faster than any survey
of it, so drift here is expected and the check does not fail on it. What
it removes is the *silence* — the archive can no longer be quietly out of
date, only visibly behind.

## How to use it

    python3 .github/scripts/check-freshness.py

Re-survey a repository, then update its line. The diff on this file is
the record of what the archive was re-read against, and when.

## The survey

| Repository | Surveyed at | Read |
|---|---|---|
| `TerAustralis-Incognita` | `67d36297f9b2488e4fa72952c6d6ff468a17c831` | 2026-07-29 |
| `TerAustralis-Incognita-Code` | `26fe2364b0b7f44c8d362731fff8e26c9f366eac` | 2026-07-29 |
| `CrystalCore.OS-the-Crystal-Architecture-Archive` | `5a71054c9eb53c545c0b3a678b39d74b31f2de79` | 2026-07-29 |
| `The-Crystal-Vision` | `0f3cb8e60ab360f5c94d5772f5d2cc8903ab9959` | 2026-07-29 |
| `crystalcore` | `bd587d1ee3a55d4349f1a98ff957f8dc19a57473` | 2026-07-29 |
| `crystal-vision` | `151001d1d7acd9092a9bd654b02e2cebd25786b1` | 2026-07-29 |
| `CrystalCore.OS` | `ded3bc1116e2c1b9033c74f6c414a38383fd6ffe` | 2026-07-29 |
| `CrystalCore-AERIS` | `24bb8a9391073e106a7bf7cfee21cb80034de209` | 2026-07-29 |
| `crystalcore-os-aeris-vault12` | `a07e021a1c74a5f4264775053146d79e56388a14` | 2026-07-29 |
| `teraustralis-incognita-v2` | `8ebe7d6f0ba64b4a146a75771c604795bf30faa3` | 2026-07-29 |
| `teraustralis-v2-presentation` | `7b58f4f69f623dd68165647592ac0a7533371265` | 2026-07-29 |

## Known limits of this file

- **It records that a repository was read, not which claims came from it.**
  A moved commit means "something this archive describes may have
  changed", not "this specific Statement is now wrong". Narrowing that
  would mean per-Statement provenance, which is a larger change to the
  documentation template.
- **Only `TerAustralis-Incognita` is public.** The freshness check can
  read that one anonymously; the other ten need a checkout or
  credentials, so the check reports them as unverifiable rather than
  guessing.
