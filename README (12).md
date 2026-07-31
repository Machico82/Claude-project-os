# Componenti premium — pattern ad alto impatto visivo

> Questi componenti aggiungono il fattore "wow" che distingue una landing da 10.000€
> da una generica. Usali con parsimonia: 1-2 per pagina, dove servono al messaggio.

## Card Swap (GSAP)

Animazione di carte che ciclano automaticamente con effetto di profondità e
prospettiva. Perfetta per: testimonianze, piani pricing, feature highlight,
portfolio clienti.

### Comportamento
- Le carte ruotano automaticamente (intervallo configurabile, default 3-4s)
- Ogni carta emerge dal fondo con scala e opacità crescenti (profondità 3D)
- Perspective CSS sulla parent per l'effetto di profondità reale
- **Pause on hover** obbligatorio: l'utente deve poter leggere
- Riduce a dissolvenza statica con `prefers-reduced-motion`

### Parametri customizzabili
- `cardWidth / cardHeight` — dimensioni responsive
- `spacing` — distanza verticale tra le carte impilate
- `easing` — curva GSAP (default `power3.inOut`)
- `autoplayInterval` — millisecondi tra i cicli
- `pauseOnHover` — booleano (default `true`)

### Implementazione di riferimento
```tsx
// Modalità B (produzione React/Next.js) — richiede gsap
import { useRef, useEffect, useState } from 'react';
import gsap from 'gsap';

interface CardSwapProps {
  cards: React.ReactNode[];
  interval?: number;
  easing?: string;
  className?: string;
}

export function CardSwap({
  cards,
  interval = 3500,
  easing = 'power3.inOut',
  className = '',
}: CardSwapProps) {
  const containerRef = useRef<HTMLDivElement>(null);
  const [isPaused, setIsPaused] = useState(false);
  const prefersReduced = typeof window !== 'undefined'
    && window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  useEffect(() => {
    if (prefersReduced || !containerRef.current) return;
    const cardEls = Array.from(containerRef.current.children) as HTMLElement[];
    const total = cardEls.length;
    let activeIndex = 0;

    // Posizionamento iniziale con profondità
    cardEls.forEach((el, i) => {
      gsap.set(el, {
        zIndex: total - i,
        y: i * 8,
        scale: 1 - i * 0.04,
        opacity: 1 - i * 0.2,
      });
    });

    const cycle = () => {
      if (isPaused) return;
      const current = cardEls[activeIndex % total];
      gsap.to(current, {
        y: -200, opacity: 0, scale: 0.9,
        duration: 0.5, ease: easing,
        onComplete: () => {
          // Riporta in fondo al mazzo
          gsap.set(current, { y: (total - 1) * 8, scale: 1 - (total - 1) * 0.04, opacity: 0.2, zIndex: 0 });
          // Riordina gli z-index
          cardEls.forEach((el, i) => {
            const pos = (i - activeIndex - 1 + total * 2) % total;
            gsap.to(el, { y: pos * 8, scale: 1 - pos * 0.04, opacity: 1 - pos * 0.2, zIndex: total - pos, duration: 0.4, ease: easing });
          });
          activeIndex++;
        },
      });
    };

    const timer = setInterval(cycle, interval);
    return () => clearInterval(timer);
  }, [isPaused, prefersReduced, interval, easing]);

  return (
    <div
      ref={containerRef}
      className={`relative [perspective:1200px] ${className}`}
      onMouseEnter={() => setIsPaused(true)}
      onMouseLeave={() => setIsPaused(false)}
      aria-roledescription="carousel"
      aria-label="Testimonianze"
    >
      {cards.map((card, i) => (
        <div key={i} className="absolute inset-0 rounded-2xl shadow-lg bg-surface p-6 will-change-transform" role="group" aria-label={`Card ${i + 1} di ${cards.length}`}>
          {card}
        </div>
      ))}
    </div>
  );
}
```

### In Modalità A (single-file Tailwind CDN)
Stessa logica ma in vanilla JS: GSAP da CDN (`<script src="https://cdn.jsdelivr.net/npm/gsap@3/dist/gsap.min.js">`),
il componente è un `<div>` con carte posizionate in absolute, ciclo `setInterval`.

### Accessibilità
- `aria-roledescription="carousel"`, `aria-label` significativo
- Ogni carta `role="group"` con `aria-label`
- Pause on hover E con pulsante visibile play/pause per tastiera
- Con reduced-motion: mostra tutte le carte in griglia statica (fallback)

---

## Altri pattern premium da ReactBits / Skiper UI / animazioni custom

### Marquee menu
Effetto marquee fluido al hover delle voci di menu. GSAP per il loop infinito.
Ideale per hero creative o footer "esperienziali".

### Staggered reveal
Elementi che entrano in sequenza sfalsata (stagger 0.1-0.15s) con fade+translateY.
GSAP `stagger` o Framer Motion. Perfetto per feature grid, team section, loghi clienti.

### Number counter
Numeri che "contano" da 0 al valore finale quando entrano in viewport.
Solo se il numero È il messaggio ("+1.247 clienti", "€387.000 risparmiati").
Intersection Observer + GSAP `to` o `countUp.js`.

### Magnetic cursor
Elementi che si "attraggono" verso il cursore al passaggio.
Solo per CTA hero su desktop, mai su mobile. Effetto sottile (5-10px max).

### Progressive blur
Sezioni che sfumano con blur progressivo al bordo. CSS `backdrop-filter`
o `mask-image: linear-gradient`. Effetto elegante per transizioni tra sezioni.

---

## Fonti di ispirazione componenti
- **ReactBits** (reactbits.dev) — componenti React premium con GSAP e Framer Motion
- **Skiper UI** (skiper-ui.com) — collezione GSAP + Three.js con preview interattive
- **Aceternity UI** — componenti animati per Next.js/Tailwind
- **Magic UI** — componenti React con animazioni sofisticate

> Regola: copia il PATTERN, non il codice. Adatta al design system del progetto
> (brand/colors.md, references/design-system.md), non usare stili di default delle librerie.
