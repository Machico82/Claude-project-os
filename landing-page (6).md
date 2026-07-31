# Playbook: Landing Page da 10.000€

## Fase 0 — Contesto (5 min)
- [ ] Leggi brain/business.md, avatar.md, offers.md, customers.md, faq.md
- [ ] Se mancano dati chiave → chiedi: target, promessa, CTA, prove disponibili
- [ ] Conferma con l'utente: obiettivo di conversione + traffico atteso (freddo/caldo)
- [ ] Scegli modalità: A (single-file showcase) o B (produzione) — vedi prompts/landing-page.md

## Fase 1 — Strategia (mostra all'utente, attendi ok)
- [ ] Definisci: promessa unica, angolo differenziante, livello di consapevolezza
- [ ] Wireframe testuale: elenco sezioni nell'ordine scelto con l'idea di ciascuna
- [ ] Headline: proponi 3 varianti (formule in references/copywriting.md), scegline 1
- [ ] Identifica dove usare componenti premium (references/components-premium.md):
      es. **Card Swap** per testimonianze/feature, number counter per social proof,
      staggered reveal per feature grid. Max 2 effetti premium per pagina.

## Fase 1b — Design su Superdesign (opzionale, consigliata per clienti)
Se l'utente vuole vedere varianti di design prima del codice:
- [ ] Segui references/superdesign.md → setup design system, crea progetto,
      branch 2-3 varianti, condividi preview
- [ ] Itera sul canvas finché il design è approvato
- [ ] Scarica HTML reference (`superdesign get-design --draft-id <id>`)
- [ ] Salva draftId approvato in brain/decisions.md
→ Se saltata, procedi con lo stile di references/visual-style.md

## Fase 2 — Copy completo (prima del design)
- [ ] Scrivi TUTTO il copy sezione per sezione, con le parole di brain/avatar.md
- [ ] FAQ da brain/faq.md: 5-8, incluse le scomode
- [ ] Social proof SOLO da brain/customers.md; se vuoto, sezione con placeholder dichiarati
- [ ] CTA identica ripetuta ogni ~2 schermate + microcopy anti-obiezione

## Fase 3 — Design & build
- [ ] Setup progetto (templates/astro o nextjs) con token da brand/
- [ ] Google Font di design (Plus Jakarta Sans / Inter), palette da visual-style.md
- [ ] Componenti base da references/design-system.md, mobile-first, rounded-2xl,
      shadow-lg sottili, spaziature generose
- [ ] Micro-animazioni hover + reveal (references/animations.md + visual-style.md)
- [ ] Componenti premium selezionati in Fase 1 (references/components-premium.md):
      - Card Swap con GSAP: dimensioni, easing, pause-on-hover, a11y carousel
      - Number counter, staggered reveal, ecc. se previsti
- [ ] Three.js / Spline nella hero solo se deciso in Fase 0 (lazy, fallback statico)
- [ ] Form secondo references/forms.md + thank-you page

## Fase 4 — SEO & tracking
- [ ] Metadata, OG image, JSON-LD (Service/Product + FAQPage) da references/seo.md
- [ ] Analytics + evento conversione da references/analytics.md
- [ ] Cookie banner se ci sono tracker non essenziali

## Fase 5 — Self-review (obbligatoria)
- [ ] checklists/conversion.md → correggi
- [ ] checklists/seo.md, performance.md, qa.md, accessibility.md → correggi
- [ ] Test dei 5 secondi sulla hero: passa?
- [ ] Card Swap: pause on hover funziona? reduced-motion mostra griglia statica?
- [ ] "Un cliente pagherebbe 10.000€?" Se no: cosa manca? Fallo.

## Fase 6 — Consegna
- [ ] Note: cosa è stato fatto, cosa testare, dati reali da inserire, idee A/B test
- [ ] Se usato Superdesign: link al canvas + draftId per iterazioni future
