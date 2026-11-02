# physiboard-dict

Downloadable dictionary assets for [PhysiBoard](https://github.com/brobata/physiboard).

The keyboard ships twelve languages inside the APK. This repository hosts the full set as
release assets, so a language can be added or updated without an app release.

## Layout

Two manifests, both served over GitHub Pages:

- `dicts-manifest-pbd.json` — PhysiBoard 3.7 and later. Points at release `pbd-1`: one
  `<lang>_base.dict` per language in the `.pbd` format PhysiBoard 3.x reads.
- `dicts-manifest.json` — PhysiBoard 2.x. Points at release `1`, the older headerless format.
  Left unchanged so 2.x installs keep working.

Every asset is verified by the app against the SHA-256 in its manifest.

Filenames follow `<lang>_base.dict`. That convention is parsed by the app in several places, so
it is a contract, not a style choice.

## Provenance

### Release `pbd-1` (3.x)

Built with `scripts/build_dictionary.py` in the PhysiBoard repository from the
[wordfreq](https://github.com/rspeer/wordfreq) frequency data (CC BY-SA 4.0), up to 80,000 words
per language. German, Spanish, French, Italian, Dutch, Portuguese and Russian are also filtered
through the [pyspellchecker](https://github.com/barrust/pyspellchecker) word lists (MIT) and are
listed as spell-checked. The others are frequency-only, listed as "(Basic)": they can contain
common misspellings, which the keyboard will then treat as real words. English ships inside the
app. These word lists are released under CC BY-SA 4.0.

### Release `1` (2.x)

These are frequency-list derivatives of the
[Leipzig Corpora Collection / Wortschatz Leipzig](https://wortschatz.uni-leipzig.de/),
distributed under CC-BY 3.0, with project-maintained filtering, truncation and normalization.

Release `1` is a byte-for-byte mirror of
[palsoftware/pastiera-dict](https://github.com/palsoftware/pastiera-dict) release 12. Every asset
was verified against the upstream published SHA-256 before upload; no bytes were altered, so the
corpus and its attribution are unchanged. PhysiBoard is a GPLv3 fork of Pastiera by Andrea
Palumbo (PalSoftware) and contributors.

Full attribution lives in `THIRD_PARTY_NOTICES.md` in the PhysiBoard repository.

## Licence

GPL-3.0, matching upstream. The corpus data carries its own CC-BY 3.0 attribution terms.
