# Changelog

## [1.2.0] — 2026-07-31

### Added
- references/components-premium.md — Card Swap (GSAP, depth, pause-on-hover,
  a11y carousel) + pattern premium (marquee, staggered reveal, number counter,
  magnetic cursor, progressive blur) con fonti: ReactBits, Skiper UI
- references/superdesign.md — integrazione Superdesign AI design agent
  (install, workflow con canvas, branch varianti, replica HTML, comandi)

### Changed
- playbooks/landing-page.md — nuova Fase 1b (design su Superdesign, opzionale),
  Card Swap e componenti premium integrati in Fase 1 e Fase 3, self-review
  inclusa verifica pause-on-hover e reduced-motion
- prompts/landing-page.md — GSAP da CDN aggiunto in Modalità A, Card Swap tra
  i componenti premium disponibili, opzione Superdesign nel form di compilazione
- references/animations.md — sezione GSAP (CDN + npm, pattern predefiniti, regole)

## [1.1.0] — 2026-07-31

### Added
- references/visual-style.md — direzione estetica di default (Google Font,
  palette scura/neon o calda/beige, rounded-2xl, shadow sottili, micro-animazioni,
  Three.js/Spline in showcase mode)

### Changed
- prompts/landing-page.md — due modalità di output (A single-file Tailwind CDN /
  B produzione Next.js+shadcn); requisiti estetici espliciti; chiarito il conflitto
  ShadCN-React vs single-file CDN
- prompts/hero.md — supporto hero 3D (Spline/Three.js) con lazy-load e fallback
- CLAUDE.md — sezione "Due modalità di landing page" nello stack

## [1.0.0] — 2026-07-31

### Added
- CLAUDE.md core con pipeline agenzia e self-review obbligatoria
- brain/ — 10 file template per il contesto business
- brand/ — 4 file per identità visiva e tone of voice
- references/ — 13 knowledge base operative
- playbooks/ — 7 workflow completi (landing, SaaS, dashboard, ecommerce,
  vacation rental, blog, lead magnet)
- checklists/ — 7 quality gate pre-consegna
- prompts/ — 6 prompt riutilizzabili
- templates/ — note di setup Next.js e Astro
- automation/ — GitHub, Vercel, screenshot loop
- ai/ — prompt library per generazione immagini
