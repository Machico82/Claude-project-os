# Playbook: Dashboard / Web App interna

## Fase 0 — Contesto
- [ ] Chi la usa, quante volte al giorno, per decidere COSA?
- [ ] Le 3 domande a cui la dashboard deve rispondere a colpo d'occhio

## Fase 1 — Information architecture
- [ ] Gerarchia: KPI primari (max 4) in alto → trend → dettaglio/tabelle
- [ ] Ogni widget risponde a UNA domanda; se non porta a un'azione, eliminalo
- [ ] Layout: sidebar nav + topbar contesto; densità maggiore di un sito marketing

## Fase 2 — Componenti
- [ ] shadcn/ui: Table (sorting, filtri, paginazione server-side), Card KPI
      (valore + delta vs periodo precedente + sparkline), Chart (recharts)
- [ ] Stati SEMPRE: loading (skeleton), empty (con azione), error (con retry)
- [ ] Filtri persistenti nell'URL (condivisibili)

## Fase 3 — Dati
- [ ] Fetch server-side; cache e revalidation esplicite
- [ ] Formattazione: numeri con separatori locali, date relative + assolute al hover
- [ ] Colori semantici coerenti (verde=bene solo se è vero nel dominio)

## Fase 4 — Self-review
- [ ] checklists/qa.md + ux: si capisce in 5 secondi se le cose vanno bene o male?
- [ ] Tabelle con 0, 1, 1000 righe: reggono?
- [ ] Accessibilità tastiera su tabelle e filtri
