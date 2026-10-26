# Shohoj Quran — separate data repository package

Upload the contents of this folder to a separate GitHub repository named exactly `Shohoj-Quran-Data` under `muhammedomor-studio`, on the `main` branch:

`https://github.com/muhammedomor-studio/Shohoj-Quran-Data`

The connected Android app fetches this fixed manifest URL:
`https://raw.githubusercontent.com/muhammedomor-studio/Shohoj-Quran-Data/main/manifest.json`

## Important status
This is a repository scaffold, not complete Quran text. The bundled `quran-ar.json` is deliberately empty for every surah because the source download could not be retrieved in this environment. The app validates that the file contains all 114 surahs and exactly 6,236 non-empty ayahs, so it will refuse this placeholder. Do not mistake it for usable Quran text.

## Required quran-ar.json schema
Use a complete, verified Arabic text source, preserve the exact text verbatim, and ensure all 6,236 ayahs are included in surah order. Example shape (example text is only a schema illustration, not Quran data):

```json
{
  "schema_version": 1,
  "source": "Tanzil Project",
  "surahs": [
    { "number": 1, "ayahs": [
      { "number": 1, "text": "... exact source ayah text ..." }
    ]}
  ]
}
```

For every surah, include `number` and an `ayahs` array. Each ayah needs its 1-based `number` and non-empty `text`. The full dataset must contain 114 surahs and 6,236 ayahs. Keep ayahs in the original order.

## After adding real data
1. Replace `quran-ar.json` with the complete verified file.
2. Compute its SHA-256 hash and place it in `manifest.json` at `files.quran_ar.sha256`.
3. Commit both files.
4. In the app, open Settings → “আরবি কুরআন ডাউনলোড / আপডেট”.

The app accepts an empty hash temporarily for setup, but a real SHA-256 is strongly recommended before public release.

## Attribution
See `ATTRIBUTION.txt`. Tanzil text must remain unchanged, be attributed to Tanzil, and link to https://tanzil.net/. Check the current official terms before distribution.
