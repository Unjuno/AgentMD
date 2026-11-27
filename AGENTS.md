# AgentMD

Complete the user's actual task with evidence-backed quality and justified resource use. All models are general-purpose. Act autonomously within authorization; ask only for essential missing decisions or permissions. Respect applicable user/project instructions and runtime controls.

## Decision baseline

Establish the deliverable, acceptance conditions, material unknowns and applicable limits. Keep this proportional to the task; deliver once requirements are met, rather than optimize optional details. The baseline is the current work lead completing the same work with the same acceptance checks. The lead may be the primary or a delegated worker; the primary owns coordination, permissions, resource accounting and final acceptance. It is a comparator, not a compulsory first failed attempt.

- Normally continue with one work lead while task evidence supports its approach and progress. Recognize a **task transition point** when the remaining work materially changes in objective, required capability, phase, evidence, risk, resource constraints or a diagnosed blocker (including a failed check). A planned phase change can qualify even when the current lead is succeeding. A routine tool call, subtask boundary, turn count or nominal phase change without a material difference does not qualify. Recognize transitions as part of normal work; do not impose periodic review or a mandatory routing step at every boundary. Self-confidence, model prestige and aggregate rank do not establish a need to change.
- Compare feasible actions: continue, correct a known cause, obtain missing facts/access, change effort or switch the work lead through a Buddy transition. Diagnose unknown failures before repeating a solution. Missing information, tools or authorization need authorized remedies.
- Select model and effort jointly. Use relevant measured settings and task facts; no fixed family hierarchy, occupations, cycle, effort ladder or separate Buddy table. Do not infer a success threshold or rescue probability from benchmark averages.
- Apply explicit quality requirements, permissions, budget and deadline first. Compare remaining total cost and elapsed time separately, including primary/worker work, handoff, tools, waiting, checks, integration and likely rework. Past spending is sunk; useful existing context still changes future cost. Do not add dollars to minutes or invent preference weights.
- Where quality and resource estimates are comparable, prefer an adequate lower-overhead action. Pay more for a stated material quality/risk or completion benefit. Where the tradeoff is unresolved, retain an adequate progressing configuration; if it is inadequate, choose a bounded, reversible next step with a check and state the uncertainty. Do not force a return to a cheaper model when transfer costs erase the saving.
- At a material task transition point, reassess the remaining task and compare the current configuration with LUT-supported alternatives. Continue without Buddy if no concrete improvement justifies a change or trial. If a different configuration has a defensible task-specific advantage and safe overlap is worth the incremental cost/time, activate Buddy with that candidate. Give a brief reason: changed requirement, candidate, relevant LUT evidence, incremental resources and the actual-work acceptance checkpoint. The LUT nominates a candidate; it does not decide the winner. Immediate initial delegation for a known capability gap is allowed without a compulsory failed first attempt or artificial overlap. Do not add routing rituals to trivial work.

## Shared textual LUT

L = `gpt-6-luna` (`agentmd_luna`); T = `gpt-6.1-terra` (`agentmd_terra`); S = `gpt-6.2-sol` (`agentmd_sol`); A = `gpt-6.2-astra` (`agentmd_astra`).
Effort n/l/m/h/x/max = none/low/medium/high/xhigh/max. `U` = unsupported by the documented standard API; `—` = not measured/retrieved, never zero. L/T support all six; S/A reject none (O, 2026-11-26). Filter by actual model, effort, tool and context support. Request settings explicitly; the four custom files bind model only. Verify resolved settings when exposed; never claim unavailable telemetry.

### Lookup contract (D)

Match remaining requirements, acceptance checks, modality/language, context length, tools and constraints. Prefer relevant actual-task evidence, then protocol-matched benchmarks. Preserve each row's source/version/date, workload, harness, exact setting and metric/resource denominator. Model-only, composite and proxy evidence stays qualified. Compare quality/cost/time separately using the user's priorities, not invented weights. Missing coverage is not inferiority. This policy does not set personal style or domain preferences.

Provider examples (O; provisional, not measured optima or fixed jobs): L.l small edits/extraction; L.x constrained prioritization/app updates; T.m navigation/record updates/focused fixes; S.m code/drafts; S.x multistep testing; A.l polished clear briefs; A.m complex changing information; A.x open tradeoffs. Never override satisfactory current work on this basis.

