# Codex Optimization Pack

Date: 2026-06-11

## Installed

- Global guidance: `~/.codex/AGENTS.md`
- User skills: `~/.agents/skills/`
- Workspace mirror: `work/`
- Advisory rule audit: `work/rule-audit.md`

## Skills

- `codex-repo-truth`: source-truth-first repo recovery and startup.
- `codex-build-verify`: scoped implementation with matching verification.
- `codex-review-merge`: PR review, CI, merge, and closeout discipline.
- `codex-research-synthesis`: current-source research with citations.
- `codex-writing-handoff`: concise durable prompts, handoffs, and status notes.
- `codex-frontend-qa`: rendered UI/browser/responsive verification.
- `codex-optimization-loop`: suggest or apply future optimization updates.

## Defaults Captured

- Verify before claiming done.
- Keep scope and readiness denominators explicit.
- Prefer durable repo-local context over chat-only state.
- Avoid output bloat and cosmetic loops.
- Preserve unrelated work and keep commits reviewable.
- Inspect secrets by name/status, not value.
- Keep readiness/stub/non-production labels out of user-facing UI and public
  surfaces; put them in internal docs, trackers, handoffs, or PR notes.
- Treat rules and hooks as later enforcement, not first-pass defaults.

## Verification

- Workspace git initialized.
- Progressive commits created for context, guidance/templates, core skills, loop
  skill/rule audit, and final verification artifacts.
- Installed global guidance matches the mirror.
- Installed user skill tree matches the mirror.
- No config, model, plugin, trusted-project, or rule-policy change was made.

## Maintenance Loop

Future sessions should use `codex-optimization-loop` when a repeated failure,
command pattern, verification gate, output correction, or template improvement
is worth preserving. Normal product sessions should suggest updates first;
sessions explicitly about this optimization pack may update the mirror directly
and commit the change.
