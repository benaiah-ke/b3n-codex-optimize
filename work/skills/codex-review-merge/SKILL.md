---
name: codex-review-merge
description: Use for PR review, merge readiness, GitHub comments, CI failures, stacked branches, tracker closeout, or publishing changes where current PR and remote state must drive decisions.
---

# Codex Review Merge

Review and close out GitHub work from current truth.

## Workflow

1. Resolve the repo, branch, PR number, base branch, and local dirty state.
2. Fetch or inspect remote truth before reviewing: PR metadata, changed files,
   comments, checks, mergeability, and related issues.
3. Review for bugs, regressions, missing tests, security/privacy risks, deploy
   gaps, and scope drift. Findings come before summary.
4. If fixing, keep changes narrow and preserve stack boundaries. Do not edit
   downstream PRs unless asked.
5. Verify locally and through GitHub checks where relevant.
6. Merge, close stale PRs, update trackers, or create closeout PRs only when the
   user authorized that scope.

## PR Body Shape

- `Summary`
- `Verification`
- `Security / Secrets`
- `Remaining Gates`

## Failure Handling

- If GitHub reports `mergeable: UNKNOWN`, wait or re-check before rewriting.
- If tracker generation returns empty or stale state, treat access as suspect and
  rerun through an authenticated path.
- If CI fails, inspect logs before guessing from local code.