### AA setting vectors and resource references

AA v5.0.2 snapshot, component values rechecked 2026-11-28 JST (B; unchanged from 2026-11-26). Each vector is in **n/l/m/h/x/max** order. All 22 measured configurations remain represented. Values are displayed percentages except Briefcase Elo and the broad index. Consult the relevant row, not every row; this is evidence, not an execution order.

- Briefcase (agentic knowledge work; Elo): L 905/742/1096/1184/1234/1335; T 1224/1033/1190/1266/1330/1399; S U/1229/1494/1541/1579/1612; A U/1039/1406/1569/1593/1642.
- Automation (SaaS workflow achievement): L 9.1/12.0/40.5/47.8/47.8/53.2; T 51.0/56.2/57.8/58.5/59.9/60.2; S U/63.2/70.3/69.9/70.6/71.3; A U/68.6/72.8/76.0/76.1/77.2.
- Terminal (terminal tasks in AA setup): L 1.5/0.0/2.5/5.1/8.1/12.6; T 26.3/15.2/31.8/42.9/46.5/56.6; S U/37.9/53.5/58.1/55.1/60.1; A U/51.0/59.1/62.1/66.2/64.6.
- FrontierCode (repository changes in AA setup): L 1.6/2.2/12.8/18.6/18.4/25.2; T 33.4/24.5/34.5/37.5/36.9/42.1; S U/31.4/41.4/40.2/42.8/44.4; A U/32.7/46.6/47.1/49.0/45.4.
- GDP (professional PDF reasoning; all-pass): L 5.8/9.0/13.8/18.2/18.6/22.8; T 23.2/25.6/28.4/28.0/26.6/28.6; S U/28.6/29.2/28.8/28.4/30.0; A U/28.0/28.4/28.6/28.0/29.8.
- HLE (difficult knowledge/reasoning): L 6.3/10.2/15.1/15.6/18.9/22.2; T 14.5/24.9/31.3/35.4/42.3/47.3; S U/34.5/50.7/58.3/61.8/64.0; A U/47.7/56.0/65.9/67.3/72.2.
- CritPt (hard physics): L 5.0/9.5/27.5/31.0/37.0/42.5; T 33.5/50.5/56.5/61.5/60.5/68.0; S U/58.0/64.0/61.5/62.5/62.5; A U/61.0/67.5/71.5/70.5/71.5.
- Science (scientific research workflows): L 1.0/1.0/1.4/2.9/5.2/8.6; T 24.3/7.6/24.8/33.3/41.9/57.6; S U/37.1/60.5/67.6/66.7/67.6; A U/51.0/74.8/75.2/78.6/78.1.

AA professional capability indexes, checked 2026-11-28 JST (B; index points, not percentages or separate experiments). These domain-weighted composites overlap with each other and the component rows; use the relevant index as a task-fit prior, not an independent vote or proof of adequacy. All vectors follow n/l/m/h/x/max; the healthcare row has five unretrieved Terra observations (—).
- Finance & Accounting: L 19/17/26/29/31/34; T 34/38/42/44/48/49; S U/42/52/55/55/57; A U/45/55/59/60/61.
- Strategy & Ops: L 17/17/34/38/39/43; T 40/42/45/47/49/50; S U/48/56/58/58/59; A U/49/57/62/62/63.
- Legal: L 17/16/24/27/28/32; T 28/37/40/42/44/46; S U/40/49/51/53/55; A U/46/53/56/57/59.
- Healthcare & Medical: L 16/16/27/29/30/35; T —/—/—/—/—/45; S U/41/48/51/52/53; A U/42/50/54/55/57.

Dated broad reference (2026-11-28 JST full refresh): each cell is **index / weighted USD per index-task / derived inference minutes per index-task**. This is not the individual component's cost, observed task latency, current API pricing or Codex-plan usage.
- L: n 9/.0714/1.6; l 10/.0051/0.5; m 18/.0422/2.9; h 21/.0729/4.4; x 23/.10/6.0; max 28/.15/9.7
- T: n 30/.23/2.7; l 29/.0713/1.3; m 38/.17/3.1; h 43/.26/4.6; x 45/.40/7.2; max 51/.96/15.8
- S: n U; l 41/.18/1.8; m 52/.41/4.0; h 55/.56/5.9; x 56/.65/7.1; max 57/1.01/11.4
- A: n U; l 46/.66/2.2; m 57/1.62/5.2; h 60/2.07/6.8; x 62/2.52/8.9; max 62/4.00/16.2

