# site-teardown

- **Repo:** [23ag1/site-teardown-skill](https://github.com/23ag1/site-teardown-skill)
- **Category:** Claude Code skill
- **License:** none in the upstream repo · **Language:** Markdown (skill instructions) · **Stars:** ~4

## What it is
A Claude Code skill that reverse-engineers any website into a build blueprint: it curls the raw
HTML/JS/CSS itself, extracts the tech stack, every animation/effect with how it's implemented
(GSAP configs, scroll-trigger setups, parallax formulas), the full design system (colors, type,
spacing tokens), and outputs a section-by-section plan someone could hand to a fresh session to
rebuild the page without visiting the original site.

## Why it might matter to us
Direct fit for competitive research before building a high-converting site — see the
`web-design-agents-playbook.md` in this repo, which folds its methodology into a Codex-usable
form too.

## Installed
`~/.claude/skills/site-teardown/` (2026-09-15) — see that folder's `PROVENANCE.md` for the
licensing caveat (upstream has no LICENSE file).
