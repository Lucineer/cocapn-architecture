# PRODUCT.md — Cocapn.ai Product Specification

## What It Is

Cocapn is an AI inference convenience layer. One API key, any model, transparent cost.

**Value prop:** People pay for the convenience, not the compute.

## Current State

### Live (deployed)
Nothing yet — needs first deployment.

### Built (code complete)
- **cocapn-chat** — Complete product in a single Cloudflare Worker (42KB)
  - Repo: github.com/Lucineer/cocapn-chat
  - Landing page, chat UI, auth, dashboard, settings
  - OpenAI-compatible API proxy
  - BYOK provider key management
  - Usage logging and cost tracking

## User Flows

### 1. Landing → Signup → Chat
1. User lands on cocapn.ai
2. Sees hero: "One API key. Any AI model. See what it costs."
3. Clicks "Get started free"
4. Signs up with email + password
5. Gets JWT + API key
6. Redirected to chat
7. Picks a model, starts chatting
8. Sees cost per message in real-time

### 2. API Integration
1. Developer reads docs
2. Signs up, gets API key
3. Changes one line in their code: `base_url = "https://cocapn.ai/v1"`
4. Starts making requests
5. Gets cost headers on every response

### 3. BYOK Setup
1. User goes to Settings
2. Adds provider API keys (DeepSeek, Google, OpenAI, Anthropic)
3. Keys stored encrypted
4. All requests use their keys first, server keys as fallback

## Tech Stack

- **Runtime:** Cloudflare Workers (free tier: 100K req/day)
- **Storage:** KV (auth, keys), D1 (usage logs)
- **Auth:** JWT + PBKDF2 password hashing
- **Frontend:** Vanilla JS SPA (no framework, no build step)
- **API:** OpenAI-compatible format

## Deployment Checklist

- [ ] wrangler login (needs Casey)
- [ ] Create KV namespaces: USERS, PROVIDER_KEYS, USAGE
- [ ] Create D1 database: cocapn
- [ ] Set JWT_SECRET
- [ ] Set provider API keys (optional, for non-BYOK users)
- [ ] wrangler deploy
- [ ] Point cocapn.ai DNS to worker
- [ ] Test signup → chat → dashboard flow
- [ ] Test API proxy with curl
- [ ] Monitor for errors

## Revenue Model

| Tier | Price | Margin | What they get |
|------|-------|--------|---------------|
| Free | $0 | 20% cost-plus | 50 req/day, BYOK, ads |
| Standard | $5/mo | 2% cost-plus | 5K req/day, analytics, no ads |
| Gold | $15/mo | At cost | Unlimited, containers, webhooks |
| Enterprise | $50/seat/mo | At cost + SLA | Custom domains, SSO, audit logs |

Revenue = subscription + (cost-plus margin on provider compute)

## Metrics to Track

- DAU/MAU
- Requests per user per day
- Average cost per request
- BYOK vs server-key ratio
- Free → Standard conversion rate
- Most-used model
- Churn rate

## Next Features (Priority Order)

1. **Streaming** — Already supported in API, polish in chat UI
2. **Conversation history** — Save chats to KV, resume later
3. **System prompts** — Customizable per-chat system prompts
4. **Image input** — Via Gemini/GPT-4o multimodal
5. **Team/org accounts** — Multiple users, shared billing
6. **Usage alerts** — Email when daily/weekly spend exceeds threshold
7. **API playground** — Interactive API tester in dashboard
8. **Webhooks** — On completion, on error, on spend threshold
9. **Embeddable chat widget** — `<script>` for other sites
10. **Mobile app** — React Native wrapper
