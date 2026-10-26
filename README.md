# সহজ কোরআন (Shohoj Quran) — Android project

এই প্রজেক্টে ডেটা GitHub-এ আলাদা করে হোস্ট করতে হয় না। অ্যাপটি অনলাইনে Al Quran Cloud-এর public REST API ব্যবহার করে:

- Surah metadata: `https://api.alquran.cloud/v1/surah`
- Arabic + Bengali translation: `https://api.alquran.cloud/v1/surah/{number}/editions/quran-uthmani,bn.bengali`
- Arabic fallback: `https://api.alquran.cloud/v1/surah/{number}`
- Mishary Alafasy surah audio: `https://cdn.islamic.network/quran/audio-surah/128/ar.alafasy/{number}.mp3`

API docs: https://alquran.cloud/api
Audio CDN docs: https://alquran.cloud/cdn

## Features

- Bengali UI and custom Shohoj Quran logo/splash screen
- Home, Quran, Bookmarks, Settings and Donation pages
- Light/dark theme saved on device
- Surah search and animated up/down scroll controls
- Surah reader retrieves Quran text online and caches opened surah JSON in app-private storage
- Mishary Alafasy audio streaming
- Donation guidance page (does not collect money)
- GitHub source-code link in Settings
- GitHub Actions workflow builds a debug APK

## Important limitations

- Network access is needed to fetch a surah the first time and to stream audio. Previously opened surahs may be available offline from the app cache. This is not a complete offline Quran download manager.
- Audio is streamed, not downloaded for offline listening.
- Bengali translation availability depends on the API edition `bn.bengali`; if that edition is unavailable, the app attempts to show Arabic text as a fallback.
- The APK has not been built/tested in this environment because Android SDK/Gradle tooling is not installed here. Run GitHub Actions to verify the build before publishing.
- API/CDN availability and terms can change; check the linked official documentation before public release.

## Build APK with GitHub Actions

1. Upload the *contents* of this ZIP (not the ZIP file itself) to the root of `muhammedomor-studio/Shohoj-Quran`.
2. Commit to `main`.
3. Open the repository's **Actions** tab.
4. Run **Build Shohoj Quran APK** (or wait for a push-triggered run).
5. Download the `shohoj-quran-debug-apk` artifact from the completed workflow run.

Package: `com.shohojquran.app`
