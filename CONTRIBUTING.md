# Contributing to LootDrop

Keep changes focused on giveaway browsing and reliable interface states. Read the [README](README.md) before adding features or changing dependencies.

## Development

Use the existing lockfile and inspect the Android dependency override before altering it. Its comment records a prior release-startup workaround; that comment alone is not proof of a current upstream defect or fix. Reproduce the relevant release behaviour before removing the pin.

Keep HTTP access in the feed provider, search/category logic in the browse provider and preference writes in the settings provider. Reuse the existing widgets rather than introducing a new architecture for a small change.

## Verification

Run the README's format, analyser and test commands. Report actual results and distinguish mocked tests from live requests and emulator checks from physical-device testing.

For feed changes, cover malformed records, non-list JSON, empty responses, initial failure, successful replacement, duplicate refresh suppression and failed-refresh retention. For settings changes, check restored values, failed writes, pending controls and restart behaviour.

For UI changes, exercise narrow layouts, long titles, large text, both themes, keyboard/focus and loading/error/empty states. Test external-link failure on the target platform. Do not claim accessibility conformance from the widget matrix alone.

## Pull requests

Explain the problem, focused change, verification and remaining gaps. Include screenshots for visual changes, but remove private account details. Keep generated builds and unrelated platform/identifier changes out of the patch. Follow [SECURITY.md](SECURITY.md) for sensitive reports.
