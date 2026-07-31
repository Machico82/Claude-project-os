# GitHub — workflow e CI

## Repo setup
- main protetto; feature branch → PR → merge (anche in solo: la PR è la review)
- Conventional commits: feat / fix / refactor / docs / chore / perf
- .gitignore: node_modules, .env*, .next/dist, .DS_Store

## CI minima (.github/workflows/ci.yml)
```yaml
name: CI
on: [push, pull_request]
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 22, cache: npm }
      - run: npm ci
      - run: npm run lint
      - run: npx tsc --noEmit
      - run: npm run build
```

## Regole per Claude
- Commit atomici a fine di ogni fase del playbook
- Mai forzare push; mai committare file generati o secrets
- CHANGELOG.md aggiornato a ogni release significativa
