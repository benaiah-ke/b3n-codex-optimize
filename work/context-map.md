# Codex Optimization Context Map

Last updated: 2026-06-11

## Purpose

This workspace mirrors the active Codex optimization setup. It should stay small,
reviewable, and useful as a source of truth for global guidance, reusable skills,
templates, and future update suggestions.

## Repeated Success Patterns

- Start from source truth before editing: branch, worktree, open PRs/issues,
  tracker/docs, CI, deployed SHA, and live `/health` or `/version` when relevant.
- Keep scope explicit: separate MVP, full vision, local readiness, CI readiness,
  live runtime readiness, and provider or owner acceptance.
- Verify before claiming completion. A green local check is not the same as a
  live deploy, an accepted provider flow, or a finished release.
- Preserve durable context in repo-local artifacts: `docs/CONTEXT.md`,
  handoff docs, starter prompts, tracker/status notes, PR bodies, and closeout
  notes.
- Prefer small, reviewable commits and PRs, especially when the user asks to
  commit progressively or pause cleanly.
- Keep output concise: lead with what changed, what was verified, and what
  remains. Avoid cosmetic loops once the core workflow is useful.
- Treat secrets carefully: inspect names, counts, and presence by default; do
  not print raw values, tokens, webhook material, DB URLs, or credentials.

## Common Verification Gates

- Repo truth: `git status --short --branch`, `git fetch`, current branch, remote
  state, open PRs/issues, worktree inventory, and relevant local docs.
- Python: `uv --cache-dir .uv-cache ...`, `ruff`, `pytest`, `compileall`, and
  `PYTHONPYCACHEPREFIX=/private/tmp/...` when macOS cache writes are blocked.
- JavaScript or frontend: `pnpm install` only when needed, `pnpm build`, unit
  tests, Playwright or browser QA, and screenshot checks for UI work.
- GitHub closeout: PR checks, Actions logs when failing, mergeability after a
  short re-check if GitHub reports `UNKNOWN`, and tracker regeneration only when
  GitHub access is authenticated.
- Live deployment: public route checks, `/health`, `/version`, service/image
  inventory, deploy SHA, and route-specific smoke checks rather than broad
  readiness claims.
- Security: `git diff --check`, secret-pattern review over touched files, no
  secret values in logs, and explicit approval gates for destructive or live
  infrastructure changes.

## Repeated Failure Patterns

- Changing the progress denominator without saying so damages trust. Always name
  the scope behind a percent or completion claim.
- Browser or localhost tooling can fail even when the app is healthy. Record the
  tooling limitation separately from product state.
- Sandbox auth/network failures can make GitHub, tracker, DB, or local services
  look broken. Re-run through the authenticated or approved path before
  diagnosing the repo.
- Tracker or generated status can become stale or bogus when upstream access is
  blocked. Regenerate only after confirming the command has real data access.
- Deployment success can be partial. Inspect live service/image/tag state and
  route payloads before saying the artifact changed.
- UI integration can drift past backend reality. Reflect verified contracts and
  label missing surfaces honestly instead of filling gaps with mock controls.

## Output Defaults

- Working updates: short, factual, and tied to the current gate.
- Final answers: concise summary, verification evidence, remaining blockers or
  caveats, and file links for durable artifacts.
- PR bodies: `Summary`, `Verification`, `Security/Secrets`, and `Remaining Gates`
  when applicable.
- Handoffs: current truth, required first checks, required reading, sync policy,
  review focus, verification, merge criteria, and closeout.

## Optimization Loop

When a future session uncovers a reusable command, failure mode, verification
gate, or style rule:

- If the task is explicitly about this optimization pack, update the workspace
  mirror and commit the change.
- If the task is normal product or repo work, suggest the exact optimization
  update in the final answer unless the user explicitly asks to apply it.
- Keep updates small. Put always-on behavior in global guidance, workflows in
  skills, repo-specific expectations in repo templates, and mechanical command
  policy in rules or hooks only after repeated evidence.
