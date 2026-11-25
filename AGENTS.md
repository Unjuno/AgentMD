# AgentMD — Shared routing policy

## Objective

Complete the user's task with defensible quality within available resources. All models are general-purpose. Respect user/project instructions, permissions and tools. Use ordinary verification and optional, event-driven Buddy collaboration.

## Runtime and shared lookup table

Confirm available models, tools and effort settings from the runtime. L = `gpt-6-luna` (`agentmd_luna`); T = `gpt-6.1-terra` (`agentmd_terra`); S = `gpt-6.2-sol` (`agentmd_sol`); A = `gpt-6.2-astra` (`agentmd_astra`). Do not guess identity, silently substitute generations, or infer competence from confidence. Explicit user restrictions apply; merely starting with a model does not forbid useful delegation.

Match observable demands of remaining work; several rows may apply. O is provider guidance, not a measured optimum or fixed occupation.

| Observable demand | Candidate anchors (O) |
| --- | --- |
| Bounded edit or extraction with clear acceptance | L low |
| Dependent steps with clear constraints | L xhigh, S medium |
| Visual interpretation or changing browser/desktop state | T medium |
| Repository changes or debugging | S medium |
| Iteration requiring tests and correction | S xhigh |
| Finished artifact from a clear brief | A low |
| Complex dependencies or changing requirements | A medium |
| Open constraints and difficult tradeoffs | A xhigh |

**AA v5.0.2, checked 2026-11-26 JST, Standard.** Cells: index / weighted USD per evaluation task / estimated inference minutes per evaluation task. Time derives from output tokens and speed. These rounded aggregates are not success probabilities, whole-task latency or Codex charges; row uncertainty is unavailable.

| Model | low | medium | high | xhigh | max |
| --- | --- | --- | --- | --- | --- |
| L | 10/.0051/.6 | 18/.0422/3.1 | 21/.0729/4.9 | 23/.10/6.4 | 28/.15/10.6 |
| T | 29/.0713/1.1 | 38/.17/2.7 | 43/.26/4.2 | 45/.40/6.4 | 51/.96/14.0 |
| S | 41/.18/1.6 | 52/.41/3.5 | 55/.56/5.2 | 56/.65/6.2 | 57/1.01/10.0 |
| A | 46/.66/2.0 | 57/1.62/4.6 | 60/2.07/6.2 | 62/2.52/8.1 | 62/4.00/14.2 |

Prefer task-similar evidence to composites; other feasible candidates remain eligible.

| Evidence scope | What it supports |
| --- | --- |
| FC: repository patches, max | S and A have nearby published scores; S has lower reported rollout cost. T is unmeasured here. |
| TB: terminal tasks, max | Retain S and A; published score intervals overlap. No claim about lower effort. |
| AC: real coding sessions, max | Retain T alongside S and A; their intervals overlap. This index is not a pass rate. |
| FS: web search and factual extraction, medium | S and A have overlapping score uncertainty; S has lower measured cost and median time in this setup. |
| VS: agentic science | A has the higher observed score than S and L; model pages list max, with benchmark-specific setting uncertainty. |

Evidence tags refer to `research/benchmark-evidence.md` in the AgentMD repository, not the user's working directory. It is not a runtime dependency; do not research benchmarks during ordinary work. Missing evidence means unknown, not zero. Do not extrapolate max to other efforts, average incompatible metrics, count overlapping suites independently, or infer conditional retry rankings. Dominance on one benchmark does not exclude other uses. Cache hits and actual cost require runtime evidence.

## Choose work and route

Establish deliverables, acceptance checks, constraints and unresolved dependencies. Compare the current and eligible model/effort configurations using the shared LUT, actual requirements, progress and evidence, error consequences, resources and handoff overhead. Keep a suitable context making progress. Choose a coherent output, not individual tool calls. No initial failure, fixed model hierarchy or intermediate effort is required.

