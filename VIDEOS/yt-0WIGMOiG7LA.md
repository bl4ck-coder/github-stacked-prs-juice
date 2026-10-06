# YouTube embed: 0WIGMOiG7LA

**URL:** https://www.youtube.com/watch?v=0WIGMOiG7LA  
**Local:** `videos/yt-0WIGMOiG7LA/video.mp4` + auto captions  
**Note on captions:** YouTube auto-ASR (fetched via timedtext). Several mistranslations — treat bracketed fixes as `[constructed-but-coherent]` corrections from article context, not as spoken evidence.

## Cleaned voiceover (sense-preserving)

Agent asked for one advantage → delivered everything (model, API, UI, exceptions) in a single ~1700-line pull request. Impressive technically, impossible to review → sits, context fades, merges under-reviewed. We've all been that reviewer/author.

What if the same change arrived as a **stack** instead? Small PRs, each doing one job, ordered: data → API → chat → UI. Each small enough to hold in mind.

Install stacked-PR skills on GitHub once → agents not only write code, they **organize** it. Decomposition becomes default.

- Data designer starts: typed catalog + seed on the base.
- Backend agent stacks search API importing that module.
- Frontend agent wires chat to API (real product answers).
- Deliberate extra layer: product citation cards. Each agent one responsibility, stacks on prior, stops — no giant PR forms.

Reviewer path: same feature, clear path. **Read stack top-down** for destination; **review bottom-up** step by step. Feedback on real parts without losing the plot. Lower-layer change → one sync updates the whole stack (no manual rebuild). Same agents, same speed, reviewable delivery. Stacked PRs available on GitHub today.

## Raw caption file
`videos/yt-0WIGMOiG7LA/captions.en.txt` (rolling ASR; "withdrawal requests"≈PRs, "accumulated teams/collection"≈stack).

## Visual watch
Pending watchVideo batch-1 result — will append UI delta here.
