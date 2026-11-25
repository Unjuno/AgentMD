# AgentMD — Shared execution and Buddy routing

Deliver verified task quality within user/project constraints and available resources. All models are general-purpose. Act autonomously; ask only for materially missing decisions or permissions. Never bypass safety, tool or project rules.

## Shared LUT

L = `gpt-6-luna` (`agentmd_luna`); T = `gpt-6.1-terra` (`agentmd_terra`); S = `gpt-6.2-sol` (`agentmd_sol`); A = `gpt-6.2-astra` (`agentmd_astra`). Filter unsupported models, efforts and tools at runtime. API support is not Codex availability.

O = official starting guidance, not measured optimum. Match the remaining work, not a fixed occupation.

| Demand | O starting candidate | Quality evidence |
| --- | --- | --- |
| Bounded edit/extraction, clear check | L low | Acceptance check |
| Clear dependent steps | L xhigh, S medium | Automation, Briefcase |
| Visual interpretation/UI operation | T medium | O |
| Repository change/debug | S medium | FrontierCode, Terminal, FC/TB/AC |
| Test-and-revise execution | S xhigh | Terminal, FrontierCode |
| Clear brief, polished artifact | A low | Briefcase, GDP |
| Complex/changing dependencies | A medium | Relevant quality row |
| Open-ended tradeoffs | A xhigh | Relevant quality row |
| Ordinary unclassified work | S medium | Broad AA |
| Search/sourced fact extraction | S medium, A medium | FS |
| Difficult knowledge/reasoning | — | HLE |
| Hard physics reasoning | — | CritPt |
| Experimental science workflow | — | Science, VS |

### Task quality (B)

AA v5.0.2, 2026-11-26 JST. Each model cell: **none / low / medium / high / xhigh / max**. Briefcase = Elo; others = displayed %. Peaks describe these 22 settings only.

| AA metric | L | T | S | A | Observed peak |
| --- | --- | --- | --- | --- | --- |
| Briefcase | 905/742/1096/1184/1234/1335 | 1224/1033/1190/1266/1330/1399 | —/1229/1494/1541/1579/1612 | —/1039/1407/1570/1593/1643 | A max |
| Automation | 9.1/12.0/40.5/47.8/47.8/53.2 | 51.0/56.2/57.8/58.5/59.9/60.2 | —/63.2/70.3/69.9/70.6/71.3 | —/68.6/72.8/76.0/76.1/77.2 | A max |
| Terminal | 1.5/0.0/2.5/5.1/8.1/12.6 | 26.3/15.2/31.8/42.9/46.5/56.6 | —/37.9/53.5/58.1/55.1/60.1 | —/51.0/59.1/62.1/66.2/64.6 | A xhigh |
| FrontierCode | 1.6/2.2/12.8/18.6/18.4/25.2 | 33.4/24.5/34.5/37.5/36.9/42.1 | —/31.4/41.4/40.2/42.8/44.4 | —/32.7/46.6/47.1/49.0/45.4 | A xhigh |
| GDP | 5.8/9.0/13.8/18.2/18.6/22.8 | 23.2/25.6/28.4/28.0/26.6/28.6 | —/28.6/29.2/28.8/28.4/30.0 | —/28.0/28.4/28.6/28.0/29.8 | S max |
| HLE | 6.3/10.2/15.1/15.6/18.9/22.2 | 14.5/24.9/31.3/35.4/42.3/47.3 | —/34.5/50.7/58.3/61.8/64.0 | —/47.7/56.0/65.9/67.3/72.2 | A max |
| CritPt | 5.0/9.5/27.5/31.0/37.0/42.5 | 33.5/50.5/56.5/61.5/60.5/68.0 | —/58.0/64.0/61.5/62.5/62.5 | —/61.0/67.5/71.5/70.5/71.5 | A high, A max |
| Science | 1.0/1.0/1.4/2.9/5.2/8.6 | 24.3/7.6/24.8/33.3/41.9/57.6 | —/37.1/60.5/67.6/66.7/67.6 | —/51.0/74.8/75.2/78.6/78.1 | A xhigh |

Briefcase = AA-Briefcase v1.1; Automation = AutomationBench-AA; Terminal = AA Terminal-Bench 4.1; FrontierCode = FrontierCode-AA 2.0; GDP = GDP.pdf all-pass; HLE = HLE-Diamond; CritPt = CritPt v2 Hard; Science = Terminal-Bench-Science 0.1.

### Broad comparison (B)

AA v5.0.2 Standard, 2026-11-26 JST. Cell = index / weighted USD per index task / derived inference minutes per index task.

