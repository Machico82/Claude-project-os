# Visual style — direzione estetica di default

> Estetica di riferimento: moderna, minimale, elegante. Ispirazione:
> Linear, Vercel, Stripe. Meno decorazione, più spazio e gerarchia.

## Tipografia
- Font Google di design: **Plus Jakarta Sans** o **Inter** (heading e body).
  Caricali con preconnect + preload del solo peso above-the-fold, `display=swap`.
- Scala tipografica ampia (headline grandi), line-height generoso sul body.

## Palette (scegli UNA direzione, coerente con brand/colors.md)
- **Scura premium:** sfondo quasi-nero (#0A0A0B–#111), testo chiaro, UN accento
  saturo (verde neon / lime, o viola elettrico). Accento usato con parsimonia.
- **Calda minimale:** beige/crema e off-white, testo scuro caldo, accento pastello.
- Contrasto WCAG AA sempre verificato, anche sull'accento.

## Spazio e forma
- Spaziature generose: padding/margin ampi, sezioni ariose (py grandi).
- Bordi arrotondati: `rounded-2xl` su card e superfici, `rounded-xl` su input/bottoni.
- Ombre sottili: `shadow-lg` morbide, mai dure; su sfondo scuro preferisci glow/bordo
  luminoso 1px anziché ombre nere.

## Micro-animazioni
- Hover fluidi su bottoni e card: `transition`, scale ≤1.02, cambio ombra/bordo,
  durata 150–250ms, ease-out.
- Reveal leggero (fade + translate-y 8–16px) all'ingresso delle sezioni.
- SEMPRE dentro `@media (prefers-reduced-motion: reduce)` per disattivarle.

## Responsive
- Mobile-first reale: progetta a 375px, poi espandi. Nessun overflow orizzontale.
- Touch target ≥44px; CTA raggiungibile col pollice.

## 3D e scene (Three.js / Spline) — opzionale, "showcase mode"
- Usali solo se aggiungono significato (hero prodotto, oggetto interattivo), non come riempitivo.
- **Spline:** embed via web component `<spline-viewer url="...">` (script da CDN) o
  export React; caricalo lazy (sotto la fold o dopo interazione), placeholder statico prima.
- **Three.js:** solo per 3D custom; scena leggera, `dispose()` delle risorse,
  pausa del render loop quando fuori viewport.
- Entrambi: mai bloccare l'LCP, disattiva/riduci con reduced-motion, fallback statico
  su mobile a basse prestazioni. In showcase mode il budget performance si rilassa
  consapevolmente — dichiaralo nelle note di consegna.
