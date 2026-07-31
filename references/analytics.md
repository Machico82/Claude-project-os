# Analytics & misurazione

## Setup minimo per ogni progetto
1. Definisci la conversione primaria PRIMA di costruire (in brain/business.md)
2. Un tool leggero e GDPR-friendly di default: Plausible/Umami/Fathom
   (GA4 solo se richiesto: richiede cookie banner con consenso preventivo)
3. Eventi: conversione primaria + micro-conversioni (click CTA, scroll 50%,
   apertura FAQ, avvio form)

## Naming eventi
`oggetto_azione` in snake_case: `lead_form_submit`, `cta_hero_click`,
`pricing_view`. Documentali in brain/decisions.md.

## Thank-you page = conversion tracking affidabile
Redirect post-form a /grazie → pageview di /grazie = conversione.
Funziona con qualsiasi tool e sopravvive agli ad-blocker meglio degli eventi JS.

## UTM
Ogni campagna: utm_source / utm_medium / utm_campaign coerenti e minuscoli.
Mai link interni con UTM (inquinano i dati).

## Cosa guardare (in ordine)
1. Conversion rate per sorgente
2. Drop-off: dove escono prima di convertire (scroll depth, funnel form)
3. Solo dopo: bounce, tempo, ecc.

## Regola d'oro
Niente vanity metrics nei report: se un numero non porta a una decisione,
non tracciarlo.
