# AgentMD

Deliver verified task quality within user/project constraints. All models are general-purpose. Act autonomously; ask only for essential missing decisions or permissions. Respect safety, tools and project rules.

## Route by task evidence

L = `gpt-6-luna` (`agentmd_luna`); T = `gpt-6.1-terra` (`agentmd_terra`); S = `gpt-6.2-sol` (`agentmd_sol`); A = `gpt-6.2-astra` (`agentmd_astra`).
Effort suffixes: n=none, l=low, m=medium, h=high, x=xhigh, max=max. S.m means Sol medium. Filter unsupported settings/tools; none is measured only for L/T. API support does not establish Codex availability.

Identify the deliverable, checks, constraints and acceptance bottleneck. Prefer direct evidence and validated progress, not self-assessed competence. For bounded work use a relevant O anchor or proven current setting. For demanding quality-critical work choose the highest relevant feasible observed candidate provisionally. If demands overlap, prioritize the bottleneck or separate coherent outputs. If no specific demand fits, use the ordinary anchor or broad quality order.

### Official starting anchors (O, not measured optima)

- Bounded edit or extraction with clear checks: L.l.
- Clear dependent steps: L.x or S.m.
- Visual interpretation or UI operation: T.m.
- Repository change/debugging: S.m.
- Test-and-revise execution: S.x.
- Polished artifact from a clear brief: A.l.
- Complex/changing dependencies: A.m.
- Open-ended difficult tradeoffs: A.x.
- Ordinary unclassified work: S.m.

### Measured quality preferences (B)

AA v5.0.2, 2026-11-26 JST. Each line lists all 22 measured configurations: `>` higher displayed quality, `=` exact displayed tie, not statistical equivalence. These are selection preferences, not a retry sequence. Rank omits gap sizes; a small or unknown gain alone does not justify switching a validated approach. Filter by actual resources/capabilities and relevant evidence. Never average unlike metrics.

- Agentic knowledge work (Briefcase): A.max > S.max > A.x > S.x > A.h > S.h > S.m > A.m > T.max > L.max > T.x > T.h > L.x > S.l > T.n > T.m > L.h > L.m > A.l > T.l > L.n > L.l.
- Multi-step SaaS/workflow execution (Automation): A.max > A.x > A.h > A.m > S.max > S.x > S.m > S.h > A.l > S.l > T.max > T.x > T.h > T.m > T.l > L.max > T.n > L.h = L.x > L.m > L.l > L.n.
- Terminal tasks (Terminal-Bench): A.x > A.max > A.h > S.max > A.m > S.h > T.max > S.x > S.m > A.l > T.x > T.h > S.l > T.m > T.n > T.l > L.max > L.x > L.h > L.m > L.n > L.l.
- Repository change quality (FrontierCode-AA): A.x > A.h > A.m > A.max > S.max > S.x > T.max > S.m > S.h > T.h > T.x > T.m > T.n > A.l > S.l > L.max > T.l > L.h > L.x > L.m > L.l > L.n.
- Professional document reasoning (GDP.pdf): S.max > A.max > S.m > S.h > T.max = S.l = A.h > T.m = S.x = A.m > T.h = A.l = A.x > T.x > T.l > T.n > L.max > L.x > L.h > L.m > L.l > L.n.
- Difficult knowledge/reasoning (HLE-Diamond): A.max > A.x > A.h > S.max > S.x > S.h > A.m > S.m > A.l > T.max > T.x > T.h > S.l > T.m > T.l > L.max > L.x > L.h > L.m > T.n > L.l > L.n.
- Hard physics reasoning (CritPt): A.h = A.max > A.x > T.max > A.m > S.m > S.x = S.max > T.h = S.h > A.l > T.x > S.l > T.m > T.l > L.max > L.x > T.n > L.h > L.m > L.l > L.n.
- Scientific research workflows (Terminal-Bench-Science): A.x > A.max > A.h > A.m > S.h = S.max > S.x > S.m > T.max > A.l > T.x > S.l > T.h > T.m > T.n > L.max > T.l > L.x > L.h > L.m > L.n = L.l.
- Broad mixed work (AA Intelligence Index): A.x = A.max > A.h > S.max = A.m > S.x > S.h > S.m > T.max > A.l > T.x > T.h > S.l > T.m > T.n > T.l > L.max > L.x > L.h > L.m > L.l > L.n.

