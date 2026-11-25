# AgentMD — Active evidence registry

**Checked:** 2026-11-26 JST. This is an offline maintenance reference, not routine agent context. Earlier snapshots and superseded policies remain in Git history. No new model-performance experiment was run for this revision.

| Alias | Exact model ID |
| --- | --- |
| L | `gpt-6-luna` |
| T | `gpt-6.1-terra` |
| S | `gpt-6.2-sol` |
| A | `gpt-6.2-astra` |

**Evidence classes:** B = published benchmark observation; O = provider workload guidance; D = AgentMD design choice; UNKNOWN = not established by the checked sources. A published model name is not proof of availability in the user's Codex client.

## A. AA — Broad comparison: Intelligence Index v5.0.2 (B)

[Provider table](https://artificialanalysis.ai/providers/openai/), checked above; Standard only. Cells: **index / weighted USD per evaluation task / estimated minutes per evaluation task**.

| Model | low | medium | high | xhigh | max |
| --- | --- | --- | --- | --- | --- |
| L | 10/.0051/.6 | 18/.0422/3.1 | 21/.0729/4.9 | 23/.10/6.4 | 28/.15/10.6 |
| T | 29/.0713/1.1 | 38/.17/2.7 | 43/.26/4.2 | 45/.40/6.4 | 51/.96/14.0 |
| S | 41/.18/1.6 | 52/.41/3.5 | 55/.56/5.2 | 56/.65/6.2 | 57/1.01/10.0 |
| A | 46/.66/2.0 | 57/1.62/4.6 | 60/2.07/6.2 | 62/2.52/8.1 | 62/4.00/14.2 |

Time derives from output tokens and speed (rolling five days), not task wall-clock duration. Rounded values lack row uncertainty and HW/clock/batch details; costs are not Codex-plan charges.

[Methodology](https://artificialanalysis.ai/methodology/intelligence-benchmarking): nine evaluations span knowledge work, coding, science and general knowledge. The suite is primarily text-based and English-language. The composite and its component benchmarks are dependent evidence, not independent confirmations. One index point is not a calibrated change in task success probability. Rounded ties do not establish equivalence.

## B. FC — Repository changes: FrontierCode 2.0 (B)

[Cognition leaderboard and methodology](https://cognition.com/frontiercode), checked on the date above: 132 tasks, Codex harness for these rows, max effort. Score aggregates mergeability rubrics; a blocking failure scores zero. Pass rate is a separate metric. Cost is mean API-equivalent USD per rollout. Hardware, clock, batch, exact CLI version and confidence intervals are not established by the cited table.

| Model | Effort | Score | Pass rate | USD/rollout |
| --- | --- | ---: | ---: | ---: |
| L | max | 22.7% | 25.1% | 0.17 |
| S | max | 43.8% | 48.2% | 1.29 |
| A | max | 44.2% | 48.2% | 5.97 |

T is UNKNOWN here. S and A remain relevant candidates for comparable repository work; their small score difference does not establish statistical superiority. These rows provide no lower-effort estimate or conditional rescue rate after another model fails.

## C. TB — Terminal work: Terminal-Bench 4.1 (B)

[Leaderboard](https://www.tbench.ai/?efforts=all&version=4.1), checked on the date above. All four rows use max effort and the Codex harness. Ranges below expand the published 95% confidence intervals. Cost is the displayed evaluation-suite total, **not cost per task**. Exact per-row CLI version, repetition count, hardware, clock and batch conditions were not verified.

| Model | Resolution rate | 95% interval | Suite cost |
| --- | ---: | ---: | ---: |
| L | 15.2% | 12.5–17.9% | $0.1k |
| T | 53.3% | 50.2–56.4% | $0.9k |
| S | 61.5% | 58.7–64.3% | $0.3k |
| A | 62.1% | 59.8–64.4% | $1.4k |

[Version 4.1 notes](https://www.tbench.ai/news/terminal-bench-4-1): verifier corrections were applied to saved 4.0 artifacts. These are not independent new model runs. Do not count 4.0 and 4.1 as independent supporting experiments or infer that an overlapping interval proves equivalence.

## D. AC — Real interactive coding: Agent Arena (B)

Ranking date: 2026-11-22; individual pages retrieved on the checked date. All four configurations are max. [Methodology](https://arena.ai/leaderboard/methodology) distinguishes trace-based agent indices from pairwise preference leaderboards: these coding scores combine task completion, feedback, steering and tool signals. They are not pass percentages. Ranges expand displayed uncertainty intervals; the methodology describes 95% confidence intervals.

| Model and source | Coding index | Interval | Sessions | P50 USD/task | P50 min/task |
| --- | ---: | ---: | ---: | ---: | ---: |
| [L](https://arena.ai/leaderboard/agent/code/models/gpt-6-luna-max-yjhb) | 1122 | 1113–1131 | 67,362 | 0.13 | 10.1 |
| [T](https://arena.ai/leaderboard/agent/code/models/gpt-6.1-terra-max-9oju) | 1275 | 1254–1296 | 9,038 | 1.62 | 22.5 |
| [S](https://arena.ai/leaderboard/agent/code/models/gpt-6.2-sol-max-i7fj) | 1258 | 1212–1304 | 2,610 | 1.73 | 14.4 |
| [A](https://arena.ai/leaderboard/agent/code/models/gpt-6.2-astra-max-hwhs) | 1313 | 1265–1361 | 2,379 | 5.53 | 19.1 |

The [coding board](https://arena.ai/leaderboard/agent/code) labels its cost comparison as the median over the last 14 days; resource values can change independently of ranking dates. Hardware, clock, batch, exact harness version and a matched task set for these four entries are not established here. Keep T eligible even when a broad composite ranks it lower. These observations do not prove T outperforms S, or that any model will repair another's failure. Do not use displayed token-price fields as current standard API pricing.

## E. FS — Search and extraction: Firecrawl Search Bench (B)

[Report](https://www.firecrawl.dev/benchmarks/gpt-6-2): 429 private questions, one run per setting on 2026-11-17–18. OpenAI API, medium effort, Codex 0.169.0, Firecrawl search and scrape, 25-minute timeout, judge `gpt-5.5-2026-04-23`. Hardware, clock and batch are unreported. Score is average answer-key fact coverage, not the percentage of entirely correct answers.

| Model | Effort | Score/100 | 95% bootstrap interval | Mean total USD/question | Median seconds/question |
| --- | --- | ---: | ---: | ---: | ---: |
| S | medium | 96.7 | 95.1–98.1 | 0.080 | 13.2 |
| A | medium | 96.6 | 95.0–97.9 | 0.224 | 16.0 |

Total cost includes judge and Firecrawl credits. The paired A-minus-S difference is −0.1 points, with a 95% interval of −1.5 to 1.3. That does not prove equivalence. S medium is a lower-cost candidate for comparable search work; retain A where other requirements justify it. L and T are UNKNOWN in this comparison. A vendor's private, single-run question set does not establish general research superiority.

## F. VS — Agentic science: Vals Science Index (B)

[Science index](https://www.vals.ai/benchmarks/science_index), updated 2026-11-19: equal-weight biology investigation, mechanism discovery and research-workflow components. The linked model pages report max effort. They also warn that individual benchmarks can use different parameters. Preserve that limitation.

| Model and settings source | Score | Range from published ± | USD/test | Published duration/test |
| --- | ---: | ---: | ---: | ---: |
| [L](https://www.vals.ai/models/openai_gpt-6-luna) | 28.38% | 26.90–29.86% | 0.11 | 30m15s |
| [S](https://www.vals.ai/models/openai_gpt-6.2-sol) | 57.76% | 55.50–60.02% | 1.12 | 19m00s |
| [A](https://www.vals.ai/models/openai_gpt-6.2-astra) | 68.44% | 66.31–70.57% | 4.76 | 22m15s |

The uncertainty coverage level and whether duration is a mean or median were not verified; do not label these ranges 95% intervals or these durations medians. Hardware, clock, batch and matching per-component configurations remain unverified. T is UNKNOWN. These data support retaining A max for similar science work, not assigning it all research or mathematics.

## G. Provider guidance and operational interpretation

**O:** [OpenAI model selection](https://developers.openai.com/api/docs/guides/model-selection), checked 2026-11-26, provides workload and effort starting points. The eight non-exclusive O anchors in `AGENTS.md` are provider recommendations, not measured optimal assignments. They do not establish self-assessment accuracy or a benefit from AgentMD itself. Check actual runtime support separately.

**D:** Match the remaining work to relevant observations, current progress, acceptance evidence and resource constraints. Compare model and effort jointly. Preserve a suitable context unless switching has a concrete justification. Benchmark evidence may support candidate selection; it cannot supply a calibrated probability for every task or a uniquely optimal routing graph. No model has a permanent occupation. Missing data are not zero performance. Max-effort observations must not be transferred to other efforts.

**D:** The recovery allowance is at most three substantive attempts, including the initial attempt, for the same unresolved acceptance condition or blocker. Local work, workers and parallel attempts share its ledger. A validated checkpoint can retire that blocker before a genuinely new subgoal begins; relabeling, changing models or proposing another hypothesis cannot reset it. The previous six-attempt cap over the entire task is superseded. Three is a provisional prompt-level guardrail, not an empirically optimal or runtime-enforced number. Explicit user budgets take priority; productive new subgoals have no arbitrary task-wide attempt count.

**UNKNOWN:** Conditional rescue rates, task-level success calibration, correlation of model errors, optimal effort, sequence and stopping thresholds, and improvements caused by these instructions. Distinct model names or fresh contexts do not establish statistical independence. Routine adversarial audits and diversity-only calls are not part of this policy.

## H. Coverage gaps and maintenance

- This registry is sufficient to supply initial priors, not complete capability coverage. It lacks matched four-model effort sweeps for visual interaction, long-context degradation, multilingual work, broad creative work and most real task combinations.
- Arena preference boards, LiveBench, SWE-bench variants, OSWorld and tool-use suites are possible future sources. They remain outside the active numeric LUT until exact model IDs, effort, versions and comparable conditions are checked. Do not import snippets or older generations as substitutes.
- Costs, durations, indices, preference ratings and task pass rates have different units and populations. Do not average them into a new score without a defined objective and defensible normalization. Check units before comparisons; seconds and minutes are time, USD/task and suite USD are different denominators.
- Update this registry and the compact runtime LUT together when a model, effort, source version or verified result changes. Preserve checked dates and unknowns. Do not fetch leaderboards during routine user work. Historical snapshots remain available through Git.

## I. Validation status and acceptance

Static consistency and executed model behavior are separate claims. This revision does not assert improved task quality, model availability, honored effort settings, cache reuse or actual resource savings.

**Executed static and installation checks, 2026-11-26 JST:** eight files; four TOMLs parsed with Python `tomllib`; exact IDs and common worker contract matched; no fixed effort; ten relative Markdown links resolved; all twenty AA configurations matched between the runtime and registry; `AGENTS.md` measured 8,144 UTF-8 bytes, below 8 KiB. The POSIX installer passed `sh -n` and seven isolated filesystem scenarios: clean installation, repeated installation, existing guidance, existing override, an existing worker, a dangling guidance symlink, and missing source files. Existing-content scenarios preserved their files without a partial installation. The target path alone was redirected to temporary directories for these checks; no user profile was installed or altered.

**Policy walkthrough, not model execution:** a checked success ends the task; multiple successful independent stages are not capped at three total; three attempts on one unresolved condition exhaust its allowance across model changes; parallel attempts reserve the same allowance; a new hypothesis cannot reset it; missing access is a blocker rather than evidence for a stronger model. These are checks of the written rules, not observations of model compliance.

**Not executed:** a Codex inference session using this revision, real model/effort switching, instruction-inheritance tracing or a comparative performance experiment. Runtime and performance verdicts remain UNCERTAIN.

| Item | Definition or current status |
| --- | --- |
| H — falsifiable claim | In a supported Codex client, the policy can select available settings, preserve instructions and handoff state, stop failed recovery within its shared allowance, and deliver evidence-backed results. Quality gains over a single model are a separate, untested claim. |
| T — minimum check | Static: parse four TOMLs; check eight-file structure, exact IDs, common contract, links, numeric transcription and consistent recovery rules. Runtime: when available, record actual client/version, resolved model/effort, loaded instructions, one necessary handoff, acceptance evidence and stop reason; do not run benchmark experiments during ordinary work. |
| D — verdict | Static PASS only for checks actually executed. Runtime PASS only for observed requirements; FAIL for wrong settings, false success or broken bounds; UNCERTAIN if execution or acceptance evidence is missing. Current runtime verdict: UNCERTAIN, not executed for this revision. |
| C — alternative explanations | Apparent improvements may come from tools, context, effort, task mix, verifier behavior, harness changes or random variation rather than routing. |
| U — uncertainty | Task selection, model variance, judge error, cache state, resource contention and unknown client support remain material. No combined uncertainty or coverage factor has been estimated; do not invent one. |

No runtime result is inferred from successful Markdown, TOML or shell checks.

