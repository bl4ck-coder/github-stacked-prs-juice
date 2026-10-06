# gh-stack-rebase.mp4

**Source:** watchVideo (compact).

## IDE / CLI
- Pane: **View Stack v0.0.7** · Base `main` · #8…#5 OPEN (`feat/grounded-ui` current)

## Agent prompts (verbatim sense)
1. "Implement the two Copilot review suggestions on PR #5. Validate with the relevant existing checks then create a local commit only. Do not push or modify unrelated files."
   - Outcome: `Lint and build pass. Local commit: ccfaa3c. Nothing pushed.`
2. "Push branch and reply to the threads on the PR"
   - `git push origin feat/catalog-data`
   - `gh api graphql` to resolve Copilot review threads

## After push — stack widget on #5
- #8, #7: **Blocked downstack** (yellow)
- #6: **Not ready** (yellow)
- #5: **Ready** (green)

## On PR #6 — dual banners
1. **"Some branches in this stack have diverged and must be rebased"** / "Rebase the stack to restore a linear commit history across its branches." + button **Rebase stack**
2. **"Unable to merge as a stack"** / "One or more pull requests in this stack cannot be merged."
- **Merge stack** disabled

## Important rung note
No on-screen warning about **unsigned commits** appears in this video. That footgun is stated in the **article prose** only (`[claimed]` from text / `[empirically-grounded]` only if verified elsewhere). Do not attribute unsigned-commit UI to this demo.
