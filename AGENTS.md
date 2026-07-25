# AptAI Sales Demos — Shared Agent Instructions

Single source of truth for AI assistants (Claude, Codex, Gemini, Grok).

**Grok:** `agents/Grok.md` is a thin shim → this file + `CLAUDE.md`. Put shared rules here, not only in the Grok file.

---

## What This Is

Two **static sales demos** in one repo / one Vercel project:

| Path | File | Audience | Product frame |
|------|------|----------|---------------|
| `/` | `index.html` | B2B SaaS / tech | Cold outbound · **Revenue Gen** |
| `/PE` | `pe/index.html` | PE / M&A / financial services | **Proprietary Deal Origination Engine** |

**Sales use:** cold reply → “Can I share more?” → 2-min Loom walking this UI → book the call.

No backend, no build. Demo numbers are illustrative; sidebar ESP cost math matches Operator send-infra SOPs.

---

## Repository Map

| Path | Role |
|------|------|
| `index.html` | Revenue Gen demo (full SPA) |
| `pe/index.html` | PE Origination demo (1:1 structure, different nouns/story) |
| `vercel.json` | `/PE` → `pe/index.html` |
| `PLAN.md` | Product plan, vocabulary swap, 3-month thesis |
| `AGENTS.md` | This file |
| `CLAUDE.md` | Working playbook |
| `GROK.md` / `agents/Grok.md` | Grok entrypoint |
| `README.md` | Human overview |

---

## Architecture (each HTML file)

Same pattern in both demos (~2.6k lines):

1. **`<style>`** — AptAI cream/teal design system + demo-switcher / month-card / case-card  
2. **Shell** — topbar (with Revenue Gen | Deal Origination switcher), sidebar roadmap, ESP sliders, `#page-container`  
3. **`<script>`** — `PAGES` dictionary, `state` + `render()`, `ESP` calculator  

### Nav order (both)

```js
const order = ['tam','icp','infra','launch','analytics','sprint','cases'];
```

| Key | Revenue Gen label | PE label |
|-----|-------------------|----------|
| `tam` | TAM Mapping | Market Map |
| `icp` | ICP & List Building | Investment Criteria |
| `infra` | Infrastructure | Origination Infra |
| `launch` | Launch Campaigns | Activate Sourcing |
| `analytics` | Outbound Analytics | Origination Analytics |
| `sprint` | 3-Month Plan | 3-Month Plan |
| `cases` | Case Studies | Case Studies |

Internal keys stay the same so routing/code stays simple; **user-facing copy diverges**.

### Three-month thesis (required in both)

| Month | Story |
|-------|--------|
| **1** | Full install (weeks 0–4). Early results possible in week 1. Client commits to **3 months**. |
| **2** | Iterate: double down winners, kill losers, run experiments. **Warm extra domains/mailboxes** for M3. Hunt the spark. |
| **3** | **Message-market fit → ~3× volume** behind the winner. Steady pipeline after the spike. |

**Message-market fit** = proven **who + what + when** that reliably produces qualified conversations (meetings for SaaS; owner/advisor conversations for PE). Explicitly call it out — it is the point of the circus.

### PE vocabulary (enforce in `pe/index.html`)

| Never (in PE demo) | Use instead |
|--------------------|-------------|
| GTM pipeline | Origination / deal pipeline |
| TAM (as primary label) | Market Map / Target Universe |
| ICP as “customers” | Investment / acquisition criteria · Ideal Company Profile |
| Campaign (primary) | Sourcing cadence / coverage |
| Cold traffic offer | Approach asset (Ownership Fit & Value-Driver Brief) |
| Lead gen framing | Proprietary / off-market origination |

### Privacy / public safety

- **Do not** name Sean McNally or Permanent Corp in public demo UI unless explicitly cleared. Use **composite** “platform origination lead / permanent-hold acquirer.”  
- **Apala Capital** metrics (23 opps / 20 calls / 3 diligence) OK if already used in AptAI proof; keep accurate.  
- No real lead PII.

### ESP calculator (both — keep Operator-true)

| ESP | Mbx/domain | Sends/mbx | Cost/domain/mo |
|-----|------------|-----------|----------------|
| SMTP | 3 | 20 | $10.50 |
| Outlook | 49 | 5 | $30 |
| Google | 3 | 20 | $10.50 |

Domains: **$12/yr**. Align with Operator `SOPs/sending-infrastructure.md` when changing.

### Design system

Cream `--bg: #FFFCF0`, teal `--accent: #00CFC0` / `--accent-dark: #045660`. Fonts: Plus Jakarta Sans, JetBrains Mono. Assets on AptAI S3. Reuse component classes; don’t invent a second brand.

---

## Edit Rules

1. Prefer surgical edits inside the relevant HTML file.  
2. When changing process spine, update **both** demos unless the user asks for one only.  
3. Keep KPI stories coherent within a demo.  
4. PE demo: origination language only — no lazy “same as GTM” copy-paste.  
5. Public-safe: no secrets, no live-client identifiers without clearance.  
6. After edits: open both files, click every nav item + subtab, drag ESP sliders, `node --check` the script block if possible.

---

## Common Recipes

| Intent | Where |
|--------|--------|
| Revenue Gen copy/KPIs | `index.html` → `PAGES` |
| PE copy/KPIs | `pe/index.html` → `PAGES` |
| New phase (both) | Sidebar + `PAGES` + `order` in **both** files |
| Switcher / routing | Topbar links + `vercel.json` |
| Infra pricing | `ESP` object in both files |
| Product strategy | `PLAN.md` first, then implement |

---

## Verification

1. `open index.html` and `open pe/index.html`  
2. Every `data-page` + every subtab  
3. ESP sliders recompute  
4. Switcher: `/` ↔ `/PE` (works on Vercel; local file:// may need relative `pe/index.html` — topbar uses absolute `/` and `/PE` for production)  
5. PE file: no Sean / Permanent Corp strings  
6. Console clean  
