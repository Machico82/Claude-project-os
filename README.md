# Claude Project OS (CPO) v1.0

**The Ultimate Framework for Claude Code** — un sistema di file Markdown che
trasforma Claude Code in un'agenzia digitale senior, pronta a lavorare con
tutto il contesto necessario fin dal primo prompt.

## Filosofia

1. **Il contesto batte il prompt.** Un CLAUDE.md ben progettato + knowledge
   base modulare produce risultati migliori di qualsiasi mega-prompt.
2. **On-demand, non tutto insieme.** Claude legge `references/` e `playbooks/`
   solo quando servono: un contesto gonfio degrada la qualità (context rot).
3. **Self-review obbligatoria.** La differenza tra "buono" e "professionale"
   è la fase in cui Claude critica e corregge il proprio lavoro prima di
   consegnare. È codificata nel CLAUDE.md e nelle checklist.
4. **Il business prima del codice.** La cartella `brain/` contiene chi sei,
   per chi lavori e cosa vendi. Senza quello, ogni landing page è generica.

## Struttura

```
claude-project-os/
├── CLAUDE.md            ← il cervello operativo (letto sempre)
├── README.md, ROADMAP.md, CHANGELOG.md
├── brain/               ← contesto business (DA COMPILARE per ogni progetto)
├── brand/               ← identità visiva e voice (DA COMPILARE)
├── references/          ← best practice per dominio (pronte all'uso)
├── playbooks/           ← workflow passo-passo per deliverable completi
├── checklists/          ← quality gate pre-consegna
├── prompts/             ← prompt library riutilizzabile
├── templates/           ← note di setup per Next.js e Astro
├── automation/          ← CI/CD, deploy, screenshot loop
└── ai/                  ← prompt per generazione asset (Flux, Midjourney…)
```

## Quick start

1. Copia l'intera cartella nella root del tuo nuovo progetto
2. Compila `brain/business.md`, `brain/avatar.md`, `brain/offers.md`
   (bastano questi tre per iniziare)
3. Compila `brand/colors.md` e `brand/voice.md` (o lascia che Claude li
   proponga: "leggi brain/ e proponi brand/colors.md e voice.md")
4. Apri Claude Code e chiedi ad esempio:
   > "Segui playbooks/landing-page.md e crea la landing per l'offerta
   > descritta in brain/offers.md"

## Uso con GSD (opzionale ma consigliato)

CPO definisce **come** Claude lavora; [get-shit-done](https://github.com/gsd-build/get-shit-done)
definisce **in che ordine** (fasi, spec, esecuzione). Si integrano bene:

```bash
npx get-shit-done-cc@latest   # installa GSD
/gsd-new-project              # pianificazione a fasi
```

CPO resta la fonte di verità su standard, brand e business context;
GSD gestisce roadmap, fasi e context rot su progetti lunghi.

## Licenza

MIT — usalo, forkalo, rivendilo dentro i tuoi servizi.
