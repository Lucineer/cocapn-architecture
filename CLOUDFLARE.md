# Cocapn Cloudflare Deployment

## Architecture

Cocapn runs entirely on Cloudflare's edge network. No traditional servers.
31+ Workers handle routing, auth, rate limiting, and API proxying.

## Cloudflare Account

- **Active account**: Dad's account
- **Account ID**: `049ff5e84ecf636b53b162cbb580aae6`
- **Subdomain**: `casey-digennaro.workers.dev`
- ⚠️ **Old account**: `2bd99d5b13b2186382cd3dc995b0bb18` — token INVALID, do not use

## Worker Architecture

### Core Workers

| Worker | Route | Purpose |
|--------|-------|---------|
| cocapn-api | cocapn.ai/api/* | Main API gateway |
| cocapn-auth | cocapn.ai/auth/* | Authentication (JWT) |
| cocapn-billing | cocapn.ai/billing/* | Subscription management |
| cocapn-proxy | cocapn.ai/v1/* | OpenAI-compatible proxy |
| cocapn-dashboard | cocapn.ai/app/* | Web dashboard (static) |
| cocapn-ads | cocapn.ai/ads/* | Ad serving (free tier) |

### Infrastructure Workers

| Worker | Route | Purpose |
|--------|-------|---------|
| cocapn-rate-limit | * (middleware) | Per-user rate limiting |
| cocapn-logging | * (middleware) | Request logging + analytics |
| cocapn-keys | internal | Key rotation + secrets management |
| cocapn-health | cocapn.ai/health | Health check endpoint |

### Provider Proxy Workers

Each AI provider gets a dedicated proxy worker that:
1. Validates the user's API key for that provider
2. Forwards the request to the provider's API
3. Logs token usage and cost
4. Returns the response (streaming supported)
5. Updates the user's daily spend counter

| Worker | Provider | Notes |
|--------|----------|-------|
| cocapn-deepseek | DeepSeek | Primary provider, lowest cost |
| cocapn-google | Google AI (Gemini) | Flash/Pro models |
| cocapn-anthropic | Anthropic (Claude) | Haiku/Sonnet/Opus |
| cocapn-openai | OpenAI | GPT-4o/mini |
| cocapn-xai | xAI (Grok) | Grok 2/3 |
| cocapn-moonshot | Moonshot | Kimi-K2.5 |

## BYOK v2: Zero Keys in Code

All API keys are stored in Cloudflare Secrets Store (env bindings), not in
source code or Worker configuration.

### User Setup Flow
1. User signs up at cocapn.ai
2. User adds their provider API keys in the dashboard
3. Keys encrypted and stored in Cloudflare KV (encrypted at rest)
4. Worker retrieves key at request time, never persisted in Worker memory
5. Key injected into upstream provider request, never logged

### Internal Secrets
All Cocapn infrastructure secrets live in Cloudflare Secrets Store:
`https://dash.cloudflare.com/?to=/:account/secrets-store/`

## Data Stores

| Store | Purpose | Edge Location |
|-------|---------|---------------|
| Cloudflare KV | User profiles, API keys (encrypted), config | Global |
| Cloudflare D1 | Usage logs, billing records, analytics | Single region |
| Cloudflare R2 | Static assets, model metadata, logs archive | Global |
| Cloudflare Queues | Async processing (analytics, billing) | Global |

## Deployment Pipeline

```
GitHub push → Cloudflare Pages/Workers (auto-deploy)
  ├─ workers/ → wrangler deploy (each worker)
  ├─ dashboard/ → Pages (static React app)
  └─ secrets/ → wrangler secret put (manual, CI blocked)
```

## Rate Limiting

| Tier | Requests/min | Requests/day | Concurrent |
|------|-------------|-------------|------------|
| Free | 5 | 50 | 1 |
| Standard | 30 | 5,000 | 3 |
| Gold | 100 | Unlimited | 10 |
| Enterprise | Custom | Unlimited | Custom |

Rate limits enforced at the middleware Worker using Cloudflare's built-in
rate limiting (sliding window counter in KV).

## Monitoring

- **Health endpoint**: `cocapn.ai/health` (returns provider status, latency)
- **Error tracking**: Cloudflare Logs + Workers Analytics
- **Uptime**: Built-in Cloudflare monitoring (Enterprise gets custom alerts)
- **Cost tracking**: D1 database, per-user, per-request granularity

## Migration Status

- ✅ All 31+ repos migrated to Cloudflare Workers (2026-04-03)
- ✅ BYOK v2 implemented (zero keys in code)
- 📋 Custom domains (cocapn.ai, cocapn.com) configured
- 📋 SSL/TLS auto-managed by Cloudflare
- 📋 DDoS protection enabled (Cloudflare default)
