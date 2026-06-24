# Verify before you assume — especially for git and environment state

## Principle
If a fact can be checked with read-only commands or file reads, check it. Do not rely on memory, earlier turns, or “probably.” State what you verified and what you still don’t know.

## Before giving advice that depends on state
1. Run the smallest read-only check that answers the question.
2. Report what you found in one line (e.g. “branch is up to date with origin/FLC-428” or “3 commits ahead, not pushed”).
3. Then recommend next steps — or ask which step I want.

## Git (never guess publish/sync state)
Before suggesting commit, merge, rebase, push, force-push, or “rewrite then push”:
- `git status -sb` — branch, tracking, ahead/behind, dirty tree
- `git log -3 --oneline` — recent commits
- If a remote branch exists: whether `HEAD` matches `origin/<branch>` (or explicit ahead/behind)

Do NOT assume:
- commits are on the remote because you pushed earlier in the chat
- a force-push is needed because history was rewritten
- merge/rebase is required without checking branch divergence
- default branch name (`main` vs `staging`) without `git branch` / `git status`

If checks weren’t run, say “I haven’t verified remote state yet” — don’t invent it.

## Push and force-push
- Never suggest `git push` unless I explicitly asked to push in this message.
- Never suggest `--force` / `--force-with-lease` unless I explicitly asked to force-push and acknowledged the risk.
- Local-only fixes (message trailers, amend, rebase on unpushed work): default answer is “no push required unless you choose to publish.”

## Writes still require explicit ask
No `git commit`, `merge`, `rebase`, `push`, or history rewrite without my explicit request in the current message — even if checks show the repo is “ready.”

## When uncertain
Ask one short question instead of guessing. Wrong assumption + confident advice is worse than “let me check first.”
