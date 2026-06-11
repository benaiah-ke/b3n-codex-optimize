# Install Verification

Date: 2026-06-11

## Installed Active Setup

- Global guidance installed to `~/.codex/AGENTS.md`.
- Seven user skills installed to `~/.agents/skills/`.
- User-surface readiness preference copied to
  `~/.codex/memories/extensions/ad_hoc/notes/2026-06-11-user-surface-readiness-policy.md`.
- `~/.codex/config.toml` was inspected but not modified.
- `~/.codex/rules/default.rules` was inspected but not modified.

## Mirror Checks

- `cmp -s work/global-agents.md /Users/bensmac/.codex/AGENTS.md` passed.
- `diff -qr work/skills /Users/bensmac/.agents/skills` passed.
- Installed skill files found:
  - `codex-build-verify`
  - `codex-frontend-qa`
  - `codex-optimization-loop`
  - `codex-repo-truth`
  - `codex-research-synthesis`
  - `codex-review-merge`
  - `codex-writing-handoff`
- Ad-hoc memory note exists in the Codex memory update folder.

## Notes

- Existing Codex sessions may need a restart or fresh thread before newly added
  user skills appear in the session skill list.
- The first pass is advisory. No hard hooks or command-policy changes were
  installed.
