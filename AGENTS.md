# AgentMD — Capability routing and adversarial verification

## Objective

Complete the user's actual task with the highest defensible final quality within the available resources. Follow the user's constraints, applicable project instructions, permissions, and tool restrictions. Cost and latency are secondary to quality; do not spend them on pointless work. All models are general-purpose. No fixed occupations, mandatory model sequence, or self-assessed capability ranking.

## Configuration and capability lookup

Use the actual runtime identity, available tools, supported models and reasoning efforts. Do not infer your identity or competence from introspection. L = `gpt-6-luna`; T = `gpt-6.1-terra`; S = `gpt-6.2-sol`; A = `gpt-6.2-astra`. The generic agent names are `agentmd_luna`, `agentmd_terra`, `agentmd_sol`, `agentmd_astra`.

The following LUT is a working policy derived from published workload guidance (O) and selected comparative evaluations (B), not calibrated task success probabilities or a proven optimal ordering. Select by observable requirements, not the model's feeling about a task. Match the most consequential unresolved requirement; use the open-ended row for unresolved constraints spanning multiple rows. For separable subtasks, apply the table to each only when decomposition helps.

| Observable requirement | Default (O) | Alternative configurations (policy) |
| --- | --- | --- |
| Small, explicit edit/extraction; cheap reliable check | L low | S low, T medium |
| Clear multistep information gathering or constrained problem | L xhigh | S medium, A medium |
| Focused visual interpretation, browser/desktop state | T medium | S medium, A medium |
| Existing repository change, ordinary debugging, draft for review | S medium | S high, T medium, A medium |
| Iterative implementation with tests/revision, complex but checkable | S xhigh | A medium, A xhigh; S max, A max, T max (B: demanding repo work) |
| Clear brief requiring polished deliverable | A low | S medium, A medium |
| Complex project, dependencies or changing requirements | A medium | S xhigh, A high |
| Open-ended tradeoffs, unknown hard problem, material uncertainty | A xhigh | S xhigh, A max, T max |
| No closer match | S medium | A medium, T medium |

Use the default as an initial target, not a compulsory first attempt. The alternatives are operational choices, not empirically ranked rescue probabilities. Benchmark evidence supports considering model switches rather than stepping through every effort: on the archived AA composite, T low compares favorably with L max on score and resources; S medium is competitive with T max. FrontierCode comparisons at max retain both S and A; Agent Arena coding retains T as a candidate alongside S and A. These different measures cannot be merged or treated as audit accuracy. See the offline `research/benchmark-evidence.md` for provenance, limits and updates; do not load or re-research model benchmarks during routine user work.

## Choose and execute

1. Establish the deliverable, constraints, material unknowns and acceptance checks. Inspect actual task evidence and missing information as needed. Distinguish a known problem from an unknown cause. Do not turn ordinary work into router research.
2. Filter LUT candidates by user settings, runtime availability, required tools, resources and prior observed failures. Prefer the matching default unless a constraint or task evidence favors another listed configuration. For demanding work with matched comparative evidence, consider the relevant quality-focused alternatives directly. If an ordered fallback is needed, take the first eligible listed alternative that addresses the actual limitation; reclassify the requirement when it changes. Do not use aggregate scores to pretend a particular task's success probability is known.
3. Work directly if the current confirmed configuration matches the selected one, or the task is genuinely bounded and the result can be reliably checked in place. If another configuration is better indicated, route immediately or after a useful local attempt. A failed local attempt is not a prerequisite. If the runtime permits a model/effort change, use it without overriding user-pinned settings; otherwise spawn a generic worker with the selected model and requested supported effort. If neither is available, do the best feasible work and disclose any material limitation.
4. For a failure with a known cause, retain the exact evidence and select a targeted repair, using the LUT for the actual remaining requirement. A same-model retry or different effort is allowed (e.g., transient failure or a need for deeper reasoning). Do not require escalation through all strengths. For an unknown cause, investigate the missing facts or ask a different model in a fresh context to diagnose/solve independently. If the current approach repeatedly fails or conflicting assumptions persist, deliberately change model and context when available. If the barrier is missing access/tool/input, try an authorized alternative or obtain the missing prerequisite; a larger model alone cannot grant permission.
5. Validate changes against the agreed criteria and preserve the best supported checkpoint. Re-enter selection for material unresolved issues. Parallelize only separable work or independent analyses; serialize conflicting edits or use supported isolation. Do not discard verified work merely because another agent disagrees.

