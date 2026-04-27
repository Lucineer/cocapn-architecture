# Cocapn Architecture

Business architecture for the Cocapn ecosystem — brand identity, pricing model, business entity structure, and Cloudflare deployment. The non-technical blueprint.

## Quick Reference

| Area | Status | Details |
|------|--------|---------|
| Brand | ✅ Active | Cocapn (AI inference platform) |
| Pricing | ✅ Designed | 4-tier pay-for-convenience |
| Cloudflare | ✅ Deployed | 31+ Workers, BYOK v2 |
| Business Entity | 📋 Planned | LLC structure TBD |
| Domain | ✅ Active | cocapn.ai |

## Pricing Architecture

| Tier | Price | Cost Model | Limits |
|------|-------|------------|--------|
| Free | $0 | 20% cost-plus + ads | 50 req/day |
| Standard | $5/mo | 2% cost-plus | 5K req/day |
| Gold | $15/mo | At cost | Docker containers, unlimited |
| Enterprise | $50/seat/mo | At cost + SLA | Custom domains |

Revenue streams: membership fees + ad revenue (free tier) + bulk inference savings.

## Cloudflare Deployment

- **Account**: Dad's account (active) — `049ff5e84ecf636b53b162cbb580aae6`
- **Old account**: `2bd99d5b13b2186382cd3dc995b0bb18` — token INVALID, do not use
- **Subdomain**: `casey-digennaro.workers.dev`
- **All 31+ repos migrated** (2026-04-03)

### BYOK v2: Zero Keys in Code
All API keys stored in Cloudflare Secrets Store (env bindings). Users set up at:
`https://dash.cloudflare.com/?to=/:account/secrets-store/`

## Files

```
cocapn-architecture/
├── BRAND.md           # Brand identity, voice, visual guidelines
├── PRICING.md         # Full pricing model with math
├── CLOUDFLARE.md      # Deployment architecture
├── BUSINESS-ENTITY.md # LLC structure, legal, compliance
└── README.md          # This file
```

---

## Fleet Context

Part of the Lucineer/Cocapn fleet. See [fleet-onboarding](https://github.com/Lucineer/fleet-onboarding) for boarding protocol.

- **Vessel:** JetsonClaw1 (Jetson Orin Nano 8GB)
- **Domain:** Low-level systems, CUDA, edge computing
- **Comms:** Bottles via Forgemaster/Oracle1, Matrix #fleet-ops
