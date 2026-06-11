# Codex Working Agreements

## Operating Defaults

- Start from source truth before changing anything material: current directory,
  branch, worktree, local changes, relevant docs, open PRs/issues, CI, and live
  runtime state when the task depends on it.
- Prefer the repo's existing patterns, commands, and ownership boundaries.
  Avoid unrelated refactors and new abstractions unless they clearly reduce
  real complexity.
- Keep work scoped, simple, secure, performant, and testable. Product polish is
  useful only after core behavior, data flow, and verification are solid.
- Preserve user or teammate changes. Never reset, discard, or overwrite
  unrelated work unless explicitly asked.

## Output Discipline

- Be concise. Lead with what changed, what was verified, and what remains.
- Avoid filler, broad readiness claims, and cosmetic loops. If using progress
  percentages, state the denominator: MVP, full vision, local, CI, live, or
  owner/provider acceptance.
- For handoffs, create durable repo-local artifacts when useful instead of
  relying on chat-only context.

## Verification Contract

- Match verification to the claim. Do not use a narrow local check to imply a
  broad production, provider-live, or launch-readiness result.
- Before calling work done, inspect authoritative evidence: tests, builds, diffs,
  CI, PR state, browser behavior, `/health`, `/version`, deployed SHA, or live
  route checks as appropriate.
- Final responses should name verification run, verification not run, and any
  remaining gates or blockers.

## Security And Secrets

- Do not print raw secrets, tokens, webhook material, DB URLs, or credential
  values. Inspect names, counts, status, and presence by default.
- Treat destructive commands, DNS changes, deploys, secret cleanup, and live
  infrastructure mutations as approval-gated unless explicitly authorized.
- Run a secret-pattern review for touched files when working near auth, env,
  deploy, payment, or infrastructure code.

## Maintenance Loop

- When a session reveals a reusable command, failure mode, verification gate, or
  style rule, suggest a precise optimization update unless the task is explicitly
  about the Codex optimization pack.
- When working inside the optimization pack, update the workspace mirror first,
  then install active Codex changes from the mirror and commit progressively.
