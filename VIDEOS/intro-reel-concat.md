# Intro reel (watchVideo batch — arrived as one 2:11 continuous file)

Covers install + multi-agent stack + submit + review + rebase narrative. Cross-check with individual demos.

## Surfaces
- VS Code dark + Copilot chat; agent dropdown: Default → Data Modeler → Backend → Frontend
- macOS Terminal (`gh`)
- GitHub PR UI light mode + Stacked PRs UI
- Slide graphics (bar charts)

## Commands (verbatim)
- `gh extension install github/gh-stack`
- `gh skill install github/gh-stack`
  - Skill: `gh-stack - Manage stacked branches...`
  - Target: GitHub Copilot (menu also lists Claude Code, Cursor, Gemini, Cline, CodeBuddy, Continue)
  - Scope: `Project: github/zava-demo`
  - Warning: skills not verified; may contain prompt injections / malicious scripts
- Agent runs: `gh stack view`, `gh stack push`, `gh stack submit` (fails once: `Submit cancelled - no branches were pushed`, succeeds second time)
- Web: open `feat/catalog data #5`, open `Stack #9` dropdown, click `Rebase stack`

## Monolith PR
- Title: Ground chat assistant in catalog data #2
- Branch: `main <- juliamuiruri4-ground-chat-in-catalog` (alt naming vs compare video)
- +1,535 −186 (33 files) — compare video had −168 / 38 files; slight demo variance
- Overlay: "Reviewer: I'll get to this later!" + clock
- Narration says ~1700-line PR

## Stacked PRs created
| # | Title | Branch | Diff (reel) |
| --- | --- | --- | --- |
| 5 | feat/catalog data | feat/catalog-data | +545 −2 |
| 6 | Add product search API | feat/search-api | +201 −8 |
| 7 | Ground chat replies in product search | feat/chat-grounding | +399 −39 |
| 8 | Render grounded product citation cards | feat/grounded-ui | +215 −0 |

UI states: `Blocked downstack`, `Not ready`, `Ready`. Divergence banner: "Some branches in this stack have diverged and must be rebased..."
Closing: "GitHub Stacked PRs / gh.io/stacks"

## Extra juice (beyond slogan)
1. `gh skill` is multi-agent (not Copilot-only).
2. Workflow = **manual persona switch** per layer, not one mega-prompt.
3. First `gh stack submit` failure left in edit — not always one-shot.
4. Native GitHub stack UI (Stack #N, merge-as-stack, blocked downstack) — CLI + platform, not CLI-only.
