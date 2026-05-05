# Due Diligence Briefer

**An agent skill that evaluates any business for purchase using web research alone.** Calculates valuation multiples against industry benchmarks, ranks red flags by severity, builds a negotiation ammunition list, and delivers a BUY / CAUTION / PASS verdict — before you write a cheque.

## What It Does

Evaluates a business for purchase using web research alone. Calculates
valuation multiples against industry benchmarks, surfaces financial and
operational red flags, builds a negotiation ammunition list, and delivers a
structured briefing with a BUY / CAUTION / PASS verdict. Built for business
operators evaluating an acquisition — not for financial professionals running
a formal audit.

## Trigger Phrases

```
"due diligence on [business name]"
"should I buy this business"
"evaluate this acquisition"
"what's wrong with this business"
"red flag check on [business]"
"buying a business checklist"
```

## Output

A markdown file saved as `due-diligence-[business-name]-[YYYY-MM-DD].md`
containing:
- Valuation multiples vs. industry benchmarks
- Ranked red flag list (financial and operational)
- Negotiation ammunition (what to push for)
- BUY / CAUTION / PASS verdict with rationale
- First 3 actions if proceeding

## File Structure

```
due-diligence-briefer/
├── SKILL.md          # Core skill — 3-phase workflow
├── README.md         # This file
└── LICENSE           # MIT
```

## Installation

Copy to your skills directory:

```bash
cp -r due-diligence-briefer ~/.hermes/skills/
```

Or from the skills-brain:

```bash
cp -r skills/due-diligence-briefer ~/.hermes/skills/
```

No API keys or paid services required. Works with web search alone.