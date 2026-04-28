# Cocapn Business Entity

## Current Status

📋 **Planned** — Business entity structure TBD.

## Recommended Structure

### Option A: Single LLC (Simplest)

**Cocapn LLC** — single entity for everything.

| Aspect | Detail |
|--------|--------|
| Type | Single-Member LLC |
| State | Alaska (no state income tax, $50 annual filing) |
| Registered Agent | TBD (commercial registered agent service) |
| EIN | Apply via IRS (free, online) |
| DBA | "Cocapn" — trade name registration |

**Pros:**
- Simplest setup ($250-500 total)
- Single tax return (Schedule C or 1065)
- No state income tax in Alaska
- Casey has full control

**Cons:**
- No liability separation between platform and services
- Personal assets at risk if sued

### Option B: Holding Company + Operating LLC (Recommended)

**Cocapn Holdings LLC** — owns everything, holds IP
**Cocapn Platform LLC** — operates the inference platform
**Cocapn Services LLC** — consulting, custom deployments

| Entity | Purpose | Ownership |
|--------|---------|-----------|
| Cocapn Holdings LLC | IP, brand, domain ownership | 100% Casey |
| Cocapn Platform LLC | cocapn.ai runtime operations | 100% Holdings |
| Cocapn Services LLC | Enterprise consulting, on-prem | 100% Holdings |

**Pros:**
- Liability isolation (platform liability doesn't touch services)
- IP protection (brand and code in separate entity)
- Clean cap table if investors ever wanted in
- Each entity can have different insurance

**Cons:**
- More complex ($1,500-2,500 total setup)
- Multiple tax returns (but can file consolidated)
- Annual fees ×3 ($50 state fee × 3 = $150/yr)

### Option C: C-Corp (If Seeking Investment)

Only pursue if planning to raise venture capital.

| Aspect | Detail |
|--------|--------|
| Type | Delaware C-Corporation |
| Cost | $500-800 setup + $300/yr franchise tax |
| Reason | VC standard, preferred stock, 409A valuation |

**Do NOT pursue unless:**
- Actively raising money
- Need employee stock options
- Expect revenue >$500K/yr

## Compliance Requirements

### Federal
- [ ] EIN application (IRS, free online)
- [ ] BOI filing (FinCEN, required 2024+) — Beneficial Ownership Information
- [ ] Annual tax return (Form 1065 for LLC, or Schedule C for single-member)

### Alaska State
- [ ] Articles of Organization ($250 filing fee)
- [ ] Biennial report (every 2 years, $100)
- [ ] Registered agent (commercial service ~$50-100/yr)
- [ ] Business license (Anchorage: $50/yr if operating there)

### Financial
- [ ] Separate business bank account (required for LLC liability protection)
- [ ] Business credit card (for API costs, infrastructure)
- [ ] Bookkeeping system (QuickBooks Self-Employed $15/mo, or Wave free)
- [ ] Monthly reconciliation

### Insurance
- [ ] General liability ($300-500/yr)
- [ ] Cyber liability ($500-1,000/yr) — important for API platform
- [ ] Errors & omissions ($500-1,000/yr) — for enterprise SLA
- [ ] D&O insurance (only if C-Corp or multiple owners)

## Tax Considerations

### Alaska Advantage
- No state income tax
- No state sales tax (local sales tax varies)
- No inventory tax
- No franchise tax

### Federal Tax
- Single-member LLC: pass-through (Schedule C on personal return)
- Multi-member LLC: partnership (Form 1065)
- C-Corp: double taxation (corporate + personal)

### Estimated Taxes
If expecting >$1,000 tax liability:
- Q1: April 15
- Q2: June 15
- Q3: September 15
- Q4: January 15

### Deductions
- Cloudflare infrastructure costs
- API provider costs (pass-through to users, but Cocapn's own usage)
- Home office deduction (if dedicated space)
- Internet (business %)
- Developer tools and subscriptions
- Travel (conferences, meetups)

## Revenue Projections (Conservative)

| Metric | Month 1-3 | Month 4-6 | Month 7-12 | Year 1 Total |
|--------|-----------|-----------|------------|-------------|
| Free users | 50 | 200 | 500 | — |
| Standard ($5) | 5 | 20 | 50 | ~$400 |
| Gold ($15) | 1 | 5 | 15 | ~$900 |
| Enterprise | 0 | 0 | 1 | ~$600 |
| **MRR** | $40 | $175 | $725 | — |
| **ARR** | — | — | — | ~$1,900 |

*Very conservative. Break-even around Month 8-10 at this pace.*

## Next Steps

1. [ ] Decide on entity structure (Option A vs B)
2. [ ] File Articles of Organization in Alaska
3. [ ] Get EIN from IRS
4. [ ] Open business bank account
5. [ ] File BOI with FinCEN
6. [ ] Set up bookkeeping
7. [ ] Get insurance
8. [ ] Review with accountant (free consultation available from several)

## Resources

- [Alaska LLC filing](https://www.commerce.alaska.gov/web/cbpl/Corporations.aspx)
- [IRS EIN application](https://www.irs.gov/businesses/small-businesses-self-employed/apply-for-an-employer-identification-number-ein-online)
- [FinCEN BOI filing](https://www.fincen.gov/boi)
- [Alaska registered agents](https://www.alaskaregisteredagent.com/)
