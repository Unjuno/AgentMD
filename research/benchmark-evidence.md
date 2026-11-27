# AgentMD — Active evidence registry

**Checked:** 2026-11-28 JST. The [general-purpose routing LUT](#general-purpose-routing-lut--2026-11-28-jst) adds reproducibly extracted ALE effort rows, LiveBench suite quality/cost, AA max-only coverage and an explicit task-to-evidence index. The [matched task-resource and specialist LUT extension](#matched-task-resource-and-specialist-lut-extension--2026-11-28-jst) adds task-matched cost/duration references and specialist capability observations. The [task-transition and domain LUT extension](#task-transition-and-domain-lut-extension--2026-11-28-jst) adds professional capability indexes and refreshes resource references without changing the 176 original component scores. The [2026-11-26 component snapshot](#lut-quantitative-refresh--2026-11-26-jst) supersedes the earlier AA component snapshot and records provider/supplemental observations; the 2026-11-28 extension supersedes its rolling resource references. Historical tables and audits are preserved below. This is an offline maintenance reference, not routine agent context. Earlier snapshots and superseded policies remain in Git history. No new model-performance experiment was run for the benchmark snapshot. The strategy audit on 2026-11-26 preserves the numeric snapshot, replaces the active proxy-frontier policy and records the limits of the logical baseline.

| Alias | Exact model ID |
| --- | --- |
| L | `gpt-6-luna` |
| T | `gpt-6.1-terra` |
| S | `gpt-6.2-sol` |
| A | `gpt-6.2-astra` |

**Evidence classes:** B = published benchmark observation; O = provider workload guidance; D = AgentMD design choice; UNKNOWN = not established by the checked sources. A published model name is not proof of availability in the user's Codex client.

## A. AA — Earlier broad comparison: Intelligence Index v5.0.2 (B)

[Provider table](https://artificialanalysis.ai/providers/openai/), checked above; Standard only. Cells: **index / weighted USD per evaluation task / estimated minutes per evaluation task**.

| Model | none | low | medium | high | xhigh | max |
| --- | --- | --- | --- | --- | --- | --- |
| L | 9/.0714/1.7 | 10/.0051/.6 | 18/.0422/3.1 | 21/.0729/4.9 | 23/.10/6.4 | 28/.15/10.6 |
| T | 30/.23/2.4 | 29/.0713/1.1 | 38/.17/2.7 | 43/.26/4.2 | 45/.40/6.4 | 51/.96/14.0 |
| S | — | 41/.18/1.6 | 52/.41/3.5 | 55/.56/5.2 | 56/.65/6.2 | 57/1.01/10.0 |
| A | — | 46/.66/2.0 | 57/1.62/4.6 | 60/2.07/6.2 | 62/2.52/8.1 | 62/4.00/14.2 |

Time derives from output tokens and speed (rolling five days), not task wall-clock duration. Rounded values lack row uncertainty and HW/clock/batch details; costs are not Codex-plan charges.

[Methodology](https://artificialanalysis.ai/methodology/intelligence-benchmarking): nine evaluations span knowledge work, coding, science and general knowledge. The suite is primarily text-based and English-language. The composite and its component benchmarks are dependent evidence, not independent confirmations. One index point is not a calibrated change in task success probability. Rounded ties do not establish equivalence.

## A.1. Earlier matched AA component observations (B), 2026-11-26

Sources: [Astra vs Sol](https://artificialanalysis.ai/models/comparisons/gpt-6-2-astra-vs-gpt-6-2-sol), [Sol vs Terra](https://artificialanalysis.ai/models/comparisons/gpt-6-2-sol-vs-gpt-6-1-terra), [Terra vs Luna](https://artificialanalysis.ai/models/comparisons/gpt-6-1-terra-vs-gpt-6-luna), [AA methodology](https://artificialanalysis.ai/methodology/intelligence-benchmarking). All three display v5.0.2. Columns are sorted by index: remap by explicit model/effort headers. The 88 overlapping observations (five Sol and six Terra settings across eight metrics) agreed; duplicates are not independent trials.

Each model cell: **none / low / medium / high / xhigh / max**. Briefcase is Elo; other rows are displayed percentages. Eight of the nine index components have a complete retrieved table over 22 configurations (176 distinct scores); comparable AA-Omniscience values were not retrieved and are not imputed. The [API catalog](https://developers.openai.com/api/docs/models) and [deployment checklist](https://developers.openai.com/api/docs/guides/deployment-checklist) list none for L/T but not S/A. The two added non-reasoning broad entries are from the AA provider table; Codex support is unverified. Prior composite times are retained from the provider snapshot rather than mixing rolling estimates across pages.

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

| Row | Evaluation scope |
| --- | --- |
| Briefcase | AA-Briefcase v1.1; agentic knowledge work, Elo |
| Automation | AutomationBench-AA; SaaS workflow achievement, partial credit |
| Terminal | Terminal-Bench 4.1 in AA setup |
| FrontierCode | FrontierCode-AA 2.0; repository change quality |
| GDP | GDP.pdf; professional document reasoning, all-pass |
| HLE | HLE-Diamond; difficult knowledge and reasoning |
| CritPt | CritPt v2 Hard Subset; physics reasoning |
| Science | Terminal-Bench-Science 0.1; scientific research workflows |

Matched AA framework improves comparability but is not identical to the official Terminal-Bench or Cognition FrontierCode setup. Per-setting sampling intervals, paired outcomes, exact run compliance, HW/clocks/batch were not verified. Observed differences are descriptive, not established significance. Components and composite are dependent. Do not infer task-specific cost from weighted composite cost.

**Published protocol, rechecked 2026-11-26:** [AA methodology](https://artificialanalysis.ai/methodology/intelligence-benchmarking) declares the following task counts/repeats. These are protocol statements, not independently observed compliance for every model/effort run.

| Evaluation | Tasks/questions | Repeats |
| --- | ---: | ---: |
| Briefcase | 91 | 1 |
| Automation | 657 | 1 |
| GDP.pdf | 100 | 5 |
| FrontierCode-AA | 132 | 3 |
| Terminal-Bench | 66 | 3 |
| Terminal-Bench-Science | 70 | 3 |
| CritPt hard subset | 40 | 5 |
| HLE-Diamond | 1,000 | 1 |

**Source recheck, 2026-11-26:** the three comparison pages above reproduced all 176 component values, 88 overlapping observations and all 22 broad indices/USD values. Thirteen derived minute estimates differed from the saved snapshot, including A max 14.2 to 14.7, T max 14.0 to 14.4 and L max 10.6 to 10.5. These are rolling speed-derived values, not evidence of incorrect old transcription. The active LUT retains the internally consistent older resource snapshot and labels it historical; no selected time was silently refreshed.

### Historical derived comparison (D), superseded for runtime selection

- Direct maxima over these settings include ties: CritPt A high/A max, with A high lower composite cost and derived time. A xhigh exceeds A max on Terminal and FrontierCode; S max peaks on GDP; T max exceeds S max on CritPt. Effort and model rankings are not universal.
- Composite Pareto candidates (maximize displayed index; minimize displayed USD/task and derived minutes/task): L low, L medium; T low, T medium, T high, T xhigh; S low, S medium, S high, S xhigh, S max; A low, A medium, A high, A xhigh. This is a descriptive frontier of 22 rounded observations, not a statistical or task-specific frontier. Do not remove a configuration from individual task rows on this basis.
- The active runtime now preserves all 22 measured configurations and their component vectors. The proxy-frontier selection below is retained only as a superseded derivation. Neither frontier membership nor the highest score authorizes routing or exclusion.

### Superseded proxy-frontier policy (D), 2026-11-26

Derived from the saved AA component and broad tables, without changing or remeasuring any observation. For each of the eight component metrics and the broad index, compare all 22 configurations. Configuration X proxy-dominates Y when its displayed quality is at least as high, its broad weighted USD/index-task is no greater, and its broad derived minutes/index-task is no greater, with at least one strict improvement. Retain all nondominated configurations. The broad index frontier uses three measurements from the same composite; the eight component frontiers mix component quality with broad resource proxies and **are not actual per-component cost/time Pareto frontiers**. They cannot establish a globally optimal route, calibrated task success, recovery rate, budget guarantee or a unique best configuration.

At commit 3b7da7e, the textual runtime LUT listed the frontier with each original displayed quality value, sorted by proxy cost solely for readability. It also retained omitted within-family peak configurations (including ties), explicitly separate from the frontier. All model families remain eligible; a configuration omitted from the shortlist can still be suitable with direct evidence, actual runtime restrictions, context reuse, different cost or distinct Buddy contribution. No forced route or sequential ladder is derived. Resource-reference values are transcribed from the broad table, with their original denominator and estimated-time qualification.

| Metric | Proxy frontier count | Omitted family-peak alternatives |
| --- | ---: | ---: |
| Briefcase | 16 | 1 |
| Automation | 13 | 2 |
| Terminal | 14 | 2 |
| FrontierCode | 15 | 1 |
| GDP | 7 | 3 |
| HLE | 16 | 2 |
| CritPt | 11 | 2 |
| Science | 13 | 2 |
| Broad | 15 | 3 |

The historical policy also described an escalation decision: continue if adequate; otherwise select a relevant contribution whose incremental total cost is justified by an expected quality/risk or rework benefit. Provider anchors are provisional, not hard assignments. With a useful concurrent contribution, the primary and Buddy both work and then integrate evidence. The Buddy need not have a higher single-agent benchmark score. No pairwise rescue or audit advantage has been measured.

**Historical static check of 3b7da7e:** 4,356 ordered pair comparisons (9 metrics × 22 × 22, including self-comparisons) reproduced the nine nondominated sets and established a frontier witness for every omitted dominated candidate. 120 frontier entries and 18 additional family-peak entries across metrics; counts refer to metric/configuration pairs, not distinct models. Verified the 176 component observations and 22 broad observations were preserved, all runtime candidate scores and resource references were transcribed, and all four families remained represented for each metric. This is static consistency, not a runtime experiment.

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

**O:** [OpenAI model selection](https://developers.openai.com/api/docs/guides/model-selection), rechecked 2026-11-26, supplies illustrative workload/effort starting points. The runtime now narrows L xhigh to updates across apps, prioritization and clearly constrained problems. S medium covers existing-codebase fixes/features or drafts for review; S xhigh covers multistep testing/revision. The earlier combined "clear dependent steps" paraphrase was broader than the Luna example. Provider examples are not measured optimal assignments, fixed occupations or evidence of self-assessment accuracy. The general Sol starting suggestion does not override a satisfactory current configuration. Actual client support must be checked separately.

**D — baseline and next action:** compare against the current model/effort completing the same work with the same tools, permissions and checks. It is a logical comparator, not a measured control run or compulsory failed first attempt. Use task facts, capability fit and available actions. Explicit quality requirements, limits and preferences take priority; compare remaining monetary cost and elapsed time separately. Include primary/worker execution, transfer, waiting, checks and integration. Do not invent calibrated adequacy thresholds, conditional rescue probabilities or utility weights. A nominally cheaper return model may cost more after transfer.

**D — recovery:** before recovery/duplicate solving, declare a finite task-scoped recovery allowance selected for scope, consequences and user/runtime constraints. No universal three-attempt default remains. Reserve centrally and count additional local, worker and parallel recovery/duplicate attempts when started. Ordinary first-pass work on distinct requirements and necessary checks are not recovery slots. An overlapping candidate solving the same unresolved condition costs one slot; an authorized continuation of the incumbent or selected approach is not a new attempt unless it changes approach or starts a new correction after a failed checkpoint. Two new recovery solves cost two. Changing model, thread, hypothesis, blocker or label does not replenish the allowance. Explicit user scope/budget changes must be recorded.

The parent marks each solve INITIAL or RECOVERY/DUPLICATE and authorizes first-pass scope separately from reserved recovery. One stated approach ends at its planned acceptance checkpoint. A new correction after failure or replacement approach starts a new attempt; routine tool actions do not. Workers report classified starts.

Before retrying failed setup, declare a separate finite task-scoped setup-retry allowance. Classify first setup, retry and continuation from observed history; allowance alone proves no prior attempt. Unknown usage remains UNKNOWN and must be reconciled before relying on remaining capacity. Initial setup is not a retry; record failures and costs. A retry consumes its slot on dispatch. Failed launch before solving does not demonstrate solving failure. Track every worker dispatch (INITIAL included), retaining scope/ownership and any reservation on an ambiguous reply. Do not redispatch or start conflicting replacement work until reconciled and safe to replace. Release a solving reservation only after confirming that dispatch never started and cannot later start. Started solves remain consumed after interruption. When no unreserved recovery allowance remains, prohibit new counted attempts; authorized attempts may finish their checkpoint within other limits. Report what remains when no permitted correction is available, and continue eligible work. This deliberately may leave useful work unfinished; it is neither optimal stopping nor a proof of bounded task spend/time. Repeated unproductive checks/searches are disallowed even though routine checks are not recovery slots.

**D — Buddy (current policy):** a justified model/effort transition temporarily overlaps the current work lead and a candidate selected through the same LUT. Both pursue the same remaining problem at a bounded checkpoint and generate evidence through real tests/actions where feasible; each examines and responds to the other's results. Select or integrate the supported approach, retain an adequate incumbent if no material advantage is shown, and let the selected participant continue with its existing context. Retire the other active solve and confirm cessation or isolation of conflicting writes before transferring write ownership. Finish if acceptance is established; otherwise subsequent transitions start from the current lead. The primary continues to own orchestration, accounting, permissions and final acceptance, and brokers transitions for worker leads. A lead transfer is not a runtime change of the primary model. If parallel overlap, reciprocal exchange or continuation cannot be performed, disclose the best feasible direct/sequential path. Isolate competing writes and confirm safe ownership before final verification. No per-task decomposition, mandatory full duplicate solve, permanent pair or repeated routine audit is required. Historical sections describe the policies at their respective revisions.

**D — acceptance:** an identified result supports PASS only to the extent its stated acceptance conditions are covered by checks actually performed. Report failed required checks, external blockers and material missing verification. Another model's agreement cannot turn an unverified requirement into proven success. Status labels summarize evidence; they do not replace it.

**UNKNOWN:** conditional rescue rates, calibrated task success, joint model error structure, best pair/effort/route/stopping threshold and any gain from AgentMD. Different models and fresh contexts may produce different approaches, but neither proves independence or improvement. Benchmark evidence guides candidate consideration, not an identified optimal graph.

## H. Coverage gaps and maintenance

- This registry is sufficient to supply initial priors, not complete capability coverage. Eight retrieved AA component rows cover multiple demands across all four families. Matched effort sweeps for visual interaction, long-context degradation, multilingual/creative work, AA-Omniscience and most real task combinations remain unavailable.
- Arena preference boards, LiveBench, SWE-bench variants, OSWorld and tool-use suites are possible future sources. They remain outside the active numeric LUT until exact model IDs, effort, versions and comparable conditions are checked. Do not import snippets or older generations as substitutes.
- Costs, durations, indices, preference ratings and task pass rates have different units and populations. Do not average them into a new score without a defined objective and defensible normalization. Check units before comparisons; seconds and minutes are time, USD/task and suite USD are different denominators.
- Update this registry and the compact runtime LUT together when a model, effort, source version or verified result changes. Preserve checked dates and unknowns. Do not fetch leaderboards during routine user work. Historical snapshots remain available through Git.

## I. Validation status and acceptance

Static consistency and executed model behavior are separate claims. This revision does not assert improved task quality, model availability, honored effort settings, cache reuse or actual resource savings.

**Previous revision (a72ab65), executed static and installation checks, 2026-11-26 JST:** eight files; four TOMLs parsed with Python `tomllib`; exact IDs and common worker contract matched; no fixed effort; ten relative Markdown links resolved; all twenty AA configurations matched between the runtime and registry; `AGENTS.md` measured 8,144 UTF-8 bytes, below 8 KiB. The POSIX installer passed `sh -n` and seven isolated filesystem scenarios: clean installation, repeated installation, existing guidance, existing override, an existing worker, a dangling guidance symlink, and missing source files. Existing-content scenarios preserved their files without a partial installation. The target path alone was redirected to temporary directories for these checks; no user profile was installed or altered.

**Superseded policy walkthrough at a72ab65, not model execution:** a checked success ends the task; multiple successful independent stages are not capped at three total; three attempts on one unresolved condition exhaust its allowance across model changes; parallel attempts reserve the same allowance; a new hypothesis cannot reset it; missing access is a blocker rather than evidence for a stronger model. These are checks of the written rules, not observations of model compliance.

**LUT tuning (2026-11-26):** retrieved three explicit comparison tables, checked 88 duplicate values, transcribed 176 distinct scores, calculated eight observed peaks and the composite Pareto set. Added L/T none, with runtime eligibility checks. Static source-data and policy validation only; no Codex performance experiment.

**Superseded ordinal LUT update (2026-11-26, based on 44c6ff7; historical):** the runtime numeric matrices were converted to ordinal candidate preferences. All 176 AA component scores and 22 broad configurations remain unchanged in this registry. Each quality order is descending by the displayed value; exact displayed ties are grouped. Broad cost and derived-time orders are ascending. The 11 orders each cover all 22 measured settings; unsupported none entries are excluded. Runtime effort suffixes n/l/m/h/x/max denote none/low/medium/high/xhigh/max; abbreviation changes notation, not ordering. Ordinal compression intentionally omits numerical gap sizes, absolute proxy magnitudes and any claim of statistical superiority. Use direct evidence, real constraints and matched observations first; never treat a rank list as a retry sequence or use resource ranks to certify a budget. Static generation from the registry and pairwise order validation are not evidence of improved inference, latency, token use or final quality.

**Superseded capability/resource escalation revision at 3b7da7e:** replaced the ordinal lists with nine proxy-efficient candidate sets and resource references; the old highest-score preference is superseded. That revision did not change the then-current three-attempt guardrail, installer or model bindings. The later logical-baseline revision supersedes the guardrail. No actual Codex execution, cost reduction or quality gain was measured in this revision.

**Previous Buddy policy update (2b7f0e3):** changed routing prose without changing LUT numbers, worker TOMLs or installer. Static consistency and review of the written rules do not establish that a real primary will do useful work while a Buddy runs. Runtime trace, resolved model/effort, concurrent progress, join/integration and outcome improvement are untested; runtime and performance verdicts remain UNCERTAIN.

| Item | Definition or current status |
| --- | --- |
| H — falsifiable claim | In a supported Codex client, the policy can select available settings, preserve instructions and handoff state, account for recovery/setup within declared shared allowances, and deliver evidence-backed results. Quality gains over a single model are a separate, untested claim. |
| T — minimum check | Static: parse four TOMLs; check eight-file structure, exact IDs, common contract, links, numeric transcription, artifact-aware acceptance and consistent recovery/setup rules. Runtime: when available, record actual client/version, resolved model/effort, loaded instructions, one necessary handoff, actual primary work between Buddy spawn and join, both outputs and their integration, acceptance evidence and stop reason; do not run benchmark experiments during ordinary work. |
| D — verdict | Static PASS only for checks actually executed. Runtime PASS only for observed requirements; FAIL for wrong settings, false success or broken bounds; UNCERTAIN if execution or acceptance evidence is missing. Current runtime verdict: UNCERTAIN, not executed for this revision. |
| C — alternative explanations | Apparent improvements may come from tools, context, effort, task mix, verifier behavior, harness changes or random variation rather than routing. |
| U — uncertainty | Task selection, model variance, judge error, cache state, resource contention and unknown client support remain material. No combined uncertainty or coverage factor has been estimated; do not invent one. |

No runtime result is inferred from successful Markdown, TOML or shell checks.


## J. Logical baseline and repeated audit (D)

This section distinguishes a defensible policy from an identified optimum. It is a maintenance explanation, not extra runtime reading. The requested revision audits the strategy itself; it does not require routine user tasks to perform multiple audits.

### J.1. The preserved strategy

Use one shared policy and model/effort evidence table. Continue adequate task progress. At a capability gap, consequential uncertainty, failed check or useful parallel opportunity, choose a feasible next action with an explicit contribution and acceptable remaining resources. Buddy means useful work by both primary and worker, followed by evidence-based integration. The primary owns completion and allocation. Model identity is not a permanent job or a universal capability rank.

The logical baseline is current single-configuration execution with the same task and acceptance checks. The revision's claim is that its rules expose unsupported inferences and account for relevant costs; it does not claim that routing empirically beats this baseline.

### J.2. Why a unique optimal graph is not identified

A routing optimum would require an objective defining quality/error tradeoffs, available actions, context-dependent outcomes, conditional recovery, actual costs/latency and the reliability of acceptance checks. The saved public means do not supply all of these. Missing information cannot be manufactured by calling an agent more confident or by repeating a prose audit.

**Constructive counterexample — marginal averages:** let X and Y be hypothetical models evaluated on 100 equally weighted tasks with exact binary success. X and Y are categorical model labels, not numerical variables.

| World | Both succeed | Only X | Only Y | Neither | X total successes | Y total successes | Y recovery among X failures |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| Shared failures | 70 | 10 | 0 | 20 | 80 | 70 | 0 of 20 |
| Complementary coverage | 50 | 30 | 20 | 0 | 80 | 70 | 20 of 20 |

Each row partitions all 100 tasks. Adding the both-success and X-only cells gives 80 in either world; adding both-success and Y-only gives 70. X fails on 20 tasks in either world. Y succeeds on none of those in the first world and all of them in the second. Thus identical marginal observations admit opposite conditional rescue values. Any rule using only these marginals sees identical inputs and cannot identify the correct rescue value in both worlds. With a positive extra-call cost and a sufficiently valuable successful resolution, the preferred escalation action differs too.

An equal random choice between X and Y, independent of task, succeeds on 75% of tasks in expectation in either construction: half the probability mass receives the 80% option and half the 70% option. It is below X's 80%. Blind alternation is therefore not a general improvement theorem. This does not disprove informed selection or useful collaboration.

**Mixed-population counterexample:** a hypothetical X can have component score 90 and broad average cost/time USD 0.20 / 2 min, while Y has 88 and USD 0.30 / 3 min. X appears dominant in that mixed vector. On the actual target task X could cost USD 8 / 20 min and Y USD 0.50 / 3 min. The actual resources reverse. All values can be true because the resource populations differ. Even matched one-shot averages do not identify conditional behavior after a particular failure.

**Switching counterexample:** hypothetical remaining work costs USD 0.02 on the current model, or USD 0.01 plus USD 0.10 transfer/integration on another. Switching consumes USD 0.11, so a lower per-work model cost does not establish lower next-action cost. Returning to a cheaper model has the same issue.

**Verification counterexample:** two agents can agree because both inherited the same incorrect assumption. A test encoding that assumption can also pass. Agreement and test pass are limited observations; the check must address the actual acceptance condition, and material unchecked assumptions remain unknown.

All examples are constructed, not new benchmark measurements. Counts/probabilities are dimensionless; USD comparisons use one currency/denominator and minutes compare elapsed time only. No USD-plus-minute utility is asserted.

### J.3. A limited accounting invariant

The task-scoped recovery guard is a policy choice. Its finite count can be proved only under fixed scope/allocation and faithful central reservation. It is not a proof that Markdown enforces a runtime limit.

| Symbol | Meaning (日本語) | SI unit | Definition | Domain / assumptions | Type |
| --- | --- | --- | --- | --- | --- |
| B | 固定した回復・重複実行の総枠 | 1 (count) | Declared recovery allowance | Nonnegative integer; unchanged during this proof | Integer scalar |
| A | 開始確認済み実行数 | 1 (count) | Confirmed started counted solves | Nonnegative integer; never refunded after start | Integer scalar |
| Q | 予約済み・開始未確認枠 | 1 (count) | Reservations not yet moved to A, including ambiguous launches that may have started | Nonnegative integer; each refers to at most one solve | Integer scalar |
| R | 未予約の残枠 | 1 (count) | B minus A minus Q | Nonnegative integer; reservations cannot exceed it | Integer scalar |
| N | 実際に開始した実行の累計 | 1 (count) | Actual started recovery/duplicate solves, whether their start is known yet or not | Nonnegative integer; may be unobservable | Integer scalar |

The invariant and bound are:

$$
A+Q+R=B,\qquad A,Q,R\geq0,\qquad N\leq A+Q\leq B.
$$

1. Initially there are no counted starts or reservations, and all B slots are in R.
2. A permitted reservation transfers one slot from R to Q. Dispatch at most one solve under that reservation; do not dispatch again under the same unresolved reservation.
3. If execution starts but its response is delayed or lost, its slot stays in Q. Every such actual start is still covered by a reservation, so N cannot exceed A plus Q.
4. Confirmation of start moves its slot from Q to A. No capacity is returned. Actual starts remain covered by A plus Q.
5. A reservation can move from Q to R only after confirming that its solve never started and cannot subsequently start under that dispatch, such as a confirmed rejection or effective pre-start cancellation. An ambiguous timeout cannot justify a refund.
6. A completed or interrupted started solve stays in A. Parallel work reserves each solve separately. These transitions preserve the sum and nonnegativity, and every actual counted start remains covered.
7. Therefore N is at most A plus Q, and A plus Q is at most B because R is nonnegative.

All terms have the same dimensionless count unit. A separately declared finite setup-retry allowance uses the same reserve-before-dispatch discipline; a dispatched retry is consumed whether it succeeds or fails. The initial setup request is outside the retry count, while its failures and resources are still recorded. User-authorized scope/budget revisions begin a recorded revised allocation, so this fixed-allocation proof does not bound all future revisions.

This proof assumes one solve per reservation/dispatch, confirmed refunds, faithful central accounting and no hidden extra starts. It does not cover uncounted ordinary work, elapsed duration, monetary spend, runtime enforcement or task success. Any finite count can stop a useful next correction; no finite universal count guarantees completion of all tasks.

**ERROR CHECK:** the four joint-outcome cells in each hypothetical world are nonnegative and sum to 100; the marginals match; the accounting proof never refunds started or ambiguously started work. No independence of model errors, calibrated utility, optimal count or real-model performance is assumed.

### J.4. Relation to published routing research

[FrugalGPT, Chen et al., arXiv:2305.05176](https://arxiv.org/abs/2305.05176) studies learned LLM cascades and reports outcomes for its evaluated models/tasks. [RouteLLM, Ong et al., arXiv:2406.18665](https://arxiv.org/abs/2406.18665) trains routing from preference data and evaluates cost/quality tradeoffs. These primary papers support studying selection under a defined objective and data; they do not validate this four-family Buddy policy, its lookup table or its retry allocation. No numerical gain from either paper is transferred to AgentMD.

Decision theory supplies the objective and action comparison; statistics separates marginals from conditional/joint evidence; distributed systems supplies artifact identity, centralized reservation and integration discipline. None supplies missing empirical model outcomes by itself.

### J.5. Issue ledger and audit protocol

| Defect found at 3b7da7e | Repair in this revision | Required recheck |
| --- | --- | --- |
| Mixed component quality/broad resources narrowed candidate sets | Full 22-setting vectors; old frontiers historical only | All 176 values and 22 broad entries preserved; no active frontier exclusion |
| Cost and latency tradeoff unspecified | Explicit user priorities and separate remaining resources | Cheaper/slower and switching-overhead cases |
| Marginal averages could appear to determine rescue or averaging benefit | Constructive counterexamples and unknown conditional outcomes | Same marginals, different rescue; blind alternation |
| Automatic return to a cheap model could erase savings | Account for future transfer/integration | Small remaining-work example |
| Three initial-inclusive attempts treated as a general budget | Task-scoped finite recovery allowance; no universal number | Distinct first-pass work, shared recovery, no silent reset |
| Failed launch could consume all solving allowance | Separate setup-retry accounting; refund only confirmed unused solve reservations | Unavailable model, successful retry and interrupted started solve |
| Lost launch response could hide a running worker | Keep ambiguous reservation; reconcile/cancel before replacement | Delayed-start and timeout oversubscription cases |
| Initial worker authorization could conflict with zero recovery slots | Explicit INITIAL/RECOVERY classification and checkpoint boundary | First-pass worker, new fix after a failed checkpoint |
| Disjoint files could still produce stale integration checks | Artifact/revision identity and shared-state coordination | Actual integrated artifact rechecked |
| PASS and model agreement could overstate acceptance | Evidence-scoped statuses; missing essential check stays uncertain | Failure/unknown coexist with a summary status |
| Mandatory join could wait for superseded work | Safely cancel/discard irrelevant work, account for edits | Completed useful branch with obsolete worker |
| Repeated audit could be mistaken for correctness/performance proof | Distinct scoped passes and explicit residual uncertainty | No runtime or performance claims from static checks |

Audit sequence: first locate counterexamples and source-scope defects; then review revised decisions, ownership and accounting; finally recheck the fixes for regressions and verify the released content. Newly found material issues require a repair and another targeted pass. Stop the scoped review after the actionable issues are resolved and the follow-up exposes no new material finding. Repeated agreement is not a proof that no defect exists.

**Release audit outcome (2026-11-26 JST):**

| Pass | Scope | Findings and resolution |
| --- | --- | --- |
| 1 | Independent logic, primary-source and execution-policy reviews of 3b7da7e | Identified mixed-scope pruning, undefined cost/time tradeoffs, non-identified conditional rescue, arbitrary attempt semantics, stale integration checks and overstated status. Revised the policy and documented counterexamples. |
| 2 | Re-review of the working revision | Caught a generator selecting the alias table instead of broad data; repaired table scoping/shape validation and independently rechecked all numeric entries. Clarified initial-worker authorization, attempt boundaries, separate setup retries and ambiguous launches. |
| 3 | Targeted logic/accounting/evidence regression review | Confirmed the repaired strategy and data within scope. Found the shortened refund wording could admit a queued-but-not-yet-started job; synchronized the full never-started-and-cannot-later-start condition with the proof. |
| Final targeted check | Release contents, refund condition and reproducible static/reference checks | Confirmed the final wording matches the proof; no unresolved material finding remains in the enumerated audit scope. This is not an assertion that every possible defect is absent. |

Separate reviewer contexts were used; their agreement is not statistical independence, a cross-model experiment or proof of correctness. Newly introduced drafting defects were fixed before publication.

Executed checks: eight-file layout; four TOMLs parsed with Python `tomllib`, exact bindings, common contract and no fixed effort; 11 relative file links resolved; all 176 component observations and 22 broad entries matched both registry and baseline; no missing/undefined runtime values. The first-install shell block is byte-identical to baseline, passes `sh -n`, and passed seven isolated scenarios: clean, repeated, existing guidance, existing override, existing worker, dangling guidance symlink and missing source. No actual user profile was changed.

The mathematical reference calculation checked the constructed marginal/switching examples and explored 781 states with 4,102 permitted transitions for allowances zero through four, including delayed or unknown starts. It explicitly demonstrates that refunding a possibly started job can oversubscribe a one-slot allowance. This explores a deliberately small reference accounting model; the general bound is the proof in J.3, not an extrapolation from finite enumeration.

The runtime instruction file is 12,624 UTF-8 bytes in this revision; staying below Codex's default combined limit does not establish model compliance or prompt efficiency. Actual Codex loading, resolved settings, concurrent Buddy behavior, total spend/time and comparative model performance remain **UNCERTAIN / unmeasured**. No new model-performance experiment was run.

### J.6. Reproduce the small reference calculation

This dependency-free Python calculation checks only the hypothetical example and the declared reservation transitions. It does not read model outputs or execute Codex.

Reference-code variable table (the formal budget symbols are defined in J.3):

| Identifier | Meaning (日本語) | SI unit | Definition | Domain / assumption | Type |
| --- | --- | --- | --- | --- | --- |
| worlds | 仮想的な同時成功・失敗の件数 | 1 (count per cell) | Two partitions in J.2 | Four nonnegative cells per world, totaling 100 | List of integer tuples |
| both, x_only, y_only, neither | 両者成功・片方成功・両者失敗の件数 | 1 (count) | One partition's cells | Integers from 0 to 100 | Integer scalars |
| rescue | X失敗時にYが成功する割合 | 1 | Y-only count divided by X-failure count | Positive failure denominator; each value from 0 to 1 | List of exact rational probabilities |
| edges | 許可した予約状態遷移 | Not a physical quantity | Successor states for each token state | F/R/U/X/A; refunds require the stated confirmation | Categorical mapping |
| budget | 固定した実行枠 | 1 (count) | B in J.3 | Integers 0 through 4 in this finite check | Integer scalar |
| start, state, successor | 各枠の初期・現在・次の状態 | Not a physical quantity | One token state per slot | Tuples of length budget | Categorical vectors |
| seen, pending | 発見済み・未処理の状態 | Not a physical quantity | Visited set and traversal queue | Finite collections of state tuples | Set / deque |
| states, transitions | 検査した状態・遷移の件数 | 1 (count) | Cumulative enumeration counters | Nonnegative integers | Integer scalars |
| confirmed, reserved, free | 開始確認済み・予約中・空き枠 | 1 (count) | A, Q, R in J.3 | Nonnegative integers summing to budget | Integer scalars |
| actual, next_actual | 現在・次状態の実際の開始件数 | 1 (count) | N in current/successor state | Nonnegative; may be unobservable outside this reference model | Integer scalars |
| position | 変更する枠の位置 | 1 (index) | Tuple index | Integer from 0 to budget minus one, when nonempty | Integer scalar |
| token, next_token | 枠の現在・次状態 | Not a physical quantity | State codes explained in the code | F/R/U/X/A | Categorical scalars |


```python
from collections import deque
from fractions import Fraction

# Two exact hypothetical joint distributions over 100 equally weighted tasks.
worlds = [(70, 10, 0, 20), (50, 30, 20, 0)]
rescue = []
for both, x_only, y_only, neither in worlds:
    assert both + x_only + y_only + neither == 100
    assert both + x_only == 80 and both + y_only == 70
    rescue.append(Fraction(y_only, y_only + neither))
assert rescue == [0, 1]
assert Fraction(1, 2) * Fraction(80, 100) + Fraction(1, 2) * Fraction(70, 100) == Fraction(75, 100)
assert Fraction("0.01") + Fraction("0.10") > Fraction("0.02")

# F: free; R: reserved; U: dispatched, ambiguous, actually not started;
# X: dispatched, ambiguous, actually started; A: confirmed started/consumed.
# U->F requires confirmed non-start AND prevention of any later start.
# A reserved slot permits at most one dispatch; a started slot is never freed.
edges = {"F": "R", "R": "FUA", "U": "XF", "X": "A", "A": ""}
states = transitions = 0
for budget in range(5):
    start = ("F",) * budget
    seen, pending = {start}, deque([start])
    while pending:
        state = pending.popleft()
        confirmed = state.count("A")
        reserved = sum(state.count(s) for s in "RUX")
        free = state.count("F")
        actual = state.count("A") + state.count("X")
        assert confirmed + reserved + free == budget
        assert actual <= confirmed + reserved <= budget
        states += 1
        for position, token in enumerate(state):
            for next_token in edges[token]:
                successor = state[:position] + (next_token,) + state[position + 1:]
                next_actual = successor.count("A") + successor.count("X")
                assert actual <= next_actual <= budget
                transitions += 1
                if successor not in seen:
                    seen.add(successor)
                    pending.append(successor)
assert (states, transitions) == (781, 4102)
print(states, transitions)
```

The state symbols are categorical reservation states, not model IDs or SI measurements. `budget`, counts and positions are nonnegative integers with count unit 1; `state` is a finite tuple and `edges` maps categorical states to permitted successors. In proof notation, `confirmed` is A, `reserved` is Q, `free` is R, `actual` is N, and `budget` is B. This reference model exposes actual start states for checking; the real primary may not observe them and must retain ambiguous reservations.

## K. Targeted safety tuning and regression check (D), 2026-11-26

The user prioritizes adequate task completion and correction of material defects, not maximizing marginal benchmark scores. This update keeps the strategy, all 176 component observations, all 22 broad references, model bindings, effort settings and installer unchanged. It clarifies acceptance stopping, setup classification and launch ownership for INITIAL as well as recovery work. The previous wording could be read as protecting only a counted recovery reservation, despite INITIAL work having no such reservation. A prior scenario also classified setup as a retry merely from the existence of an allowance. Neither is evidence of actual runtime compliance.

Executed an isolated OS subprocess regression using temporary files and a pipe-controlled delayed writer. An initial script using multiprocessing synchronization timed out after its first unguarded case; replaced that harness with bounded subprocess/pipe operations. In both the INITIAL-labeled and RECOVERY-labeled cases, an unguarded replacement passed a file check and was subsequently overwritten by the still-live child; the guarded sequence confirmed the child terminated before assigning and checking the replacement, preserving the accepted file. Five reference classification examples passed: no prior setup + new dispatch = INITIAL; known previous attempt + new dispatch = RETRY; unknown history + new dispatch = UNKNOWN; two existing-work continuation cases = CONTINUATION. These five examples test a reference classification function, not a language model's judgment. The process experiment reproduces a late-write hazard and verifies one safe sequence; it does not assert that the previous prompt necessarily caused that hazard or that a prompt can enforce isolation.

The current chat did not expose a general-purpose subagent launch action, and its local environment had neither Codex executable nor API credentials. No new LLM subagent, target Codex client, model/effort resolution, live Buddy compliance, quality or cost improvement was tested. Static/OS-process regression is not a substitute for those checks. No routine new audit step or model occupation is added. A later supported-client test should solve actual bounded tasks with independently checkable outputs and record real model/effort, worker launches, primary progress, integration, verification and stop reasons rather than replaying scripted model answers.

## L. Buddy as an overlapping transition (D), 2026-11-26

The user clarified that Buddy is not primarily a task-decomposition scheme: when changing configurations, temporarily run the incumbent and candidate together, compare their actual actions/results through reciprocal discussion and let the more effective participant continue the work. This revision replaces the previous generic parallel contribution policy with that transition rule. It distinguishes work lead from coordinating primary, permits an adequate incumbent to remain, and allows the selected worker to request later transitions through the primary. Existing context, write ownership, acceptance checks and recovery accounting survive lead transfer. The same LUT and all original measurements are preserved. This is a design choice, not evidence that a brief comparison identifies the globally best model or that reciprocal discussion always improves quality. The bounded checkpoint, continued single lead, and safe sequential fallback limit overhead. No live model transition, reciprocal agent exchange, target-client setting or performance gain was measured in this revision. The historical scenario and audit results do not test this new transition mechanism.

## M. Transition follow-up: narrow regression (D), 2026-11-26

Reviewed the active overlap policy at 94ccc7d and the official [Codex subagent documentation](https://learn.chatgpt.com/docs/agent-configuration/subagents). Supported clients can route follow-up instructions and stop/close worker threads; a particular client's resolved settings and behavior remain untested. Two material ambiguities were clarified: verify cessation or isolation of the losing participant's conflicting writes BEFORE transferring ownership, not merely before final verification; exhausting unreserved recovery slots prohibits new starts but does not automatically stop an already authorized continuation of the selected approach. If the task is already accepted, do not start another solving stage. The coordinating primary remains responsible for orchestration and acceptance.

Executed a dependency-free Python reference regression using isolated subprocesses, not LLMs. Two scripted interval-merge implementations processed the same four cases. The candidate-only pass, incumbent-only pass, both-pass and neither-pass cases produced the expected selections (4/4); both-pass retained the incumbent in this equal-overhead fixture. Five reference assertions checked last-slot continuation, prohibition of a new start, changed approach and binding-limit cases. A delayed-writer subprocess overwrote the selected lead's work under an unguarded transfer; terminating and confirming cessation before the transfer preserved it. These observations validate the fixtures and reproduce a concrete file hazard, not adherence of a model to instructions. No general-purpose subagent launch action, Codex executable, or configured OpenAI API key was available in this chat; no actual agent dialogue, model/effort switch, or comparative quality/cost result was measured. No changes to the LUT, model bindings, worker contracts, installer or eight-file structure were made.

## Live Dot collaboration checks — November 26, 2026 (JST)

**Scope.** Applied the shared policy explicitly to real Dot collaboration workers with synthetic, bounded tasks. This did not install or load AgentMD through Codex, and is not a benchmark rerun. We requested GPT-6 Luna / low, GPT-6.1 Terra / medium and GPT-6.2 Sol / medium; independent model/effort-resolution and billed-usage telemetry were not exposed. GPT-6.2 Astra was not dispatched: the checked tasks did not justify an additional configuration. No user Codex, paid infrastructure, outside data, new service, or external side effects in the trials.

- **Budget / deadline triage, Luna / low, single.** B was the only option meeting budget, PDF + checksum and deadline: ¥8,600 available, ¥100 left, 16:55 JST vs 17:00 JST. The worker verified the calculation but reported a write permission barrier and correctly returned BLOCKED on producing JSON. Primary verified and wrote the artifact in its authorized workspace; no model escalation for permissions.
- **Ledger implementation, Terra / medium, single.** First checkpoint reported PASS (8/8 supplied checks and an independently chosen boundary). The primary had predeclared a separate check: add integer cents `[9007199254740991, 2, -9007199254740991]` in a single account. Inputs and final sum are safe integers in JavaScript; intermediate sums need not be. Expected `2`, got `1`. Overall FAILED_VALIDATION, not success.
- **Matched ledger recovery.** From the same captured checkpoint and failure, Terra / medium solo recovery, Terra / medium incumbent and Sol / medium candidate generated byte-identical corrected artifacts (SHA-256 `841dc217426d3eb865b2475b46a88330001bf544327ba523229d73d6acbc8631`): accumulate exactly and convert only at the validated final boundary. Each passed 8/8 plus the cancellation check across three orders. At the recorded solve checkpoints, incumbent 01:43:46–01:43:54 UTC and candidate 01:43:58–01:44:11 UTC **did not overlap**, despite the dispatch intent. Matched solo recovery 01:44:06–01:44:11 UTC. These are local solve intervals, not end-to-end or model-inference-only latency. Two solving starts plus evidence exchange versus one start on the matched solo arm; amounts paid are unknown.
- **Evidence exchange and composition.** Each worker actually reviewed the other's hash, raw checks, and assumptions and replied; candidate's extra ordinary-object/replay checks supplemented rather than changed the conclusion. All writers stopped and the primary independently re-ran both suites. Incumbent retained, no lead transfer warranted after acceptance; ownership transfer to a different solving agent, cancel-in-flight and real enforced spend caps remain untested.
- **Controlled concurrent verification, distinct from the original solve.** Both accepted implementations ran a read-only check on 120,000 constructed permutations of replay, void, cancellation and account names, once each. Terra recorded 01:48:00.004–01:48:00.250 UTC and Sol 01:48:00.002–01:48:00.304 UTC, both exit 0. The overlapping interval is 246 ms. This establishes concurrent local test work under a synchronized checkpoint, not naturally overlapping model inference or faster completion via Buddy.
- **Minimal prompt retest.** A generic condition-to-evidence reminder alone still yielded the same held-out failure despite 8/8. A fresh Terra / medium run with the explicit boundary sentence (“a guarantee on inputs or final outputs need not hold during intermediate steps”) passed 8/8, independently tested that boundary, and passed the primary's held-out replay. This is one observed run per prompt variant, not a reliable causal estimate. The companion policy line forbids claiming overlap on dispatch alone. LUT, bindings, repository structure, routing options, recovery budget mechanism, and installer were not changed.

**Release checks.** Python `tomllib` parsed four unchanged model-only bindings with a common worker contract; the LUT prefix is byte-identical; only the two AgentMD policy lines above changed, to 15,109 UTF-8 bytes. The unchanged README installer passed `sh -n` and was not installed. Separate commands reproduced original and generic-retune failures and verified both recovery and final retune outputs. These checks support the finite results above, not general superiority, universal prompt compliance, or native Codex runtime behavior.


## LUT quantitative refresh — 2026-11-26 JST

**Active snapshot.** Supersedes only the numeric snapshot and missing-setting notation in sections A/A.1, which are retained as historical data; their derived comparisons remain historical. This follows the Deep Research review and a same-day source recheck. No change to routing, Buddy, recovery, worker TOMLs, installer or model bindings. Source observations were transcribed from public search-indexed first-party page excerpts; direct page fetches returned cache misses. The excerpts exposed the selected rows of the three comparison tables. No benchmark rerun or Codex performance test.

### Provider facts (O)

Sources checked 2026-11-26: [gpt-6-luna](https://developers.openai.com/api/docs/models/gpt-6-luna), [gpt-6.1-terra](https://developers.openai.com/api/docs/models/gpt-6.1-terra), [gpt-6.2-sol](https://developers.openai.com/api/docs/models/gpt-6.2-sol), [gpt-6.2-astra](https://developers.openai.com/api/docs/models/gpt-6.2-astra). [Deployment checklist](https://developers.openai.com/api/docs/guides/deployment-checklist) and [reasoning guide](https://developers.openai.com/api/docs/guides/reasoning) confirm L/T support all six efforts, S/A reject none. U denotes unsupported by the documented standard API; — denotes missing observations. Client-specific support still needs verification.

| Model | Input | Cache hit | 30-min cache write | Output |
| --- | --- | --- | --- | --- |
| L | .10 | .01 | .125 | .50 |
| T | 1 | .05 | 1.25 | 5 |
| S | 2 | .10 | 2.50 | 10 |
| A | 8 | .40 | 10 | 40 |

Units: Standard API USD per million text tokens, short context. For requests above 272K input tokens, the documented input/cache and output multipliers are 2 and 1.5, respectively, for the full request. Cache retention, processing tier and tools can add/change charges. Do not equate token prices, weighted benchmark cost, task cost and Codex-plan usage. Luna's exact provider cache-write price is .125, not AA's rounded .13 display.

### AA v5.0.2 capability and resource snapshot (B)

Sources checked 2026-11-26: [Terra vs Luna](https://artificialanalysis.ai/models/comparisons/gpt-6-1-terra-vs-gpt-6-luna), [Sol vs Terra](https://artificialanalysis.ai/models/comparisons/gpt-6-2-sol-vs-gpt-6-1-terra), [Astra vs Sol](https://artificialanalysis.ai/models/comparisons/gpt-6-2-astra-vs-gpt-6-2-sol). Remapped by explicit model/effort column headers, not index order. Eight component rows cover the same 22 supported configurations. AA-Omniscience remains unfilled, so this is eight of nine components, not a complete reproduction of the index. Each vector is n/l/m/h/x/max. Briefcase is Elo; others are displayed percentages.

| Metric | L | T | S | A |
| --- | --- | --- | --- | --- |
| Briefcase | 905/742/1096/1184/1234/1335 | 1224/1033/1190/1266/1330/1399 | U/1229/1494/1541/1579/1612 | U/1039/1406/1569/1593/1642 |
| Automation | 9.1/12.0/40.5/47.8/47.8/53.2 | 51.0/56.2/57.8/58.5/59.9/60.2 | U/63.2/70.3/69.9/70.6/71.3 | U/68.6/72.8/76.0/76.1/77.2 |
| Terminal | 1.5/0.0/2.5/5.1/8.1/12.6 | 26.3/15.2/31.8/42.9/46.5/56.6 | U/37.9/53.5/58.1/55.1/60.1 | U/51.0/59.1/62.1/66.2/64.6 |
| FrontierCode | 1.6/2.2/12.8/18.6/18.4/25.2 | 33.4/24.5/34.5/37.5/36.9/42.1 | U/31.4/41.4/40.2/42.8/44.4 | U/32.7/46.6/47.1/49.0/45.4 |
| GDP | 5.8/9.0/13.8/18.2/18.6/22.8 | 23.2/25.6/28.4/28.0/26.6/28.6 | U/28.6/29.2/28.8/28.4/30.0 | U/28.0/28.4/28.6/28.0/29.8 |
| HLE | 6.3/10.2/15.1/15.6/18.9/22.2 | 14.5/24.9/31.3/35.4/42.3/47.3 | U/34.5/50.7/58.3/61.8/64.0 | U/47.7/56.0/65.9/67.3/72.2 |
| CritPt | 5.0/9.5/27.5/31.0/37.0/42.5 | 33.5/50.5/56.5/61.5/60.5/68.0 | U/58.0/64.0/61.5/62.5/62.5 | U/61.0/67.5/71.5/70.5/71.5 |
| Science | 1.0/1.0/1.4/2.9/5.2/8.6 | 24.3/7.6/24.8/33.3/41.9/57.6 | U/37.1/60.5/67.6/66.7/67.6 | U/51.0/74.8/75.2/78.6/78.1 |

All 176 numeric component values were checked against the earlier snapshot. Only three changed: A.m 1407 → 1406; A.h 1570 → 1569; A.max 1643 → 1642 (Briefcase Elo). Treat them as a dated display refresh, not demonstrated errors in the prior transcription. The 88 overlapping component cells agreed across comparison pages; duplicates are not independent runs. The 22 index/cost pairs were unchanged.

| Model | n | l | m | h | x | max |
| --- | --- | --- | --- | --- | --- | --- |
| L | 9/.0714/1.7 | 10/.0051/.6 | 18/.0422/3.1 | 21/.0729/4.7 | 23/.10/6.3 | 28/.15/10.3 |
| T | 30/.23/2.6 | 29/.0713/1.2 | 38/.17/2.9 | 43/.26/4.4 | 45/.40/6.8 | 51/.96/14.9 |
| S | U | 41/.18/1.7 | 52/.41/3.6 | 55/.56/5.5 | 56/.65/6.5 | 57/1.01/10.5 |
| A | U | 46/.66/2.1 | 57/1.62/4.9 | 60/2.07/6.6 | 62/2.52/8.4 | 62/4.00/15.2 |

Cell units: index / weighted USD per Intelligence Index task / derived inference minutes per Intelligence Index task. The broad cost population is the full index, not an individual component. All 22 measured minute estimates were taken from the same recheck; 19 differ from the prior saved snapshot. The values also differ slightly from the earlier Deep Research retrieval because the speed proxy rolls. AA calculates time from output tokens and output speed averaged over recent endpoint measurements, not observed agent task duration. Compare task-specific evidence before these proxies. Per-setting uncertainty and hardware/clock/batch are not exposed in the checked table excerpts. Original protocol counts remain in A.1.

For offline reference only, single-request AA API performance (seconds, not agent completion time):

| Metric/model | n | l | m | h | x | max |
| --- | --- | --- | --- | --- | --- | --- |
| TTFA L | 1.28 | 2.22 | 5.96 | 10.67 | 17.69 | 69.25 |
| TTFA T | 2.27 | 2.80 | 5.70 | 13.87 | 37.75 | 196.77 |
| TTFA S | U | 1.97 | 4.33 | 19.55 | 52.09 | 116.99 |
| TTFA A | U | 2.98 | 3.42 | 27.73 | 57.16 | 170.18 |
| SingleE2E L | 26.84 | 22.74 | 31.46 | 39.79 | 53.54 | 152.47 |
| SingleE2E T | 36.48 | 24.89 | 32.67 | 58.30 | 125.91 | 425.23 |
| SingleE2E S | U | 51.61 | 56.82 | 102.38 | 159.59 | 277.74 |
| SingleE2E A | U | 75.64 | 80.69 | 140.98 | 190.99 | 439.11 |

TTFA = time to first answer token; SingleE2E = mean end-to-end duration for AA's single-request workloads. Endpoint speed/latency uses rolling five-day measurements. Do not treat the mean as a deadline bound. All 143 duplicate cells across the 13 extracted fields (8 capability, index, cost, derived time, TTFA, single-request E2E) agreed.

### Supplemental quality observations (B)

[AA-AnalystAgent](https://artificialanalysis.ai/evaluations/aa-analyst-agent), [launch/methodology](https://artificialanalysis.ai/articles/aa-analyst-agent), checked 2026-11-26. Private 80-question, 14-domain quantitative spreadsheet/document evaluation; five independent attempts per question in Stirrup. All-five-pass (pass^5): A.high 61.3%, A.xhigh 62.5%, A.max 62.5%. Other comparable pass^5 rows and matched cost/time cells were not recovered. Rounded ties do not establish equivalence. L.max pass@5 85.0% is a separate at-least-once metric, not comparable to these pass^5 values. The publisher's inference-time chart is a token/speed proxy, not task wall-clock.

[AA-3D v1.0](https://artificialanalysis.ai/evaluations/aa-3d), checked 2026-11-26. 55 briefs for interactive three.js scenes across seven domains, Stirrup offline isolated sandboxes, 250-turn or three-hour limit, blind human pairwise preference votes.

| Setting | Elo | Published 95% interval |
| --- | --- | --- |
| L.max | 1000 | Fixed anchor |
| S.max | 1259 ± 28 | 1231–1288 |
| A.max | 1318 ± 31 | 1286–1349 |
| T | — | — |

The anchor is not an absolute quality measure or a confidence interval. The displayed S/A intervals overlap; rank alone does not prove superiority. L.max $0.20/task is the reported benchmark-specific cost; matched S/A costs were not recovered, so no cross-model cost comparison is added. This tests interactive 3D artifact creation, not general UI operation. For both supplemental benchmarks, exact run hardware, clock, batch, per-run verification and all relevant pairwise outcome uncertainties are unavailable. Keep them separate from the full eight-component vectors.

### Held-out evidence

[MKA](https://artificialanalysis.ai/evaluations/mka), [AA-LCR v1.1](https://artificialanalysis.ai/evaluations/artificial-analysis-long-context-reasoning), general desktop/UI work, and joint model error/conditional rescue remain gaps: the Deep Research review did not retrieve complete comparable target-model/effort evidence. Do not infer missing quality from resource-only observations or use an older model as an exact substitute. The existing FrontierCode, official Terminal-Bench, Agent Arena, Firecrawl and Vals matched/qualified observations remain in the active LUT. No conditional rescue, pair complementarity, actual cost or performance gain is established by this refresh.

## Task transition and domain LUT extension — 2026-11-28 JST

### Evidence (B)

Sources checked 2026-11-28 JST: [Astra/Sol](https://artificialanalysis.ai/models/comparisons/gpt-6-2-astra-vs-gpt-6-2-sol), [Sol/Terra](https://artificialanalysis.ai/models/comparisons/gpt-6-2-sol-vs-gpt-6-1-terra), [Terra/Luna](https://artificialanalysis.ai/models/comparisons/gpt-6-1-terra-vs-gpt-6-luna), [capability methodology](https://artificialanalysis.ai/methodology/capability-indexes), [intelligence methodology](https://artificialanalysis.ai/methodology/intelligence-benchmarking). The eight component rows from the 2026-11-26 snapshot and 22 broad index/cost pairs remain unchanged in the checked comparisons. Remap by exact model/effort column labels. New domain indexes are published weighted composites, not independent tasks or calibrated success probabilities. Four domains cover 83 numeric cells of 88 supported settings (five healthcare/Terra observations not retrieved); eight unsupported Sol/Astra none cells are U. All vectors use n/l/m/h/x/max. No missing value is imputed.

| Domain index (index points) | L | T | S | A |
| --- | --- | --- | --- | --- |
| Finance & Accounting | 19/17/26/29/31/34 | 34/38/42/44/48/49 | U/42/52/55/55/57 | U/45/55/59/60/61 |
| Strategy & Ops | 17/17/34/38/39/43 | 40/42/45/47/49/50 | U/48/56/58/58/59 | U/49/57/62/62/63 |
| Legal | 17/16/24/27/28/32 | 28/37/40/42/44/46 | U/40/49/51/53/55 | U/46/53/56/57/59 |
| Healthcare & Medical | 16/16/27/29/30/35 | —/—/—/—/—/45 | U/41/48/51/52/53 | U/42/50/54/55/57 |

The publisher's domain weights reflect occupational activity mixes, not a particular user's acceptance criteria. Finance uses Briefcase 30%, Omniscience business knowledge 25%, HLE 15%, Omniscience non-hallucination 15%, Automation 10%, GDP 5%. Strategy/Ops: Automation 35%, Briefcase 30%, Omniscience business knowledge 25%, GDP 5%, Omniscience non-hallucination 5%. Legal: Omniscience legal knowledge 30%, Briefcase 25%, HLE 15%, Omniscience non-hallucination 15%, GDP 10%, Automation 5%. Healthcare: Omniscience medical knowledge 25%, Briefcase 25%, MLCR 15%, Automation 15%, Omniscience non-hallucination 10%, HLE 10%. These share component data, so do not average them with components or treat them as independent confirmations. No independent domain task counts or domain-specific costs/times are established. See original component protocol counts in A.1; Omniscience/MLCR complete comparable scores, Engineering/Economics indexes, hardware/clock/batch and setting-specific uncertainty were not recovered here.

### Resource refresh (B)

All 22 derived minutes are refreshed together. Index / weighted USD per index-task / derived minutes per index-task. These are benchmark-population references, not per-component costs, wall-clock agent completion, or Codex charges.

| Model | n | l | m | h | x | max |
| --- | --- | --- | --- | --- | --- | --- |
| L | 9/.0714/1.6 | 10/.0051/0.5 | 18/.0422/2.9 | 21/.0729/4.4 | 23/.10/6.0 | 28/.15/9.7 |
| T | 30/.23/2.7 | 29/.0713/1.3 | 38/.17/3.1 | 43/.26/4.6 | 45/.40/7.2 | 51/.96/15.8 |
| S | U | 41/.18/1.8 | 52/.41/4.0 | 55/.56/5.9 | 56/.65/7.1 | 57/1.01/11.4 |
| A | U | 46/.66/2.2 | 57/1.62/5.2 | 60/2.07/6.8 | 62/2.52/8.9 | 62/4.00/16.2 |

Single-request endpoint reference (seconds, not agent task duration):

| Metric/model | n | l | m | h | x | max |
| --- | --- | --- | --- | --- | --- | --- |
| TTFA L | 1.30 | 2.03 | 5.10 | 9.07 | 15.19 | 63.81 |
| TTFA T | 2.54 | 2.95 | 5.89 | 13.89 | 37.09 | 194.88 |
| TTFA S | U | 2.15 | 4.17 | 19.51 | 51.55 | 121.26 |
| TTFA A | U | 3.08 | 3.44 | 26.49 | 55.90 | 170.14 |
| SingleE2E L | 26.53 | 22.24 | 29.75 | 36.93 | 49.17 | 144.11 |
| SingleE2E T | 38.00 | 26.69 | 34.55 | 59.25 | 124.77 | 420.78 |
| SingleE2E S | U | 56.08 | 61.78 | 105.68 | 162.12 | 288.03 |
| SingleE2E A | U | 80.25 | 83.02 | 141.59 | 188.97 | 440.44 |

TTFA = first answer token; SingleE2E = mean endpoint end-to-end time across AA's single-request workloads. Rolling measurements, not guaranteed latencies. For the 7 newly extracted fields (four domain rows, minutes, TTFA, SingleE2E), 77 overlapping cells agreed, including missing markers. Repeated values are not new trials. Missing per-setting uncertainty, hardware, clock, batch and full workload metadata limit inference.

[AA release report, 2026-11-17](https://artificialanalysis.ai/articles/openai-has-the-2-model-in-the-intelligence-index-with-the-release-of-gpt-6-2-astra-and-gpt-6-2-sol/): S.max 55%, A.max 59% AA-Omniscience hallucination rate, a conditional guessing metric, not overall error frequency. [Terra release report, 2026-10-26](https://artificialanalysis.ai/articles/gpt-6-1-terra-pushes-the-cost-efficiency-frontier) states 38% but does not explicitly identify effort for this value in the retrieved text; retain as historical context, not an active exact-configuration cell. The full Omniscience accuracy and hallucination vectors remain incomplete. Do not assume lower guessing implies better factual accuracy or general trustworthiness.

### Policy change and scoped static audit (D)

A task transition point is a material change in the remaining work's requirements, phase, capability demand, evidence, risk, resources or a diagnosed blocker. A successful phase may lead to such a point; routine subtask/tool boundaries need not. It is a decision opportunity, not a mandate to spawn. Use the common LUT to nominate a materially justified candidate, then, if warranted, overlap both leads on the actual user task, exchange and integrate their tested results, and select a continuing lead based on task evidence. No mandatory failure first, periodic Buddy, synthetic routing trial, fixed model roles or required model-pair table. Existing recovery allowances, ownership, runtime fallbacks and final acceptance remain in effect.

Static regression cases: normal progress or cosmetic boundary → continue without Buddy; material transition with no justified alternative → continue; successful research-to-implementation transition with justified candidate and safe budgeted overlap → compare actual implementation work; candidate not better → retain adequate incumbent; candidate better or combined approach supported → transfer to the suitable lead; failed check with known local cause → correct rather than blindly switch; unavailable overlap or conflicting writes → use safe disclosed fallback. These are policy walkthroughs, not observed Codex traces or performance evidence.


## Matched task-resource and specialist LUT extension — 2026-11-28 JST

**Evidence (B), checked 2026-11-28 JST.** Vals AI leaderboard rows dated 2026-11-19; each triple is displayed benchmark score in percent / USD per test / duration per test, retaining displayed precision (including rounded hour/minute durations). These are publisher-reported observations, not AgentMD experiments. The [L](https://www.vals.ai/models/openai_gpt-6-luna), [T](https://www.vals.ai/models/openai_gpt-6.1-terra), [S](https://www.vals.ai/models/openai_gpt-6.2-sol), and [A](https://www.vals.ai/models/openai_gpt-6.2-astra) profiles report max effort; individual leaderboard-run effort was not independently verified. Consequently * marks qualified model-level evidence rather than a confirmed max configuration. Do not infer effort curves from these entries. Hardware, clock, batch, per-run seeds and paired outcomes were not established; USD/test and reported duration are specific to the benchmark, harness and snapshot. No conversion into live API bills, Codex usage or universal task times.

| Primary source | Scope | L* | T* | S* | A* |
| --- | --- | --- | --- | --- | --- |
| [EMB v1.1](https://www.vals.ai/benchmarks/emb-v1-1) | financial workbooks | 69.95/.14/17m21s | 73.33/.56/12m37s | 74.29/.84/14m47s | 76.03/2.80/21m26s |
| [Finance Agent v2.1](https://www.vals.ai/benchmarks/fabv2-1) | financial research | 56.84/.12/15m27s | 55.96/1.92/29m47s | 58.91/2.06/21m58s | 60.75/7.98/37m38s |
| [Legal Research Bench](https://www.vals.ai/benchmarks/legal_research) | US legal research | 30.29/.44/42m28s | 25.96/3.22/1h10m | 37.02/3.77/1h09m | 42.79/12.84/1h19m |
| [Vibe Code v1.1.1](https://www.vals.ai/benchmarks/vibe-code-v1-1-1) | application coding (OpenHands) | 65.31/1.35/37m00s | 75.52/6.00/37m30s | 79.48/3.23/47m51s | 78.57/7.92/44m12s |
| [Terminal-Bench-Science (Vals)](https://www.vals.ai/benchmarks/terminal-bench-science) | scientific terminal tasks (mini-swe-agent) | 4.29/.24/1h16m | — | 58.57/2.53/39m03s | 71.43/11.08/47m41s |
| [BioMysteryBench](https://www.vals.ai/benchmarks/biomysterybench) | biological data investigation | 61.48/.05/8m44s | — | 77.78/.34/7m02s | 80.74/1.49/8m30s |
| [ProofBench v1.1 (archived)](https://www.vals.ai/benchmarks/proof_bench) | formal verification | 64.00/.04/7m31s | — | — | — |
| [SWE-bench Multimodal](https://www.vals.ai/benchmarks/swebench-multimodal) | visual software issues | 37.50/.03/5m16s | — | — | — |
| [Vals Finance Index (composite)](https://www.vals.ai/benchmarks/finance_index) | GDP-weighted finance aggregate | 53.05/.15/22m01s | 53.32/1.55/29m25s | 56.66/1.77/26m47s | 57.31/6.23/40m12s |
| [Vals Legal Index (composite)](https://www.vals.ai/benchmarks/legal_index) | revenue-weighted legal aggregate | 62.20/.31/32m30s | 58.76/2.29/43m12s | 66.67/2.80/46m31s | 69.68/9.35/1h04m |
| [Vals Science Index (composite)](https://www.vals.ai/benchmarks/science_index) | equal-weight science aggregate | 28.38/.11/30m15s | — | 57.76/1.12/19m00s | 68.44/4.76/22m15s |

EMB v1.1 uses a shared financial workbook evaluation with equal weighting of seven categories and partial rubric credit; Vibe Code v1.1.1 uses OpenHands; Vals Terminal-Bench-Science uses mini-swe-agent and must not be merged with AA Terminal-Bench-Science. Legal Research Bench concerns US law only. ProofBench v1.1 is archived, with only a retrieved Luna observation; SWE-bench Multimodal covers software issues with visual context, not general image understanding. Vals Finance and Legal indexes are respectively GDP-weighted and revenue-weighted aggregates; Science Index equally weights BioMysteryBench, MysteryMechanismBench and Terminal-Bench-Science. Composite scores and resource aggregates are dependent on components. Same-row comparisons are more task-matched than comparisons using AA broad resource references, but uncertainty, effort and setup differences limit inferences. Missing cells remain —; no estimated task costs or times inserted.

### Specialist quality evidence and provenance

- Epoch FrontierMath Tier 4 v2 (advanced mathematics): T.max 92.7% ±4.1 pp; A.max 100.0%; L/S —. A's displayed perfect score is not a universal guarantee.
- Epoch GPQA Diamond (graduate science questions): T.max 94.3% ±1.5 pp; A.max 96.8% ±1.2 pp; L/S —.
- Epoch SimpleQA Verified (short factual questions, answer-required protocol): A.max 78.5% ±1.3 pp; L/T/S —. Accuracy is not a hallucination or abstention rate.
- Epoch Furniture Assembly (manual-guided spatial reasoning): rounded best model scores L 44%, T 79%, A 89%, S —; benchmark protocol uses highest supported API effort, individual run configuration not verified.
- OpenAI Terra internal difficult factual prompts: T.low 16.7%, T.max 4.3% error rate (lower is better); other settings/models —. Do not compare directly with SimpleQA or AA guessing-conditioned hallucination.

Sources: [FrontierMath Tier 4 v2](https://epoch.ai/benchmarks/frontiermath-tier-4-v2?tab=leaderboard&view=table), [GPQA Diamond](https://epoch.ai/benchmarks/gpqa-diamond), [SimpleQA Verified](https://epoch.ai/benchmarks/simple-qa-verified), [Furniture Assembly methodology](https://epoch.ai/benchmarks/furniture-assembly), [L model card](https://epoch.ai/models/gpt-6-luna), [T model card](https://epoch.ai/models/gpt-6-1-terra), [A model card](https://epoch.ai/models/gpt-6-2-astra), and [OpenAI Terra release](https://openai.com/index/introducing-gpt-6-1-terra/), checked 2026-11-28 JST. The Epoch ± values are displayed uncertainty margins in percentage points; no missing uncertainty margin was inferred. SimpleQA Verified uses 1,000 factual questions and an answer-required prompt, so is not a test of natural abstention. Furniture Assembly uses 60 assembly photographs, manuals and a bounded tool-use protocol; best scores are rounded model-profile values rather than exact effort-specific estimates. Terra internal error-rate observations are provider-reported and do not establish cross-model ranking. Resource values were not retrieved for these specialist scores, and no unsupported mapping to the four-model effort grid was made.

**Scope of static check (D).** The extension records 35 complete score/cost/duration triples (24 direct benchmark observations and 11 composite observations); two Science Index scores already occurred in the previous LUT. Five explicitly effort-labeled Epoch scores, three rounded spatial scores and two provider error-rate values are additional references. The FrontierCode wording is clarified to individual pass rates of 48.2% each, not a joint pass rate (see existing individual rows). All existing component and resource vectors are retained, no existing Buddy/decision/recovery rules change. Remaining gaps include full 22-setting matched task resources, long context, direct desktop operation, instruction following, creative writing, and joint failure/recovery data. AA component-specific resource graphs were not reliably extractable as numeric tables; values were not guessed. Static transcription/structure validation only; no measured AgentMD/Codex runtime, speedup, cost saving or performance improvement is claimed.


## General-purpose routing LUT — 2026-11-28 JST

### Purpose, classification and provenance

This maintenance update constructs an expanded general-purpose evidence lookup, not a universal optimum or a personality policy. B denotes publisher observations; D denotes transparent arithmetic or routing design. Actual runtime settings and task outcomes still require runtime evidence. Existing 22-setting vectors, Vals triples and historical snapshots remain distinct populations. No model-performance experiment was run.

| Field | Definition / admissibility | Unit / type |
| --- | --- | --- |
| Workload key | Task family, modality/language, input length, tools, harness, version and snapshot; missing fields stay unknown | Categorical record |
| Configuration | Exact model and reported effort; model-only evidence cannot populate an effort cell | Categorical pair |
| Quality | Preserve rubric/accuracy/full-pass/all-five-pass/preference definitions; no calibrated current-task probability | Dimensionless score, %, or rating points as labeled |
| Cost | Source total or transparently derived mean with matching workload denominator; exclusions retained | USD (non-SI currency), nonnegative scalar |
| Runtime | Source sum of execution durations, observed latency or inference proxy must remain distinct | SI seconds; active ALE display in hours, 3,600 s per hour |
| Count | Source tasks/questions, runs, attempts and votes are different populations | 1, nonnegative integer |
| Unknown | Missing does not mean zero, failure or unsupported; U remains documented unsupported | Marker |

Evidence fit is not established by a high score alone. Do not mix providers' harnesses, benchmark revisions, effort levels, resource denominators or source time windows to construct dominance. Prefer directly relevant observations without suppressing useful complementary evidence. No arbitrary task weights, hard pass threshold or fixed best-model map is added.

### ALE source snapshot and exact records (B)

Primary [leaderboard](https://agents-last-exam.org/leaderboard) and its linked [public JSON](https://agents-last-exam.org/api/demo/leaderboard/v1.1), retrieved 2026-11-28 JST. The endpoint was discovered in the page's linked static JavaScript and read as data; no site code was executed. Snapshot JSON SHA256: `eb256326e54beca1d90341cacc6d00927cb239dd06b00c67064545ae319d11b0`.

`resultsUpdatedAt` = `2026-11-18T01:01:54.886914Z`; `costRatesAsOf` = `2026-11-17`. Benchmark reference [commit 2e91edd](https://github.com/rdi-berkeley/agents-last-exam/commit/2e91edd3cd26baa35a38127c90c8e5241dfbe62f), 2026-10-27. The page warns runs can predate the reference; do not claim this exact revision was used by every run. All admitted records have `harness=codex`, `split=v1.1`, `runs=tasks=splitTasks=122`; efforts are directly in `harnessVariant=reasoning-*`, not inferred from a model profile. There are 86 Linux and 36 Windows tasks; these are dependent subsets and not pure GUI/CLI classes. Target Luna is absent from all 41 snapshot rows; no old Luna substitution. Display defaults are T.max, S.xhigh, A.xhigh, not uniformly max.

Raw fractions and seconds below retain source precision; missing input-token totals are null, never zero. `costSource=list` for every target record. No hidden assumption about which cost components are omitted is inferred from null token aggregates.

| Setting | avgScore fraction | passRate fraction | Perfect runs | totalDurationS | totalCostUsd |
| --- | --- | --- | --- | --- | --- |
| T.n | 0.6421414878786305 | 0.36885245901639346 | 45 | 225730 | 38.91 |
| T.l | 0.6639686667831649 | 0.4016393442622951 | 49 | 158910 | 18.08 |
| T.m | 0.6492203268418958 | 0.3442622950819672 | 42 | 232035.518 | 28.59 |
| T.h | 0.6455196236140132 | 0.36065573770491804 | 44 | 287594.926 | 35.13 |
| T.x | 0.70368886837223 | 0.4098360655737705 | 50 | 346667 | 59.95 |
| T.max | 0.6978073386766798 | 0.4180327868852459 | 51 | 448551.26 | 106.80 |
| S.l | 0.666509910606572 | 0.3524590163934426 | 43 | 62650.439 | 34.84 |
| S.m | 0.7025776982820281 | 0.38524590163934425 | 47 | 71544.679 | 74.30 |
| S.h | 0.7203595245098597 | 0.4016393442622951 | 49 | 96497.997 | 89.41 |
| S.x | 0.7248200922037955 | 0.4180327868852459 | 51 | 114017.169 | 111.32 |
| S.max | 0.7304398616455706 | 0.4016393442622951 | 49 | 165914.747 | 169.46 |
| A.l | 0.6576912195967535 | 0.3770491803278688 | 46 | 49366.525 | 63.56 |
| A.m | 0.7206460188560668 | 0.4098360655737705 | 50 | 66106.722 | 139.43 |
| A.h | 0.7596382128009247 | 0.45901639344262296 | 56 | 84514.722 | 265.07 |
| A.x | 0.7833238426868974 | 0.47540983606557374 | 58 | 104791.47 | 372.01 |
| A.max | 0.7760714844257192 | 0.4672131147540984 | 57 | 155586.833 | 571.17 |

Score is mean partial credit; full-pass is the share of perfect runs. Missing scores count zero; failed/timed-out runs retain their graded credit. Runtime sums per-task average agent execution times over completed/timed-out runs, excluding setup/evaluation. It is not suite elapsed wall-clock time. Cost sums per-task mean model API estimates using recorded usage and dated list rates, with cache and long-context treatment where recorded. Tool fees are excluded; missing usage can understate cost. Individual Codex build, prompts beyond effort, hardware/clock, batch/concurrency, paired outcomes and uncertainty were not recovered. Documentation example concurrency/timeouts/retries do not establish these runs' settings.

Active formatting rounds score/full-pass to 0.1 percentage point and divides seconds by 3,600 for hours rounded to 0.01; monetary source totals retain cents. Dimensional check: converting seconds to hours changes display units, not runtime scope; no USD is added to time. Exact passes divided by 122 reproduce every source pass fraction. Hours and percentages are derived displays, not new measurements.

Validity limitation: [Epoch's review](https://epoch.ai/benchmarks/agents-last-exam/review) flags 22 of 50 inspected tasks as admitting full credit without intended work. The [publisher's response](https://agents-last-exam.org/blogs/verifier-check) disputes practical exploitation frequency and acknowledges two network restrictions were only in task cards invisible to agents. Do not infer that later enforcement retroactively fixes this snapshot. Active evidence carries this caveat and cannot solely decide a switch or establish isolated GUI/instruction-following skill. See also [release docs](https://agents-last-exam.org/docs/ale/pages/configure.html) and [harness docs](https://agents-last-exam.org/docs/ale/pages/agents.html).

### LiveBench 2.0 suite snapshot (B) and cost normalization (D)

Primary [site](https://livebench.ai/) / [methodology](https://livebench.ai/#/methodology), release-data label `20261106`, retrieved 2026-11-28 JST. The linked static [UI data loader](https://livebench.ai/static/js/main.099aad9b.js) identifies these public source files and explicitly declares effort `max` for all four exact target model IDs; run notes say highest supported effort unless the name specifies another setting. This is publisher-reported benchmark configuration, not AgentMD-observed telemetry. A hardcoded November 11 page-update label is not an individual run date, including for later-added models.

| Primary data URL | Observed SHA256 |
| --- | --- |
| [ table.csv ](https://livebench.ai/data/20261106/table.csv) | cd68d30168e61337b3285e9020e6242746cc18a3892d855580b51ec72d266a0a |
| [ cost.csv ](https://livebench.ai/data/20261106/cost.csv) | 95a68251660318b70eff30c75bd87b7508e946af0fd2fab9fef024e2e4f17ed3 |
| [ categories.json ](https://livebench.ai/data/20261106/categories.json) | b5366a69719445fa91e970de6f248c666115bbc5d8b8d134f33bb5fcc399a7ce |
| [ breakdown.json ](https://livebench.ai/data/20261106/breakdown.json) | e3816cfde6682ab1062c738d9b5758a47c308249b27ee4f1617e1d2bbe780500 |
| [ notes.json ](https://livebench.ai/data/20261106/notes.json) | 812556975b3e6306ad413a5be8918bd7990a8b43291e6955ee737939c4cc3a10 |

The source data are mutable; hashes identify this retrieved snapshot. Current direct files resolve stale search-cache variants (Terra Agentic 55.3, not 56.2). Store suite observations, not mixed cached aggregates.

| LiveBench suite | Count | L.max | T.max | S.max | A.max |
| --- | --- | --- | --- | --- | --- |
| Agentic | 18 | 24.7/0.6669 | 55.3/6.1459 | 63.6/4.0741 | 70.8/17.0234 |
| Design | 25 | 76.1/0.0306 | 79.7/0.2702 | 80.0/0.4866 | 82.8/1.9926 |
| Coding | 24 | 70.8/0.1356 | 89.2/1.2981 | 83.7/1.1299 | 91.9/5.1222 |
| Browser Use | 25 | 70.3/0.1932 | 93.1/1.9496 | 88.2/0.6568 | 93.0/2.5049 |
| Data Analysis | 150 | 73.4/0.0166 | 82.3/0.0628 | 81.1/0.0985 | 84.1/0.3547 |
| Research | 22 | 48.5/0.4261 | 79.1/1.4620 | 90.1/2.0750 | 91.5/6.6314 |
| Reasoning | 202 | 81.8/0.0214 | 88.7/0.0403 | 90.6/0.0312 | 91.6/0.1323 |

Cells are published suite score (0–100) / derived USD per source task or short question. The source totals below are divided by the matching `nq_*` column with Decimal arithmetic and rounded half-up to four decimal places. Four places preserve transcription and are not a claim about measurement uncertainty. Counts agree across all four models and the breakdown file. Each source question can include the publisher's possible rerun, so this denominator does not estimate cost of one API call or imply one physical solve attempt.

| Suite | Source count | L total USD | T total USD | S total USD | A total USD |
| --- | --- | --- | --- | --- | --- |
| Agentic | 18 | 12.0049 | 110.6270 | 73.3343 | 306.4219 |
| Design | 25 | 0.7642 | 6.7559 | 12.1646 | 49.8162 |
| Coding | 24 | 3.2545 | 31.1532 | 27.1185 | 122.9317 |
| Browser Use | 25 | 4.8303 | 48.7405 | 16.4201 | 62.6222 |
| Data Analysis | 150 | 2.490824 | 9.427008 | 14.768816 | 53.204464 |
| Research | 22 | 9.3740 | 32.1644 | 45.6505 | 145.8908 |
| Reasoning | 202 | 4.323805 | 8.139872 | 6.302824 | 26.715417 |

Unit check: reported suite USD divided by the dimensionless count gives USD per defined source question. For example Sol Browser Use totals 16.4201 USD across 25 questions, yielding 0.6568 USD/question after rounding. This is not all-in operational cost. The methodology prices model calls at list rates including cached input, excluding fixed starting state and harness helper calls. Infrastructure, tool fees, handoff and integration costs remain outside the established scope. No conversion from overall cost-per-success is used.

One recorded run per suite/model; unmeasurable items receive one rerun and then zero if still unmeasurable. This scoring rule is source behavior, not permission to fill AgentMD missing cells with zero. Agentic covers changing applications, long operations, systems and optimization. Design covers visual/structural DOCX/PDF/presentation checks; Research uses written-report rubrics. Coding uses merged-PR bugs in frozen code and penalizes regressions. Browser Use tests screenshot-driven web application tasks, not desktop OS control. Data Analysis and Reasoning are short no-tool questions, with equal subcategory aggregation; do not pool their prices with agentic workloads. Scores are not universally binary success rates. Exact per-row harness build, dates, HW/clock/batch, repeated-run uncertainty and paired outcomes remain unknown.

Excluded aggregates: `notes.json` says equal suite weights, while `categories.json` and rendering code weight Agentic 2, Coding/Design 1.5, others 1. Runtime therefore omits Overall and overall cost-per-success. The hidden `llm_time.csv` is intentionally omitted: UI sets `hasTime=false`, and its Data Analysis/Reasoning denominators differ from quality/cost counts. No conversion to wall-clock time is warranted.

### AA exact max-only record extension (B)

Primary [Omniscience page](https://artificialanalysis.ai/evaluations/omniscience), retrieved 2026-11-28 JST, exposes public serialized chart model records. JSON was parsed without executing scripts or estimating graph coordinates. Each of these four records explicitly labels `effort.slug=max`; missing fields are null on this retrieved surface. Other efforts are not imputed. Exact source UUIDs:

| Alias | Release slug | Source UUID |
| --- | --- | --- |
| L | gpt-6-luna | 6fb13851-40ce-4bda-ad3f-6b38e0c5daa7 |
| T | gpt-6-1-terra | b0c462cf-f2d0-4126-9434-28db9502219f |
| S | gpt-6-2-sol | a1a84b18-e8c9-48fb-8e04-6003bd9f6ff4 |
| A | gpt-6-2-astra | 75c1b0b8-9db3-4c7e-95be-d74e59defee4 |

The following keys are relative to the source model record; raw fractions are not percentages, except `omniscience` which is already net points. Preserve original numeric precision as serialization, not statistical precision.

| Source key | L.max | T.max | S.max | A.max |
| --- | --- | --- | --- | --- |
| omniscience | -8.26666666666667 | 29.5666666666667 | 40.3666666666667 | 50 |
| omniscienceBreakdown.accuracy | 0.3963333333333333 | 0.47633333333333333 | 0.6163333333333333 | 0.6856666666666666 |
| omniscienceBreakdown.hallucinationRate | 0.7934842628382109 | 0.3450031826861871 | 0.5543006081668115 | 0.5906680805938495 |
| lcr | 0.833333333333333 | 0.826666666666667 | null | null |
| analystAgent | 0.4375 | null | 0.5375 | 0.625 |
| mmmuPro | 0.796531791907514 | 0.846820809248555 | null | 0.894797687861272 |

| AA max-only metric | L.max | T.max | S.max | A.max |
| --- | --- | --- | --- | --- |
| Omniscience net points (higher better) | -8.3 | 29.6 | 40.4 | 50.0 |
| Omniscience accuracy % | 39.6 | 47.6 | 61.6 | 68.6 |
| Omniscience conditional hallucination % (lower better) | 79.3 | 34.5 | 55.4 | 59.1 |
| AA-LCR v1.1 accuracy % (legacy) | 83.3 | 82.7 | — | — |
| AA-AnalystAgent all-five-pass % | 43.8 | — | 53.8 | 62.5 |
| MMMU-Pro accuracy % (AA setup) | 79.7 | 84.7 | — | 89.5 |

Active percentages multiply source fractions by 100 and round half-up to 0.1 point; net points only round. All units are dimensionless; net points are on -100 to 100. Net score gives positive credit for correct answers, negative credit for incorrect answers and neutral credit for abstention. Conditional hallucination divides incorrect answers by all non-correct responses, including partial answers/abstentions in the denominator; it is not the overall incorrect fraction. Omniscience v1.1 has 3,000 questions and one repeat with tools off. The [original paper](https://arxiv.org/abs/2511.13029) concerns v1's 6,000 questions and does not establish these v1.1 scores.

[AA-LCR v1.1](https://artificialanalysis.ai/evaluations/artificial-analysis-long-context-reasoning) is a legacy 100-question long-document pass@1 benchmark, about 10k–100k tokens using cl100k_base, removed from Intelligence Index v5.0. [AA-AnalystAgent](https://artificialanalysis.ai/evaluations/aa-analyst-agent) has 80 questions across 14 domains, five attempts each, Stirrup, 100-turn cap; `analystAgent` is all-five-pass, not `analystAgentPassAtK`. A.max 62.5% already existed in the active LUT; A.high/xhigh 61.3/62.5% remain. [MMMU-Pro](https://artificialanalysis.ai/evaluations/mmmu-pro) uses AA's 1,730-question, ten-option, regex-scored implementation. Its background description of the full 3,460-question benchmark is not this implementation denominator. L/T/A fractional scores correspond to 1,378/1,465/1,548 correct answers out of 1,730; consistency is not proof of every run condition. See [AA implementation methodology](https://artificialanalysis.ai/methodology/intelligence-benchmarking).

There are 20 nonmissing numeric cells across six metrics, with dependencies and prior observations (including A.max AnalystAgent and previously rounded S/A hallucination). They are not 20 independent trials. Full 22-setting curves, matched cost/time, CIs and exact run HW/clock/batch are absent. Do not synthesize costs from available token counts without resolving caching, prices, populations and repeats.

### Design preferences and explicit coverage gaps

[DesignArena text-to-HTML](https://www.designarena.ai/leaderboard/code), timestamp 2026-11-27 16:19 UTC (2026-11-28 01:19 JST): Sol rating 1463 / 1,715 battles; Astra 1448 / 2,190. [Method](https://www.designarena.ai/about): anonymous human choices and Bradley–Terry ratings. These labels do not establish effort. Luna/Terra appear in controls but their numerical rows were not retrieved. Different prompts/opponents/vote populations prevent treating this as a matched correctness trial. Personal aesthetics, functional correctness, accessibility and creative prose are not established. Percentage MoE cells versus Elo-confidence wording and reported time aggregation are unresolved; the active LUT excludes intervals/time rather than inventing meanings.

| Coverage need | Primary benchmark or source | Admission status |
| --- | --- | --- |
| Direct desktop operation | [OSWorld 2.0](https://osworld-v2.xlang.ai/) | Benchmark exists; exact target-model rows unretrieved. Browser and ALE mixtures are not substitutes. |
| Verifiable instruction constraints | [IFEval paper](https://arxiv.org/abs/2311.07911), [AA IFBench](https://artificialanalysis.ai/evaluations/ifbench) | No matched target values admitted; raw max IFBench fields null. |
| Creative prose | [Arena creative writing](https://arena.ai/leaderboard/chat/text/creative-writing) | Category exists; exact target ratings unretrieved. |
| Japanese / multilingual work | [Global-MMLU-Lite](https://artificialanalysis.ai/evaluations/global-mmlu-lite) | Target max fields null; Japanese-specific long-document fit remains unestablished. This is not a claim no relevant benchmark exists. |
| Engineering / economics aggregates | [Engineering](https://artificialanalysis.ai/indexes/engineering), [Economics](https://artificialanalysis.ai/indexes/economics) | Index methods exist, exact target values unretrieved; do not synthesize composite scores. |
| Conditional rescue / joint failure | Individual marginal scores are insufficient | No candidate-pair benefit or Buddy gain is inferred. |

### Routing design and source corrections (D)

The active task-to-evidence index selects relevant evidence rather than assigning a model a permanent occupation. It keys on remaining capability, inputs, tools and acceptance conditions. Compatible actual task results take priority; benchmark observations nominate candidates without proving adequacy. Model-only, proxy and composite evidence stays qualified. Unresolved quality/cost/time tradeoffs use the user's expressed priorities; no generic style, aesthetics, personality or jurisdiction preference is installed. Existing transition/Buddy/recovery rules remain unchanged. A bounded actual-work check is appropriate for a material unknown; routine work must not fetch benchmarks or load this archive.

Date correction: the previous matched-resource section's blanket November 19 leaderboard date was too broad. On this retrieval, [Vibe Code v1.1.1](https://www.vals.ai/benchmarks/vibe-code-v1-1-1) displays November 21, 2026; the other ten referenced Vals pages display November 19. Historical numeric triples remain preserved; these dates must not be represented as individual run dates. This update does not claim a new complete numeric Vals refresh.

### Scoped validation record

Performed on the completed local revision, 2026-11-28 JST:

- PASS: parsed the four TOMLs with Python tomllib; exact model IDs, identical worker contract and no fixed effort; all four byte-identical to the base. The eight-file layout and local Markdown links/anchors passed.
- PASS: all original eight component vectors, four domain vectors, broad references, endpoint observations, token rates, 35 Vals triples and specialist rows retained. Earlier duplicate references were consolidated without losing measurements; dated source history remains available.
- PASS: all 16 ALE rows / 64 numeric cells reproduce the primary JSON, including integer pass counts and the stated seconds-to-hours display conversion. All 28 LiveBench score/cost pairs reproduce the primary CSVs with matching denominators, and all 20 AA nonmissing cells reproduce explicit max records. Missing values remain missing. DesignArena's two rating/vote records were checked against the primary rendered table.
- PASS: installer POSIX syntax and an isolated installation; six existing-file blockers and a dangling symlink prevented overwrite. Only the target-directory assignment was redirected to a task-specific temporary directory. No real user profile or CODEX_HOME/HOME value was changed. The original installer snippet is byte-identical to the base.
- PASS: decision baseline and all Buddy/recovery text outside the LUT are byte-identical to the base. A separate scoped review checked the lookup index, source comparability and ALE data. Compression briefly broadened an unknown-metadata statement to imply confirmed effort might be unknown; this was corrected to other/unreported metadata and the affected clauses checked.
- Runtime AGENTS.md: 28,523 UTF-8 bytes (27.85 KiB); LUT from its level-two heading to before Buddy: 16,755 bytes (16.36 KiB). Remaining space to the documented 32,768-byte combined guidance default: 4,245 bytes (4.15 KiB). Existing project guidance may consume that remainder; this is not a measurement of instructions loaded in any client.

Acceptance hypothesis for this maintenance task: active data can be regenerated from identified source fields with zero transcription/denominator mismatches, unsupported and missing settings stay distinct, required static checks pass, and the runtime stays within the chosen 28 KiB maintenance budget. Counterexamples include a wrong effort label, converting suite time into elapsed latency, mixing source populations, or a known setting hidden by an overbroad unknown label. The checks above address these finite conditions; they do not prove general model behavior.

Uncertainty remains in benchmark validity, task transfer, snapshot freshness, sampling, missing run metadata and user-specific tradeoffs. No combined performance uncertainty or coverage factor can be computed from these incomplete and heterogeneous records. No model/Codex run, comparative task success, measured cost saving or latency improvement was established. Further numeric refreshes require their own source snapshot; this scoped audit is complete.
