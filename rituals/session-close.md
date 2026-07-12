# SESSION-CLOSE — capture, update, hand off

> Run at a REAL close only: context nearly full, or the human says stop. Task-finished ≠ session over.

**Run these in order.**

### 1. Capture novel knowledge
- Every new technique/lesson/quirk from this session → one atomic entry in the correct domain file (see `capture-standard.md`).
- Not captured = session not closed.

### 2. Update project state
- OVERWRITE `projects/<name>/STATE.md` with a fresh one-page snapshot: active task · last completed step · next action · blockers · live-system state. Never accumulate history here — one page, always current.

### 3. Git close step (per `git-discipline.md`)
- In EVERY repo touched: `git add -A` → run the secret gate → commit (message = what shipped) → push. Uncommitted work at close = NOT closed.

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
