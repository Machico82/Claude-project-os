# Checklist: Security

- [ ] Nessun secret nel codice/repo; .env in .gitignore
- [ ] Input validato server-side (zod) su ogni endpoint
- [ ] Security headers attivi (CSP, nosniff, referrer-policy)
- [ ] HTTPS forzato; nessun mixed content
- [ ] Rate limiting su form/endpoint pubblici; honeypot antispam
- [ ] Dipendenze: npm audit pulito o eccezioni motivate
- [ ] Errori: nessun dettaglio interno esposto all'utente
- [ ] Auth (se presente): provider gestito, authz server-side su ogni risorsa
- [ ] GDPR: consenso prima dei tracker, policy linkate, dati minimi