If relevant quality is not distinguished, prefer lower handoff, cost and time. Broad AA resource proxies (lower first; not task-specific):
- Cost: L.l > L.m > T.l > L.n > L.h > L.x > L.max > T.m > S.l > T.n > T.h > T.x > S.m > S.h > S.x > A.l > T.max > S.max > A.m > A.h > A.x > A.max.
- Inference time: L.l > T.l > S.l > L.n > A.l > T.n > T.m > L.m > S.m > T.h > A.m > L.h > S.h > S.x = A.h > L.x = T.x > A.x > S.max > L.max > T.max > A.max.

Other matched evidence:
- Repository patches (Cognition FrontierCode, max): S/A have close scores and equal published pass rates; S lower rollout cost; T unmeasured.
- Terminal-Bench 4.1 (max): S/A reported intervals overlap.
- Agent Arena coding (max): T/S/A intervals overlap; retain T despite its lower broad rank.
- Firecrawl search (medium): S/A paired difference interval spans zero; S lower cost and median time.
- Vals science: A higher observed score than S/L; model pages list max, component settings uncertain.

No calibrated success probabilities, rescue rates or task-specific budgets follow from these orders. Do not extrapolate across efforts or count related evaluations as independent. AA cost/time are broad proxies, not actual Codex charges or wall-clock latency. The full numerical data and conditions remain in AgentMD's `research/benchmark-evidence.md`; do not load it or re-research model capabilities during ordinary work.

## Execute and reassess

Do the work directly when suitable. Reassess on material changes, unresolved decisions or failure. Correct supported causes; diagnose unknown causes or choose a supported alternative. Missing facts, tools or permissions require authorized remedies, not stronger models.

Before nontrivial routing, identify the observed need, LUT/evidence, model/effort and expected output/check. Compare effort changes and model changes; account for handoff/rework. Request supported settings; custom roles pin model, not effort. Verify resolved settings when exposed; otherwise use a feasible alternative and disclose material limitations. No mandatory first failure, hierarchy or effort ladder.

## Buddy — work together

When the LUT favors another model for useful remaining work and parallel progress is possible, **spawn it at the selected supported effort and keep working yourself**. Consider a distinct model for consequential, weakly verifiable decisions even before detected failure. Use the same LUT, not a fixed pair, mandatory audit or diversity-only call.

- Define both outputs and checks: delegate a complementary subtask or independent approach; continue your own useful work. Share needed evidence/constraints without anchoring independent judgments. Use disjoint writable paths, read-only work or isolated copies.
- Continue research, reasoning, implementation or tests while Buddy runs. Wait only at a real dependency or when safe useful work is exhausted. Direct/sequential execution remains valid if parallelism is infeasible.
- Join before dependent decisions or completion. Verify and integrate both outputs, resolve discrepancies with evidence, preserve validated work and correct unsupported assumptions in context. Agreement or model identity is not proof. End or reselect Buddy when useful.

## Handoff and completion

Preserve objective/checks, sourced facts, hypotheses/refuted assumptions, artifacts, attempts and remaining resources. Reuse useful context or start fresh for independent/refuted approaches; separate threads do not guarantee independent errors or files.

Give workers relevant policy/state, allowed actions/paths, checks and remaining allowance. No recursive spawning. Return `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `RESULT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, `ATTEMPTS_USED`, optional `NEXT_CANDIDATE`. Report skipped checks. Primary verifies acceptance, not status claims.

Respect explicit user/runtime limits. Default: **three substantive attempts on the same unresolved acceptance condition**, including initial, local, delegated and parallel/resumed attempts. Reserve before launch; failed launch counts once. Two independent solves consume two slots; routine checks do not. Distinct checkable subgoals have separate counts. Model/effort/thread/hypothesis changes do not reset the ledger; only validated resolution retires a blocker. This provisional limit is neither hard enforcement nor an optimum.

Stop on verified acceptance, exhausted resources or no useful feasible correction. Continue independent useful work if a branch stops. Do not repeat failures without a concrete reason. Report actual results/limits; never claim unobserved settings, checks, cache hits or success.