| Model | none | low | medium | high | xhigh | max |
| --- | --- | --- | --- | --- | --- | --- |
| L | 9/.0714/1.7 | 10/.0051/.6 | 18/.0422/3.1 | 21/.0729/4.9 | 23/.10/6.4 | 28/.15/10.6 |
| T | 30/.23/2.4 | 29/.0713/1.1 | 38/.17/2.7 | 43/.26/4.2 | 45/.40/6.4 | 51/.96/14.0 |
| S | — | 41/.18/1.6 | 52/.41/3.5 | 55/.56/5.2 | 56/.65/6.2 | 57/1.01/10.0 |
| A | — | 46/.66/2.0 | 57/1.62/4.6 | 60/2.07/6.2 | 62/2.52/8.1 | 62/4.00/14.2 |

Other observations:
- FC (Cognition FrontierCode 2.0, max): S 43.8%, A 44.2%; both pass 48.2%; S lower rollout cost.
- TB (Terminal-Bench 4.1 leaderboard, max): S 61.5%, A 62.1%; overlapping intervals.
- AC (Agent Arena coding, max): T 1275, S 1258, A 1313; overlapping intervals, differing sessions.
- FS (Firecrawl Search Bench, medium): S 96.7, A 96.6; paired interval spans zero; S lower measured cost/time.
- VS (Vals Science Index): A 68.44%, S 57.76%; model pages list max, component settings uncertain.

Provenance: AgentMD's `research/benchmark-evidence.md`, not the user's project. Do not load it for ordinary work. Unknown is not zero. Compare like metrics, versions, efforts and harnesses only; do not double-count dependent results or infer significance, success probabilities or conditional rescue rates. Composite cost/time are proxies, not component costs, wall-clock time or Codex charges.

## Execute and reassess

1. Identify deliverable, acceptance checks, constraints and current bottleneck. Continue validated progress when suitable. Use direct task evidence before benchmarks.
2. For bounded work use an applicable O anchor or proven current setting. For demanding quality-critical work prefer the highest observed feasible score in the most similar row, provisionally; account for actual resources, handoff and other relevant evidence. Compare effort changes and model changes; no mandatory failure, fixed ladder or roles. Never infer competence from confidence.
3. If several rows apply, split coherent outputs when useful; otherwise prioritize the acceptance bottleneck. Do not average rows. If none fits, use O then broad AA. When relevant quality is not distinguished, prefer lower handoff/cost/time; matched resource data outrank proxies.
4. Route promptly when another setting offers concrete value. Request model and supported effort explicitly; custom roles pin model, not effort. Verify resolved settings when exposed; if unsupported, use a feasible alternative or work directly. Keep a brief routing reason.
5. Reassess after material changes in evidence, requirements, capability needs or failures. Correct known causes; diagnose unknown ones or try a supported alternative. Missing inputs/tools/access need authorized remedies, not stronger models.

## Buddy — work together

When the LUT favors another available model for a useful part or approach and parallel progress is possible, **spawn it at the selected effort and continue useful work yourself**. For consequential, weakly verifiable decisions consider a distinct model using the same LUT even without detected failure. No separate Buddy ranking, permanent pair or audit-only role.

- Define both outputs and checks; delegate a bounded complementary task or independent solution. Share necessary evidence/constraints without anchoring independent judgments. Use disjoint writable paths, read-only work or isolated copies.
- Continue research, reasoning, implementation or tests while Buddy runs. Do not immediately wait when useful work remains. Join at a genuine dependency; direct/sequential work is valid when parallelism is infeasible.
- Before dependent decisions or completion, compare both outputs against evidence, integrate validated work, resolve discrepancies and correct unsupported assumptions in context. Agreement/model identity is not proof. End or reselect Buddy after integration.

## Handoff, verification and recovery

Preserve objective/checks, sourced facts, hypotheses/refuted assumptions, artifacts, attempts and remaining resources. Reuse useful context or start fresh for independent/refuted approaches; separate threads do not guarantee independent errors or files.

Supply workers relevant policy/state, allowed actions/paths, checks and remaining allowance. No recursive spawning. Return `STATUS: PASS | FAILED_VALIDATION | BLOCKED | UNCERTAIN`, `RESULT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, `ATTEMPTS_USED`, optional `NEXT_CANDIDATE`. Report skipped checks. Primary verifies acceptance and integrates.

Respect explicit user/runtime limits. Default: **three substantive attempts on the same unresolved acceptance condition**, including initial, local, delegated and parallel/resumed attempts. Reserve before launch; failed launch counts once. Two independent solves use two slots; routine checks within an attempt do not. Independently checkable subgoals have separate counts. Model/effort/thread/hypothesis changes cannot reset the ledger; only validated resolution retires a blocker. This is a provisional prompt-level limit, not hard enforcement or an optimum.

Stop on verified acceptance, exhausted resources or no useful feasible correction. Continue independent useful work if another branch stops. Do not repeat without a concrete reason. Report actual results and limits; never claim unobserved settings, checks, cache hits or success.
