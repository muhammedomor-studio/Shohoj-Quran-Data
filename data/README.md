# Data package plan

This folder is intentionally a placeholder in v1. Do not treat the app as a complete Quran reader yet.

Planned data files (to add only after source/licence verification):
- `quran-arabic.json` — verified Arabic ayah text and verse identifiers
- `quran-bangla.json` — Bengali translation with translator/source metadata and redistribution permission
- `audio-manifest.json` — reciter, surah number, file URL, file size, SHA-256, and licence/source notes

Important: this v1 starter does NOT yet include complete ayah text, Bengali translation, Mishary Al-Afasy audio, or an operational downloader. These need to be implemented and tested before calling it the final app. Adding files to GitHub alone cannot make this current build display them unless the app has code to fetch and parse them.
