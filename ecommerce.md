# Checklist: Performance

- [ ] Lighthouse mobile ≥ 95 (incognito, throttling attivo)
- [ ] LCP < 2.5s: immagine hero prioritaria, non lazy, < 200KB
- [ ] CLS < 0.1: dimensioni immagini esplicite, niente layout shift a caricamento
- [ ] INP < 200ms: niente long task, JS minimo
- [ ] Font: ≤ 2 WOFF2, swap, preload; niente FOIT
- [ ] Immagini AVIF/WebP responsive; lazy sotto la fold
- [ ] JS iniziale < 150KB gzip; dipendenze auditate
- [ ] Script terzi defer/lazy; niente widget che bloccano il render
- [ ] Test su Fast 3G: usabile entro 3s
