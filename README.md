# Cocapn Architecture

> Brand, business entity, pricing, and infrastructure for the Cocapn ecosystem.

## The Three Pillars

**Don't muddy the water with naming — three pillars only:**

1. **Purplepincher** (purplepincher.org) — the nonprofit umbrella for open-source agentic computing, Plato ecosystem philosophy, and fleet coordination
2. **Cocapn** (cocapn.com) — the operating company. cocapn.com = billing, cocapn.ai = runtime
3. **Deckboss** — the design layer. User-facing products, visual identity, commercial interface

## Brand Architecture

- **Cocapn** = umbrella company name
- **PLATO** = the git-agent maintenance mode system
- **Git-Agent** = the paradigm: the repo IS the agent
- **Turbo-Shell** = the persistent shell that survives agent replacement
- **Bottles** = async git-based fleet messaging
- **Tiles** = knowledge units in Plato rooms
- **Rooms** = workspace environments in Plato
- **Spells** = executable commands in Plato
- **Equipment** = tools and capabilities in Plato

## Business Entity

- Nonprofit: purplepincher.org
- Operating: Cocapn (Casey Digennaro)
- Cloudflare account: Dad's account (casey.digennaro@gmail.com)

## Cloudflare Infrastructure

- **Active account** (Dad's): casey.digennaro@gmail.com, paid Workers plan
- **Subdomain**: casey-digennaro.workers.dev
- **All 31+ repos migrated** (2026-04-03)
- **Old account**: token INVALID, do not use
- **BYOK v2**: Zero keys in code — all keys via CF Secrets Store (env bindings)
- ⚠️ Account ID and API token in vessel TOOLS.md or openclaw.json (never committed to git)

## Pricing Architecture (Pay-For-Convenience)

| Tier | Price | Margin | Requests | Features |
|---|---|---|---|---|
| Free | $0 | 20% cost-plus | 50/day | Ads |
| Standard | $5/mo | 2% cost-plus | 5K/day | No ads |
| Gold | $15/mo | At cost | Unlimited | Docker containers |
| Enterprise | $50/seat/mo | At cost | Unlimited | SLA, custom domains |

**Revenue sources:** membership fees + ad revenue (free) + bulk inference savings

## Key Products

### Actualizer.ai
- Reverse Actualization Protocol vessel
- Single-file Cloudflare Worker (~550 lines)
- 7 time horizons (1yr→100yr), multi-model parallel ideation
- 16 BYOK v2 providers, KV-stored reports
- URL: actualizer-ai.casey-digennaro.workers.dev
- Repo: github.com/Lucineer/actualizer-ai

### Everything App Vision
- 5 presentation layers: Spreadsheet, Messenger, Feed, Matrix/Gamified, Research Lab
- Personal Digital Organism (PDO) concept — 2040 realization
- Critical mass: 50K developer-users
- 7 repos to build: fleet-orchestrator, seed-ui, dream-engine, local-bridge, memory-fabric, membership-api, free-tier-router

### Luciddreamer.ai
- Podcast room network — Plato rooms as streaming daily shows
- Website portal to web of podcast rooms
- Repo: github.com/Lucineer/jc1-luciddreamer-ai

## Repo Inventory

All repos under github.com/Lucineer/ (renamed from CedarBeach2019 on 2026-03-31).

See `fleet-onboarding` repo for full fleet map and vessel capabilities.

---

## Fleet Context

Part of the Lucineer/Cocapn fleet. See [fleet-onboarding](https://github.com/Lucineer/fleet-onboarding) for boarding protocol.

- **Vessel:** JetsonClaw1 (Jetson Orin Nano 8GB)
- **Domain:** Low-level systems, CUDA, edge computing
- **Comms:** Bottles via Forgemaster/Oracle1, Matrix #fleet-ops
