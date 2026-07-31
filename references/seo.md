# SEO tecnica e on-page

## Fondamenta tecniche
- Rendering: SSG/SSR per tutto il contenuto indicizzabile
- `robots.txt` + `sitemap.xml` generati automaticamente
- Canonical su ogni pagina; www vs non-www: una sola versione con redirect 301
- 404 personalizzata; redirect 301 per ogni URL cambiato
- HTTPS, nessun mixed content

## On-page per ogni pagina
- 1 `<h1>` con la keyword primaria, gerarchia h2/h3 logica
- `<title>` ≤ 60 char: keyword + beneficio + brand
- Meta description ≤ 155 char: promessa + CTA (non ranking factor, ma CTR sì)
- URL breve, parlante, senza stop-word inutili
- Alt text descrittivi; nomi file immagine sensati (villa-piscina-scarlino.avif)
- Link interni con anchor text descrittive

## Structured data (JSON-LD in <head>)
- Sempre: Organization/LocalBusiness + WebSite
- Landing: Product/Service + FAQPage (se c'è FAQ) + Review/AggregateRating (se reali)
- Casa vacanze: VacationRental/LodgingBusiness con geo, amenity, rating
- Articoli: Article + BreadcrumbList
- Valida con Rich Results Test prima di consegnare

## Open Graph / Twitter
og:title, og:description, og:image (1200×630, testo leggibile), og:url,
twitter:card=summary_large_image. Immagine OG dedicata, non il logo.

## Contenuto
- Search intent prima del volume: la pagina risponde alla domanda dietro la query?
- Un topic per pagina; niente pagine doppie che cannibalizzano
- E-E-A-T: autore reale, contatti veri, chi-siamo credibile
