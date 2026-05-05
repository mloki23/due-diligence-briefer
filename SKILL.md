---
name: due-diligence-briefer
description: >-
  Use when a business owner or investor wants to evaluate a business before
  buying it. Triggers on: "due diligence on [business]", "should I buy this
  business", "evaluate this acquisition", "what's wrong with this business",
  "red flag check", "buying a business checklist". Researches financial
  health, industry benchmarks, red flags, and negotiation leverage — then
  delivers a structured briefing with a buy/caution/pass verdict. No API keys
  or paid tools required — works with web search alone.
---

# Due Diligence Briefer

> Before you write a cheque, know what you're really buying. This skill
> transforms a business listing, broker memo, or seller-provided financials
> into a structured due diligence briefing with red flags, industry context,
> and negotiation ammunition.
>
> Author: mloki23 | Pipeline: pairs with competitor-intel-briefer for
> pre-acquisition market context

---

## Minimum Required Inputs

Do not proceed without all 3:

1. **Business name and industry** — what they sell, who they serve
2. **Key financials** — at minimum: asking price, annual revenue, and claimed
   profit (EBITDA or SDE). If the user only has a listing URL, extract what's
   available and flag gaps.
3. **Location** — country at minimum; city/state for regional benchmarking

Ask for missing inputs before starting Phase 1. If the user provides a URL
(e.g. business-for-sale listing), extract inputs from it first.

---

## Phase 1: Financial Stress Test (15-20 min)

**Goal:** Determine whether the asking price is reasonable and uncover
financial red flags.

### 1.1 Calculate baseline valuation multiples

Compute using the figures the user provides:

```
Revenue multiple = Asking Price / Annual Revenue
Profit multiple = Asking Price / Annual Profit (EBITDA or SDE)
```

### 1.2 Research industry valuation multiples

Search for typical multiples for the specific industry:
```
[business industry] business valuation multiples [year]
[business industry] average EBITDA multiple small business
typical revenue multiple for [industry] sale
```

Cap at 3 searches for 1.2.

### 1.3 Flag valuation discrepancies

Compare the calculated multiples against industry averages:

- If asking price multiple is >1.5x the industry average: HIGH PREMIUM flag
- If profit multiple >5x for a small business (<$5M revenue): caution
- If seller isn't using a standard multiple (e.g., "asset value only" for a
  service business): flag the non-standard valuation method

### 1.4 Check for common financial red flags

Run these specific checks (web-searchable):

```
[A] "seller's discretionary earnings" OR "add-backs" red flags small business
[B] "working capital" adjustment business sale trap
[C] [industry] revenue concentration risk "customer concentration"
```

Cap at 3 searches for 1.4.

**PROHIBITED during Phase 1:** Do not make a buy/caution/pass assessment yet.
Observation and calculation only.

### Phase 1 Gate — DO NOT proceed until ALL checked:

- [ ] Revenue and profit multiples calculated
- [ ] Industry benchmark multiples found (at least 1 source)
- [ ] Discrepancy flagged if multiple exceeds 1.5x industry average
- [ ] Minimum 3 financial red flag areas checked (A, B, C above)
- [ ] Summary presented to user: "Here's what the numbers say so far — does
  this match what you expected?"

---

## Phase 2: Operational & Market Red Flags (15-20 min)

**Goal:** Uncover non-financial risks the seller isn't volunteering.

### 2.1 Customer and revenue risk

Search:
```
[industry] customer concentration risk small business
what happens when key customer leaves [industry] business
```

### 2.2 Owner dependency check

Search:
```
[industry] business owner dependency "key person risk"
buying a business where owner is the brand
```

### 2.3 Industry headwinds

Search:
```
[industry] outlook [current year] challenges risks
[industry] disruption technology regulatory threats
```

### 2.4 Competitive pressure check

Search:
```
[industry] new competitors entering market [current year]
[industry] losing market share to [alternative/disruption]
```

Cap at 5 searches total across 2.1-2.4.

### 2.5 Cross-check with competitor-intel-briefer

If the user has run competitor-intel-briefer for this industry, reference
those findings. If they haven't, offer: "I can run a competitive intelligence
briefing on this industry for deeper context — want me to?"

### Phase 2 Gate:

- [ ] Customer concentration risk assessed
- [ ] Owner dependency risk assessed
- [ ] At least 1 industry headwind identified
- [ ] At least 1 competitive threat identified
- [ ] Red flags compiled into a numbered list presented to user

---

## Phase 3: Negotiation Position & Verdict (10-15 min)

