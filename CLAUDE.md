# AptAI Sales Demos — Claude SOP

Shared policy: [AGENTS.md](AGENTS.md). Product plan: [PLAN.md](PLAN.md).

Grok enters via [GROK.md](GROK.md) → [agents/Grok.md](agents/Grok.md).

---

## Role

Maintain **two** single-file interactive demos for sales calls and Loom teases:

1. **Revenue Gen** (`index.html`) — B2B SaaS/tech cold outbound  
2. **Deal Origination** (`pe/index.html`) — PE / M&A / financial services proprietary sourcing  

Audience is a buyer on a call or a Loom — not an engineer. Clarity and narrative beat architecture cleverness.

---

## First Session

1. Read `AGENTS.md` + `PLAN.md`  
2. Open both demos; click all phases and subtabs  
3. Confirm switcher works (relative `./` / `./pe/` / `../`)  
4. Edit the file that matches the audience  

---

## How to Work

### Content
- Revenue story → `index.html` `PAGES`  
- PE story → `pe/index.html` `PAGES`  
- Process spine changes (e.g. new month, new phase) → **both** unless asked otherwise  
- PE: enforce vocabulary table in AGENTS/PLAN; no GTM-speak  

### Visual
- Keep cream/teal AptAI system  
- Reuse `.month-card`, `.case-card`, `.mmf-callout`, existing components  

### Privacy
- No Sean McNally / Permanent Corp in public UI  
- Apala metrics OK if already public in AptAI copy  
- Composite permanent-hold persona for live-client patterns  

### Infra widget
- Keep Operator-true ESP math in **both** files  

### Do not
- Add a build/framework without request  
- Commit secrets or real lead lists  
- Leave demos diverged on shared thesis (MMF, 3-month sprint) without intent  

---

## Verification

- [ ] All 7 nav pages × subtabs on **both** demos  
- [ ] ESP sliders  
- [ ] Switcher both directions  
- [ ] PE: no live-client names  
- [ ] Console clean  
- [ ] Vercel: `/` and `/PE` after deploy  

---

## Deploy

Static Vercel. `vercel.json` rewrites `/PE` → `pe/index.html`. No build command.
