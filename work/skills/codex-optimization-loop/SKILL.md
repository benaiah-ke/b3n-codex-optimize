---
name: codex-optimization-loop
description: Use when a Codex session uncovers a reusable failure mode, command pattern, verification gate, output preference, skill improvement, template update, or global guidance change worth preserving in the Codex optimization pack.
---

# Codex Optimization Loop

Keep the Codex optimization pack current without turning every normal task into
meta-work.

## Trigger Signals

- A repeated sandbox, auth, cache, CI, deploy, browser, or tracker failure.
- A command pattern that reliably fixes or verifies a recurring class of work.
- A new verification gate needed to support completion claims.
- A user correction about output bloat, scope drift, progress framing, or
  readiness claims.
- A user correction about keeping readiness/stub/non-production labels off
  user-facing interfaces and public surfaces.
- A reusable handoff, prompt, PR-body, or context-doc structure.
- A skill, template, rule, or global guidance item that is now stale.

## Decision Path

1. If the current task explicitly asks to maintain the optimization pack, update
   the workspace mirror first.
2. If the current task is ordinary product or repo work, suggest the exact update
   in the final answer and do not mutate the optimization pack unless asked.
3. Put durable behavior in the smallest correct surface:
   - global `AGENTS.md` for always-on defaults
   - skills for reusable workflows
   - repo templates for project-local norms
   - rule audit for command approval recommendations
   - hooks only after repeated evidence proves mechanical enforcement is useful
4. Keep each update small, testable, and free of secret values.

## Update Checklist

- Update the mirror file under this workspace.
- Install active user-level changes only from the mirror.
- Verify installed files match the mirror.
- Commit the mirror update with a narrow message.
- Record what changed and why in the handoff artifact when relevant.

## Non-Goals

- Do not add hard gates in the first advisory pass.
- Do not store raw secrets, tokens, credential values, or private host material.
- Do not expand global guidance with project-specific facts that belong in a
  repo `AGENTS.md` or `docs/CONTEXT.md`.
