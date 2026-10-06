# Escena — article + all demos

**Piece:** Julia Muiruri, GitHub Blog, 2026-08-04 — stacked PRs for agent-generated work.  
**Demo repo:** `github/zava-demo` · personas: Data Modeler / Backend / Frontend · Stack #9 · PRs #5–#8.

## Text layer (article)
Problem: agents ship monolith PRs (~1.5–1.7k lines). Solution: decompose by dependency into native stacked PRs + `gh-stack` extension/skill. Review read top-down, merge bottom-up. Article warns web Rebase stack can unsigned-reset committer (not shown on-screen in demos).

## Video inventory (all watched)

| File | What happens |
| --- | --- |
| YT `0WIGMOiG7LA` | Narrated pitch (~2 min); same story as intro reel |
| intro reel / agent-full path | VS Code multi-agent + install + submit fail-once + Stack UI + Rebase |
| compare-before-and-after | Graphic: +1535 monolith → 4 stacked (+561/+201/+399/+215 bars; reel diffs differ slightly) |
| gh-stack-xtension / gh-skill | Covered inside intro: `gh extension install` + `gh skill install` multi-target |
| layer1-data | Data Modeler → `feat/catalog-data` +545 −2 · catalog lib |
| layer2-backend | Backend → `feat/search-api` + API route · curl paint search |
| layer3-frontend | Frontend → `feat/chat-grounding` · plain-text grounded/empty/error |
| layer4-frontend | Frontend → `feat/grounded-ui` · citation cards |
| gh-stack-submit | TUI Submit Stack **v0.8.7** · creates PRs #5–#8 |
| stack-map | Stack #9 popover · Merge PR vs Merge stack |
| gh-stack-rebase | Fix #5 locally (`ccfaa3c`) · push · Blocked downstack · Rebase stack banner |
| gh-stack-sync-lc | `gh stack sync --remote` clears divergence · all Ready |

## Mechanism (pointers)
host teaches agents via **skill** → each persona owns **one layer** → `gh stack add` bases on prior → submit TUI opens linked PRs → platform Stack map → fix downstack → **sync/rebase upstack**.

## Numeric variance (do not flatten)
- Narration: ~1700-line PR
- Compare title / monolith UI: **+1,535** (files 33 or 38; deletions −168 or −186 across cuts)
- Layer view L1: +545 −2 (compare bar +561)
Keep as demo snapshots, not one sacred number.
