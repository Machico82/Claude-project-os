# Performance & Core Web Vitals

## Budget (non negoziabili senza motivo scritto)
- LCP < 2.5s · INP < 200ms · CLS < 0.1 · Lighthouse ≥ 95
- JS iniziale < 150KB gzip · CSS critico inline se necessario
- Font: max 2 file WOFF2, preload, `font-display: swap`

## Immagini (causa n°1 di pagine lente)
- AVIF/WebP con fallback; dimensioni responsive (`sizes` corretto)
- `width`/`height` sempre espliciti (CLS); lazy sotto la fold
- L'immagine LCP: `priority`/`fetchpriority="high"`, MAI lazy
- Hero < 200KB; niente video autoplay pesanti come sfondo su mobile

## JavaScript
- Server Components / static di default; idratare solo l'interattivo
- Dynamic import per ciò che sta sotto la fold o dietro interazione
- Audita le dipendenze: se una lib serve per una funzione, scrivi la funzione
- Script terze parti: `defer`/lazyload, caricali dopo l'interazione se possibile
  (chat widget, analytics pesanti)

## CSS
- Tailwind con purge attivo; niente framework CSS aggiuntivi
- Evita @import a catena; critical CSS gestito dal framework

## Verifica prima di consegnare
1. Lighthouse mobile (non desktop) in incognito
2. Network throttling "Fast 3G": la pagina è usabile entro 3s?
3. Controlla CLS scrollando: nulla deve "saltare"
