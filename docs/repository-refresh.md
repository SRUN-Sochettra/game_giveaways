# Repository refresh and verification notes

## Identity

Keep **lootdrop** as the repository slug and **LootDrop** as the display name. It already matches the app and describes the subject without an unnecessary technology suffix.

Suggested description:

> Flutter giveaway browser with search, category filters, resilient refresh states and persistent appearance settings. Riverpod and the GamerPower API.

Suggested topics: flutter, dart, riverpod, gamerpower, giveaways, material-design, mobile-app.

No GitHub settings, rename, commit, push or release update was performed. The internal package game_giveaways and platform identifiers remain unchanged.

## Apply this overlay

Extract into the existing repository root. Replace README.md and add CONTRIBUTING.md, SECURITY.md and this document. Preserve all source, lockfile, screenshots, platform assets and Git history. This is a documentation overlay, not a complete application archive.

## Editorial decisions

The README leads with browsing and the existing screenshots, then explains state handling, setup and limitations. It separates previous verification reports from current checks and avoids presenting dynamic giveaway counts, an old APK checksum or download size as current facts.

The original README reports 19 passing tests, a successful release build and emulator interaction checks using Flutter 3.47.6 / Dart 3.13.5. It also reports an Android preferences workaround. Those reports were not independently reproduced here. The dependency override remains untouched; no current upstream diagnosis or resolution is claimed.

No licence, release asset, screenshot, performance result or new configuration mechanism was invented. The release link is retained from the original README without a fresh availability claim.

## Implementation notes

The feed provider handles HTTP 201 as an empty list, rejects other non-200 responses and validates the JSON list/record structure. A malformed record fails the fetch rather than being silently dropped. Refresh retains the current list on failure and prevents a second refresh while one is pending.

Appearance writes optimistically update state, disable controls while saving and restore the previous choice on failure. The UI changes mode or accent separately. The controller accepts both arguments, but its persistence branch writes only one key when both are supplied; do not assume combined updates are fully persisted without changing/testing that path.

The app has no persistent catalogue cache. Local browsing state and retained feed data should not be advertised as offline synchronisation. HTTPS checks do not authenticate external destinations.

## Verification boundary

Read all 16 application Dart files, both Dart test files, manifest/lockfile, existing README and relevant Android/macOS configuration. Other platform scaffolding was inventoried rather than exhaustively audited. Screenshot paths were confirmed in the export inventory; binary images were not visually assessed.

Checked source assertions, relative documentation/image paths, archive members, UTF-8/control characters and ZIP byte round-trip. The input XML was unchanged. No dependency installation, Flutter analysis, tests, build, device/browser session, release download or live API request was performed.

To revert, restore the previous README and remove the three added documents using version control. Application behaviour is unchanged.
