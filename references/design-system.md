# Design system operativo

## Token (fonte: brand/colors.md e typography.md)
- Spacing su scala 4px: 4·8·12·16·24·32·48·64·96·128
- Radius coerente: scegli UN valore base (es. 8px) + 1 per pill/full
- Ombre: 3 livelli max (sm per hover, md per card, lg per modali)
- Container: max-w-6xl/7xl, padding orizzontale 16px mobile / 24px+ desktop

## Layout
- Griglia 12 colonne concettuale; sezioni verticali con py-16/24 (mobile) e py-24/32 (desktop)
- Gerarchia: 1 elemento dominante per viewport; il resto è supporto
- White space generoso: se sembra vuoto, probabilmente è giusto

## Componenti — regole di costruzione
- Ogni componente: varianti esplicite (primary/secondary), taglie, stati completi
  (hover, focus-visible, active, disabled, loading)
- Bottoni: primario pieno (1 per viewport), secondario outline/ghost
- Card: stessa altezza in griglia, gerarchia interna titolo→testo→azione
- Accordion FAQ: nativo `<details>` o headless accessibile
- Form: vedi references/forms.md

## Catalogo componenti standard di una landing
Navbar (minima) · Hero · LogoCloud · ProblemSection · FeatureCards ·
Testimonials · Steps ("come funziona") · Pricing · FAQ · FinalCTA ·
Footer · CookieBanner

## Qualità visiva ("vale 10.000€?")
- Allineamenti perfetti, spaziature dalla scala, mai valori a caso
- Contrasto e gerarchia prima della decorazione
- Ispirazione: Linear, Stripe, Vercel — sobrietà, non effetti speciali
