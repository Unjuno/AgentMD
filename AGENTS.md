# AgentMD — Shared routing policy

## Objective

Complete the user's task with defensible quality within available resources, including verification, handoff and rework. All models are general-purpose. Respect user/project instructions, permissions and tools. Use ordinary verification; no agents solely for diversity, consensus or routine adversarial review.

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

## Select necessary work

Establish deliverables, acceptance conditions, constraints and unresolved dependencies. Keep simple tasks together. Delegate a coherent unit with a useful output/check, relevant context and clear change ownership, not individual tool calls or a model sequence.

Compare current and eligible configurations jointly by model and effort, considering demands, error consequences, checks, resources and handoff. No first failure or intermediate effort is required. For unfamiliar work, use O and AA as uncertain priors and choose a useful next action without invented probabilities or universal rankings.

| Observed state | Decision |
| --- | --- |
| Current approach makes validated progress and meets the demand | Continue; a phase name or small leaderboard gap is not a reason to switch. |
| Missing fact, input, access or working tool | Obtain the specific evidence through an authorized route or report the blocker. More reasoning does not supply missing access. |
| Failure has a supported cause | Make a targeted correction and check it. Keep the current configuration unless the correction calls for a different capability. |
| Failure cause remains unclear | Use a focused diagnostic; if it cannot resolve the issue, choose a materially different approach/configuration supported by the LUT or observed failure. |
| Remaining work has a capability mismatch or relevant evidence favors an alternative | Switch where the runtime supports it, or delegate a coherent unit, when the expected contribution justifies handoff. |
| Acceptance is established | Finish; do not start a model-review loop. |

Before a nontrivial switch, note the observed need, selected model/effort with supporting evidence, and expected output/check. Greater intelligence alone is insufficient. Prefer lower overhead when relevant quality is not materially distinguished. Raise effort for a stated reasoning need; change model when evidence or capabilities better address it.

Reassess on changed requirements, material failure, resolved uncertainty or changed capability demand. Preserve validated work; parallelize useful independent units without conflicting edits. If routing is unavailable, do the best feasible work and state material limitations. Never claim an unobserved switch.

## Handoff and completion

Keep compact state: objective/checks, sourced facts, marked hypotheses, refuted assumptions, artifact/checkpoint, attempted configurations/failures and remaining resources. Reuse useful context; start fresh for separate work or a refuted approach. Omit irrelevant history. A fresh thread is not independent evidence or a separate filesystem.

Give workers the applicable shared policy, objective, relevant state, permitted paths/actions, checks, and remaining attempt allowance. If the policy was not inherited, include its relevant rules. Workers must not recursively spawn. They return concise `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `RESULT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, `ATTEMPTS_USED`, and optional `NEXT_CANDIDATE` (model, effort, evidence-based reason). Use PASS only with the specified checks; skipped or unavailable checks stay explicit. The primary integrates against acceptance evidence, not a worker's status or model identity.

## Finite recovery

Explicit time, cost, concurrency and attempt budgets take precedence. Without a task-specific recovery limit, allow **at most three substantive attempts on the same unresolved acceptance condition**, including the initial attempt, across local work, workers, parallel attempts and resumed attempts. Reserve allowance before launch; failed launches count once. Routine reads and checks inside a coherent attempt are not separate attempts. If no useful correction or alternative remains, stop earlier.

The primary owns the shared attempt ledger. A model/effort/thread change, renamed task, new hypothesis or worker restart does not reset it. Only a validated checkpoint that retires the old blocker permits a new independently checkable subgoal; do not split or relabel a stalled condition to evade the limit. Finish other useful independent work when one branch stops. This limits repeated failure, not the number of successful stages in a large task.

The three-attempt default is a provisional policy choice, not an optimized value or hard enforcement. Do not repeat an unchanged failed approach. Stop on exhausted resources, an unresolved blocker with no feasible route, or established acceptance; report actual results and remaining limits. Never claim exact budget enforcement, model/effort execution, cache hits or success beyond what the runtime and checks establish.

