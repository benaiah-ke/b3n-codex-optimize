# Codex Rule Audit

Last reviewed: 2026-06-11

Source reviewed: `~/.codex/rules/default.rules`

## Summary

The current user rules file has 112 `prefix_rule` entries. It includes useful
reusable read and verification commands, but also many narrow one-off commands
from prior infrastructure sessions.

This audit is advisory only. No command rule was changed by this optimization
pass.

## Keep As Reusable

- Git read/publish primitives already used often: `git fetch`, `git status`,
  `git log`, `git add`, `git commit`, `git push`, `git rebase`.
- GitHub inspection primitives: `gh pr list`, `gh pr view`, `gh pr checks`,
  `gh run list`, `gh run view`, `gh auth status`, `gh repo view`.
- Common build/test tools: `pnpm build`, `pnpm install`, `uv --cache-dir`,
  `docker build`, `docker compose`.
- Known platform CLIs: `sentinel status`, `sentinel projects`,
  `sentinel services`, `sentinel logs`, B3n Knowhere/Sentinel login/status.

## Review Before Keeping

- Broad network/file movement prefixes such as `curl` and `scp`; they are useful
  but deserve periodic review because they can act on many targets.
- `ssh` entries that include full host-side mutation scripts; keep only while
  the related infrastructure work is active and still trusted.
- Old process-specific entries such as fixed `kill` or `pkill` commands.
- Exact `sed`, `nl`, and `rg` commands against historical memory or session
  files. These are low risk but add noise and rarely need persistent approval.
- Exact long `/bin/zsh -lc` commands with embedded DB URLs or environment
  variables. Prefer scoped project-local guidance over long-lived global allow
  rules for these.

## Suggested Next Cleanup

1. Group rules into durable categories: git, GitHub read, GitHub publish,
   package/build, Docker, Sentinel/B3n CLIs, and project-specific temporary.
2. Remove or comment one-off historical commands after confirming the related
   sessions are closed.
3. Keep destructive, broad SSH mutation, DNS, and credential-changing flows
   prompt-gated unless the exact recurring workflow is still active.
4. Add future hard gates only after repeated failures show advisory guidance is
   insufficient.

## Current Policy

- Advisory first.
- No new hard hooks or rules from this pass.
- Use the `codex-optimization-loop` skill to suggest future rule changes when a
  command pattern becomes clearly reusable.
