# Form che convertono

## Regole di conversione
- Chiedi il minimo: ogni campo extra costa conversioni. Nome+email spesso bastano
- Un form = un obiettivo; multi-step se i campi sono > 5 (progress visibile)
- Label sopra il campo, sempre visibili (mai solo placeholder)
- CTA specifica: "Ricevi il preventivo" non "Invia"
- Microcopy anti-obiezione sotto il submit: privacy, no spam, tempi di risposta

## Validazione
- Inline, al blur, mai solo al submit; messaggi che dicono COME correggere
- Client E server: mai fidarsi del client
- Errore: bordo + icona + testo (mai solo colore) + focus sul primo campo errato

## Tecnica
- `autocomplete` corretti, `inputmode` per mobile (email, tel, numeric)
- Submit disabilitato durante l'invio + spinner + testo "Invio in corso…"
- Stato di successo esplicito o redirect a thank-you page (meglio: traccia la conversione)
- Honeypot + rate limiting server-side contro spam (evita CAPTCHA se possibile)

## Dopo il submit
- Thank-you page con: conferma, cosa succede ora, eventuale secondo step
- Email di conferma se il flusso lo prevede
- Evento di conversione tracciato (references/analytics.md)
