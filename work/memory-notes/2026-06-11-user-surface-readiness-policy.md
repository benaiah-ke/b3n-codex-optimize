# Memory Update: User-Facing Readiness Labels

Date: 2026-06-11

Add this as a durable user preference:

- Do not put internal readiness, stub, mock, blocked, or non-production labels on
  user interfaces, public pages, or user-facing surfaces.
- User-facing surfaces should represent actual expected data, real empty,
  loading, and error states, and available user actions.
- Readiness status, stub status, implementation gaps, and production-readiness
  labels belong in internal documentation, trackers, handoffs, or PR notes.
