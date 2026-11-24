# Contributing to AgentMD

AgentMD's objective is **real user-task completion**, not a perpetual experimental evaluation project. Never require a model to gather or update benchmark data as a prerequisite for doing the user's work.

## Responsibilities

- `AGENTS.md`: runtime choice among doing the task directly, delegating, adjusting effort, checking outcomes, and stopping.
- `models/*.md`: short, non-exclusive per-model operating priors; avoid duplicating default Codex behavior and broad generic rules.
- `.codex/agents/*.toml`: stable model identity and generic worker contract, **not benchmark tables or fixed professions**.
- `research/benchmark-evidence.md`: offline research for maintaining routing priors. Do not load by default.
- `README.md`: usage, caveats, and installation.

## Routing rules to preserve

1. No exclusive model occupations. Select model and reasoning effort based on the actual task and available evidence.
2. No mandatory Luna-first execution. An initial Luna parent may delegate before attempting the task.
3. No fixed ladder or requirement to invoke all four models.
4. Same-model reruns, effort changes, and switching families are all allowed if useful within the global budget.
5. Use actual tool results and acceptance checks; do not trust unverified model self-assessments.
6. Child workers recommend next steps but do not recursively spawn. Parent tracks bounded worker attempts (initial default 4, not a mathematical optimum).
7. Missing permissions, unavailable models, or absent tools are blockers, not reasons to invent results.
8. Shared files and destructive operations retain Codex approval, sandbox, and project constraints.

## Updating the policy

- A model release or new benchmark updates the **offline evidence** and, only if it changes operational advice, the small runtime prior.
- Changing a prompt needs a clear reason: which real failure does the instruction prevent, or which outcome does it improve?
- Separate the effect of a different model/effort from the effect of different instructions; do not attribute gains to both.
- Keep Git changes minimal and reversible. For substantial revisions, record the scenario, expected improvement, observed behavior, failed checks, and known uncertainties in the PR or commit.
- Do not publish credentials, private task inputs, or sensitive logs.

A simple smoke test must check that the configured role names/model IDs match the router, no fixed reasoning effort overrides a requested one, file paths resolve in the target Codex client, and unavailable orchestration fails transparently. This verifies configuration, **not** optimal task performance.

Reference: [Codex subagents](https://developers.openai.com/codex/subagents).