**Goal:** Deliver the final briefing with a clear recommended action.

### 3.1 Build the negotiation ammunition list

From Phases 1-2, extract every weakness that weakens the seller's position:
- Over-market valuation
- Customer concentration above 30%
- Owner-is-the-business dependency
- Declining industry or new competitor threats
- Inflated add-backs in profit claims
- Missing working capital in deal structure

### 3.2 Research recent comparable sales

Search:
```
[industry] business sold for less than asking price [year]
[industry] business sale "deal fell through" OR "price reduced"
```

Cap at 2 searches.

### 3.3 Deliver the final briefing

**Output format** — save to `due-diligence-[business-name]-[YYYY-MM-DD].md`:

```markdown
# Due Diligence Briefing: [Business Name]
**Date:** [YYYY-MM-DD] | **Status:** BUY / CAUTION / PASS

## The Numbers
| Metric | This Business | Industry Avg | Flag |
|--------|--------------|--------------|------|
| Revenue Multiple | X.Xx | X.Xx | [OK/HIGH] |
| Profit Multiple | X.Xx | X.Xx | [OK/HIGH] |
| [Revenue/Profit Trend if available] | | | |

## Red Flags (ranked by severity)
1. **[Red flag]** — [specific detail with source]
2. ...

## What The Seller Isn't Saying
*Pick the 2–3 most relevant to this deal — at least one must be supported by a specific finding:*
- **Walkout risk:** If the owner handles key relationships or is the public face, what revenue leaves with them?
- **Hidden capex:** Equipment age, lease renewals imminent, staff paid below-market (deferred cost bomb)
- **Market timing signal:** Why is the seller selling now — plateau, new competitor, regulatory headwind?
- **Concentration cliff:** What breaks if the top customer, supplier, or contract disappears?
- **Earn-out trap:** Is the asking price padded with performance milestones that depend on the seller's cooperation post-sale?

## Negotiation Ammunition
- [Specific weakness] → use this to push for [specific concession]
- ...

## Verdict: [BUY / CAUTION / PASS]
[2-3 sentence rationale referencing the strongest evidence]

## If Proceeding: First 3 Actions
1. [Specific — e.g., "Request last 3 years of tax returns, not just P&L"]
2. [Specific]
3. [Specific]

---
*Researched via web search. Not financial or legal advice. Hire a
professional for the binding stuff.*
```

### 3.4 Ask the closing question

After delivering the briefing: "Want me to run a competitor-intel-briefer on
this industry for deeper market context before you decide?"

### Phase 3 Gate:

- [ ] Negotiation ammunition list has minimum 3 items
- [ ] Verdict (BUY/CAUTION/PASS) delivered with rationale
- [ ] Output saved to `due-diligence-[name]-[date].md`
- [ ] Closing question asked

---

## Prohibited Behaviours

| Prohibited Action | Why |
|-------------------|-----|
| Skip financial ratio calculation | Without numbers, the verdict is opinion, not analysis |
| Exceed search caps (3/3/5/2 per phase) | Anti-loop — compile with what you have |
| Make a verdict without industry benchmarks | A multiple is meaningless without context |
| Present as financial advice | Always include the disclaimer — legal liability risk |
| Skip Phase gate checks | Gates prevent delivering half-researched verdicts |
| Use paid data sources or APIs | Web search only — this is our differentiator |

---

## Quality Standards — Complete When:

- [ ] All 3 phases executed in sequence with every gate passed
- [ ] Revenue and profit multiples calculated and benchmarked
- [ ] Minimum 5 red flags checked across financial and operational dimensions
- [ ] Negotiation ammunition has 3+ items tied to specific findings
- [ ] Verdict is BUY, CAUTION, or PASS — never "it depends"
- [ ] Output file saved with correct naming convention
- [ ] Disclaimer included in output

---

## Australian-Aware

If the user provides an Australian business or ABN/ACN:
- Use AUD throughout (skip USD default)
- Search for Australian-specific benchmarks: "Australian [industry]
  valuation multiples", "small business sale Australia multiples"
- Check for Australian-specific traps: earn-out structures, vendor finance
  terms, GST on going concern, stamp duty on business assets (state-varying)
- Reference ATO small business benchmarks if relevant

---

## Context Budget

After Phase 1: retain only the calculated multiples, industry benchmarks, and
flag list — discard raw search results.
After Phase 2: retain only the numbered red flag list — discard individual
search outputs.
After Phase 3: the briefing file is the artifact. Nothing else from the
session needs to be retained.