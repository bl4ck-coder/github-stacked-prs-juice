# compare-before-and-after-improved.mp4

**Source:** watchVideo (visual). Blog demo compare graphic.

## Title card
- "GitHub Stacked PRs"
- Sub: "Breaking one **1,535-line** PR into **4** focused, reviewable PRs"

## Before — single PR
- Title: `Ground chat assistant in catalog data #2`
- Open; `julianna-rut4` wants to merge 1 commit into `main` from `julianna/ui-ground-chat-in-catalog`
- Diff: **+1,535 / −168**
- Tabs: Conversation 4 · Commits 6 · Checks 7 · Files changed **38**
- Button: Submit review

## After — 4 stacked PRs

### L1 `catalog-data` (+561, green)
- PR: `feat/catalog data #5` → merge into `main` from `feat/catalog-data` (2 commits)
- Ready to merge; Files changed 5; Checks 19
- Desc: "Add typed catalog data foundation (model, schema, synthetic data, access)"
- Reviewer: Copilot

### L2 `product-api` / `feat/search-api` (+201, blue)
- PR: `Add product search API #6` → base `feat/catalog-data` from `feat/search-api`
- Files 3; Desc: validated GET `/api/products/search` via catalog data-access; safe JSON errors

### L3 `ground-chat` / `feat/chat-grounding` (+399, orange)
- Base `feat/search-api` from `feat/chat-grounding`
- Title obscured in animation; Files 4
- Desc: replace mock chat with product search API; grounded / no-result / failure replies
- "Co-authored by Copilot App"

### L4 `grounded-ui` (+215, purple)
- PR: `Render grounded product citation cards #8` → base `feat/chat-grounding` from `feat/grounded-ui`
- Files 2; Desc: product citation cards on chat UI

Footer on cards: "Stack created with GitHub CLI `gh pr create`".

## Numerics cross-check
Article prose cites ~1,721 lines in one place; this demo graphic uses **1,535** additions on the monolith PR. Treat 1,535 as `[empirically-grounded]` from this video; 1,721 as `[claimed]` article narration (possibly different snapshot). Stack adds: 561+201+399+215 = **1,376** (not equal to 1535 — expected: deletions/refactors and layer boundaries differ from monolith).
