# Vercel — deploy

## Setup
- Import repo → framework auto-rilevato; env vars da dashboard (mai nel codice)
- Preview deployment per ogni PR: il link preview è il QA environment
- Dominio: apex + www, una versione canonica con redirect

## Configurazione consigliata
- Regione più vicina al pubblico (eu per l'Italia: fra1/cdg1)
- Security headers via next.config o vercel.json (references/security.md)
- Vercel Analytics/Speed Insights: attivare per Web Vitals reali (RUM)

## Regole per Claude
- Prima di dire "deployato": verificare che il build passi in locale
- Rollback: promuovere il deployment precedente, non hot-fixare nel panico
- Cron/Edge functions solo se il playbook lo richiede
