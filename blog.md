# Checklist: Launch (pre-pubblicazione)

## Prima del deploy
- [ ] Tutte le altre checklist passate (conversion, seo, performance, qa, a11y, security)
- [ ] Contenuti reali al posto di ogni placeholder; dati cliente verificati
- [ ] Dominio, DNS, SSL configurati; www→apex (o viceversa) con 301
- [ ] Env vars di produzione impostate su Vercel

## Deploy
- [ ] Deploy su preview → verifica → promote a produzione
- [ ] Sitemap inviata a Google Search Console; proprietà verificata
- [ ] Analytics attivo e evento conversione testato IN PRODUZIONE

## Post-launch (prime 24h)
- [ ] Test conversione reale end-to-end (form/acquisto vero)
- [ ] Search Console: nessun errore di indicizzazione
- [ ] Uptime/error monitoring attivo (Vercel + eventuale Sentry)
- [ ] Consegna al cliente: accessi, guida rapida, cosa monitorare

## Note per l'utente
- [ ] Elenco "dati reali mancanti" se qualcosa è rimasto provvisorio
- [ ] 3 idee di A/B test per iterare (headline, CTA, ordine sezioni)
