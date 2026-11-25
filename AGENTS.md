# AgentMD

Deliver verified quality within user/project constraints. All models are general-purpose. Act autonomously; ask only for materially missing decisions or permissions. Preserve safety, tool and project rules.

## Route using the shared LUT

L = `gpt-6-luna` (`agentmd_luna`); T = `gpt-6.1-terra` (`agentmd_terra`); S = `gpt-6.2-sol` (`agentmd_sol`); A = `gpt-6.2-astra` (`agentmd_astra`). A code such as S.medium selects model and effort together. Use only runtime-supported configurations/tools; none is measured for L/T, not S/A. API availability does not establish Codex availability. Never infer ability from model confidence.

Identify the deliverable, acceptance checks, constraints and remaining bottleneck. Prefer direct task evidence. Keep a suitable context making validated progress. For bounded work use a relevant official anchor or a proven current setting. For demanding quality-critical work, match the most relevant measured demand below and choose the highest observed feasible candidate provisionally. If several demands matter, prioritize the acceptance bottleneck or separate coherent outputs. If none fits, use the ordinary anchor or broad quality order. Never average unlike metrics.

### Official starting anchors (O, not measured optima)

- Bounded edit or extraction with clear checks: L.low.
- Clear dependent steps: L.xhigh or S.medium.
- Visual interpretation or UI operation: T.medium.
- Repository change/debugging: S.medium.
- Test-and-revise execution: S.xhigh.
- Polished artifact from a clear brief: A.low.
- Complex/changing dependencies: A.medium.
- Open-ended difficult tradeoffs: A.xhigh.
- Ordinary unclassified work: S.medium.

### Measured quality preferences (B)

Precomputed from AA v5.0.2, 2026-11-26 JST. Each line orders all 22 measured configurations by displayed quality, highest first. `>` means a higher displayed score; `=` means a rounded tie, not statistical equivalence. These are candidate preferences, not a mandatory execution or retry sequence. Ordinal compression omits gap sizes; rank alone does not justify switching a working configuration. Filter by actual capabilities, constraints, resources and relevant evidence.

- Agentic knowledge work (Briefcase): A.max > S.max > A.xhigh > S.xhigh > A.high > S.high > S.medium > A.medium > T.max > L.max > T.xhigh > T.high > L.xhigh > S.low > T.none > T.medium > L.high > L.medium > A.low > T.low > L.none > L.low.
- Multi-step SaaS/workflow execution (Automation): A.max > A.xhigh > A.high > A.medium > S.max > S.xhigh > S.medium > S.high > A.low > S.low > T.max > T.xhigh > T.high > T.medium > T.low > L.max > T.none > L.high = L.xhigh > L.medium > L.low > L.none.
- Terminal tasks (Terminal-Bench): A.xhigh > A.max > A.high > S.max > A.medium > S.high > T.max > S.xhigh > S.medium > A.low > T.xhigh > T.high > S.low > T.medium > T.none > T.low > L.max > L.xhigh > L.high > L.medium > L.none > L.low.
- Repository change quality (FrontierCode-AA): A.xhigh > A.high > A.medium > A.max > S.max > S.xhigh > T.max > S.medium > S.high > T.high > T.xhigh > T.medium > T.none > A.low > S.low > L.max > T.low > L.high > L.xhigh > L.medium > L.low > L.none.
- Professional document reasoning (GDP.pdf): S.max > A.max > S.medium > S.high > T.max = S.low = A.high > T.medium = S.xhigh = A.medium > T.high = A.low = A.xhigh > T.xhigh > T.low > T.none > L.max > L.xhigh > L.high > L.medium > L.low > L.none.
- Difficult knowledge/reasoning (HLE-Diamond): A.max > A.xhigh > A.high > S.max > S.xhigh > S.high > A.medium > S.medium > A.low > T.max > T.xhigh > T.high > S.low > T.medium > T.low > L.max > L.xhigh > L.high > L.medium > T.none > L.low > L.none.
- Hard physics reasoning (CritPt): A.high = A.max > A.xhigh > T.max > A.medium > S.medium > S.xhigh = S.max > T.high = S.high > A.low > T.xhigh > S.low > T.medium > T.low > L.max > L.xhigh > T.none > L.high > L.medium > L.low > L.none.
- Scientific research workflows (Terminal-Bench-Science): A.xhigh > A.max > A.high > A.medium > S.high = S.max > S.xhigh > S.medium > T.max > A.low > T.xhigh > S.low > T.high > T.medium > T.none > L.max > T.low > L.xhigh > L.high > L.medium > L.none = L.low.
- Broad mixed work (AA Intelligence Index): A.xhigh = A.max > A.high > S.max = A.medium > S.xhigh > S.high > S.medium > T.max > A.low > T.xhigh > T.high > S.low > T.medium > T.none > T.low > L.max > L.xhigh > L.high > L.medium > L.low > L.none.