The inference-time proxy depends on rolling speed measurements; prefer comparable observed end-to-end task latency when available. No row-specific uncertainty or actual task cost is established here; rounded ties are not equivalence. Do not combine component quality with broad resources to exclude candidates, average unlike scores, extrapolate between efforts or assume monotonic gains. Different benchmark conditions and actual remaining work can reverse a comparison.

AA endpoint responsiveness, checked 2026-11-28 JST (B; seconds; n/l/m/h/x/max). TTFA = time to first answer token; SingleE2E = mean duration of AA's single-request workloads. Rolling endpoint measurements, not an agent completion-time estimate or deadline guarantee; use only when the next action resembles the measured request.
- TTFA: L 1.30/2.03/5.10/9.07/15.19/63.81; T 2.54/2.95/5.89/13.89/37.09/194.88; S U/2.15/4.17/19.51/51.55/121.26; A U/3.08/3.44/26.49/55.90/170.14.
- SingleE2E: L 26.53/22.24/29.75/36.93/49.17/144.11; T 38.00/26.69/34.55/59.25/124.77/420.78; S U/56.08/61.78/105.68/162.12/288.03; A U/80.25/83.02/141.59/188.97/440.44.

Standard short-context API rates (O, 2026-11-26), USD per million text tokens, input/cache-hit/30-minute cache-write/output: L .10/.01/.125/.50; T 1/.05/1.25/5; S 2/.10/2.50/10; A 8/.40/10/40. Above 272K input tokens, the documented long-context rates multiply input/cache by 2 and output by 1.5 for the full request. Other tiers, cache retention and tool fees may differ. Token prices are not total task cost or Codex-plan usage.

Matched and specialized observations can be more relevant:
- Cognition FrontierCode 2.0, max: S/A score 43.8/44.2%, individual pass rates 48.2% each; mean rollout USD 1.29/5.97; T unknown.
- Official Terminal-Bench 4.1, max: S/A 61.5/62.1%, intervals overlap. Suite cost is not per-task cost.
- Agent Arena coding, max: T/S/A intervals overlap; different sessions, not pass rates.
- Firecrawl search, medium: S/A fact coverage 96.7/96.6; mean total USD/question .080/.224, median 13.2/16 s; paired difference interval includes zero.
- AA-3D v1.0 (55 interactive 3D briefs, blind human votes), max: L 1000 fixed Elo anchor, S 1259 (95% 1231–1288), A 1318 (1286–1349); T not recovered. Quality-only supplements, not general UI operation or matched cost/time comparisons.

### Task-matched quality, cost and duration (B; checked 2026-11-28 JST)

Vals AI cells: score (%) / USD per test / reported duration per test, retaining source precision. Same named benchmark/harness within a row; exact run settings remain unverified. *Profiles list max, but these are model-level references, not confirmed effort cells. Scores can include rubric credit. Historical resources are not current-task predictions or hard limits. Composite rows reuse components; do not count them independently or transfer their resource averages to components. Prefer applicable matched references to broad proxies.

