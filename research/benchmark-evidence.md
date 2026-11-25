# AgentMD — Benchmark Evidence Registry

**Snapshot:** 2026-11-24 (JST). **Use:** inform initial routing priors, NOT prove that a prompt or a routing edge is optimal.

Only the current target models are routed: `gpt-6-luna`, `gpt-6.1-terra`, `gpt-6.2-sol`, `gpt-6.2-astra`. Results from prior generations are clearly labeled, never silently substituted. Model availability and names must be verified in the actual Codex client.

## A. Same evaluation framework: Artificial Analysis Intelligence Index v5.0.1

**Source:** [Artificial Analysis — OpenAI models](https://artificialanalysis.ai/providers/openai/) (checked 2026-11-24); [AA Index methodology](https://artificialanalysis.ai/). The index is a composite of **nine** evaluations: AA-Briefcase v1.1, AutomationBench-AA, Terminal-Bench 4.0, FrontierCode-AA 2.0, AA-Omniscience v1.1, GDP.pdf, HLE-Diamond, CritPt v2 hard subset, and Terminal-Bench-Science 0.1.

**Measurements:** composite index (higher better); average USD cost per **AA Index evaluation task** (not API price per token or Codex subscription cost); average minutes per AA Index task. The publication page rounds score and cost in the provider table. We preserve those displayed precisions. HW/clock, batch size, and precise sampling variance per row were not disclosed on that table. Do not interpret 1–2 index points as a statistically verified superiority.

| Exact model | Effort | AA Index v5 | USD / index task | min / index task |
| --- | --- | ---: | ---: | ---: |
| GPT-6 Luna | low | 10 | 0.0051 | 0.6 |
| GPT-6 Luna | medium | 18 | 0.0422 | 3.4 |
| GPT-6 Luna | high | 21 | 0.0729 | 5.4 |
| GPT-6 Luna | xhigh | 23 | 0.10 | 7.0 |
| GPT-6 Luna | max | 28 | 0.15 | 11.5 |
| GPT-6.1 Terra | low | 29 | 0.0713 | 1.1 |
| GPT-6.1 Terra | medium | 38 | 0.17 | 2.7 |
| GPT-6.1 Terra | high | 42 | 0.26 | 4.2 |
| GPT-6.1 Terra | xhigh | 45 | 0.40 | 6.4 |
| GPT-6.1 Terra | max | 51 | 0.96 | 14.4 |
| GPT-6.2 Sol | low | 41 | 0.18 | 1.6 |
| GPT-6.2 Sol | medium | 53 | 0.41 | 3.6 |
| GPT-6.2 Sol | high | 55 | 0.56 | 5.2 |
| GPT-6.2 Sol | xhigh | 56 | 0.65 | 6.3 |
| GPT-6.2 Sol | max | 57 | 1.01 | 10.1 |
| GPT-6.2 Astra | low | 46 | 0.66 | 2.1 |
| GPT-6.2 Astra | medium | 57 | 1.62 | 4.8 |
| GPT-6.2 Astra | high | 60 | 2.07 | 6.5 |
| GPT-6.2 Astra | xhigh | 62 | 2.52 | 8.0 |
| GPT-6.2 Astra | max | 62 | 4.00 | 14.2 |

**Inferences (not verified task-routing decisions):**
- Changing effort sometimes causes a larger observed difference than changing the model; e.g. the index for Luna low versus Luna max differs greatly.
- Cost and quality are not strictly ordered: Sol max and Astra medium both round to **57** on this broad index, but cost and runtime differ.
- These are pooled benchmark results, not calibrated success probabilities for a particular user task. Do not treat a composite score as probability of succeeding, nor do you infer the *conditional* best model for a particular task from this single table.
- For evidence-based delegation, use relevant task evidence and compare eligible model/effort candidates. Failure is not a prerequisite for routing.

## B. Real-repository coding: Cognition FrontierCode 2.0

**Source:** [Cognition FrontierCode leaderboard](https://cognition.com/frontiercode) (retrieved 2026-11-24); [Methodology](https://cognition.com/blog/frontier-code-2.0). **Conditions:** 132 maintainer-written repository tasks; Codex harness for the OpenAI entries below; the listed setting is **max reasoning**; weighted mergeability score, separate pass rate, USD API-equivalent average per rollout; solution-leak checks. HW/clock/batch conditions are not disclosed on the public leaderboard.

| Exact model | Effort | Score | Pass rate | USD / rollout | Output tokens / rollout |
| --- | --- | ---: | ---: | ---: | ---: |
| GPT-6 Luna | max | 22.7% | 25.1% | 0.17 | 79.7k |
| GPT-6 Sol (**older**) | max | 34.9% | 38.3% | 2.35 | 54.2k |
| GPT-6.1 Sol (**older**) | max | 39.6% | 43.0% | 1.03 | 41.5k |
| GPT-6 Astra (**older**) | max | 44.0% | 47.6% | 6.68 | 36.4k |
| GPT-6.2 Sol | max | 43.8% | 48.2% | 1.29 | 38.1k |
| GPT-6.2 Astra | max | 44.2% | 48.2% | 5.97 | 46.0k |

These are useful when the task resembles mergeable coding changes. **Astra–Sol's 0.4-point score difference at max** is small relative to their cost difference, but this is NOT proof that Sol outperforms Astra in a particular hard task. Terra is absent from the cited published leaderboard slice; missing data is not a zero score.

## C. Same-model effort sweep: VulcanBench Frontier v4, GPT-6 Luna

**Source:** [VulcanBench v3.16 report](https://vulcanbench.com/benchmarks/swe-v4-gpt6-luna-v316.html), September 25–28 2026. **Conditions:** 23 specific reimplementation-oriented tasks, Codex CLI **0.155.0**, ChatGPT Pro, **one run per task and effort**, three-hour cap per task; quality grading uses a custom multi-part rubric and external model judges. HW/clock/batch not publicly stated. This is a *specialized third-party test*, not a representative Codex task distribution.

| Effort | Passed / 23 | Timeouts / 23 | Combined score (all timeouts treated as 0) | Mean minutes / task | Reported USD API-equivalent / priced task |
| --- | ---: | ---: | ---: | ---: | ---: |
| low | 0 | 0 | 40.83 | 5.6 | 0.028 |
| medium | 0 | 0 | 45.72 | 3.6 | 0.010 |
| high | 2 | 0 | 57.35 | 15.6 | 0.052 |
| xhigh | 11 | 2 | 71.94 | 52.6 | 0.160 |
| max | 12 | 4 | 67.26 | 60.5 | 0.098 |

**Qualification:** For xhigh/max, reported cost excludes timeout runs whose usage was not captured. Do NOT interpret lower reported cost at max as proof of lower full-run cost. This sweep demonstrates why arbitrary effort fixed values are risky: increased effort can raise the number passed while increasing timeout risk.

## D. Additional published benchmark observations — different versions and methods

The entries below are **separate observations**, not a common leaderboard. We retain comparisons and exact conditions; some results compare a current model to an **older** generation.

| Source / evaluation | Tested models and settings | Published result | Use / caveat |
| --- | --- | --- | --- |
| [OpenAI GPT-6 Sol/Luna release](https://openai.com/index/introducing-gpt-6-sol-and-luna/): DeepSWE 1.1 | GPT-6 Luna max | 66.6% | [Epoch review: Flawed](https://epoch.ai/benchmarks/deepswe/review); not a pass-rate prior for every code task |
| Same: DeepSWE 1.1 | GPT-6 Sol max (**older Sol**) | 68.8% | Cannot attribute to GPT-6.2 Sol |
| Same: AutomationBench 1.0.6 | GPT-6 Sol xhigh (**older**) | 33.2%, USD 0.27/task | 47-tool business workflows; not current Sol |
| Same: AutomationBench 1.0.6 | GPT-6 Astra low (**older**) | 30.3%, 3.9× older Sol xhigh task cost | Reasoning settings differ; do not infer global ordering |
| Same: Agents' Last Exam | GPT-6 Sol max (**older**) | 56.4% | Not the current GPT-6.2 Sol |
| Same: AutomationBench | GPT-6 Luna high vs GPT-5.6 Luna | +5.4 percentage points; 58% less per task | Relative prior-generation improvement; absolute score unspecified |
| [OpenAI GPT-6.1 Terra](https://openai.com/index/introducing-gpt-6-1-terra/): Terminal-Bench 4.0 | GPT-6.1 Terra max | 50.3% | [Epoch audit: Flawed](https://epoch.ai/data/benchmark-reviews-documentation/included-benchmarks); public vendor-reported |
| Same: Terminal-Bench 4.0 | GPT-5.6 Terra (**older**) | 21.5% | Historical comparison; not paired conditions |
| Same: difficult factual prompts | GPT-6.1 Terra low | 16.7% error rate | Internal, selected error-inducing prompts; lower better |
| Same: difficult factual prompts | GPT-6.1 Terra max | 4.3% error rate | Internal; cannot generalize to normal user tasks |
| Same: Agents' Last Exam | GPT-6.1 Terra medium vs GPT-5.6 Terra | +15 percentage points, about one-third the cost | Relative comparison, no absolute figure in prose |
| [OpenAI GPT-6.2 Astra/Sol](https://openai.com/index/introducing-gpt-6-2-astra-sol/): Agents' Last Exam | GPT-6.2 Astra vs GPT-6 Astra (**older**) | +5.2 points; less than 1/3 cost | Exact effort details not stated in release prose |
| Same: Terminal-Bench-Science 0.1 | GPT-6.2 Astra vs GPT-6 Astra (**older**) | +9 points; less than 1/3 cost | Science workflow benchmark, not general code |
| Same: GDPval v2 | GPT-6.2 Astra vs GPT-6 Astra (**older**) | +6.2 points; 22% fewer output tokens | Long-horizon knowledge work |
| Same: GDPval v2 | GPT-6.2 Sol vs GPT-6.1 Sol (**older**) | +5.3 points | Long-horizon knowledge work |
| Same: AA-AnalystAgent | GPT-6.2 Astra | 62.5% correct on **all 5 independent attempts** | Strict multi-try criterion, not the usual pass@1 |
| Same: FrontierCode 2.0 | GPT-6.2 Sol max vs Astra max | Within 0.5 points, around 1/5 cost | See first-party Cognition results in section B |

### Benchmark audit and evidence quality

- [Epoch AI: DeepSWE v1.1 review](https://epoch.ai/benchmarks/deepswe/review): **Flawed**; at least 23/113 tasks had issues in the audit.
- [Epoch AI: SWE-bench Verified review](https://epoch.ai/benchmarks/swe-bench-verified/review): **Flawed**; contamination and incorrect rejection of functional patches.
- [Epoch AI benchmark reviews](https://epoch.ai/data/benchmark-reviews-documentation/included-benchmarks): Terminal-Bench 4.0 and OSWorld 2.1 were also marked **Flawed**. Treat numbers on these suites as diagnostic context, not decisive routing rules.
- [OpenAI model selection](https://developers.openai.com/api/docs/guides/model-selection): the provider's workload fit categories are useful **priors**, not evidence that a model can introspect its own accuracy or that its `AGENTS.md` prompt improves it.

## E. Price reference (not an outcome benchmark)

**USD per 1,000,000 tokens; Standard API**, current references [OpenAI models](https://developers.openai.com/api/docs/models) and [pricing](https://developers.openai.com/api/docs/pricing), checked 2026-11-24. Cost within Codex plans is NOT given by this table.

| Model ID | Input | Cached-input READ | Output |
| --- | ---: | ---: | ---: |
| `gpt-6-luna` | 0.10 | 0.01 | 0.50 |
| `gpt-6.1-terra` | 1.00 | 0.05 | 5.00 |
| `gpt-6.2-sol` | 2.00 | 0.10 | 10.00 |
| `gpt-6.2-astra` | 8.00 | 0.40 | 40.00 |

The [OpenAI caching guide](https://developers.openai.com/api/docs/guides/prompt-caching) distinguishes cache reads from writes (standard GPT-5.6+ write is 1.25× ordinary input for the default 30-minute lifetime), and explains that the cache reuses an identical prefix, not a Markdown document by filename. A model switch is not evidence of cache reuse; measure cached input tokens in the actual runtime.

## F. Evidence-to-routing policy (what these benchmarks DO and DO NOT justify)

**Supported as initial priors:**
1. For a tiny well-bounded task, Luna at the current setting is an admissible first attempt; do not exclude higher-effort Luna when quality demands it.
2. For high-impact or difficult requests, compare alternatives at *both model and effort level*; do not equate Astra low with Astra max or Luna high with Luna max.
3. A specialist's second opinion or cross-model verification is useful only if it can test a different failure mode or produce new evidence.
4. A failed attempt with clear test evidence may trigger a higher-effort rerun or a different model. Missing permissions / broken tools are not repaired merely by using a more powerful model.
5. A validated success can end the loop. There is no rule that all four model families must be visited.

**Not supported by these results:** a fixed hierarchy of model roles; monotonic improvement of a particular task with effort; a calibrated posterior for each task class; a guarantee that the model accurately assesses itself; a guarantee that multi-agent loops outperform the best single agent.

## G. Next experiment to validate the static graph

- **H:** An evidence-based, bounded routing graph increases independently validated completion compared with Luna-only and strongest-single-model baselines.
- **T:** A balanced task set spanning small edits, debugging, multi-step implementation, visual inspection, and independent review; record task IDs, Git revisions, model IDs, exact effort, prompts, tool/sandbox configuration, cached and total tokens, stop reason, validation result, and wall-clock time. Pilot at least 5 tasks per stratum; expand until uncertainty is acceptably small. A pilot is not a statistically powered proof.
- **D:** PASS only if the proposed workflow improves the chosen objective under matched conditions without new critical failures; FAIL for false-success declarations, wrong model/effort, unbounded loops or independently verified regressions; UNCERTAIN for missing tool/model/ground-truth evidence.
- **C:** Differences may be caused by Codex harness, effort, environment, variance, benchmark bias, or judge error rather than model choice.
- **U:** Main uncertainty sources are task distribution, sampling, verifier reliability, non-deterministic outputs, cache state, and wall-clock load. Estimate combined uncertainty and confidence intervals after data are collected; do not invent them now.

**Provenance policy:** If numbers or model names change, update this file with the checked date and evidence link before updating short runtime guidance. No unverified number belongs in a model's operating prompt.

## H. Runtime policy update — 2026-11-25

The single AGENTS.md uses these source classes:

- **O — workload guidance, not an optimum:** [OpenAI model selection](https://developers.openai.com/api/docs/guides/model-selection), retrieved 2026-11-25. It presents L low for small edits/extraction, L xhigh for clearly constrained multi-step problems, T medium for visual/desktop work, S medium for repo changes/drafts, S xhigh for iterative work, A low for polished work from a brief, A medium for complex projects, and A xhigh for open-ended tradeoffs. The alternative ordering is a policy design choice, not an empirical conditional ranking. The default six substantive attempts is an adjustable guardrail, not an optimized parameter.
- **B — composite (historical and rechecked):** Section A retains its dated v5.0.1 snapshot, rather than silently mixing versions. On the 2026-11-25 [AA provider page](https://artificialanalysis.ai/providers/openai), standard rows displayed L max 28 / $0.15 / 10.6 min, T low 29 / $0.0713 / 1.1 min, T max 51 / $0.96 / 14.0 min, S medium 52 / $0.41 / 3.5 min. Some values have changed since A. They are rounded composite index and average USD/min per index task, not calibrated probabilities, audited statistical differences, or Codex-plan costs. No HW, clock or batch conditions confirmed.
- **B — coding:** Section B preserves the recorded FrontierCode 2.0 snapshot (max effort only). On the [Agent Arena coding index](https://arena.ai/leaderboard/agent/code?projection=output-tokens), dated 2026-11-22, A max, T max and S max appeared at ranks 6, 9 and 11 among 69 models (1,064,228 sessions in aggregate, not per model). The index includes multiple signals of agent work. This is a different measure from mergeability or a pass rate; no inference of statistical superiority or conditional rescue performance is made. Keep these alternatives eligible; do not generalize max results to lower effort settings.
- **Feasibility:** [OpenAI deployment checklist](https://developers.openai.com/api/docs/guides/deployment-checklist) lists low/medium/high/xhigh/max for the four API models; none is also supported by Luna and Terra. [Codex subagents](https://developers.openai.com/codex/subagents) describes model/effort settings, pinned configuration precedence and spawning. API support is not proof of availability in any user's Codex client. No runtime invocation is asserted here.

### Independent adversarial audit

- Du et al., *Improving Factuality and Reasoning in Language Models through Multiagent Debate*, ICML 2024 ([paper and code](https://composable-models.github.io/llm_debate/), [arXiv:2305.14325](https://arxiv.org/abs/2305.14325)): reports gains from multiple reasoning and critique paths on evaluated tasks.
- Zhang et al., *If Multi-Agent Debate is the Answer, What is the Question?*, [arXiv:2502.08788](https://arxiv.org/abs/2502.08788): finds that debate did not consistently beat simpler baselines and reports benefits from heterogeneous model outputs in tested settings.
- Batra et al., *Who Convinced Whom? Tracing How LLMs Change Their Minds in Multi-Agent Systems*, [arXiv:2610.35930](https://arxiv.org/abs/2610.35930) (preprint): reports cases where increased agreement accompanies more shared errors.

These are method-level motivations, not measured audit efficacy for the AgentMD model combinations. Prefer independent initial analysis and verifiable counterexamples over repeated persuasive debate; update context only by evidence, not consensus. Distinct model families and fresh contexts do not establish independence. The actual conditional rescue rates, false-audit rates, shared failure correlations, and best sequence remain unknown.
