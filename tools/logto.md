# Logto

- **Repo:** [logto-io/logto](https://github.com/logto-io/logto)
- **Category:** Auth infrastructure (IAM)
- **License:** MPL-2.0 · **Language:** TypeScript · **Stars:** ~14.6k

## What it is
Open-source authentication and authorization infrastructure for SaaS and AI apps, built on OIDC
and OAuth 2.1, with multi-tenancy, SSO, and RBAC out of the box.

## Why it might matter to us
**Directly relevant, not just interesting.** Shift Tasks is mid-build on generalizing its auth
surface from a single Google-only sign-in to a provider registry (google/azure/linkedin_oidc),
plus per-tenant provider policy and domain auto-join (see the
`spec/auth-provider-generalization` work, 2026-09-07). Logto solves almost exactly this problem
class — multi-tenant, multi-provider OIDC/OAuth with RBAC — as a real product, not a spec. Worth
reading its docs/source for prior art on:
- how it models a provider registry + per-tenant enabled-provider policy,
- its multi-tenancy RBAC shape,
- whether it's a viable *replacement* for the custom Supabase-Auth-hook approach if the
  hand-rolled admission/provision gates ever become a maintenance burden.

Not a recommendation to migrate — Shift Tasks' current approach (Supabase Auth + custom hooks) is
deliberate and already has real invariants built up around it (see `docs/decisions.md`). This is
prior art to consult, not a drop-in replacement to reach for casually.

## Notes
- Added 2026-09-15, not yet evaluated hands-on.
