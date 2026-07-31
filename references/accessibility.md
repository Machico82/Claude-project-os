# Accessibilità (WCAG 2.1 AA)

## Struttura
- HTML semantico: header/nav/main/section/footer, heading gerarchici
- Landmark unici; skip-link "Vai al contenuto" come primo elemento focusabile
- Ordine DOM = ordine visivo = ordine di lettura sensato

## Tastiera
- Tutto raggiungibile e azionabile con Tab/Enter/Esc
- Focus visibile SEMPRE (mai outline:none senza sostituto)
- Modali: focus trap, Esc per chiudere, ritorno del focus all'origine

## Contrasto e testo
- Testo 4.5:1, testo grande e componenti UI 3:1
- Zoom 200% senza rotture; niente testo dentro immagini per contenuti chiave

## Form
- `<label>` associata a ogni campo (mai solo placeholder)
- Errori: testo esplicito vicino al campo + `aria-describedby`, non solo colore
- `autocomplete` corretto (email, name, tel…)

## Media e motion
- Alt text: descrivi funzione/contenuto; decorative → alt=""
- `prefers-reduced-motion`: disattiva animazioni non essenziali
- Niente autoplay audio; sottotitoli per i video informativi

## ARIA
- Prima regola dell'ARIA: non usare ARIA se esiste l'elemento nativo
- `aria-expanded` su accordion/menu, `aria-live` per feedback dinamici
