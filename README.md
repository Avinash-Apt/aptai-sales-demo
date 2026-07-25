# AptAI Sales Demos

Interactive sales-enablement walkthroughs of the AptAI process — used on **sales calls** and **2-minute Loom follow-ups** after a cold reply (“Can I share more?”).

## Two demos · one Vercel project

| URL | Audience | Frame |
|-----|----------|--------|
| [`/`](https://aptai-sales-demo.vercel.app/) | B2B SaaS / tech | **Revenue Gen** — cold outbound engine |
| [`/PE`](https://aptai-sales-demo.vercel.app/PE) | PE / M&A / financial services | **Deal Origination** — proprietary deal sourcing |

Switcher in the topbar jumps between them.

## Roadmap (both)

**Week 0 — Foundation** → **Week 2 — Activation/Coverage** → **Week 4+ — Optimization** → **Months 1–3 — Validation Sprint** (3-Month Plan + Case Studies)

The validation sprint teaches **message-market fit**: Month 1 install + early signal, Month 2 iterate/experiments (+ warm extra infra), Month 3 lock MMF and ~3× volume.

## Local

```bash
open index.html          # Revenue Gen
open pe/index.html       # Deal Origination
```

Or any static host. No build step.

## Deploy

Static on Vercel. `vercel.json` rewrites `/PE` → `pe/index.html`.

## Agent docs

- [PLAN.md](PLAN.md) — dual-demo product plan  
- [AGENTS.md](AGENTS.md) — architecture + edit rules  
- [CLAUDE.md](CLAUDE.md) — working playbook  
- [GROK.md](GROK.md) → [agents/Grok.md](agents/Grok.md)

## Scripts

2-minute walkthrough scripts (SaaS + PE): [`sales-demo-scripts.md`](sales-demo-scripts.md)

## Case study assets

Screenshots and logos live in [`Case-Studies/`](Case-Studies/) (mirrored under `pe/Case-Studies/` for the PE page paths).

