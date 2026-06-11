# Repository Working Agreements

## Source Truth

- Start by checking branch, local changes, remote state, open PRs/issues, and
  relevant docs before editing.
- Prefer existing commands and patterns in this repo. Add dependencies or
  abstractions only when they clearly pay for themselves.

## Verification

- Before handoff, run the smallest verification set that proves the changed
  behavior. Include tests, builds, browser checks, CI, or live smokes as needed.
- Do not claim production, provider-live, launch, or full readiness without
  matching evidence.

## Security

- Do not print secret values. Inspect env and secret presence by name/status.
- Keep destructive, deploy, DNS, and credential-changing actions approval-gated.

## User-Facing Surfaces

- Do not expose internal readiness, stub, mock, blocked, or production-readiness
  labels in UI or public user surfaces.
- Represent actual expected data, real empty/loading/error states, and available
  user actions. Keep implementation status in internal docs or PR notes.

## Handoff

- Final answers should include changed files, verification, remaining gates, and
  links to durable docs or PRs when relevant.
