# CloakBrowser

- **Repo:** [CloakHQ/CloakBrowser](https://github.com/CloakHQ/CloakBrowser)
- **Category:** Browser automation / anti-detection
- **License:** MIT · **Language:** Python · **Stars:** ~31.4k

## What it is
A stealth Chromium build with source-level fingerprint patches, claimed to pass bot-detection
tests (30/30 in the project's own suite). Positioned as a drop-in Playwright replacement.

## Why it might matter to us
Our Shift Tasks e2e suite and any future scraping/automation work already leans on Playwright
heavily. If a target site's bot detection ever blocks a legitimate automated check (monitoring,
QA, or a client-authorized scrape), this is worth evaluating as a swap-in browser.

## Cautions before adopting
- "Drop-in Playwright replacement" claims should be verified against our actual Playwright version
  and config before trusting it in CI — vet compatibility on a throwaway branch first.
- Confirm the intended use is authorized (site ToS, scope of engagement) before pointing stealth
  automation at anything we don't own. This is a dual-use capability.

## Notes
- Added 2026-09-15, not yet evaluated against our stack.
