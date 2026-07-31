# Prompt: Landing page completa

Segui `playbooks/landing-page.md` e la direzione estetica in
`references/visual-style.md`. Prima di generare, scegli la MODALITÀ di output.

## Scegli la modalità

**Modalità A — Single-file "showcase" (demo, landing veloce, effetto wow)**
Output: un unico `index.html` autonomo. Stack:
- **Tailwind CSS via CDN** (`<script src="https://cdn.tailwindcss.com">`), con
  config inline per i token brand (colori, font, radius).
- **Google Font** di design (Plus Jakarta Sans o Inter) con preconnect + swap.
- Componenti costruiti a mano **nello stile visivo di ShadCN** (palette neutra,
  `rounded-2xl`, bordi 1px sottili, `shadow-lg` morbide) — NON i componenti React
  di shadcn/ui, che qui non sono utilizzabili.
- Opzionale: **Spline** via `<spline-viewer>` (CDN) o **Three.js** (CDN) per la
  hero 3D, in lazy-load e con fallback statico. Vedi visual-style.md → "showcase mode".
- Micro-animazioni hover fluide, reveal on scroll, tutto sotto `prefers-reduced-motion`.

**Modalità B — Produzione (SEO, performance, progetto reale, riuso)**
Output: progetto Next.js o Astro (templates/). Stack:
- **Tailwind via build** (non CDN) + **componenti reali di shadcn/ui** copiati nel repo
  e adattati ai token di `brand/`.
- **next/font** (o self-host) per il Google Font; immagini ottimizzate.
- Three.js/Spline solo se richiesti, lazy e senza bloccare l'LCP.
- Rispetta il budget performance del framework (Lighthouse ≥95, JS iniziale <150KB).

> Regola: ShadCN UI (React) vive solo in Modalità B. In Modalità A si replica il suo
> LOOK, non i suoi componenti. Se l'utente chiede "componenti ShadCN" + "single file
> Tailwind CDN", segnala il conflitto e proponi: A per la resa rapida, B per usarli davvero.

## Compila prima di eseguire

```
Modalità: [A single-file showcase | B produzione]
Contesto: leggi brain/ (business, avatar, offers, customers, faq) e brand/.
Obiettivo di conversione: [ES: richieste di preventivo via form]
Traffico: [freddo da ads | caldo da lista | SEO]
Estetica: segui references/visual-style.md → direzione palette: [scura premium | calda minimale]
3D/Spline: [no | sì, nella hero — accetto il costo performance dichiarato]
```

## Requisiti estetici non negoziabili (entrambe le modalità)
- Font Google di design (Plus Jakarta Sans / Inter), non font di sistema
- Palette sofisticata e coerente con brand/colors.md (scura con accento neon, o calda/beige)
- Spaziature generose, `rounded-2xl`, `shadow-lg` sottili
- Micro-animazioni hover fluide + reveal on scroll, disattivabili con reduced-motion
- Layout completamente responsive, mobile-first (test a 375px: nessun overflow)
- Cura maniacale dei dettagli: allineamenti perfetti, contrasto AA, zero placeholder

## Flusso
Fermati dopo la Fase 1 del playbook (strategia + wireframe testuale + 3 headline +
modalità scelta) e attendi il mio ok prima di scrivere copy e codice.
Chiudi sempre con la self-review (checklists/) prima di consegnare.
