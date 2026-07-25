# Dual Sales Demo Plan — Revenue Gen + PE Origination

**Goal:** One Vercel project, two demos, switchable by audience.

| Path | Audience | Product frame |
|------|----------|---------------|
| `/` (`index.html`) | B2B SaaS / tech — revenue generation | Cold outbound engine |
| `/PE` (`pe/index.html`) | PE / M&A / financial services — deal sourcing | Proprietary **Origination Engine** |

**Sales motion (both):** cold reply → “Can I share more?” → 2-min Loom walking this demo → book the call.

---

## 1. Original demo upgrades (B2B tech)

### Keep as-is (structure)
- Week 0: TAM · ICP · Infrastructure  
- Week 2: Launch Campaigns  
- Week 4+: Outbound Analytics  

### Add below the 4-week process

**Phase: Months 1–3 · Validation Sprint**

| Nav item | Subtabs | Story |
|----------|---------|--------|
| **3-Month Plan** | Month 1 · Month 2 · Month 3 | Why clients give 3 months; early wins possible week 1; iteration; **message-market fit**; then scale |
| **Case Studies** | (single page or 2–3 cards) | Named/anonymized proof that the process works |

#### Three-month thesis (both demos — same spine, different nouns)

| Month | What happens | Why it matters |
|-------|----------------|----------------|
| **1** | Foundation + first live sends. Full Week 0–4 engine. Real replies/meetings can appear in **week 1**. Client commitment: **3 months**, not a one-week trial. | Install the system; show early signal without claiming a silver bullet. |
| **2** | **Iteration.** Double down on winners; kill losers; run disciplined experiments (subject, opener, segment, cadence, offer). Warm **extra domains/mailboxes** so Month 3 can absorb volume. Hunt for the **spark**. | Most of the learning lives here. |
| **3** | **Message-market fit → scale.** Once a message/segment combination works, put **3× volume** behind it. Scale infrastructure that was warming in M2. New variants appear under load; keep a **steady pipeline** after the spike. | MMF is the point of the whole circus. Without it, more volume only multiplies noise. |

**Message-market fit (call out explicitly in both demos):**  
The highest-leverage concept in cold outbound. It is *not* “more mailboxes.” It is the proven pairing of **who + what + when** that reliably produces qualified conversations. Month 3 is when you earn the right to scale that pairing.

**Subtle truth (show through design, don’t preach):** this is a system and a time-boxed sprint — not a magic button.

### Case studies tab (B2B)
- Prefer real AptAI B2B/tech outcomes if public-safe; otherwise strong anonymized cohort cards.
- Structure: problem → motion → metrics → lesson.

---

## 2. PE / M&A demo (1:1 rebuild)

### Product name
**Proprietary Deal Origination Engine** (never “GTM pipeline”).

### Vocabulary (enforced)

| SaaS demo | PE demo |
|-----------|---------|
| TAM Mapping | **Market Map** / Target Universe |
| ICP | **Investment Criteria** / Ideal Company Profile |
| Cold outbound | **Proprietary sourcing** / off-market origination |
| Campaign | **Sourcing cadence** / coverage |
| Pipeline | **Deal / origination pipeline** |
| Lead magnet | **Approach asset** (Ownership Fit & Value-Driver Brief) |
| Reply → meeting | Reply → call / management meeting / NDA |
| Hot lead | **Actionable conversation** / mandate-fit opportunity |

### Roadmap mirror

| SaaS | PE |
|------|-----|
| TAM Mapping | Market Map |
| ICP & List Building | Investment Criteria & Target List |
| Infrastructure | Origination Infrastructure |
| Launch Campaigns | Activate Sourcing Cadence |
| Outbound Analytics | Origination Analytics |
| 3-Month Plan | 3-Month Validation Sprint (same spine, PE nouns) |
| Case Studies | Case Studies (Apala named; permanent-hold composite **anonymized**) |

### Content anchors (from context package)
- Master ICP: long-hold, founder-friendly acquirers who want proprietary origination as a real channel.
- Persona A: operator-led search / partner-equity (Apala arc — operational likeness as wedge).
- Persona B: platform origination lead at permanent-hold group (Sean composite — **genericize name/company** for public demo unless cleared).
- Offer beat: **Ownership Fit and Value-Driver Brief** (not valuation, not calendar-first CTA).
- Proof: Apala — 23 opportunities / 20 booked calls / 3 diligence-stage deals (~11k emails). Lesson: successor-operator credibility.
- Day-in-life beats for origination operator (reply triage, thesis fit, confidential approach, durable engine vs activity).

### Encapsulate vertical flavors
Copy should read as covering **buy-side PE, M&A advisory adjacency, and financial services deal sourcing** — sourcing companies that want to sell, merge, or be acquired / partnered — without forcing pure RIA “customer acquisition” GTM language into the PE demo.

---

## 3. Vercel dual-host architecture

```
aptai-sales-demo/
├── index.html          # B2B Revenue Gen demo
├── pe/
│   └── index.html      # PE Origination demo
├── vercel.json         # /PE → pe/index.html
├── PLAN.md
├── AGENTS.md …
```

**Switcher:** topbar control on both demos  
`Revenue Gen` ↔ `Deal Origination` (links `/` and `/PE`).

**vercel.json**
```json
{
  "rewrites": [
    { "source": "/PE", "destination": "/pe/index.html" },
    { "source": "/PE/(.*)", "destination": "/pe/$1" },
    { "source": "/pe", "destination": "/pe/index.html" }
  ]
}
```

No build step. Same brand system (cream + teal). Different nouns, KPIs, personas, case studies.

---

## 4. Implementation order

1. ~~Plan (this file)~~  
2. Upgrade `index.html` — sprint + cases + light MMF language + demo switcher  
3. Build `pe/index.html` — full 1:1 PE rewrite  
4. Add `vercel.json`  
5. Update `AGENTS.md` / `CLAUDE.md` / `GROK.md` / `README.md`  

---

## 5. Public-safety rules

- **Do not** put Sean McNally / Permanent Corp as a named public case study unless explicitly cleared. Use composite “permanent-hold platform origination lead.”  
- **Apala** metrics OK if already used in AptAI proof copy (confirm before heavy brand use).  
- No real lead PII, no private CRM screenshots.
