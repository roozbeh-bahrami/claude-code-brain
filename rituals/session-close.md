# SESSION-CLOSE — capture, update, hand off

> Run at a REAL close only: **the human says stop.** Task-finished ≠ session over.
>
> *Amended 2026-09-03: "context nearly full" was a close trigger here and is not one any more.
> The context ladder is warn-only — it reports depth and closes nothing (mb-knowledge
> START-HERE.md Rule 12, IIP-022 amended 2026-08-29). No hook runs this ritual.*

**Run these in order.**

### 1. Capture novel knowledge
- Every new technique/lesson/quirk from this session → one atomic entry in the correct domain file (see `capture-standard.md`).
- Not captured = session not closed.

### 2. Update project state
- OVERWRITE `projects/<name>/STATE.md` with a fresh one-page snapshot: active task · last completed step · next action · blockers · live-system state. Never accumulate history here — one page, always current.

### 3. Git close step — SCOPED PATHSPEC (per `git-discipline.md` rule 10)

In every repo touched, commit **only the paths this session changed**:

```bash
git add <path> [<path> ...]
./gate.sh                                        # the secret gate — any hit = ABORT
git commit -m "what shipped" -- <path> [<path> ...]
git push
```

The **trailing `-- <path>` on the commit** is the half people miss: `git add <path>` scopes what you
*stage*, not what gets *committed*. A plain `git commit` writes whatever is in the index, including
anything another session staged.

Never `git add -A`, `git add .`, `git commit -a`, or `git stash` — all four reach across the whole
working tree. Uncommitted work belonging to *another* session is not yours to commit.

### 4. Lean checks
- Did the always-loaded core gain domain detail? Move it out to a domain file.
- Any domain file over ~600 lines? Consolidate.
- No secret written to any markdown file.

### 5. Emit the resume prompt — the LITERAL LAST OUTPUT
Fill with the real current state, never generic:

```
Resume <project>. Read rituals/session-open.md and execute it verbatim.
THEN do: <the exact carry-over task>.
HARD RULES that bite this task: <the 2-3 that matter>.
```
