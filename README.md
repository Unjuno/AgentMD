# AgentMD

One shared `AGENTS.md` for OpenAI Codex: **task-aware escalation using model × reasoning effort, with selective Buddy collaboration**. Public benchmarks supply bounded evidence; the current task, acceptance checks and incremental resources determine the next action. All four models remain general-purpose.

## Strategy and logical baseline

The objective is to complete the user's actual task at its required quality within applicable constraints. Preserve useful progress. Spend on a different configuration or an additional agent when a concrete contribution justifies the transfer, execution, checking and integration work. Neither balanced model use, a larger model nor more reasoning is an objective in itself.

The **logical baseline** is one current configuration completing the same task with the same tools, permissions and acceptance checks, without an unnecessary extra agent. This is a comparison rule, not a measured experiment and not a requirement to make the cheapest model fail first. A known capability gap can justify immediate delegation.

| Decision input | Meaning | Unit | Definition / limits | Type |
| --- | --- | --- | --- | --- |
| Acceptance | What the deliverable must satisfy | Not a physical quantity | User requirements and task-grounded checks; retain material unknowns | Conditions / observations |
| Configuration | Available model and reasoning effort | Not a physical quantity | Exact runtime-supported settings and tools | Categorical pair |
| Remaining resources | Cost and elapsed time of the next action through integration | USD, s, or explicitly labeled unavailable | Include current work, workers, transfer, tools, checks and rework; do not add USD to seconds | Separate nonnegative estimates |
| State | Work already done and what remains unresolved | Not a physical quantity | Artifact identity, sources, assumptions, checks and active workers | Structured record |
| Recovery allowance | Additional recovery or duplicate solving that may start | 1 (count) | A finite task-scoped design guard, reserved centrally; not a monetary budget | Nonnegative integer |

Choose using explicit quality requirements, permissions, budget, deadline and user priorities. If two actions trade cheaper cost for longer latency, there is no unique optimum without an applicable preference. Keep an adequate progressing configuration in an unresolved comparison. If it is inadequate, take a defensible bounded next step and check its output. Preserve usable context; switching back to a nominally cheaper model is justified only when future savings exceed transfer/integration overhead.

## What the evidence can establish

The shared textual LUT now preserves **all 176 AA component values across all 22 measured model/effort configurations**, with separate historical broad resource references. It does not prefilter configurations using mixed-scope Pareto membership. Every candidate remains subject to actual runtime support, task fit and constraints.

A score is an observation under an evaluation's conditions. It is not a probability that the model will solve the current task, rescue a previous failure or detect its own error. Provider workload examples are starting guidance, not permanent occupations. Effort and model selection must be considered together; there is no mandatory family cycle or effort ladder.

**Why benchmark averages cannot determine a unique escalation graph:** consider 100 equally weighted hypothetical tasks and two models, X and Y.

| Hypothetical world | Both succeed | X only | Y only | Neither | X succeeds | Y succeeds | Y solves tasks X failed |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| Shared failures | 70 | 10 | 0 | 20 | 80 | 70 | 0 of 20 |
| Complementary coverage | 50 | 30 | 20 | 0 | 80 | 70 | 20 of 20 |

Both worlds have the same single-model averages. The benefit of invoking Y after X fails is different. Therefore averages alone do not identify rescue value, the best sequence or the best Buddy. These numbers are a constructive example, not measurements of Luna, Terra, Sol or Astra. Alternating models blindly also does not ensure improvement.

