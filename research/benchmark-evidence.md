# AgentMD — Active evidence registry

**Checked:** 2026-11-28 JST. The [task-transition and domain LUT extension](#task-transition-and-domain-lut-extension--2026-11-28-jst) adds professional capability indexes and refreshes resource references without changing the 176 original component scores. The [2026-11-26 component snapshot](#lut-quantitative-refresh--2026-11-26-jst) supersedes the earlier AA component snapshot and records provider/supplemental observations; the 2026-11-28 extension supersedes its rolling resource references. Historical tables and audits are preserved below. This is an offline maintenance reference, not routine agent context. Earlier snapshots and superseded policies remain in Git history. No new model-performance experiment was run for the benchmark snapshot. The strategy audit on 2026-11-26 preserves the numeric snapshot, replaces the active proxy-frontier policy and records the limits of the logical baseline.

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
