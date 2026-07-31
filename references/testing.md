# Testing & QA

## Piramide pragmatica (per siti/landing)
1. **Type-check + lint** — sempre, in CI (`tsc --noEmit`, eslint)
2. **Test manuali strutturati** — checklists/qa.md prima di ogni consegna
3. **E2E leggeri (Playwright)** — solo i flussi critici: form → thank-you,
   checkout, login. 3-5 test valgono più di 100 unit test su una landing
4. **Unit test** — solo per logica di business reale (calcoli, parsing)

## Cosa testare SEMPRE a mano
- Mobile reale (o DevTools iPhone SE 375px): niente overflow orizzontale
- Form: invio ok, errori, doppio click sul submit, campi vuoti
- Link: nessun 404, target=_blank con rel="noopener"
- Dark reader/estensioni non rompono il layout critico
- JS disabilitato: il contenuto principale è leggibile? (per siti content)

## Playwright — pattern minimo
```ts
test('lead form converte', async ({ page }) => {
  await page.goto('/');
  await page.getByLabel('Email').fill('test@example.com');
  await page.getByRole('button', { name: /richiedi/i }).click();
  await expect(page).toHaveURL(/grazie/);
});
```

## Definition of Done
Un task è finito quando: build passa · checklist QA passata · Lighthouse ≥ 95
mobile · zero errori console · self-review del CLAUDE.md eseguita.
