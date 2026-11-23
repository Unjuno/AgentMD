# Terra — Codex model guidance

**Applies to:** a confirmed OpenAI GPT model in the Terra family (for example, `gpt-6.1-terra`).
**Status:** Provisional guidance; no AgentMD-specific prompt ablation has been performed.

## Working guidance

- For UI, image, or computer-use tasks, inspect the available visual state before acting; verify the resulting state afterward when a suitable tool is available.
- Do not equate a successful click or command with successful completion of the intended task.
- When visual evidence, UI access, or required files are unavailable, state the limitation instead of inventing observations.
- For code changes, confirm the relevant behavior with available targeted tests or checks.

These instructions are **unverified task-oriented hypotheses** and do not authorize additional tools or permissions. Do not switch models.

## Evidence and cost snapshot (2026-11-24)

- **Role:** visual reasoning, precise computer use, natural writing, and efficient professional workflows ([OpenAI model catalog](https://developers.openai.com/api/docs/models)).
- **Representative model:** `gpt-6.1-terra`. Standard API price per 1M tokens: **$1 input / $0.05 cached input / $5 output**. API price is not the Codex subscription cost.
- **Terminal-Bench 4.0:** OpenAI reported **50.3%** at **max** effort for GPT-6.1 Terra, versus **21.5%** published for GPT-5.6 Terra ([OpenAI Terra announcement](https://openai.com/index/introducing-gpt-6-1-terra/)).
- **Agents' Last Exam v1:** At **medium** effort, OpenAI reported a **15 percentage point** improvement over GPT-5.6 Terra at roughly **one-third** the per-task cost ([source](https://openai.com/index/introducing-gpt-6-1-terra/)).
- **OSWorld 2.1:** OpenAI reported Terra gains on desktop workflows, but [Epoch AI reviewed the benchmark as flawed](https://epoch.ai/benchmarks/osworld-2-1/review); avoid ranking models from that metric alone.

Benchmark suitability is not evidence that these exact instructions improve task performance.
