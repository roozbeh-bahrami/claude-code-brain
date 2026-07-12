# START-HERE — the lean core (always loaded)

> This is the ONLY file every session must read fully. Keep it under ~10KB forever. Everything else loads on demand. When this file bloats, sessions get slow and rules stop firing — move detail OUT to domain files.

## UNIVERSAL RULES (edit into yours — start small, grow slowly)

1. **Quality > speed.** Full coverage beats fast answers. Never cut corners to save time or tokens.
2. **Pick the best path autonomously.** Never present A/B/C menus. Ask only when ACCESS is missing (a login, a credential, a tool).
3. **Verify, don't assume.** Check live state before recommending. Banned phrases: "probably", "should be", "I think", "likely".
4. **Describe-then-ask before heavy ops.** Live writes, sends, deploys, deletes: say exactly what will happen, get the yes, then fire. Safe reads stay autonomous.
5. **Complete before advance.** Close the open thread first. No "done" without verification.
6. **Capture every lesson immediately** (see `capture-standard.md`). "I'll document it later" = it's already lost.
7. **Credentials live only in `.env`.** Never in chat, never in a markdown file, never in git (see `git-discipline.md`).
8. **Sessions open with the open ritual, close with the close ritual.** No exceptions — that's what makes the brain survive.

## WHERE DOES KNOWLEDGE GO? (the one decision rule)

Ask: *"Would another project ever need this?"*

| If it's… | It goes in… |
|---|---|
| A platform lesson / recipe / vendor quirk | `<DOMAIN>/skills.md` (per platform) |
| Cross-platform tooling or session discipline | the root (like this file, `git-discipline.md`) |
| A binding rule / decision / known issue | your governance file(s) |
| One project's live state / IDs / in-flight work | `projects/<name>/` |
| A brand-new platform | create its domain file FIRST, then capture |

## DOMAIN INDEX (map only — bodies load on demand)

> One line per domain: what's inside + when to open it. A session opens a domain file only when today's task touches it.

- `<DOMAIN-A>/skills.md` — (e.g. your CRM platform: API quirks, builder recipes, auth patterns)
- `<DOMAIN-B>/skills.md` — (e.g. your automation platform: scenario patterns, error handling)
- *(grow this list as platforms enter your life)*
