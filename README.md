# Libryo

Libryo (ERM Libryo) is a regulatory compliance management platform for Environmental, Health
and Safety (EHS) teams. It automates legal registers, streams site-specific regulatory
obligations across jurisdictions, and tracks legislative change so operators know which laws
apply to each of their sites. Founded in 2016 with a distributed team across Cape Town,
London, Toronto, Nairobi and Berlin, it is now part of ERM.

- Website: https://libryo.com
- GitHub: https://github.com/libryo
- Backed by: seedcamp

## API

Libryo runs a partner-facing RESTful API at `https://api.libryo.com/api/v1`, secured with the
OAuth 2.0 authorization-code grant. Access is partner-gated — client credentials are issued
by Libryo, and the full endpoint reference is supplied under agreement rather than published.
The public integration guide is https://github.com/libryo/libryo-api-oauth-docs.

Published scopes are read-only: `view-legal-report`, `search-legislation`, `list-libryos`.

## Artifacts

| Path | Type | Method |
|---|---|---|
| `authentication/libryo-authentication.yml` | Authentication | searched |
| `scopes/libryo-scopes.yml` | OAuthScopes | searched |
| `packages/libryo-packages.yml` | Packages | searched |
| `conventions/libryo-conventions.yml` | Conventions | searched |
| `conformance/libryo-conformance.yml` | Conformance | searched |
| `lifecycle/libryo-lifecycle.yml` | Lifecycle | searched |
| `errors/libryo-problem-types.yml` | ErrorCatalog | probed |
| `well-known/libryo-well-known.yml` | WellKnown | probed |
| `security/libryo-domain-security.yml` | DomainSecurity | probed |
| `llms/libryo-llms.txt` | LLMsTxt | generated |

## Notes for future runs

- **Wildcard DNS.** `*.libryo.com` resolves to the platform load balancer in AWS eu-west-1,
  so *any* subdomain (`developer.`, `docs.`, `api.`) returns HTTP 200 with the app login
  page. Only `api.libryo.com` and `my.libryo.com` are real API hosts. Do not record invented
  subdomains as developer surfaces.
- **No OpenAPI.** Nothing to ground overlays, MCP tool lists, Agent Skills or a data model
  in, so those artifacts are intentionally absent rather than fabricated.
- **No status page, changelog, deprecation policy, SLA, security.txt or published
  certification** was found, so no `StatusPage`, `Deprecation`, `Security` or `Compliance`
  pointer is emitted.
- **No API SDK.** `nkyimu` is first-party but is an Akoma Ntoso document library, not a
  client for the API, so no `SDKs` pointer is emitted.
