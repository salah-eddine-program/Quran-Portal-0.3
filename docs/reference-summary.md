# Project implementation summary

This repository combines the supplied design references into a single Arabic, right-to-left Quran portal built with Next.js 15 and TypeScript. It exports static files for GitHub Pages and keeps user reading data in the browser.

## Implemented capabilities

- Quran surah and juz navigation, verse deep links, last-read tracking, adjustable reading size, favorites, copy/share, and explicit local offline storage for opened surahs.
- Verse-by-verse audio using Al Quran Cloud editions and CDN, repeat counts, auto-advance, speed control, and a separate MP3Quran directory for full-surah recitations and radio.
- Reciter filtering from the recitation labels returned by MP3Quran, including Warsh when present in its catalog. This filter does not change the Quran text edition.
- Arabic-normalized section, surah, and verse search; multilingual translation editions from Al Quran Cloud; and selectable Arabic tafsir editions returned by its catalog.
- Local memorization targets, weekly progress, review session history, a self-quiz using saved ayahs, favorite surahs, and local notes.
- City-based prayer times, Hijri calendar, city-based Qibla bearing, a local tasbeeh counter, and links to cited Fortress of the Muslim references.
- Responsive Arabic UI, dark and light themes, simplified navigation, PWA manifest and service worker, SEO metadata, local backup export/import, and clear offline/error messaging.

## Data and accuracy boundaries

- Quran text is fetched from Al Quran Cloud and is rendered as returned. Translations, tafsir editions, and audio options come from that provider's catalog. Audio files are streamed from its documented CDN, with lower-bitrate fallback.
- No alternate Quran text edition is offered unless a reliable source is available. Warsh is shown as a recitation filter only when MP3Quran's catalog describes it; audio selection never changes the displayed Arabic text.
- MP3Quran supplies reciters, radio and their source labels. AlAdhan supplies prayer times. Source links are displayed in the interface.
- Personal preferences, favorites, notes, review counts, and tasbeeh count stay in local browser storage. A backup file is user-created and remains on the device unless the user moves it. The backup does not contain browser audio caches or IndexedDB Quran caches.
- The application does not request device location. Qibla bearing is computed from the selected city; selected city and calculation method are sent to AlAdhan for prayer times.
- This GitHub Pages build has no user accounts, cloud synchronization, or content administration dashboard. Those require a separate server and account system.

## Release and privacy notes

The distributable project contains the sanitized summary, not raw design exports or original source documents. Review third-party API terms and recitation rights before changing data use or redistributing downloaded content. Search text is sent to Al Quran Cloud; selected city and calculation method are sent to AlAdhan for their respective features.