The same limitation applies to resources: an aggregate cost from one task population cannot establish cost dominance for another task. Earlier proxy-frontier calculations remain in the evidence archive as **superseded derivations**, not active routing rules. Full proof assumptions, counterexamples and review outcomes are recorded in the [logical baseline and audit](research/benchmark-evidence.md#j-logical-baseline-and-repeated-audit-d).

## Execution rules

| Situation | Required response |
| --- | --- |
| Current approach is suitable and progressing | Continue and perform proportionate acceptance checks |
| A known correctable cause | Correct that cause; do not upgrade merely because a check failed |
| Unknown cause or missing facts | Diagnose or retrieve relevant evidence; do not blindly repeat a solve |
| Missing model, tool, input or authorization | Use an authorized feasible remedy; a model change cannot create permission |
| Capability gap or valuable additional contribution | Compare current execution, effort, model and Buddy using the same LUT |
| Useful parallel contributions justify their overhead | Spawn Buddy and keep doing defined useful primary work |
| Parallel work is unsafe or has no useful parent contribution | Work directly or delegate sequentially |
| Results agree but an essential condition is unverified | Preserve uncertainty; agreement is not acceptance |
| Changed artifact invalidates a prior check | Check the affected integrated result before claiming acceptance |
| Acceptance established or further recovery disallowed | Deliver evidence and remaining limits; continue independent eligible work |

### Buddy means working together

Define each agent's result, baseline artifact/revision, acceptance checks and ownership. The Buddy need not outrank the primary. It may implement, investigate, reason or check. Independent analysis can be useful at a consequential decision before failure, but a different model by itself does not justify an extra call.

The primary works while the Buddy runs, unless a real dependency prevents useful safe progress. Coordinate shared mutable state as well as file paths; tests and generated artifacts can interfere even when source paths differ. Join relevant results, integrate by evidence and check the **actual integrated artifact**. Safely cancel or discard obsolete results and account for any already-applied edits. Before final verification, confirm that any worker capable of modifying the delivered artifact has stopped writing, or isolate its remaining writes. A cancellation request alone is not confirmation. Do not manufacture busywork or wait for an irrelevant worker.

Workers do not recursively spawn. The primary owns orchestration, resource reservations and final acceptance. Fresh context is not proof of independent errors, and read-only instructions are not an enforced sandbox.

### Recovery and stopping

Before the first recovery or duplicate solve, the primary records a **finite task-scoped recovery allowance** based on declared scope, consequences and available resources. There is no fixed universal three-attempt rule. An allowance is a disclosed operational choice; it is not inferred from benchmark scores and is not claimed optimal.

Count additional local, delegated and parallel recovery/duplicate attempts once, reserving before launch. A parent already doing its initial solve plus one duplicate Buddy consumes one additional slot; two new recovery solves consume two. Ordinary first-pass work on genuinely separate requirements and necessary non-repeated checks do not use recovery slots. Renaming an unresolved requirement, changing models, starting a new thread or inventing another hypothesis does not reset the task ledger.

The parent explicitly authorizes first-pass scope and marks assigned solves INITIAL or RECOVERY/DUPLICATE. An attempt is one stated approach through its acceptance checkpoint. A new correction after a failed checkpoint or a replacement approach starts a new attempt; routine tool actions do not. Workers report classified starts so initial work cannot be double-charged or unauthorized local recovery hidden.

Before retrying failed setup, declare a finite task-scoped setup-retry allowance. Use observed history to classify first setup, retry or continuation; an allocated allowance does not prove an attempt occurred. Mark unknown usage UNKNOWN, and reconcile before relying on remaining capacity. Initial setup is not a retry; record failures and resources. A retry consumes its reserved slot at dispatch. Track every worker dispatch, including INITIAL, with scope and any available handle. An ambiguous reply retains ownership and any reservation: do not redispatch the assignment or begin conflicting replacement work before reconciling it and confirming safe replacement. Release a solving reservation only after confirming the dispatch never started and cannot later start. A started solve remains consumed after interruption. Log explicit user scope/budget revisions instead of silently replenishing allowances.

At exhaustion, stop counted recovery, preserve results, continue eligible independent work and disclose unresolved requirements. **A finite guard can stop useful work before completion.** It bounds counted actions if followed; it does not prove completion or bound all elapsed time, spend or ordinary work. Hard budgets require exposed runtime controls and usage data. No repeated searches or checks without new relevant evidence or a changed action.

### Acceptance and worker status

`PASS` means the stated acceptance conditions have evidence from checks actually performed on the identified result. `FAILED_VALIDATION` records a failed required check, `BLOCKED` an external obstacle, and `UNCERTAIN` missing or inconclusive essential verification. Report every applicable condition and skipped check; one summary label cannot erase another failure. The primary checks evidence and scope rather than trusting a label.

## The eight files

| File | Purpose |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Shared runtime policy, complete textual evidence LUT, escalation, Buddy and stopping rules |
| [.codex/agents/agentmd_luna.toml](.codex/agents/agentmd_luna.toml) | `gpt-6-luna` binding |
| [.codex/agents/agentmd_terra.toml](.codex/agents/agentmd_terra.toml) | `gpt-6.1-terra` binding |
| [.codex/agents/agentmd_sol.toml](.codex/agents/agentmd_sol.toml) | `gpt-6.2-sol` binding |
| [.codex/agents/agentmd_astra.toml](.codex/agents/agentmd_astra.toml) | `gpt-6.2-astra` binding |
| [research/benchmark-evidence.md](research/benchmark-evidence.md) | Dated evidence and limitations; offline maintenance reference |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Rules for maintaining the policy and evidence |
| [README.md](README.md) | Installation and explanation |

The four TOMLs share a short worker contract and leave effort unfixed. There are no model-specific Markdown policies. README, CONTRIBUTING and the evidence archive are not routine runtime reading requirements; the operational textual LUT is in AGENTS.md.

## Install and update

Use a local Codex client that supports standalone custom-agent TOMLs and the selected models. From the repository checkout, this POSIX-shell snippet performs a **first installation**. It stops if existing guidance or same-named agents would conflict, and it does not rewrite `CODEX_HOME`:

```sh
(
    set -euC
    agentmd_target="${CODEX_HOME:-$HOME/.codex}"

    for agentmd_rel in \
        AGENTS.override.md \
        AGENTS.md \
        agents/agentmd_luna.toml \
        agents/agentmd_terra.toml \
        agents/agentmd_sol.toml \
        agents/agentmd_astra.toml
    do
        if [ -e "$agentmd_target/$agentmd_rel" ] ||
           [ -L "$agentmd_target/$agentmd_rel" ]; then
            printf 'Existing guidance: %s\nBack up and merge before installing.\n' \
                "$agentmd_target/$agentmd_rel" >&2
            exit 1
        fi
    done

    test -f AGENTS.md
    for agentmd_family in luna terra sol astra; do
        test -f ".codex/agents/agentmd_$agentmd_family.toml"
    done

    mkdir -p "$agentmd_target/agents"
    cat AGENTS.md > "$agentmd_target/AGENTS.md"
    for agentmd_family in luna terra sol astra; do
        cat ".codex/agents/agentmd_$agentmd_family.toml" \
            > "$agentmd_target/agents/agentmd_$agentmd_family.toml"
    done
)
```

For an existing installation, save a backup of the affected files, compare them with this revision and merge the routing policy with your existing preferences. Preserve unrelated agent definitions and project rules. Review an existing `AGENTS.override.md` before deciding which guidance should be active; do not delete it merely to make installation pass. Keep a rollback copy. Restart Codex after installing or merging.

Start with a model available to your account, for example `codex --model gpt-6-luna`. Starting with Luna does not require it to attempt every work unit first.

## Loading and runtime settings

[Codex discovers guidance at startup](https://learn.chatgpt.com/docs/agent-configuration/agents-md): global instructions, then project-root-to-current-directory instructions. An applicable `AGENTS.override.md` takes precedence at its level; nearer project instructions take precedence over earlier guidance. The default combined limit is 32 KiB. Leave room for project instructions, and check loaded sources when the client exposes them.

[Custom agents](https://learn.chatgpt.com/docs/agent-configuration/subagents) live under the Codex home `agents/` directory or project `.codex/agents/`. Their configured model and effort take precedence over spawn settings. These files set only the model, preserving the effort already resolved from the spawn request, defaults or parent. Request the intended supported effort explicitly and check the resolved configuration. Model availability can differ between clients. The API catalog lists none for Luna and Terra, but not Sol and Astra; none is eligible only when supported by the actual Codex runtime.

Markdown does not grant tools, enforce budgets or change the parent model by itself. CLI users can choose an active model and supported effort with [`/model`, then inspect `/status`](https://learn.chatgpt.com/docs/developer-commands?surface=cli). Delegate when useful and supported; otherwise complete the best feasible work directly. Separate agent context does not guarantee separate writable files. Workers inherit the parent's permissions, so changing agents cannot bypass a blocker.

## Evidence and validation status

Evidence classes are published observations (B), provider guidance (O), design choices (D), and unknowns. The [registry](research/benchmark-evidence.md) preserves source versions, dates, settings, units, published protocols and missing run metadata. AA resource values are historical weighted costs and derived inference times, not live prices or task-specific cost/latency. Normal work does not trigger benchmark collection.

This revision removes unsupported candidate pruning, clarifies the logical baseline, separates recovery from setup failures, and strengthens artifact-aware integration and status semantics. Repeated audits seek counterexamples and regressions; they cannot prove the absence of all defects. Static checks, observed runtime behavior and measured outcome gains are separate claims. No model-performance improvement or actual Codex execution is claimed by editing these files.

The relevant disciplines are decision theory (objective and tradeoffs), statistics (marginal versus conditional evidence), and distributed systems (reservations, mutable state and integration). Their practical role here is to make decisions and evidence traceable, without adding a service, separate policy per model or a compulsory experiment.

Unofficial community project.
