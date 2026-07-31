# Playbook: Sito SaaS

## Fase 0 — Contesto
- [ ] brain/products.md, pricing.md, competitors.md, avatar.md
- [ ] Mappa pagine: Home, Features, Pricing, [Casi d'uso], About, Blog?, Legal

## Fase 1 — Home
- [ ] Segui playbooks/landing-page.md per la home (è una landing)
- [ ] Hero con screenshot/demo REALE del prodotto (o placeholder dichiarato)
- [ ] Logo cloud clienti se esistono (brain/customers.md)

## Fase 2 — Pricing page
- [ ] Tabella da brain/pricing.md: piano consigliato evidenziato
- [ ] Toggle mensile/annuale; prezzo annuale mostrato come €/mese
- [ ] FAQ pricing sotto la tabella; garanzia/trial accanto a ogni CTA
- [ ] JSON-LD Product con offers

## Fase 3 — Feature pages
- [ ] Una pagina per job-to-be-done, non per feature tecnica
- [ ] Struttura: problema → come lo risolve il prodotto → screenshot → prova → CTA

## Fase 4 — Signup flow
- [ ] Attrito minimo: email (+ SSO se previsto); niente carta se trial free
- [ ] Onboarding: la prima azione di valore entro 2 minuti dal signup

## Fase 5 — Tecnica
- [ ] Next.js App Router; auth con provider gestito (references/security.md)
- [ ] SEO programmatica valutata per /alternatives/[competitor] e /use-cases/
- [ ] Analytics con funnel: visit → signup → activation

## Fase 6 — Self-review
- [ ] Tutte le checklist + domanda chiave: "il valore si capisce senza demo call?"
