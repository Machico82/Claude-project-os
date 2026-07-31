# Frontend — Next.js / React / Astro

## Scelta framework
- Sito vetrina / landing / blog → **Astro** (zero JS di default, isole per interattività)
- Web app / SaaS / dashboard / auth → **Next.js App Router**
- Motivare la scelta in brain/decisions.md

## Next.js — regole
- Server Components di default; `"use client"` solo su foglie interattive
- Data fetching sul server; niente useEffect per fetch iniziali
- `next/image`, `next/font`, `metadata` API per SEO
- Route handlers per API; validazione input con zod
- Loading/error/not-found file per ogni route significativa

## React — regole
- Stato minimo: derivare invece di duplicare; sollevare solo quando serve
- Componenti < 150 righe; estrai quando un blocco ha un nome sensato
- Chiavi stabili nelle liste (mai index se la lista muta)
- Custom hook quando la logica si ripete 2 volte
- Form: react-hook-form + zod per app; form nativi + validazione per landing

## Astro — regole
- `.astro` per tutto ciò che non è interattivo
- Isole con `client:visible` (non `client:load` di default)
- Content collections per blog/contenuti tipizzati

## TypeScript
- strict: true; tipi espliciti sulle API boundary; inferenza dentro
- Niente `any`: usa `unknown` + narrowing; niente `as` per zittire errori

## Tailwind + shadcn/ui
- Token dal design system, mai colori/spacing arbitrari nei componenti
- shadcn: copia i componenti nel repo, adattali ai token, non trattarli come lib esterna
- Classi ordinate: layout → spacing → typography → colors → states
