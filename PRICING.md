# Cocapn Pricing Model

## Philosophy

**Pay for convenience, not compute.** Cocapn adds a thin convenience layer
on top of raw API costs. You bring the keys, you see the real prices, and
our margin is transparent and small.

## Tiers

### Free — $0/mo
- **20% cost-plus** on raw API costs (covers infrastructure)
- **50 requests/day** hard limit
- **Ad-supported** — non-intrusive, relevant to AI/developer tools
- All models, all providers
- No credit card required
- **Purpose**: Onboarding, experimentation, evaluation

### Standard — $5/mo
- **2% cost-plus** on raw API costs
- **5,000 requests/day**
- **No ads**
- Priority queue (skip ahead of free users)
- Basic usage analytics
- **Purpose**: Individual developers, hobbyists, light production

### Gold — $15/mo
- **At cost** (0% markup — membership covers infrastructure)
- **Unlimited requests**
- **Docker containers** — custom runtimes, persistent volumes
- Advanced analytics (cost tracking, model comparison)
- Webhook integrations
- API rate: 100 req/min
- **Purpose**: Power users, small teams, serious projects

### Enterprise — $50/seat/mo
- **At cost + SLA** (99.9% uptime guarantee)
- **Custom domains** (api.yourcompany.com)
- **SSO/SAML** integration
- **Dedicated support** (24hr response)
- **Audit logs** and compliance reporting
- **Custom rate limits** (negotiable)
- **On-prem option** (air-gapped deployment)
- **Purpose**: Companies, compliance-required environments

## Revenue Streams

1. **Membership fees** — predictable recurring revenue
2. **Ad revenue** — free tier only, non-intrusive developer-tool ads
3. **Bulk inference savings** — our volume discounts on providers = lower costs for Gold/Enterprise
4. **Enterprise add-ons** — SSO, audit logs, on-prem (premium features)

## Cost Transparency

Users always see:
- Raw API cost (what the provider charges)
- Cocapn margin (percentage and dollar amount)
- Total cost per request
- Daily/weekly/monthly spend breakdown

Example receipt:
```
Request: chat/completions
Model: deepseek-chat (DeepSeek)
Tokens: 1,247 in / 389 out
Raw cost: $0.00182
Cocapn margin: $0.00036 (20%)
Total: $0.00218
─────────────────────
Daily spend: $0.47 / $10.00 budget
```

## Pricing Math

### Free Tier Sustainability
- Average free user: 30 req/day, $0.002/req avg = $0.06/day raw cost
- 20% margin: $0.012/day revenue per user
- Ad revenue target: $0.05/day per user
- **Break-even per free user: ~$0.002/day net** (acceptable for growth)

### Standard Tier
- $5/mo subscription
- 2% margin on usage: ~$0.10/mo per active user
- **Margin: ~$4.90/mo** (mostly subscription, minimal usage cost)

### Gold Tier
- $15/mo subscription
- 0% margin on usage (at cost)
- Docker infra cost: ~$3-5/mo per user
- **Margin: ~$10-12/mo** (after infrastructure)

### Enterprise Tier
- $50/seat/mo
- SLA infrastructure cost: ~$8-12/seat/mo
- **Margin: ~$38-42/seat/mo** (high margin, high service)

## Provider Cost Reference

| Provider | Model | Cost/1M tokens (in) | Cost/1M tokens (out) |
|----------|-------|---------------------|----------------------|
| DeepSeek | deepseek-chat | $0.14 | $0.28 |
| DeepSeek | deepseek-reasoner | $0.55 | $2.19 |
| Google | Gemini 2.5 Flash | $0.15 | $0.60 |
| Anthropic | Claude 3.5 Haiku | $0.80 | $4.00 |
| Anthropic | Claude 3.5 Sonnet | $3.00 | $15.00 |
| OpenAI | GPT-4o-mini | $0.15 | $0.60 |
| xAI | Grok 3 | $3.00 | $15.00 |
| Moonshot | Kimi-K2.5 | $0.60 | $2.50 |

*Prices as of 2026-04. Updated monthly.*

## Future Considerations

- **Token packs** — prepaid bundles at discount (no subscription)
- **Model marketplace** — community-contributed fine-tunes
- **GPU spot market** — bid on idle GPU time for batch jobs
- **Open source** — self-hosted option (BYOK + free Cocapn layer)
