# CLAUDE.md — gitrepo (curated GitHub repo index)

**What this is:** a single `README.md` that indexes useful GitHub repos and
tools, organized by source and by sector. Personal project under the
`Bradical247` GitHub identity (repo: `github.com/Bradical247/gitrepo`).
Despite living under `~/suse-projects/`, this is **not** SUSE work.

---

## Commit identity — IMPORTANT

Commit/push as **Bradical247**, never the SUSE identity. Local git config
defaults to SUSE (`conrad.bachman@suse.com`), so override per-commit:

```
git -c user.name='Bradical247' \
    -c user.email='108717148+Bradical247@users.noreply.github.com' \
    commit -m "..."
```

Standing authorization: commit, push, and merge to `main` directly — no
per-change confirmation needed. Pure-research turns (no commit ask) may still
trip the auto-mode push classifier; that's expected.

---

## README structure

Top-to-bottom sections:

1. **From the transcripts** — numbered table (#1–66) of repos mentioned in
   YouTube videos. Has a "Notes & corrections" block at its end for garbled
   names (e.g. "Teleria" → Tolaria).
2. **Editor's picks** — essential repos, grouped (Run/build with AI, Automate,
   Dev QoL, Knowledge/writing, Learn).
3. **Editor's picks — DevOps, Cloud & Network Engineering** — IaC, k8s, AWS,
   observability, network tooling.
4. **More repos & tools** — AI coding skills, MCP servers, design (resolved
   from a scratch list).
5. **Curated picks by domain** — networking, agentic AI/harness, DevOps, web
   design, media, social/marketing.
6. **Build-anything toolbox I / II / III / IV** — repos by sector, the bulk of
   the index (~42 sectors, 600+ links total). Each toolbox is one research pass;
   IV also folds in a batch of hand-picked adds alongside its trending sweep.
7. **Music production** — deep-dive on one domain (DAWs/trackers, synths &
   plugins, AI audio ML, MIR, notation/live-coding, audio engines/frameworks);
   50 repos, production-focused, complements the self-hosted **Music** subsection
   (streaming servers / library management).

## Conventions

- **Verified links only.** Every repo URL is checked to exist before adding.
- **Confidence flags:** `🟡` = likely match worth a glance; `🔍` = couldn't pin
  a single canonical repo (search term given instead).
- **Owner corrections** noted inline when the source name was wrong.
- **Off-GitHub canonical dev** (KDE GitLab, Codeberg): link the official GitHub
  mirror or most-starred repo, and say so.
- **No dupes across sections** — exclude repos already listed when researching a
  new batch.
- Toolbox entries are `- **Name** — short description. URL` bullets grouped
  under `### Sector` headings. Transcript/added tables use markdown tables.

## Research → append → push workflow

1. Fan out parallel `general-purpose` agents (one per 2–3 sectors), each told to
   WebSearch, return canonical `org/repo` + 6–12 word descriptions, verify
   existence, flag uncertain with 🟡, and EXCLUDE already-listed repos.
2. No Perplexity MCP is connected — agents use WebSearch (same reach, no key).
3. Assemble results into a new `## Build-anything toolbox N` section, append to
   the README.
4. Commit as Bradical247, push to main.
5. **Fetch first if anything might have changed** — Conrad sometimes edits the
   README directly on GitHub mid-session. On push rejection: `git fetch` +
   `git rebase origin/main` + push.
