# layer3-frontend.mp4

**Agent:** Frontend Agent · skill `gh-stack`

## Prompt (sense; chat-grounding layer)
Add next layer on top of search API: replace mock chat responder with real catalog API calls; ground replies; handle empty/error; **no new UI presentation components**.

## Actions
- `gh stack add chat-grounding` → branch `feat/chat-grounding`
- Edits e.g. `ChatContext.tsx`, `chat.ts`
- Playwright browser → `127.0.0.1:3100` (Zava)

### Plain-text grounded replies (pre-UI layer)
1. Success — "show me interior paint under $70" → catalog hit: Interior Paints by ColorCraft ($34.99/gallon, in stock)
2. Empty — "purple unicorn wallpaper" → no-match fallback suggesting other product/category/brand/material
3. Error — simulated backend fail on "paint" → can't search catalog now; try again

- Commit: `Ground chat replies in product search`
- `gh stack view`: `feat/chat-grounding` → `feat/search-api` → `feat/catalog-data` → `main`
