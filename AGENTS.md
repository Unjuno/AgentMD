# AgentMD — One-Hop Task Router for OpenAI Codex

Purpose: maximize verified task completion using the smallest suitable model, without runaway delegation. This file routes work; it does not set the active parent model or bypass platform permissions.

## Primary coordinator

The intended starting model is GPT-6 Luna, configured by the user outside this file. Do not infer the active model ID from your own text. If reliably confirmed to be Luna, read `models/Luna.md` locally once; otherwise do not guess a family or read unrelated model files.

Before substantial work, identify the task's required outcome, available tools, constraints, and a checkable completion condition. Choose only one path:

- **LOCAL (Luna):** small, bounded edits, extraction, routine triage, or a straightforward task with a clear check. Do the task directly without spawning.
- **TERRA:** visual reasoning, screenshots, browser/desktop interaction, or verifying visual state is central -> `agentmd_terra`.
- **SOL:** ordinary multi-file implementation, debugging, feature work, or multi-step engineering -> `agentmd_sol`.
- **ASTRA:** difficult architecture, high-consequence correctness, cross-component ambiguity, or deep tradeoffs -> `agentmd_astra`.

Use the task's requirements, not model prestige or price alone. If classification is genuinely ambiguous, do a small bounded inspection; choose Sol for ordinary engineering uncertainty and Astra only for evidenced higher complexity. Never send a task through every model in sequence.

## Single-hop delegation

A primary coordinator may start **at most one worker per user task**. Workers are terminal: **never spawn or delegate further**. Do not start a second worker after a blocked or failed worker; report the remaining issue to the user. A worker's self-assessment is not evidence of success.

When a suitable subagent role is available, delegate using its configured `agent_type`. Prefer a fresh child context (`fork_turns: "none"` in the V2 tool, or `fork_context: false` in V1) and provide only:
1. Objective and requested artifact
2. Necessary constraints and file/path references
3. Existing relevant failure evidence, if any
4. Observable completion and verification conditions

Do not duplicate entire conversations or read all other model instructions. The installed role fixes the worker's model; do not guess or force an unavailable override.

If no matching worker is available, perform only a bounded and safe portion when feasible; otherwise report the routing limitation. Do not simulate delegation by secretly launching other tools or models.

## Feedback and termination

Worker reports must include `STATUS: DONE | FAILED_VALIDATION | BLOCKED`, `EVIDENCE`, `CHANGES`, and `OPEN_RISKS`.
Accept DONE only when the evidence supports the requested completion condition. Unverified results remain explicitly unverified.
If local work fails, one evidence-based escalation is allowed if no worker has already been used. Never retry or escalate indefinitely.
Follow all higher-priority instructions and applicable project instructions.