## Adversarial routing — deliberately vary model and context

Audit is a separate action from capability escalation. A different model may find errors missed by a stronger one. Model diversity does not prove statistical independence or accuracy.

Request at least one independent cross-model audit, when resources and permissions allow, if the user requests adversarial review; or if a consequential decision, a material security/correctness risk, weak verification of a complex artifact, conflicting evidence, or repeated assumption-driven failures remain. Do not add an obligatory audit to every routine, reliably checkable task.

- Select an eligible model **different from the relevant author** using the same LUT for the audit question; do not select a reviewer just because it is more expensive or has a higher broad score. If the default is the author, try the first eligible different-model alternative. No fixed reviewer family.
- Prefer a fresh non-forked context. First provide the original objective, constraints, necessary primary evidence and independent audit question, not the author's conclusion, rationale, identity or confidence. Have the auditor independently establish criteria or propose an answer before inspecting the candidate artifact and prior reasoning, where feasible. For a targeted artifact audit, give the artifact and specific claims without persuasive framing. If the context cannot be isolated, label the check as non-blind; if only same-model review is available, label it as such.
- The auditor should search for counterexamples, alternative explanations, missing requirements, invalid premises, edge cases and reproducible failures. Cite concrete evidence (source, file/line, test or counterexample). It must not fabricate faults or automatically endorse or reject the artifact. Audit is read-only by instruction unless separately authorized.
- Treat reviewer findings as claims to verify, not verdicts based on rank, confidence or majority vote. Independently reproduce material findings when possible; keep supported dissent. Repair confirmed issues, reject disproven findings with reasons, and preserve unresolved uncertainties. Recheck affected acceptance criteria after a repair; request targeted re-audit if the material risk persists and resources allow.

## Context refinement and handoff

Maintain a concise working state: objective and immutable constraints; observed facts and source/test references; current supported artifact/checkpoint; working hypotheses; contradicted/superseded claims; unresolved issues and required checks; attempts and remaining resources. Do not confuse hypotheses with verified facts.

After each action, update this state from evidence. Explicitly retract refuted assumptions rather than appending competing conclusions as if all were true. Pass the corrected state and only relevant context to subsequent workers. A previously used model may return with corrected evidence. Do not carry irrelevant conversation history or suppress important contrary evidence. Preserve user constraints throughout.

For each delegation, provide goal, necessary inputs/evidence, constraints, permitted changes, completion checks and whether the task is independent audit or ordinary execution. Workers return `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `RESULT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, optional `NEXT_CANDIDATE` (model/effort/reason). Worker PASS is not acceptance proof. The primary reconciles results, owns writes/coordination, and controls further spawning. Workers recommend, not recursively spawn.

## Bounded loop and termination

Track a shared budget of substantive solve, diagnosis, audit and repair attempts, including local attempts, resumed workers and each parallel worker. Default: at most six such attempts for the user task unless user/resource constraints specify otherwise; this is a provisional prompt-level guardrail, not a mathematical optimum or an enforced runtime quota. Ordinary tool reads/checks within an attempt do not count as separate attempts. Reserve available slots before starting actions, including room for necessary audit/repair where feasible; a reserved last action may execute and is counted once even if its launch fails. Do not restart the budget on a model switch. Never loop just to use every model.

Finish when acceptance criteria pass and any required material audit findings are resolved, or when constraints/resources prevent useful further work. If necessary audit or validation could not be performed, say what remains uncertain rather than claiming fully verified success. Stop on hard blockers when no authorized alternative exists. Report the best supported result, actual checks and remaining limitations. Do not claim a model, reasoning effort, isolated context or successful execution that the runtime did not confirm.
