# AgentMD — Evidence-Gated Multi-Model Router

Goal: maximize **independently verified task quality** through OpenAI Codex model/effort selection and bounded cross-model iteration. Cost and latency are secondary tie-breakers. This file is a routing policy, **not a system prompt**, and does not change the parent model.

## Identity and local instructions

- Use only the exact model ID supplied by the runtime, a trusted custom-agent configuration, or an explicit user selection. Never infer your own ID or capability from introspection.
- Read only your own locally installed guidance if available: `models/Luna.md`, `models/Terra.md`, `models/Sol.md`, or `models/Astra.md`, matched by a confirmed model-family suffix. Under a global installation, look in `$CODEX_HOME/models/` (normally `~/.codex/models/`); in this repo, use `models/`.
- If identity or the file is unavailable, proceed without model-specific guidance. Do not guess or download it.
- The benchmark evidence is in `research/benchmark-evidence.md`. **Do not load that report during ordinary work**; only consult it when evaluating/changing routing. Model guidance is a *prior*, never a fixed job assignment.

## Initial selection

The user may start the **primary** Codex session with Luna. Being the primary does not imply that Luna has superior routing judgment.

For each task, establish (1) outcome, (2) constraints, (3) checkable acceptance evidence, (4) available tools and model/effort choices. Then choose one:
- **Direct:** complete locally when the outcome is bounded and verifiable.
- **Delegate:** select a supported model-and-effort pair using observable task requirements plus current evidence. Any family may perform implementation, research, or review. Do **not** reserve a role for any model by name.
- **Independent check:** use a different model/context only when it tests a distinct failure mode or provides meaningful new evidence. Do not send every task through all models.

Treat published model scores and pricing as uncalibrated **initial priors**. They are not task-specific success probabilities. Consider raising effort **or** changing model; never automatically try every effort level or force the sequence Luna -> Terra -> Sol -> Astra.

## Static transition protocol (conditional graph)

All model families are eligible nodes. A transition to any available family (including the current one with a different effort) is allowed **only** for a reason supported by the task state:

1. **PASS / independently verified:** finish; do not continue just to exercise the graph.
2. **FAILED_VALIDATION:** retain the failing test, expected behavior, and relevant files. Decide whether an extra effort setting or a different model/context offers a plausible correction; select one alternative.
3. **UNCERTAIN / high-impact unverified:** obtain an independent check with a distinct hypothesis or verifier, if useful.
4. **BLOCKED by missing data, tools, access, or permission:** stop and explain the blocker. A more powerful model cannot create unavailable access.
5. **NO_NEW_EVIDENCE:** stop or ask the user; do not cycle on unchanged hypotheses.

A worker may **recommend** the next model, effort and reason, but must not launch another worker. The **primary** controls spawning, collects outcomes, and updates the task state. Returning to a previously used model is allowed when there is new evidence, and its existing thread may be reused when appropriate.

For an initial bounded experiment, start with a maximum of **4 delegated worker attempts per user task**, including reruns; never repeat the identical (model, effort, failure evidence) state. This is a **prompt-level safeguard, not a runtime-enforced execution quota**. Respect tighter user or platform limits.

## Delegation contract

Use the available Codex subagent tool and a configured generic `agentmd_luna`, `agentmd_terra`, `agentmd_sol`, or `agentmd_astra` role if supported. The role fixes the model, **not its task or reasoning effort**; explicitly request a compatible effort at spawn when supported. If the runtime cannot set or confirm it, do not claim that it did.

Pass only: `OBJECTIVE`, `CONSTRAINTS`, `RELEVANT_CONTEXT`, `ACCEPTANCE_CHECKS`, `EVIDENCE_SO_FAR`. Prefer independent context for independent review; reuse a worker's existing thread for genuine continuation when available. Do not forward irrelevant conversation history.

Every worker returns `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `EVIDENCE`, `CHANGES`, `NEXT_CANDIDATE` (optional: model/effort/reason), and `OPEN_RISKS`.
Do not confuse the model's claim of success with verified success. If validation is impossible, explicitly report UNCERTAIN.

Follow higher-priority instructions, project instructions, the sandbox and approval controls. Do not force unsupported models or bypass permissions.
