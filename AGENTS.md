# AgentMD — Adaptive general-purpose routing

## Objective
Complete the user's actual task with the best defensible end-to-end quality within available resources. Minimize unnecessary model calls, duplicated work, handoff, rework, time and cost without sacrificing required quality. Respect user/project instructions, permissions and tools. All models are general-purpose; no fixed occupations or compulsory escalation sequence.

## Shared capability LUT
Use confirmed runtime identity and supported configurations. L = `gpt-6-luna` (`agentmd_luna`); T = `gpt-6.1-terra` (`agentmd_terra`); S = `gpt-6.2-sol` (`agentmd_sol`); A = `gpt-6.2-astra` (`agentmd_astra`). Never infer model competence from self-confidence. Do not assume configured IDs or effort values are available.

Match observable features of the **remaining work**, not the overall task label. Features can coexist. The following sparse LUT supplies non-exclusive candidate anchors from archived OpenAI workload guidance (O), not measured optimal assignments.

| Observed capability demand | Candidate anchors (O) |
| --- | --- |
| Explicit, bounded operation with a reliable check | L low |
| Clear constraints; multiple dependent reasoning/tool steps | L xhigh, S medium |
| Visual interpretation or changing browser/desktop state | T medium |
| Repository reasoning, modification or debugging | S medium |
| Iterative implementation and test-driven correction | S xhigh |
| Polished artifact from a clear brief | A low |
| Complex dependencies or changing requirements | A medium |
| Unresolved constraints, difficult tradeoffs or novel reasoning | A xhigh |

Other supported configurations remain eligible. For unfamiliar or mixed demands, combine relevant anchors, current progress and general evidence; no forced classification. When little task-specific evidence exists, use the broad reference below to compare plausible configurations, including the current one. Do not infer exact task success probabilities.

General reference: dated AA Intelligence Index v5.0.1 snapshot (2026-11-24); each cell is **index / average USD / average minutes per index task**. Rounded aggregate measurements, not calibrated action-specific performance, current Codex usage, or guarantees of quality. Compare like metrics only.

| Model | low | medium | high | xhigh | max |
| --- | --- | --- | --- | --- | --- |
| L | 10/.0051/.6 | 18/.0422/3.4 | 21/.0729/5.4 | 23/.10/7 | 28/.15/11.5 |
| T | 29/.0713/1.1 | 38/.17/2.7 | 42/.26/4.2 | 45/.40/6.4 | 51/.96/14.4 |
| S | 41/.18/1.6 | 53/.41/3.6 | 55/.56/5.2 | 56/.65/6.3 | 57/1.01/10.1 |
| A | 46/.66/2.1 | 57/1.62/4.8 | 60/2.07/6.5 | 62/2.52/8 | 62/4/14.2 |

Task-specific evidence takes precedence over broad composites. Archived FrontierCode 2.0 at max retains S and A as strong repository-work candidates; Agent Arena coding at max also retains T. These results do not establish lower-effort performance or a reliable order of conditional retries. Use resource measurements only as rough comparative priors. See `research/benchmark-evidence.md` for dated sources, caveats and missing data; do not load or research model benchmarks during routine work.

## Route the whole task
1. Establish the requested deliverable, acceptance conditions, constraints and observable state. Identify the next necessary work and dependencies. Keep simple tasks simple; split only when distinct, meaningful work units benefit from delegation or parallel execution. Group related operations in one context. Do not route every tool call.
2. For the next meaningful work unit, identify its actual capability demands, information gaps, checkability and consequences of error. Compare eligible LUT configurations, including current model/effort, against the remaining work. Exclude unsupported tools/models/efforts and user-disallowed actions. Consider end-to-end result quality, remaining resources, handoff and expected rework, not benchmark rank alone. Treat anchors as priors; new task evidence overrides them.
3. Continue in the current context when it is a suitable candidate and switching has no supported material benefit. Prefer the lower-overhead feasible route when evidence does not distinguish quality materially. If another configuration is better indicated for actual remaining work, switch model/effort where supported and allowed, or delegate a coherent work unit to that configuration. No failed first attempt, forced intermediate effort, or extra agent required. Never override an explicit user-pinned setting. If no delegation is available, do the best feasible work.
4. Use ordinary tools, sources, tests and acceptance checks to assess progress. On a known failure, retain the cause and route its correction. On an unknown failure, choose targeted fact-finding or an alternative solving configuration based on the remaining problem. Retry the same configuration if justified; change effort or model if the evidence favors it. If an assumption is contradicted, revise it rather than repeating the same approach. If access or input is missing, seek an authorized alternative or report the blocker.
5. Integrate completed work and re-evaluate at meaningful changes in state: a changed requirement, material failure, newly resolved uncertainty or different capability demand. Do not reroute merely because a phase name changes. Preserve working checkpoints and dependencies. Independent parallel work is allowed only when useful after coordination cost; avoid conflicting edits.
6. Finish once the requested acceptance conditions are satisfied, or when no useful feasible action remains. No mandatory second opinion, adversarial audit, model-diversity quota or post-success review loop. Use normal task verification locally where possible. Additional model-based verification is an ordinary routed work unit only if requested or needed to establish a material acceptance condition and its benefit justifies its cost.

## Context and delegation
Maintain only the necessary working state: objective, constraints, relevant facts and references, current artifact/checkpoint, hypotheses, failures, open requirements and remaining resources. Correct or explicitly supersede refuted assumptions using evidence. Different models may contribute different solutions during necessary work, but agreement, disagreement, model identity or confidence is not proof. Do not invoke another model solely to obtain diversity.

Send each worker the coherent objective, relevant evidence/context, constraints, permitted changes and completion checks. Reuse a worker thread when continuation benefits; start a fresh context when solving a new issue would otherwise inherit a refuted approach. Do not duplicate work or copy irrelevant history. Workers return concise `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `RESULT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, and optional `NEXT_CANDIDATE` (model/effort/reason). A self-reported PASS is not acceptance evidence. The primary coordinates dependencies and integrates results; workers recommend, not recursively spawn.

## Resource guardrails
Respect explicit time, cost, concurrency and execution limits. As a provisional prompt-level guardrail when no different task budget is specified, allow at most six substantive attempts shared by local work, delegated work, diagnosis and repair, including each parallel worker and resumed solving attempt; routine reads/checks within an attempt are not separate attempts. Reserve before launching; count once even if a launch fails; do not reset on switching. This default is not an optimum or runtime-enforced quota. Keep attempts cohesive rather than spawning for each step. Stop purposeless retries and report actual results and unresolved requirements. Confirm actual model/effort, tool outcomes and execution where possible; never claim unsupported model switches or unverified success.
