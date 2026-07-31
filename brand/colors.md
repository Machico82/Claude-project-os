# Palette colori

<!-- Compila o chiedi a Claude di proporla partendo da brain/. Questi valori diventano i token Tailwind. -->

## Token
| Token | Hex | Uso |
|---|---|---|
| primary | [#______] | CTA, link, elementi chiave |
| primary-hover | [#______] | Stato hover della CTA |
| secondary | [#______] | Accenti, badge |
| background | [#______] | Sfondo pagina |
| surface | [#______] | Card, sezioni alternate |
| text | [#______] | Testo principale (contrasto ≥ 7:1 su background) |
| text-muted | [#______] | Testo secondario (contrasto ≥ 4.5:1) |
| success / warning / error | [#__] [#__] [#__] | Stati form e feedback |

## Regole
- La CTA primaria usa il colore più saturo della palette e appare UNA volta per viewport
- Max 1 colore d'accento oltre al primario
- Verifica sempre il contrasto WCAG AA (4.5:1 testo, 3:1 UI)
- Dark mode: definire solo se richiesta; non improvvisarla invertendo i colori

## Tailwind
```js
// tailwind.config: estendere theme.colors con i token sopra,
// mai usare colori arbitrari (bg-[#hex]) nei componenti
```
