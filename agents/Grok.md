# Grok Entrypoint — AptAI Sales Demos

## Required Reading

1. `AGENTS.md` — dual-demo architecture, PE vocabulary, privacy, ESP math  
2. `CLAUDE.md` — working playbook  
3. `PLAN.md` — product intent (when changing structure or thesis)  

## Role

Implement and maintain the **Revenue Gen** and **Deal Origination** static demos. Same rules as other agents.

Do not fork policy here — update `AGENTS.md` / `CLAUDE.md` / `PLAN.md`.

## Thin-Context Protocol

- Two files, one product: `index.html` + `pe/index.html`  
- Same `data-page` keys; different user-facing language  
- Message-market fit + 3-month sprint exist in **both**  
- PE = origination language; never “GTM pipeline”  
- No Sean / Permanent Corp in public UI  
- Prefer surgical HTML edits; no framework unless asked  

## Quick map

| Need | File |
|------|------|
| B2B SaaS demo | `index.html` |
| PE / M&A demo | `pe/index.html` |
| `/PE` routing | `vercel.json` |
| Strategy | `PLAN.md` |
