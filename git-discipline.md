# GIT-DISCIPLINE — how sessions use git

> Binding for every session in a git-tracked folder. Pairs with [git-secret-gate](https://github.com/roozbeh-bahrami/git-secret-gate).

1. **OPEN — know where you stand.** `git status -sb` → branch + dirty state. Project work happens on the project's work branch; wrong branch = switch BEFORE working.
2. **COMMIT AT MILESTONES, not only at close.** A fix proven, a doc finished → commit then. Message says what shipped.
3. **THE SECRET-GATE — mandatory between `add` and `commit`.** Scan staged CONTENT (not just filenames) for token patterns before every commit. Any hit = abort, unstage, fix `.gitignore`, rescan. Never loosen an ignore rule without re-scanning content.
4. **PUSH after every commit.** The checking lives BEFORE the commit; once a commit is clean, pushing is always safe (private remotes).
5. **CLOSE includes git.** Session-close = state updated + committed + pushed in every repo touched.
6. **PHASE COMPLETE = PR.** Finished work branch → Pull Request → the human reviews the diff → the HUMAN clicks merge. Never auto-merged.
7. **ONE-DRIVER.** One session writes to a given repo / live system at a time.
8. **PRIVATE by default.** Work repos never go public. A public repo is always a deliberate, separately-scanned artifact.
9. **Evidence lives in the repo, never in temp folders.** Scratch directories get wiped; committed evidence is forever.
