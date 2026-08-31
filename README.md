# physiboard-dict

Downloadable dictionary assets for [PhysiBoard](https://github.com/brobata/physiboard).

The keyboard ships twelve languages inside the APK. This repository hosts the full set as
release assets, so a language can be added or updated without an app release.

## Layout

- `dicts-manifest.json` — served over GitHub Pages; the app reads it to list and fetch dictionaries.
- Release assets — one `<lang>_base.dict` per language, verified by the SHA-256 in the manifest.

Filenames follow `<lang>_base.dict`. That convention is parsed by the app in several places, so
it is a contract, not a style choice.

## Provenance

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
