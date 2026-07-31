# Template Astro — setup standard CPO

```bash
npm create astro@latest [nome] -- --template minimal --typescript strict
npx astro add tailwind sitemap
```

## Post-init obbligatorio
1. Token brand in tailwind config; font self-hosted con preload
2. `src/layouts/Base.astro`: head completo (meta, OG, JSON-LD slot, canonical)
3. `src/components/sections/`: Hero, Features, Testimonials, FAQ, CTA, Footer
4. Immagini SOLO via astro:assets; hero con priority
5. robots.txt + sitemap integration configurata
6. Form: endpoint (Astro actions o servizio esterno) + /grazie per tracking

## Quando scegliere Astro
Landing, siti vetrina, case vacanze, blog: contenuto > interattività.
Se servono auth/dashboard/stato complesso → templates/nextjs.
