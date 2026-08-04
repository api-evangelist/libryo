# Libryo

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
