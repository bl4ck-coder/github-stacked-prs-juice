# layer1-data.mp4

**Agent:** Data Modeler Agent  
**Skill loaded:** gh-stack

## Prompt (verbatim)
> Start a new stack as the bottom layer for grounding Zava's AI assistant in real data. Our product data is currently hardcoded and scattered across the homepage components with inconsistent shapes. Build the catalog data foundation the API and UI layers will depend on: consolidate it into one typed, validated product catalog with a clean data-access module. Create the stack locally once done.

## Actions
1. Load gh-stack skill → init branch `feat/catalog-data`
2. Inspect: `tsconfig.json`, `schema.ts`, `index.ts`, `seed.ts`, `FeaturedProducts.tsx`, `Page.tsx`, `AllServices.tsx`, `Header.tsx`
3. Merge `origin/main`
4. Validate: `npm run build` + `npm run lint` in `src` — pass
5. User: `gh stack view`

## `gh stack view` (v0.0.7)
```
✓ Stack initialized · Base: main · 1 branch
feat/catalog-data (current) +545 -2
✓ 5 files: catalog/index.ts, schema.ts, seed.ts, package-lock.json, package.json
✓ 3 commits
main
```
