# Jugo (oficio / mechanism) — 5 cuts

Not a feature list. Cuts that change how you ship with agents.

## 1. Stack shape is a human decision agents amplify
Agents default to the training prior: one end-to-end PR. Stacked PRs don't remove the choice — they make the **decomposition** the first artifact. Design layers by dependency **before** generating the wall of code. `[constructed-but-coherent]` from post thesis + docs §1

**Steal:** prompt agents with layer boundaries + "only this layer"; refuse whole-feature drafts as merge units.

## 2. Foundation first; mistakes propagate upward
Bottom layer (data/types/migrations) is load-bearing. Review it before stacking more. A bad L1 poisons L2–Ln. `[empirically-grounded]` (dependency model) / `[claimed]` (demo narrative)

**Steal:** gate "add next layer" on green CI + human ACK of bottom.

## 3. One concern = one reviewer audience
Same Frontend agent can own L3 (wiring) and L4 (citations UI) as **separate** layers so data-flow reviewers and UI reviewers never share a 1.7k diff. `[claimed]` (demo) / `[constructed-but-coherent]` (principle)

**Steal:** split by *who must approve*, not by file-count alone.

## 4. Read top-down, review/merge bottom-up
Stack map is a compass: top shows intent; bottom is the merge unit. Fixes land on the flagged layer; upstack rebases carry them. `[empirically-grounded]`

**Steal:** never "fix everywhere" — checkout owning branch, then `rebase --upstack` / `sync`.

## 5. Web rebase is a signed-commit footgun
UI "Rebase stack" runs on GitHub servers → new committer, unsigned commits → branch protection can silently fail the stack. Prefer local `gh stack rebase` + push with your identity. `[empirically-grounded]` (mechanism stated in post)

**Steal:** document "no web rebase if signing required" in team runbooks / agent skills.

---

## Extra that cancels the dice
If the agent skill (`gh skill install github/gh-stack`) is missing, agents won't know the CLI lifecycle — you'll get giant PRs again even with the extension installed. Extension ≠ skill. `[constructed-but-coherent]`

## What a helper would plant
Catalog: `stack-base`, `layer-concern`, `reviewer-audience`, `upstack-rebase`, `signed-commit-constraint` as first-class ops tokens — not "use stacked PRs" as slogan.


### Evidence split (2026-10-06 watch)
- Divergence banners + Rebase stack + Merge stack disabled: **seen in** `gh-stack-rebase.mp4` `[empirically-grounded]`.
- Unsigned-commit / committer-reset footgun of web rebase: **article text only** in this pack — not shown in the rebase demo video. Keep as `[claimed]` until a video/docs screen proves it.


## Additional cuts from video (2026-10-06)

### 6. Extension ≠ skill; skill is multi-runtime
`gh extension install` alone is not enough — `gh skill install` teaches agents. Menu targets Copilot **and** Claude Code / Cursor / Gemini / Cline / CodeBuddy / Continue. Skills warn about prompt injection. `[empirically-grounded]`

### 7. Personas are the decomposition UX
Demo does not ask one agent for the whole feature then "please stack". Human switches Data Modeler → Backend → Frontend with **scoped prompts** that forbid leaking concerns upward. `[empirically-grounded]`

### 8. Prefer `gh stack sync --remote` in demos for recovery
Shown recovery after downstack force-push is CLI sync, not the web Rebase button. Article separately warns about web rebase + signed commits. `[empirically-grounded]` / `[claimed]` split.
