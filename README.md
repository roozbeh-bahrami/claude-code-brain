# claude-code-brain 🧠

**Give Claude Code a permanent, multi-project brain** — persistent knowledge, binding rules, and session rituals that survive every restart, crash, and context limit.

Battle-tested architecture from months of running real client automations with AI sessions daily. Not a theory — this exact structure runs production systems.

## The problem

Every new Claude session starts smart about code and dumb about YOUR world: your rules, your platforms' quirks, the lesson you learned Tuesday, where the last session stopped. Re-explaining is slow; forgetting is expensive.

## The architecture

```
knowledge-base/                     ← one shared folder, versioned with git
├── START-HERE.md                   ← lean core: universal rules + map (ALWAYS loaded)
├── capture-standard.md             ← how new lessons get saved (immediately, atomically)
├── git-discipline.md               ← how sessions use git (commit gates, push, PRs)
├── rituals/
│   ├── session-open.md             ← every session starts here: load core → project state → domain files ON DEMAND
│   └── session-close.md            ← every session ends here: capture → update state → commit+push → resume prompt
├── <DOMAIN>/                       ← per-platform lesson files (load only when needed)
│   └── skills.md
├── templates/
│   ├── STATE.md                    ← one-page "where we are" per project (overwritten, never accumulated)
│   └── project-CLAUDE.md           ← per-project context header
└── projects/<name>/                ← each project's wiring: state, IDs, charter
```

**The key idea: load the lean core always, load domains on demand.** A 500KB "read everything" brain makes sessions slow and dumb. A 10KB core + on-demand domain files makes them fast and sharp.

## The lifecycle

1. **Open** — session reads the core + the project's STATE (one page). It knows the rules and where work stopped. Zero re-explaining.
2. **Work** — new lesson learned? Captured to the right domain file NOW, not "later". Milestone done? Committed and pushed.
3. **Close** — state overwritten fresh, knowledge captured, everything committed, and the session prints a resume prompt: the exact text to paste into the next session.
4. **Crash?** — a dirty-exit check at next open reconstructs and retro-logs. Nothing slips.

## Quickstart

1. Copy this repo's structure into a folder (e.g. `~/knowledge/`), `git init`, make it private
2. Edit `START-HERE.md`: write YOUR non-negotiable rules (start with 5, grow slowly)
3. In each project's `CLAUDE.md`, point session start at `rituals/session-open.md`
4. End every working session by asking Claude to "run the close ritual"

The templates in this repo are genericized starters — every file is meant to be edited into YOUR version.

## Works best with

- [claude-code-advisor](https://github.com/roozbeh-bahrami/claude-code-advisor) — a read-only second session that verifies what your working sessions claim
- [claude-code-secret-gate](https://github.com/roozbeh-bahrami/claude-code-secret-gate) — blocks any commit containing secrets (the close ritual assumes a gate like this)

## Author

**Roozbeh Bahrami** — AI automation specialist. This is the actual system I operate daily across client projects. ⭐ if your sessions stopped forgetting.

## License

MIT
