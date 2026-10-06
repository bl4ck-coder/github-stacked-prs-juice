# Article digest (text layer)

**Title:** Turn one giant AI-generated pull request to a reviewable stack  
**Author:** Julia Muiruri (@juliamuiruri4)  
**Published:** 2026-08-04  
**URL:** https://github.blog/engineering/turn-one-giant-ai-generated-pull-request-to-a-reviewable-stack/

## Problem frame

Agents amplify throughput. Default agent ship pattern = one giant PR (example: ~1,721 lines for "add product search"): data model + seed + API + client wiring + UI + empty/error states in one diff. Review stalls; feedback quality drops; merge slows; conflicts grow. `[claimed]`

Gartner cited in post: agents projected to drive ~50% productivity gain across every SDLC stage by 2028. `[sales]` / `[claimed]` (secondary cite; not verified here)

## Solution frame

**Stacked PRs = decomposition + dependency chain.** Feature becomes ordered layers; each PR is one concern, small enough to hold in a reviewer's head; context flows from previously reviewed layer. `[empirically-grounded]` (product + tutorial)

Stack base matters: CI checks and merge rules evaluate against the **stack base** throughout the lifecycle. `[empirically-grounded]`

## Example stack (shopping assistant / product search)

Starting state described in post: mock AI assistant (random-line generator), inconsistent hardcoded product data, no catalog/API/data layer.

| Layer | Branch | Ships | Depends on |
| --- | --- | --- | --- |
| L1 | `feat/catalog-data` | Typed catalog + seed + validation + data access | `main` (stack base) |
| L2 | `feat/search-api` | Validated `/api/products/search` | L1 |
| L3 | `feat/chat-grounding` | Chat calls API; answers from real product data | L2 |
| L4 | `feat/grounded-ui` | Product citation cards + state | L3 |

Agent assignment in demo: L1 Data modeler; L2 Backend; L3+L4 Frontend (split deliberately so UI owner doesn't review data flow and vice versa). `[claimed]` (demo fiction)

## Tooling

```
gh extension install github/gh-stack
gh skill install github/gh-stack
# or: npx skills add github/gh-stack
```

Lifecycle verbs in post: `gh init stack` / `gh stack init`, `gh stack add`, `gh stack push`, `gh stack submit`, `gh stack rebase`, `gh stack sync`. Docs tutorial also uses `gh stack down` / `up` / `checkout`, `gh stack rebase --upstack`. Confirm exact CLI on `github/gh-stack` before rote memorizing aliases. `[constructed-but-coherent]`

## Review discipline

- **Read top-down** (end goal / bearing).
- **Review + merge bottom-up** (checkpoints).
- Stack map on each PR = one-click navigation across the chain.
- Fix on the **owning layer**, then rebase/sync upstack — don't patch wrong branch.

## Critical warning (post)

Web **"Rebase stack"** button runs rebase on GitHub servers → committer becomes who clicked; commits **unsigned**. If branch protection requires signed commits, that click quietly breaks the stack. Prefer local `gh stack rebase` + `gh stack push` with your git identity. `[empirically-grounded]` (stated mechanism in post)

## After bottom-layer fix

GitHub flags: "Some branches in this stack have diverged and must be rebased" + "Unable to merge as a stack". Then: rebase → `gh stack sync` (fetch, cascade rebase above changed layer, push, sync PR state). CI re-runs; stack map returns to mergeable line. `[claimed]` (demo narrative) / `[empirically-grounded]` (product behaviors named)



## Video numeric delta (compare-before-and-after)
Demo title uses **1,535** additions / −168 / 38 files on monolith PR `#2`; stacked layers +561/+201/+399/+215. Article text also mentions 1,721 — keep both with rungs; prefer video UI for the demo numbers.
