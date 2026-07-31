# Animazioni e motion design

## Principi
- Il motion comunica (gerarchia, feedback, continuità), non decora
- Se un'animazione non ha uno scopo, eliminala
- Timing: micro-interazioni 150-250ms, transizioni di sezione 300-500ms
- Easing: ease-out per entrate, ease-in per uscite; mai linear per UI

## Cosa animare (whitelist)
- Fade+translate-up leggero (8-16px) all'ingresso delle sezioni in viewport
- Hover di card e bottoni (scale ≤ 1.02, shadow, colore)
- Accordion, modali, toast
- Numeri che contano SOLO se il numero è il messaggio

## Cosa NON fare
- Parallax pesanti su mobile, animazioni su scroll che rubano lo scroll
- Elementi che si muovono mentre l'utente legge
- Animare `top/left/width` → solo `transform` e `opacity` (compositor)
- Librerie da 80KB per un fade-in

## Strumenti
- CSS transitions/animations: prima scelta
- Framer Motion: micro-interazioni e presenza (AnimatePresence) in React
- GSAP + ScrollTrigger: solo per scroll-telling esplicitamente richiesto
- Intersection Observer per reveal on scroll senza librerie

## GSAP — integrazione nel framework

### CDN (Modalità A single-file)
```html
<script src="https://cdn.jsdelivr.net/npm/gsap@3/dist/gsap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/gsap@3/dist/ScrollTrigger.min.js"></script>
```

### npm (Modalità B produzione)
```bash
npm install gsap
```
```ts
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);
```

### Pattern predefiniti (dettagli in references/components-premium.md)
- **Card Swap** — autoplay ciclico con depth, pause on hover, a11y carousel
- **Staggered reveal** — `gsap.from(els, { y: 20, opacity: 0, stagger: 0.12, scrollTrigger })`
- **Number counter** — `gsap.to(el, { textContent: target, snap: { textContent: 1 }, scrollTrigger })`

### Regole GSAP
- Mai animare `top/left/width`: solo `transform` + `opacity`
- `will-change: transform` sugli elementi animati, rimosso dopo l'animazione
- Timeline + ScrollTrigger: `kill()` nel cleanup (useEffect return / onDestroy)
- Su mobile: riduci complessità (meno particelle, meno parallax, stagger più corto)

## Accessibilità
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation: none !important; transition: none !important; }
}
```
(o gestito via hook/utility del framework)
