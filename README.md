# Cocapn Architecture 🏗️

**Business architecture for the Cocapn ecosystem** — brand, pricing, Cloudflare deployment, and entity structure. The non-technical blueprint that explains how Cocapn works as a business.

## Quick Reference

| Area | Status | Details |
|------|--------|---------|
| Brand | ✅ Active | Cocapn — AI inference platform |
| Product | ✅ Designed | Chat UI, API proxy, usage tracking |
| Pricing | ✅ Designed | 4-tier pay-for-convenience |
| Cloudflare | ✅ Deployed | 31+ Workers, BYOK v2 |
| Domain | ✅ Active | [cocapn.ai](https://cocapn.ai) |
| Business Entity | 📋 Planned | LLC structure TBD |

## Pricing

| Tier | Price | Cost Model | Limits |
|------|-------|------------|--------|
| Free | $0 | 20% cost-plus + ads | 50 req/day |
| Standard | $5/mo | 2% cost-plus | 5K req/day |
| Gold | $15/mo | At cost | Unlimited containers |
| Enterprise | $50/seat/mo | At cost + SLA | Custom domains |

Revenue streams: membership fees × ad revenue (free tier) + bulk inference savings.

## Cloudflare Deployment

- **Account**: Dad's account (active) — `049ff5e84ecf636b53b162cbb580aae6`
- **Subdomain**: `casey-digennaro.workers.dev`
- **31+ Workers migrated** (2026-04-03)
- **BYOK v2**: Zero API keys in code — all in Cloudflare Secrets Store

## Files

```
cocapn-architecture/
├── README.md           ← This file
├── BRAND.md            # Brand identity, voice, visual guidelines
├── PRICING.md          # Full pricing model with math
├── CLOUDFLARE.md       # Deployment architecture
├── PRODUCT.md          # Product features and roadmap
└── BUSINESS-ENTITY.md  # LLC structure, legal, compliance
```

## Fleet Context

Part of the Lucineer/Cocapn fleet. For the code that implements this architecture, see the SDK repos ([cocapn-py](https://github.com/Lucineer/cocapn-py), [cocapn-go](https://github.com/Lucineer/cocapn-go), [cocapn-sdk](https://github.com/Lucineer/cocapn-sdk)) and the chat UI ([cocapn-chat](https://github.com/Lucineer/cocapn-chat)).
