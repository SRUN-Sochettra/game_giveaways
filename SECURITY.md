# Security guidance

LootDrop reads third-party listings and opens external offer pages. It does not redeem giveaways or authenticate store accounts in the supplied code. This document is not a security audit or a supported-release commitment.

## External content

Artwork and claim links are accepted when they use HTTPS and have a host. There is no destination-domain allowlist in the supplied helpers. Format validation does not establish publisher authenticity, safe redirects or continued offer availability.

Check the destination before entering account details. Do not submit store passwords, tokens or payment information to this repository or its issue tracker. Listing descriptions and instructions are external data, not maintainer guarantees.

## Local state and distribution

Display mode and accent are stored through SharedPreferences. The application does not implement an encrypted vault, account sync or a persistent feed cache. Do not add secrets to preferences or client source.

Android release builds currently use debug signing and an example application ID. Review signing, identifiers and distribution separately before publishing a store release. Keep signing keys and credentials out of commits.

## Reporting

For ordinary defects, provide the affected screen, Flutter/package versions, target platform and a minimal reproduction. Redact private browser/account details from screenshots and logs.

For sensitive concerns, use a verified private maintainer channel if available, or request one without publishing sensitive details. No dedicated security address, enabled private-reporting feature, response deadline or supported-version programme is confirmed by the supplied repository.
