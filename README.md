# Rockstar Games

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
