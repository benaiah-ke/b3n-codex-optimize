---
name: codex-build-verify
description: Use for implementation tasks where Codex should make scoped code changes, avoid bloat, preserve existing patterns, and finish with tests, builds, security checks, and explicit verification evidence.
---

# Codex Build Verify

Implement the smallest durable change that proves the requested behavior.

## Workflow

1. Ground in repo truth first when the task touches an existing codebase.
2. Read the surrounding implementation and tests before editing.
3. Choose the repo's existing patterns over new abstractions.
4. Keep changes narrow. Avoid unrelated cleanup, broad rewrites, and cosmetic
   loops unless the user asked for them.
5. Add or adjust tests based on risk and blast radius.
6. Run the verification that matches the claim: lint, typecheck, unit tests,
   integration tests, builds, browser checks, CI, or live smokes.
7. Run `git diff --check` and a secret-pattern review when touching auth, env,
   deploy, payment, or infrastructure surfaces.

## Verification Contract

- A local test proves only the local behavior it covers.
- A passing build does not prove live deployment.
- A live `/health` does not prove the deployed artifact changed; use `/version`,
  SHA, route payloads, or service image state where relevant.
- If a check cannot run, say why and give the next best evidence.

## Output

- Final response: changed files, verification run, verification not run, and
  remaining gates.
- Keep prose concise. Do not inflate readiness beyond evidence.
