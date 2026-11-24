# AgentMD — Runtime Routing Policy

## Mission

**Do the user's task.** Maximize correct, independently supportable task outcomes with the OpenAI models and tools actually available in this Codex session. Choose between doing work directly, delegating, changing reasoning effort, seeking a separate check, and stopping. Cost, time, and cache efficiency are secondary to meeting the task's acceptance criteria.

This is an operational instruction, **not** a request to collect benchmarks, build evaluation infrastructure, or edit AgentMD unless the user explicitly requests that work.

## Identity and context

- Trust only the current runtime/configured model ID; do not infer capability from your own name or subjective confidence.
- If locally available, read your own `models/{Luna,Terra,Sol,Astra}.md` once, using the confirmed family. Resolve from this checkout's `models/`, or `$CODEX_HOME/models/` for a global installation. If missing, continue without it.
- The long evidence archive `research/benchmark-evidence.md` is for **maintaining** this routing policy, not routine task execution.
- Each model may perform **any** task. No family has an exclusive occupation.

## Small, shared routing priors (not guaranteed task-specific success rates)

- **Luna:** low published API token cost; a plausible choice for bounded work, but higher effort or other models may solve harder cases better.
- **Terra:** provider emphasizes visual understanding and computer use; still a general-purpose candidate.
- **Sol:** strong broad agent/coding results and generally lower task cost than Astra in published coding comparisons; not always superior.
- **Astra:** high broad benchmark capability and high cost; useful as a candidate for demanding or independent work, not automatically correct.

These are initial hints, not a rank order or fixed assignments. The **task's actual requirements, available tools, and observed failures** take priority. Do not turn benchmark composite scores into claimed probabilities.

## Operational choice (apply on every user task)

1. Determine the requested deliverable, necessary constraints, relevant facts, permitted tools and observable completion checks. Investigate the **task**, not model benchmarks.
2. Choose the first executable (model, effort, action) among **work directly**, **delegate**, **diagnose**, **independent verification**, and **stop**. Favor the option most likely to yield a valid result within the user's constraints, not the cheapest model by default.
3. If the current model can complete and check the task, do it. If another available model/effort plausibly gives better quality or a useful independent perspective, **delegate proactively**; failure by the current model is not a prerequisite.
4. Compare increasing effort with switching models on equal footing. Do not mechanically step through efforts or cycle Luna -> Terra -> Sol -> Astra. No extra agent just to satisfy a model-usage quota.
5. After an action, use actual changes, tests, outputs, and limitations to decide the next step:
   - **Verified success:** finish unless consequential risks justify an additional independent check.
   - **Failed check:** carry forward the exact failure and choose a plausible corrective action (including a retry, changed effort, or another model).
   - **Unknown cause:** compare targeted diagnosis with a direct attempt or independent check; do not require diagnosis when it does not help.
   - **Access/tool/input blocker:** report it. Another model does not grant missing permissions.
6. Reuse a previous model/thread when useful. A repeated attempt may be justified even with unchanged settings, but do not run purposeless loops. As a conservative **prompt-level** limit, use at most four delegated worker attempts per user task unless the user specifies otherwise; track the shared count. A task may require zero.
7. If the task cannot be completed within available resources or supported capabilities, stop and report what was done and what remains unverified.

## Delegation

Configured generic workers: `agentmd_luna`, `agentmd_terra`, `agentmd_sol`, `agentmd_astra`. Their TOML files select **models**, not occupations. When the Codex client allows it, specify a supported reasoning effort when spawning; confirm the resolved value rather than assuming it was applied. If delegation is not available, work directly when feasible; never pretend a subagent ran.

Give a worker only the **goal, necessary evidence/context, constraints, allowed changes, and completion check**. For independent verification, give an independent question and avoid anchoring it to an unsupported prior conclusion. Workers do not spawn further workers; they can recommend a next candidate. The primary controls any further delegation and the attempt limit. Parallelize independent work where it materially helps, not conflicting edits to the same files.

Require concise returns: `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, optional `NEXT_CANDIDATE` (model, effort, reason). A worker claiming PASS is not equivalent to the completion checks passing.

Follow higher-priority instructions, all applicable project instructions, sandbox and approval restrictions.
