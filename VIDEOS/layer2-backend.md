# layer2-backend.mp4

**Agent:** Backend Agent

## Prompt (verbatim)
> Add the next layer to the stack, on top of the catalog data foundation. Expose the catalog through a product search API that the chat frontend can call. Build on the data-access module from the layer below - don't re-implement the data or matching logic. Keep this layer to the API only - no UI, no changes to the data model. Commit and open the PR for this layer.

## Actions
1. Load gh-stack → create `feat/search-api` on top of `feat/catalog-data`
2. New App Router handler: `src/app/api/products/search/route.ts` (+ `types.ts`)
3. `cd src && npm run build` / `lint`
4. Intertitle: "A FEW MINUTES LATER / agent cooking"
5. User `gh stack view`; manual `npm run build`
6. Curl test: `curl 'http://localhost:3000/api/products/search?q=paint&limit=3'` → JSON (Interior Paint, Paint Sprayer, Painter's Tape)

## `gh stack view`
```
feat/search-api (current) +201 -0 · 2 files · 1 commit
feat/catalog-data +545 -2 · 5 files · 3 commits
main
```
