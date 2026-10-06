# gh-stack cheatsheet

Verified against [github/gh-stack](https://github.com/github/gh-stack) README (API pull 2026-10-06) + blog post + docs tutorial. Where they differ, both are noted.

## Install

```sh
gh extension install github/gh-stack
gh skill install github/gh-stack   # teaches agents the workflow
# alt skill path from post: npx skills add github/gh-stack
gh extension upgrade stack         # update
```

**Prereqs (conflict to note):**
- Docs tutorial: `gh` ≥ 2.90.0, Git ≥ 2.20
- `github/gh-stack` README: `gh` v2.0+, Git 2.36+
→ Prefer the **stricter pair** in practice: recent `gh` + Git ≥ 2.36. `[constructed-but-coherent]`

## Core loop (README quick start)

```sh
gh stack init                 # first branch / start stack
# commits on L1...
gh stack add api-endpoints    # next layer on top
# commits...
gh stack push
gh stack view
gh stack submit               # open linked PRs
```

Blog also shows: `gh init stack` (possible alias/older phrasing), `gh stack rebase`, `gh stack sync`. Docs: `gh stack down` / `up` / `checkout`, `gh stack rebase --upstack`. Confirm with `gh stack --help` on your installed extension before scripting. `[claimed]` where only blog/docs name a flag not shown in README snippet.

## Model

```
frontend      → PR (base: api)     ← top
api           → PR (base: auth)
auth          → PR (base: main)    ← bottom
─────────────
main (trunk)
```

`up` = away from trunk; `down` = toward trunk. Metadata in `.git/gh-stack` (not committed).

## Review / merge (blog)

- Read **top-down** for end goal; review & merge **bottom-up**.
- Stack map on each PR for navigation.
- Fix on owning layer → rebase upstack → push/sync.
- **Avoid web "Rebase stack"** if signed commits required (unsigned server rebase; committer = clicker).

## Don't

- Giant single agent PR.
- Mixed concerns in one layer.
- Fix downstack bugs on upstack branches.
