# Template Next.js — setup standard CPO

```bash
npx create-next-app@latest [nome] --typescript --tailwind --eslint --app --src-dir
cd [nome]
npx shadcn@latest init
```

## Post-init obbligatorio
1. Token brand: porta brand/colors.md e typography.md in tailwind config + next/font
2. `src/lib/seo.ts`: helper metadata di default (title template, OG, twitter)
3. Security headers in next.config (references/security.md)
4. `src/components/` con: navbar, footer, container, section, cta-button
5. Analytics (references/analytics.md) + cookie banner se serve
6. CI da automation/github.md; deploy da automation/vercel.md

## Struttura consigliata
```
src/
  app/           # route, layout, metadata
  components/    # ui/ (shadcn adattati) + sections/ (blocchi landing)
  lib/           # utils, seo, analytics, validations (zod)
  content/       # eventuali contenuti MDX
```
