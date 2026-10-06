# layer3-frontend.mp4

**Agent:** Frontend Agent · skill `gh-stack`

## Prompt (sense)
Add next layer on top of search API: replace mock chat responder with real catalog API calls; ground replies; handle empty/error; **no new UI presentation components**.

## Actions
- `gh stack add chat-grounding` → branch `feat/chat-grounding`
- Edits e.g. `ChatContext.tsx`, `chat.ts`
- Playwright → `127.0.0.1:3100` (Zava)

### Plain-text grounded replies (pre-UI layer)
1. **Success** — "show me interior paint under $70" → *"I searched the catalog... found 1 matching product: - Interior Paints by ColorCraft ($34.99/gallon, in stock)"*
2. **Empty** — "purple unicorn wallpaper" → *"I couldn't find any catalog products matching 'purple unicorn wallpaper'. Try another product name, category, brand, or material."*
3. **Error** — simulated fail on "paint" → *"I couldn't search the catalog right now, so I can't make a grounded product recommendation. Please try again in a moment."*

- Commit: `Ground chat replies in product search`
- `gh stack view`: `feat/chat-grounding` → `feat/search-api` → `feat/catalog-data` → `main`
