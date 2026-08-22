# Rockstar Games

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

API Evangelist profile of [Rockstar Games](https://www.rockstargames.com), the American video game publisher behind the *Grand Theft Auto* and *Red Dead Redemption* franchises. Rockstar is a wholly-owned subsidiary of [Take-Two Interactive](https://www.take2games.com/) (NASDAQ: TTWO).

This repository inventories Rockstar's HTTP API surfaces — none of which are formally documented for third parties. Rockstar does not publish a developer portal, an OpenAPI specification, or third-party API keys; the surfaces below are reverse-derived from observable behaviour of the official Rockstar Games website, the Rockstar Games Launcher, the legacy Social Club portal, and Rockstar's sign-in / OIDC provider.

## Why this profile exists

- **GTA VI launches November 19, 2026** for PlayStation 5 and Xbox Series X|S, with "a significant online mode" succeeding GTA Online — the biggest single live-service launch on the calendar.
- **Social Club is fading as a brand** — "Most branding relating to Social Club was removed from Rockstar's website by November 2023" (Wikipedia) — but its underlying APIs continue to power every active Rockstar title.
- **The OIDC provider is a real, public, standards-compliant API surface** worth documenting on its own: `signin.rockstargames.com` exposes `/connect/authorize`, `/connect/Token`, `/connect/introspect`, and `/.well-known/jwks` and supports the `authorization_code`, `client_credentials`, and `refresh_token` grant types on what appears to be an IdentityServer-style stack.

## APIs documented

| API | Surface | Public? |
|---|---|---|
| Rockstar Games Sign-In (OpenID Connect) | `signin.rockstargames.com` | Yes (OIDC endpoints reachable; client registration closed) |
| Rockstar Games Social Club | `scapi.rockstargames.com` | No (first-party clients only) |
| Grand Theft Auto Online Services | `prod.cloud.rockstargames.com` | No |
| Red Dead Online Services | `prod.cloud.rockstargames.com` | No |
| Rockstar Games Launcher | `prod.cloud.rockstargames.com` | No (client app, not an API) |
| Grand Theft Auto VI (Forthcoming) | TBA | No — service details unannounced |

See [`apis.yml`](./apis.yml) for the full machine-readable inventory.

## Notable absences

- **No public developer portal.** Rockstar has never operated one.
- **No OpenAPI / AsyncAPI / GraphQL schema** published anywhere. No artifacts are committed to this repo for that reason — the API Evangelist pipeline does not generate placeholder specs.
- **No public GitHub organization.** The `github.com/rockstar-games` user account exists but holds zero repositories ("rockstar-games doesn't have any public repositories yet").
- **No public pricing or rate-limit documentation** for the consumer-facing services; GTA+ subscription pricing is the only published commercial surface and is consumer-only, not an API plan.
- **No newswire RSS / Atom feed** is exposed; Rockstar Newswire serves only HTML behind anti-bot protection.

## Sources

- Rockstar Games corporate site — https://www.rockstargames.com
- Rockstar Sign-In OIDC discovery document — https://signin.rockstargames.com/.well-known/openid-configuration
- Wikipedia: Rockstar Games, Grand Theft Auto VI, Rockstar Games Social Club
- GitHub: https://github.com/rockstar-games (zero repos)

## Maintainer

Kin Lane — kin@apievangelist.com
