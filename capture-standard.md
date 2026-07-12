# CAPTURE-STANDARD — how lessons get saved

**The rule: capture IMMEDIATELY, atomically, in the right file. "I'll update the docs later" is how knowledge dies.**

## One lesson = one atomic entry

```
### <ID> — <one-line title> (<date>)
- **What:** the technique / quirk / fix, stated so a fresh session can apply it.
- **Why it matters:** what breaks or slows down without it.
- **How to apply:** the exact steps or the pointer to the script (long code lives in scripts/, never pasted into lesson files).
```

## Rules

1. **Right file, first time.** Platform lesson → that platform's `skills.md`. Cross-platform → root. Project-only → the project folder. New platform → create its domain file first.
2. **Stable IDs.** Number entries (`SK-001`, `KI-014`, whatever scheme) so sessions can cite them and you can grep them.
3. **Never paste long code into a lesson.** Executable recipes live in `scripts/`; the lesson points to them. Lesson files are for the WHY and the gotchas.
4. **Failures are lessons too.** A dead end that cost an hour gets an entry — the next session must not pay twice.
5. **Consolidate on a rhythm.** Every ~10 sessions or when a file passes ~600 lines: merge duplicates, delete superseded entries, keep IDs stable.

## The test

A capture is good when a BRAND-NEW session, knowing nothing of the conversation that produced it, can read the entry and apply the technique without guessing.
