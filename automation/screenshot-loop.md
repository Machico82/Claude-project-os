# Screenshot loop — auto-review visiva

## Concetto
Claude non "vede" il rendering: il loop screenshot chiude il cerchio.
Build → screenshot → Claude analizza → correggi → ripeti.

## Setup con Playwright
```bash
npm i -D playwright && npx playwright install chromium
```

```ts
// scripts/screenshot.ts
import { chromium } from 'playwright';
const url = process.argv[2] ?? 'http://localhost:3000';
const browser = await chromium.launch();
for (const [name, viewport] of Object.entries({
  mobile: { width: 375, height: 812 },
  desktop: { width: 1440, height: 900 },
})) {
  const page = await browser.newPage({ viewport });
  await page.goto(url, { waitUntil: 'networkidle' });
  await page.screenshot({ path: `screenshots/${name}.png`, fullPage: true });
}
await browser.close();
```

## Workflow per Claude
1. Avvia dev server, esegui lo script, LEGGI gli screenshot
2. Critica: gerarchia, spacing, contrasto, overflow, coerenza col design system
3. Correggi e ripeti finché la self-review visiva passa (max 3 cicli, poi
   consegna con note su ciò che resta)
