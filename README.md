# Tools Catalog

A pullable, curated index of external tools and repos worth knowing about for future projects.
Not a code dependency — a reference: what it is, why it might matter to us, and the real link.

Clone it directly, or read [`tools.json`](tools.json) programmatically from any project:

```bash
curl -s https://raw.githubusercontent.com/FrameShiftForge/tools-catalog/main/tools.json
```

## Index

| Tool | Category | Stars | What it is | Relevance |
|---|---|---:|---|---|
| [500-AI-Agents-Projects](tools/500-ai-agents-projects.md) | Reference / directory | 37.7k | Curated list of AI agent use-cases across industries, with links to open-source implementations | Idea-sourcing when scoping a new agent project |
| [CloakBrowser](tools/cloakbrowser.md) | Browser automation | 31.4k | Drop-in Playwright replacement, stealth Chromium that passes bot-detection tests | Directly useful for any scraping/automation work our Playwright e2e suites don't already cover |
| [AiSOC](tools/aisoc.md) | Security ops | 2.4k | Open-source AI-powered SOC: alert fusion, purple-team drills, MITRE ATT&CK triage | Reference if we ever build/eval security monitoring tooling |
| [ai-engineering-from-scratch](tools/ai-engineering-from-scratch.md) | Learning / reference | 54.6k | Hands-on tutorials: LLM APIs, prompt engineering, tool calling, the agent loop | Onboarding material, not a dependency |
| [archify](tools/archify.md) | Claude Code skill | 62.9k | Agent skill for architecture/workflow/sequence/data-flow diagrams as self-contained HTML | Candidate to actually install as a skill (`~/.claude/skills`) |
| [Keycloak](tools/keycloak.md) | Auth infra (IAM) | 36.8k | Mature, enterprise-grade open-source identity & access management (Java) | Heavyweight self-hosted IAM option if a project ever needs full SSO/SAML beyond Supabase Auth |
| [Logto](tools/logto.md) | Auth infra (IAM) | 14.6k | Open-source auth for SaaS/AI apps: OIDC + OAuth 2.1, multi-tenancy, SSO, RBAC (TypeScript) | **Directly relevant** to Shift Tasks' multi-provider auth generalization work — lighter-weight than Keycloak, same TS stack |
| [site-teardown](tools/site-teardown.md) | Claude Code skill | 4 | Reverse-engineers a site's HTML/CSS/JS into a tech-stack + design-system + build blueprint | Installed at `~/.claude/skills/site-teardown` — competitive research before building |
| [funnel-spy](tools/funnel-spy.md) | Claude Code skill | 4 | Walks a competitor's whole funnel (pages, offer ladder, ad signals) into a scored teardown | Installed at `~/.claude/skills/funnel-spy` — competitive research before building |

## Portable agent instructions

[`web-design-agents-playbook.md`](web-design-agents-playbook.md) — a plain-text distillation of
this team's web-design/conversion/SEO Claude skills (hero design, page structure, copywriting,
social proof, cognitive ease, visual polish, CRO, Core Web Vitals, technical SEO, and the two
teardown skills above), written so a tool that **can't** read `~/.claude/skills/` — Codex, or any
other coding agent — still gets the operative rules. Drop it into a project's own `AGENTS.md`
when working outside Claude Code. Kept live at `~/.codex/AGENTS.md` on the machine it was
authored on; treat that as the primary copy and this one as the portable/shareable mirror.

## Conventions

- One file per tool under `tools/`, named `kebab-case-of-the-repo-name.md`.
- Every entry: what it is (from its own README/description), why it might matter to *our* projects
  specifically (not generic marketing), license, primary language, and the date it was added.
- `tools.json` is the machine-readable mirror of the table above — keep both in sync in the same commit.
- This is a catalog, not an evaluation: an entry here is "worth knowing about," not "approved for use."
  Vet license, maintenance status, and security posture before actually depending on anything listed.