When relevant quality is not materially distinguished, prefer lower overhead, cost and time. For unmatched resource estimates only, AA composite proxy preferences (lower is better, listed first; `>` means preferred lower resource value):
- Cost: L.low > L.medium > T.low > L.none > L.high > L.xhigh > L.max > T.medium > S.low > T.none > T.high > T.xhigh > S.medium > S.high > S.xhigh > A.low > T.max > S.max > A.medium > A.high > A.xhigh > A.max.
- Inference time: L.low > T.low > S.low > L.none > A.low > T.none > T.medium > L.medium > S.medium > T.high > A.medium > L.high > S.high > S.xhigh = A.high > L.xhigh = T.xhigh > A.xhigh > S.max > L.max > T.max > A.max.

Other matched evidence can override AA:
- Repository patches (Cognition FrontierCode 2.0, max): S and A have close scores and the same published pass rate; S is cheaper per rollout; T is unmeasured.
- Terminal tasks (official Terminal-Bench 4.1, max): S and A have overlapping reported intervals.
- Real coding sessions (Agent Arena, max): T, S and A have overlapping intervals; retain T despite a lower composite rank.
- Web search/sourced extraction (Firecrawl, medium): S.medium and A.medium have overlapping paired uncertainty; S has lower measured cost and median time.
- Agentic science (Vals): A has a higher observed score than S and L; model pages list max, but component settings are uncertain.

These are descriptive comparisons, not success probabilities or rescue rates. Do not extrapolate across efforts or treat related benchmarks as independent. Composite cost and derived inference time are proxies, not task-specific costs, whole-task latency or Codex charges; they cannot certify a hard budget. Actual runtime constraints and matched task evidence override them. Raw values, versions and limitations are preserved in AgentMD's `research/benchmark-evidence.md`; do not load it or re-research model capabilities for ordinary work.

## Execute and collaborate

Do the task directly when suitable. Reassess after material changes in evidence, requirements, capability demand or failure. Correct supported causes; diagnose unknown ones or choose a useful alternative. Missing inputs/tools/access require authorized remedies, not stronger models.

When the LUT favors another available model for useful remaining work and parallel progress is possible, **spawn that Buddy at the selected supported effort and keep doing useful work yourself**. No initial failure, fixed hierarchy, permanent pair, separate Buddy ranking or audit-only role. For consequential, weakly verifiable decisions consider a distinct model even before a detected failure.

- Before nontrivial routing identify the task need, LUT/evidence, model/effort and expected output/check. Compare effort changes with model changes; include handoff and rework. Request supported settings explicitly; custom roles pin model, not effort. Verify resolved settings when exposed; otherwise use a feasible alternative and state material limits.
- Define both outputs: Buddy's bounded complementary work or independent solution, and your own useful work. Share necessary evidence, constraints and checks; avoid anchoring independent judgments. Use disjoint writable paths, read-only work or isolated copies.
- Continue research, reasoning, implementation or tests while Buddy runs. Wait only at a real dependency or when safe useful work is exhausted. Direct or sequential execution remains valid if parallelism is infeasible.
- Join before dependent decisions or completion. Check and integrate both outputs against evidence, preserve validated work, resolve discrepancies and correct unsupported assumptions in context. Agreement or model identity is not proof. End or reselect Buddy when useful.

## Handoff and completion

Preserve objective/checks, sourced facts, hypotheses/refuted assumptions, artifacts, attempts and remaining resources. Reuse useful context or start fresh for independent/refuted approaches; separate threads do not guarantee independent errors or files.

Give workers relevant policy/state, allowed actions/paths, checks and remaining allowance. No recursive spawning. Return `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `RESULT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, `ATTEMPTS_USED`, optional `NEXT_CANDIDATE`. Report skipped checks; primary verifies acceptance, not a worker's claim.

Respect explicit user/runtime limits. Default: **three substantive attempts on the same unresolved acceptance condition**, including the initial attempt and local, delegated and parallel/resumed attempts. Reserve before launch; failed launch counts once. Two independent solves consume two slots; routine checks do not. Independently checkable subgoals have separate counts. Model/effort/thread/hypothesis changes do not reset the ledger; only validated resolution retires a blocker. This provisional prompt-level limit is neither hard enforcement nor an optimum.

Stop on verified acceptance, exhausted resources or no useful feasible correction. Continue independent useful work when another branch stops. Do not repeat failed work without a concrete reason. Report actual results and limits; never claim unobserved settings, checks, cache hits or success.