| Observed state | Decision |
| --- | --- |
| Current approach meets the demand | Continue directly. |
| Relevant LUT evidence favors another configuration for remaining work | Delegate promptly or switch where supported; use Buddy when useful parallel work exists. |
| Consequential unresolved decision or weakly verifiable assumption | Consider an independent Buddy approach before committing, even if the current model reports confidence or success. |
| Missing input, fact, access or working tool | Obtain it through authorized means or report the blocker. |
| Supported failure cause | Correct it and check; reassess the configuration if the demand changes. |
| Unclear failure cause | Diagnose or choose a materially different approach/configuration supported by the LUT or observed failure. |
| Acceptance established | Finish after integrating required outstanding work; do not add routine reviews. |

Before nontrivial routing, identify the observed need, model/effort, supporting LUT row or task evidence, and expected output/check. For unfamiliar work use O and AA as uncertain priors, not invented probabilities. Compare effort changes with model changes; prefer lower overhead when relevant quality is not materially distinguished. If routing is unavailable, do the best feasible work and report material limits.

## Buddy routing — work together, not merely delegate

When the LUT favors another available model for a useful part or approach, and you can make useful progress concurrently, **spawn that model at the selected supported effort and keep working yourself**. Do not require a failed first attempt. The primary stays an active contributor; Buddy is neither a permanent pair nor an audit-only role.

- Define both outputs before launch: the Buddy's bounded task/check and your own useful parallel work toward the same deliverable. Complementary subtasks or independent solutions/diagnoses are valid.
- Share the goal, necessary facts/artifacts, constraints and checks. For independent judgment, share raw evidence without anchoring the Buddy to your conclusion. Assign disjoint writable paths, read-only checks or isolated copies; never make conflicting concurrent edits.
- Continue your own research, reasoning, implementation or tests while the Buddy runs. Do not immediately wait or duplicate work merely to stay busy. Wait only at a genuine dependency/join or when no safe useful work remains. Use ordinary sequential delegation if parallel progress is infeasible.
- Collect and compare both outputs before dependent decisions or completion. Check facts and artifacts, resolve discrepancies using evidence, preserve validated progress and correct unsupported assumptions in the working context. Do not decide by model prestige, agreement or majority vote.
- End the collaboration after its useful work is integrated. Reuse or choose a different Buddy for a new need through the same LUT. No permanent assignments, fixed pairs, mandatory second opinion or diversity-only calls.

## Handoff and completion

Keep compact state: objective/checks, sourced facts, marked hypotheses, refuted assumptions, artifact/checkpoint, attempted configurations/failures and remaining resources. Reuse useful context; start fresh for independent work or a refuted approach. A fresh thread is not independent evidence or a separate filesystem.

Give workers the applicable shared policy, relevant state, permitted paths/actions, checks and remaining attempt allowance. If policy was not inherited, include relevant rules. Workers must not recursively spawn. Return concise `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `RESULT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, `ATTEMPTS_USED` and optional `NEXT_CANDIDATE` (model, effort, evidence-based reason). Report skipped checks. Primary verifies acceptance, not a worker's status or identity.

## Finite recovery

Explicit user/runtime time, cost, concurrency and attempt budgets take precedence. Without a task-specific limit, allow **at most three substantive attempts on the same unresolved acceptance condition**, including the initial attempt, across local work, workers and parallel/resumed attempts. Reserve allowance before launch; failed launches count once. Two independent solving attempts on the same condition use two slots; a routine read/check within an attempt does not consume a separate slot. Distinct independently checkable subgoals have their own counts.

The primary owns the shared ledger. Model/effort/thread changes, renamed tasks and new hypotheses do not reset it. Only validated resolution retires a blocker; do not split or relabel a stalled condition to evade the limit. Continue independent useful work when another branch stops. This provisional guardrail bounds failed recovery, not successful stages; it is not a measured optimum or hard enforcement.

Stop when acceptance is established, resources are exhausted or no useful feasible correction remains. Do not repeat an unchanged failed approach without a concrete reason. Report actual results and remaining limits; never claim unobserved model/effort execution, exact budget enforcement, cache hits or success.
