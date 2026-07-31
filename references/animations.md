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

## Accessibilità
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation: none !important; transition: none !important; }
}
```
(o gestito via hook/utility del framework)