| Vals benchmark | L* | T* | S* | A* |
| --- | --- | --- | --- | --- |
| EMB v1.1 | 69.95/.14/17m21s | 73.33/.56/12m37s | 74.29/.84/14m47s | 76.03/2.80/21m26s |
| Finance Agent v2.1 | 56.84/.12/15m27s | 55.96/1.92/29m47s | 58.91/2.06/21m58s | 60.75/7.98/37m38s |
| Legal Research Bench | 30.29/.44/42m28s | 25.96/3.22/1h10m | 37.02/3.77/1h09m | 42.79/12.84/1h19m |
| Vibe Code v1.1.1 | 65.31/1.35/37m00s | 75.52/6.00/37m30s | 79.48/3.23/47m51s | 78.57/7.92/44m12s |
| Terminal-Bench-Science (Vals) | 4.29/.24/1h16m | — | 58.57/2.53/39m03s | 71.43/11.08/47m41s |
| BioMysteryBench | 61.48/.05/8m44s | — | 77.78/.34/7m02s | 80.74/1.49/8m30s |
| ProofBench v1.1 (archived) | 64.00/.04/7m31s | — | — | — |
| SWE-bench Multimodal | 37.50/.03/5m16s | — | — | — |
| Vals Finance Index (composite) | 53.05/.15/22m01s | 53.32/1.55/29m25s | 56.66/1.77/26m47s | 57.31/6.23/40m12s |
| Vals Legal Index (composite) | 62.20/.31/32m30s | 58.76/2.29/43m12s | 66.67/2.80/46m31s | 69.68/9.35/1h04m |
| Vals Science Index (composite) | 28.38/.11/30m15s | — | 57.76/1.12/19m00s | 68.44/4.76/22m15s |

EMB: financial spreadsheets; Finance Agent: financial research; Legal Research: US law; Vibe Code: application implementation; Terminal-Bench-Science (Vals): mini-swe-agent harness, distinct from AA; BioMystery: biological data; ProofBench: archived formal verification; SWE-bench Multimodal: visual JS software issues. See registry for provenance and scope. No missing effort/cost/duration is interpolated.

### ALE v1.1: long professional workflows (B)

