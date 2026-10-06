# gh-stack-sync-lc.mp4

Split: GitHub PR #6 left · editor/agent right. Context: `feat/catalog-data` force-pushed after review → upstack diverged.

## Before
- Banner: "Some branches in this stack have diverged and must be rebased" + **Rebase stack**
- Red: "Unable to merge as a stack"

## Action
- Shortcut/prompt: "Synchronize the stack"
- Agent runs: **`gh stack sync --remote`**

## After
- Divergence banner clears
- Checks re-run ("Some checks haven't completed yet" → Build/Lint/CodeQL…)
- Merge widget: "Able to merge as a stack. Merging this pull request will also merge 1 pull request below it."
- On PR #8: Able to merge as a stack; #5–#8 **Ready**
- Local `gh stack view` clean

Note: demo uses CLI sync rather than web Rebase stack for the recovery path shown here.
