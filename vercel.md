# Generazione immagini AI (Flux / Midjourney / ecc.)

## Quando usare AI vs foto reali
- Prodotti, persone del team, strutture (case vacanze!): SEMPRE foto reali
- AI ok per: illustrazioni concettuali, sfondi astratti, pattern, mockup ambientali
- Mai generare volti presentati come clienti/team reali

## Struttura del prompt
```
[soggetto specifico], [stile], [illuminazione], [composizione/inquadratura],
[palette coerente con brand/colors.md], [mood], --ar 16:9
```

## Template pronti
**Hero astratta tech:**
"abstract geometric gradient background, soft depth of field, [primary color]
and [secondary color] palette, subtle grain, minimal, premium SaaS aesthetic,
wide composition, no text --ar 16:9"

**Illustrazione concettuale:**
"minimal flat illustration of [concetto], limited palette ([brand colors]),
generous negative space, editorial style, no text --ar 4:3"

**OG image base (poi testo via codice, non via AI):**
"clean minimal background for social card, [brand colors] gradient,
subtle texture, space on left for text --ar 1.91:1"

## Regole di consegna
- Comprimi sempre (AVIF/WebP) e rinomina con nomi descrittivi
- Coerenza: stessa "famiglia" visiva in tutto il sito (stesso stile in ogni prompt)
- Dichiara nelle note quali immagini sono AI e vanno eventualmente sostituite