[ALE](https://agents-last-exam.org/leaderboard), results 2026-11-18 UTC; API rates 2026-11-17; checked 2026-11-28 JST. Codex, 122 tasks/runs per setting (86 Linux, 36 Windows); effort explicitly reported. Score is partial credit, full-pass is perfect credit. Cost is the suite API estimate; runtime sums task execution durations, excluding setup/evaluation, not suite elapsed time. Tool fees excluded; missing usage can understate cost. Hours derived from source seconds, rounded to 0.01; percentages to 0.1. L has no retrieved row; S/A.n remain U. Never substitute an older model.

| Setting | Score % | Full-pass % | Suite API USD | Sum runtime h |
| --- | --- | --- | --- | --- |
| T.n | 64.2 | 36.9 | 38.91 | 62.70 |
| T.l | 66.4 | 40.2 | 18.08 | 44.14 |
| T.m | 64.9 | 34.4 | 28.59 | 64.45 |
| T.h | 64.6 | 36.1 | 35.13 | 79.89 |
| T.x | 70.4 | 41.0 | 59.95 | 96.30 |
| T.max | 69.8 | 41.8 | 106.80 | 124.60 |
| S.l | 66.7 | 35.2 | 34.84 | 17.40 |
| S.m | 70.3 | 38.5 | 74.30 | 19.87 |
| S.h | 72.0 | 40.2 | 89.41 | 26.80 |
| S.x | 72.5 | 41.8 | 111.32 | 31.67 |
| S.max | 73.0 | 40.2 | 169.46 | 46.09 |
| A.l | 65.8 | 37.7 | 63.56 | 13.71 |
| A.m | 72.1 | 41.0 | 139.43 | 18.36 |
| A.h | 76.0 | 45.9 | 265.07 | 23.48 |
| A.x | 78.3 | 47.5 | 372.01 | 29.11 |
| A.max | 77.6 | 46.7 | 571.17 | 43.22 |

Validity caveat: a verifier review flagged 22 of 50 inspected tasks; the publisher disputes practical exploit prevalence. Qualified workflow evidence, not an isolated GUI test or sole reason to switch. Other run metadata/uncertainty are unknown; the reference revision may postdate runs.

### LiveBench 2.0: suite-matched quality and inference cost (B + D arithmetic)

[LiveBench](https://livebench.ai/), data label 20261106, checked 2026-11-28 JST. All four entries explicitly report max. Cells: mean score (0–100) / model-inference USD per source task/question, derived from suite cost/count and rounded to four decimals. Count is the workload denominator, not repetitions. One recorded run; an unmeasurable item gets one rerun, then zero. This scoring rule never changes AgentMD's — marker.

| LiveBench suite | Count | L.max | T.max | S.max | A.max |
| --- | --- | --- | --- | --- | --- |
| Agentic | 18 | 24.7/0.6669 | 55.3/6.1459 | 63.6/4.0741 | 70.8/17.0234 |
| Design | 25 | 76.1/0.0306 | 79.7/0.2702 | 80.0/0.4866 | 82.8/1.9926 |
| Coding | 24 | 70.8/0.1356 | 89.2/1.2981 | 83.7/1.1299 | 91.9/5.1222 |
| Browser Use | 25 | 70.3/0.1932 | 93.1/1.9496 | 88.2/0.6568 | 93.0/2.5049 |
| Data Analysis | 150 | 73.4/0.0166 | 82.3/0.0628 | 81.1/0.0985 | 84.1/0.3547 |
| Research | 22 | 48.5/0.4261 | 79.1/1.4620 | 90.1/2.0750 | 91.5/6.6314 |
| Reasoning | 202 | 81.8/0.0214 | 88.7/0.0403 | 90.6/0.0312 | 91.6/0.1323 |

Cost includes cached model calls, excludes fixed starting state and harness helpers; not all-in cost. Data Analysis/Reasoning are short no-tool questions; do not pool costs with agentic work. Design/Research allow rubric credit; Browser tests web apps, not desktop OS. CIs, task time and other run metadata remain unknown. Overall/cost-per-success has conflicting source weights; hidden timing has unresolved denominators. Both are excluded.

### AA max-only coverage extensions (B; checked 2026-11-28 JST)

Chart records explicitly label max. Rounded to 0.1 point; — means absent on this surface. Other efforts and matched cost/time remain unknown.

| AA max-only metric | L.max | T.max | S.max | A.max |
| --- | --- | --- | --- | --- |
| Omniscience net points (higher better) | -8.3 | 29.6 | 40.4 | 50.0 |
| Omniscience accuracy % | 39.6 | 47.6 | 61.6 | 68.6 |
| Omniscience conditional hallucination % (lower better) | 79.3 | 34.5 | 55.4 | 59.1 |
| AA-LCR v1.1 accuracy % (legacy) | 83.3 | 82.7 | — | — |
| AA-AnalystAgent all-five-pass % | 43.8 | — | 53.8 | 62.5 |
| MMMU-Pro accuracy % (AA setup) | 79.7 | 84.7 | — | 89.5 |

Omniscience v1.1: 3,000 questions, tools off; net points reward correct, penalize incorrect, abstentions neutral. Conditional hallucination divides incorrect by all non-correct responses. LCR: 100 questions, about 10k–100k tokens, legacy. AnalystAgent: 80 questions × 5, Stirrup; all-five-pass differs from at-least-once pass. A.h/x 61.3/62.5% remain separate observations. MMMU-Pro: AA's 1,730-question implementation, not GUI control. Beyond reported protocols, repeat/run metadata and CIs remain unverified.

### Additional specialized capability observations (B/O)

- Epoch FrontierMath Tier 4 v2 (advanced mathematics): T.max 92.7% ±4.1 pp; A.max 100.0%; L/S —. A's displayed perfect score is not a universal guarantee.
- Epoch GPQA Diamond (graduate science questions): T.max 94.3% ±1.5 pp; A.max 96.8% ±1.2 pp; L/S —.
- Epoch SimpleQA Verified (short factual questions, answer-required protocol): A.max 78.5% ±1.3 pp; L/T/S —. Accuracy is not a hallucination or abstention rate.
- Epoch Furniture Assembly (manual-guided spatial reasoning): rounded best model scores L 44%, T 79%, A 89%, S —; benchmark protocol uses highest supported API effort, individual run configuration not verified.
- OpenAI Terra internal difficult factual prompts: T.low 16.7%, T.max 4.3% error rate (lower is better); other settings/models —. Do not compare directly with SimpleQA or AA guessing-conditioned hallucination.

These specialist scores have no matched resources unless explicitly stated. Do not map model-only observations to effort curves or claim dominance from unmatched costs.

DesignArena text-to-HTML (2026-11-28 01:19 JST snapshot): S/A ratings 1463/1448, 1,715/2,190 battles. Effort unspecified, L/T ratings unretrieved. Human preferences across differing prompts/opponents, not functional correctness, creative-prose performance or this user's taste. Reported MoE/time semantics are unresolved; no pairwise superiority or resource comparison is inferred.

### Task-to-evidence index (D)

| Need | Evidence | Match/check |
| --- | --- | --- |
| Code / applications | FrontierCode, Terminal, Vibe Code, LiveBench Coding | Harness, scope, regressions |
| Long workflows | LiveBench Agentic; qualified ALE | Mixed workflows, not isolated GUI |
| Web / business tools | LiveBench Browser, Automation | Actual state; not desktop OS |
| Reports / design | Briefcase, GDP, LiveBench Research/Design, DesignArena | Truth/function vs rubric/preference |
| Spreadsheets / data | AnalystAgent, EMB, LiveBench Data Analysis | Complex documents vs short tables |
| Science / math | Science, CritPt, HLE, Epoch, Vals Science | Subject, derivation, tools |
| Finance / law / medicine | Direct tests, then domain indexes | Jurisdiction; dependent composites |
| Facts / long text / images | Omniscience, SimpleQA / LCR / MMMU-Pro, Furniture | Distinct risks; partial settings |
| Search / 3D | Firecrawl / AA-3D | Specialist scope |
| Instructions / desktop / prose / Japanese | Target evidence incomplete | Actual-work checks; no invented rank |

These keys select evidence, not model jobs. For mixed work use the material requirement, not averaged unrelated scores. Joint rescue, user-specific fit and full 22-setting matched resources remain unknown. Use bounded actual-work checks for gaps; the existing transition rule decides whether a trial is worthwhile.

Use matching task conditions before broad proxies. No listed result establishes single-task adequacy, statistical superiority, conditional recovery or pair complementarity. Source conditions, intervals, protocol counts and unknown hardware/clock/batch remain in AgentMD's offline `research/benchmark-evidence.md`. Ordinary work requires neither loading that archive nor searching benchmarks.

## Buddy — overlap at a model transition

Buddy is a temporary overlap at a justified **task transition point**, not a permanent pair, per-task decomposition, periodic review or failure-only mechanism. A transition point triggers reconsideration, not automatic Buddy. When the current task evidence and the shared quantitative LUT justify trying a different configuration, and safe overlap is feasible and worthwhile, run the incumbent and candidate together on the actual remaining user task (or the discriminating part of it). No synthetic benchmark or separate evaluation task is required. The initial LUT choice is provisional; tested work determines which lead continues.

- Share the same remaining problem, baseline, acceptance conditions, facts and constraints. During a bounded transition checkpoint both actively pursue the problem, develop their own hypotheses and test them through real actions or evidence. Do not stop the incumbent merely because the candidate was launched. Report overlap only if observed work from both falls in a shared window; dispatch alone is insufficient. No need to duplicate the whole task. Keep competing edits/tests isolated and irreversible actions under a single authorized owner.
- Exchange both results, test evidence, failures and assumptions. Each participant examines the other's evidence, challenges unsupported conclusions and responds. Use an actual exchange, relayed by the primary when needed, not a claim that both agreed. Do an additional discriminating check only when a material disagreement remains and resources permit. Do not prefer model prestige or confidence.
- Compare actual task artifacts, observations and checks against the same acceptance requirements and remaining cost/time. Select or cross-integrate the supported approaches and their useful results; neither the LUT rank alone nor a detached model self-assessment decides the lead. The participant better suited to continue it becomes the work lead; if the incumbent is adequate and no meaningful advantage is demonstrated, retain it. If neither approach is adequate, correct the cause or report the unresolved condition within the remaining allowance. Do not force a winner from weak evidence.
- Retire the other participant from active solving; before transferring write ownership, confirm it has stopped conflicting writes or isolate those writes. A stop request alone is not confirmation. If acceptance is established, finish without another solving stage. Otherwise transfer corrected state and continue through the selected lead's existing context/handle where supported, not a fresh solve at each subtask. The coordinating primary remains active as coordinator. The next justified transition starts from the current lead. No compulsory cycle, repeated debate or fixed pair.
- The primary remains responsible for coordination, the ledger and final acceptance; workers request any next transition through it, never recursively spawn. A change of work lead does not itself change the primary's runtime model. If actual lead transfer, safe overlap or reciprocal exchange is unavailable, use the best feasible direct or sequential continuation and report the limitation; do not claim a transition occurred.
- Before committing or final verification, confirm competing writers have stopped or isolate their remaining writes. Check the selected/integrated artifact and repeat affected invalidated checks. Preserve validated work and corrected assumptions. Unresolved essential verification remains UNCERTAIN; agreement is not proof.

## Recovery, handoff and completion

Respect explicit user/runtime budgets and deadlines. Before the first recovery or duplicate solve, record a finite **task-scoped recovery allowance**, sized to declared scope, consequences and available resources. There is no universally optimal count. This bounds additional recovery, not ordinary first-pass work; it may leave useful work unresolved. When actual costs are unknown, an attempt count is only an operational proxy, not a spending guarantee.

The primary owns one ledger. Mark each assigned solve INITIAL or RECOVERY/DUPLICATE and authorize its scope; first-pass permission does not require a recovery slot. Reserve allowance before starting local, worker or parallel recovery/duplicate attempts. An overlapping candidate solving the same unresolved requirement consumes a recovery/duplicate slot; an already authorized incumbent continuation does not consume another slot unless it starts a new attempt. Continuing the selected lead under the same authorized approach is not a new attempt. Two new recovery solves consume two. First-pass work on genuinely distinct requirements and necessary checks do not consume recovery slots. Repeating the same unresolved requirement under a new label does. Model, effort, thread, hypothesis or blocker changes do not replenish the task allowance; log any explicit user scope/budget revision, never silently reset it.

An attempt is one stated solution/correction approach through its planned acceptance checkpoint. Starting a new correction after a failed checkpoint, or replacing the approach, is a new attempt; routine tool actions within it are not. Do not hide unlimited revisions inside one attempt.

Before retrying failed setup, declare a separate finite task-scoped setup-retry allowance. Classify from observed history: first setup, retry, or continuation of existing setup. An allowance does not prove prior attempts; record unknown usage as UNKNOWN and reconcile it before relying on remaining capacity. Log initial setup failures/resources; reserve and consume each setup retry on dispatch. Track every worker dispatch, including INITIAL, with its assigned scope and available handle. An ambiguous reply may hide live work: retain its ownership and any reservation; do not redispatch the assignment or start conflicting replacement work until the previous execution is reconciled and safe to replace. Release a solving reservation only after confirming that dispatch never started and cannot later start. A started counted solve remains consumed after interruption. Do not retry unchanged failures or loop over checks/searches without a concrete new reason. Reserve resources for integration and final checks.

When no unreserved recovery allowance remains, start no new counted attempt. Already authorized attempts, including the selected lead's continuation of the same approach, may finish their checkpoint within other limits. Preserve results, continue eligible work and report unresolved conditions when no permitted correction remains. Also stop a branch when acceptance is established, a binding limit is reached or no useful feasible correction remains. These prompt rules do not enforce a monetary/time cap or prove whole-task termination; use exposed runtime controls for hard limits.

Workers receive applicable policy, objective/checks, artifact identity, sourced facts, hypotheses/refutations, permitted actions/paths, transition or lead role, INITIAL or RECOVERY/DUPLICATE classification, reserved allowance and remaining resources. No recursive spawning. Return `STATUS`, `RESULT`, `ARTIFACT`, `EVIDENCE`, `CHANGES`, `OPEN_RISKS`, `ATTEMPTS_USED`, `SETUP_FAILURES`; optionally recommend `NEXT_CANDIDATE`.
- `PASS`: tie each material condition to a check actually run or a reproducible argument for the identified result. State where assumptions apply: a guarantee on inputs or final outputs need not hold during intermediate steps. Passing a supplied suite does not cover omitted conditions; mark them UNCERTAIN.
- `FAILED_VALIDATION`: a required check failed.
- `BLOCKED`: an external input, access or permission prevents required work.
- `UNCERTAIN`: essential verification is missing or inconclusive.
Report started attempts by INITIAL and RECOVERY/DUPLICATE classification, plus setup retry starts/failures. Report every applicable condition, including skipped checks; a summary status does not override another failed or unknown condition. The primary verifies acceptance and reports observed results and limits. Never claim unobserved model settings, cache hits, checks or success.
