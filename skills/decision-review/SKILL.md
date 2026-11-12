---
name: decision-review
description: Review a project's explicit decisions, implicit assumptions, approval history, and unresolved tradeoffs when the user asks which decisions need attention or wants a decision audit before proceeding.
---

# Decision review

Produce an evidence-backed decision register that distinguishes settled choices from assumptions and identifies consequential decisions needing the user's attention. Adapt the review to the project's active goal and requested scope.

A review does not authorize implementation. Inspect existing evidence without modifying project files, running producers, starting services, making paid requests, or changing external state. Return findings in the conversation unless the user requests a saved report. Do not create threads or delegate work unless requested.

## Establish scope and evidence

Read project instructions, the current plan or backlog, relevant implementation, schemas, documentation, configuration, quality contracts, and available artifacts. Use the project's actual conventions; do not require particular filenames, tools, or a technology stack.

Identify the active goal, acceptance criteria, explicitly approved preferences, deferred work, and current authorization boundaries. Consult available conversation history, decision records, issues, and pull requests when they explain consequential choices. Search narrowly and read the underlying source before attributing approval. If history is unavailable, state the gap and proceed with the evidence at hand.

Verify documented behavior against code and artifacts. Distinguish intended design, implemented behavior, observed results, and operational state. Static inspection and read-only queries are appropriate; avoid commands that generate artifacts or mutate state merely to complete the review.

## Classify decisions and reconcile evidence

Distinguish:

- Decisions explicitly approved by the user.
- Implementation choices made by agents or other contributors, without demonstrated user approval.
- Assumptions embedded in code, defaults, configuration, or transformations.
- Proposals that have not been implemented or approved.
- Unresolved decisions and contradictions.

Implementation is not evidence of user approval. Neither assistant recommendations nor silence establish consent. An approval for one task or environment does not automatically apply to another.

Reconcile historical preferences with later explicit instructions; cite the evidence for a superseding decision. Where provenance or precedence is uncertain, expose the conflict rather than silently resolving it. Do not ask the user to reconfirm settled preferences.

Separate confirmed problems, plausible risks, and unanswered questions. Do not convert a hypothetical risk into a blocker. Keep routine implementation details out of user questions when existing authorization and sound judgment suffice.

## Assess consequences

For each consequential decision, identify what was decided, its evidence and approval status, why it matters, and the cost of changing it now versus later. Recommend **keep**, **revise**, **defer**, or **ask the user**. A recommendation to revise is not permission to make the change.

Choose review areas relevant to the project rather than applying every category mechanically:

- **Scope and success:** target users, included/excluded cases, acceptance criteria, conflicting goals, and unrequested expansion or complexity.
- **Architecture and dependencies:** component responsibilities, external services, portability, lock-in, cost assumptions, and constraints embedded in stack choices.
- **Data and contracts:** source selection and coverage, identity, missingness, exclusions, defaults, provenance, retention, corrections, schema evolution, and boundaries between processing stages.
- **Reliability and operations:** retries, idempotency, concurrency, recovery, scheduling, rollout/rollback, and differences between development, historical processing, and live use.
- **Validation and claims:** evidence quality, reproducibility, evaluation boundaries, benchmarks, acceptance thresholds, and claims stronger than observed results. For predictive systems, examine availability cutoffs, leakage, holdout exposure, and calibration where applicable.
- **Access and obligations:** consequential choices about permissions, sensitive information, ownership, and externally imposed requirements when supported by project evidence.

Prioritize decisions that affect the active goal, costly reversals, or material correctness. Include deferred areas when they expose consequential contradictions, without displacing the current milestone. Do not expand the review into an unrelated redesign or hardening exercise.

## Deliver findings

Lead with the decisions most needing attention and their practical implications. Follow with a concise decision register; use this structure when useful:

| Decision | Evidence and approval status | Consequence | Recommendation | Cost now vs later |
| --- | --- | --- | --- | --- |

Cite precise file locations, artifact identifiers, or source links so the reader can verify important claims. Identify material evidence gaps and limit conclusions accordingly; do not claim an exhaustive audit when access or scope was partial.

End with no more than five prioritized questions for the user, each with a recommended answer and its tradeoff. Ask fewer, or none, if no consequential decision needs input. Finish with the next action and any materially blocking decision, without implementing recommendations.
