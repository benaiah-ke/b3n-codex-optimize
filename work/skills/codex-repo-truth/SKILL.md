---
name: codex-repo-truth
description: Use when starting, resuming, auditing, or recovering repo work where current branch, worktree, PR, issue, CI, tracker, docs, deployment, or live runtime truth matters before editing or claiming status.
---

# Codex Repo Truth

Establish current truth before implementation, review, deploy, or handoff work.

## Workflow

1. Identify the operating root and whether it is a git repo.
2. Inspect local state: `git status --short --branch`, current branch, remotes,
   dirty files, and worktrees when relevant.
3. Refresh external truth when the task depends on it: `git fetch`, PR/issue
   metadata, CI/checks, tracker/status files, and live endpoints.
4. Read the closest durable docs first: `AGENTS.md`, `docs/CONTEXT.md`,
   handoffs, starter prompts, status notes, tracker files, and README/setup docs.
5. Separate evidence classes: local code, generated docs, CI, deployed SHA,
   live runtime, provider acceptance, and owner approval.
6. Start implementation only after the next safe action is clear. If blocked,
   name the owner, missing input, and exact unblock path.

## Output

- Keep the truth summary short: current branch/state, authoritative docs, live or
  PR truth, dirty files to preserve, and next gate.
- Do not claim completion from memory, stale docs, or a narrow check.
- If evidence conflicts, prefer current repo/live/PR state and call out the
  conflict.

## Safety

- Never reset or discard unrelated changes without explicit instruction.
- Do not print secret values. Inspect secret/env names and status only.
