# Keycloak

- **Repo:** [keycloak/keycloak](https://github.com/keycloak/keycloak)
- **Category:** Auth infrastructure (IAM)
- **License:** Apache-2.0 · **Language:** Java · **Stars:** ~36.8k

## What it is
The long-standing, mature open-source identity and access management platform — full SSO, SAML,
OIDC, fine-grained authorization, and enterprise-grade admin tooling. Backed by Red Hat.

## Why it might matter to us
Heavyweight compared to what any current project needs (Shift Tasks runs on Supabase Auth), but
it's the reference point if a client ever needs real enterprise SSO/SAML federation that Supabase
Auth genuinely can't do. Self-hosting Java infrastructure is a real operational cost — don't reach
for this unless a client's actual requirement (SAML federation, fine-grained RBAC beyond what we
have) demands it.

## Notes
- Added 2026-09-15, evaluated only by description — no hands-on trial.
- Compare against Logto (lighter-weight, same problem space, TypeScript) before choosing either.
