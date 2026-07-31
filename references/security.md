# Security baseline

## Mai, in nessun caso
- Secrets/API key nel codice o nel repo (.env in .gitignore, env vars su Vercel)
- Fidarsi dell'input utente: valida e sanifica server-side (zod)
- Query costruite per concatenazione (usa ORM/prepared statements)
- Esporre stack trace o messaggi d'errore interni all'utente

## Headers (next.config / vercel.json / astro middleware)
- Content-Security-Policy (almeno per script), X-Content-Type-Options: nosniff,
  Referrer-Policy: strict-origin-when-cross-origin, Permissions-Policy minima
- HSTS in produzione

## Form e API
- Rate limiting su endpoint pubblici (form, login)
- CSRF: usa i meccanismi del framework; CORS ristretto ai domini necessari
- Upload: valida tipo/dimensione server-side, mai eseguire ciò che arriva

## Auth (se presente)
- Mai implementare crypto/auth a mano: Auth.js, Supabase Auth, Clerk
- Password: hashing gestito dal provider; sessioni httpOnly + secure
- Autorizzazione verificata SERVER-side su ogni risorsa (non solo nascondere UI)

## Dipendenze
- `npm audit` prima del deploy; meno dipendenze = meno superficie d'attacco
- Lockfile committato; aggiornamenti di sicurezza prioritari

## GDPR/privacy (mercato EU)
- Cookie banner con consenso PRIMA di caricare tracker non essenziali
- Privacy policy e cookie policy linkate nel footer
- Dati form: solo quelli necessari, informativa al punto di raccolta
