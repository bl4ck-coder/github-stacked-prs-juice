# gh-stack-submit.mp4

**Source:** watchVideo. Submit TUI demo.

## CLI prelude
- `gh stack view -s` — stack on `main`: bottom `feat/catalog-data` → `feat/search-api` → `feat/chat-grounding` → `feat/grounded-ui` (current)
- `gh stack push` — `Pushing 4 branches... ✓ Pushed 4 branches` / hint to run submit
- First `gh stack submit` cancelled: `Submit cancelled - no branches were pushed`
- Second opens TUI

## Submit Stack TUI
- Header: `Submit Stack v0.8.7` · Repo `github/zava-demo` · Base `main` · Creating 4 PRs
- Shortcuts: ↑↓ select branch, tab cycle field, `^s` submit PRs
- Left: STACK sidebar; right: Title + Description editors

### PR drafts typed/pre-filled
1. `feat/catalog-data` — Title typed `feat/catalog data` · Desc: typed catalog foundation (model, schema, synthetic data, access) · PR 1/4
2. `feat/search-api` — Title `Add product search API` · Desc prefilled GET `/api/products/search` + `Co-authored-by: Copilot App <223556219+Copilot@users.noreply.github.com>` · PR 2/4
3. `feat/chat-grounding` — Title `Ground chat replies in product search` · mock→API + same Co-authored-by · PR 3/4
4. `feat/grounded-ui` — Title `Render grounded product citation cards` · Desc typed `Product citation cards on the chat UI` · PR 4/4 → `^s SUBMIT 4 PRs`

## Result
```
✓ Created PR #5 for feat/catalog-data
✓ Created PR #6 for feat/search-api
✓ Created PR #7 for feat/chat-grounding
✓ Created PR #8 for feat/grounded-ui
✓ Stack created on GitHub with 4 PRs
```
