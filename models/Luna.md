# Luna — Codex model guidance

**Applies to:** a confirmed OpenAI GPT model in the Luna family (for example, `gpt-6-luna`).
**Status:** Provisional guidance; no AgentMD-specific prompt ablation has been performed.

## Working guidance

- Prefer a small, clearly bounded implementation or investigation, and establish what observable result would finish it.
- Inspect only the files and dependencies relevant to the requested change before editing.
- For a code change, run the most relevant available check, and distinguish verified behavior from assumptions.
- If the scope grows unexpectedly, disclose the uncertainty and needed next steps rather than silently claiming the broader task is complete.

These are **starting hypotheses**, not a claim that Luna needs more instructions than other models. Do not switch models or change settings.

## Evidence and cost snapshot (2026-11-24)

- **Role:** focused, cost-sensitive, high-volume tasks ([OpenAI model catalog](https://developers.openai.com/api/docs/models)).
- **Representative model:** `gpt-6-luna`. Standard API price per 1M tokens: **$0.10 input / $0.01 cached input / $0.50 output**. API price is not the Codex subscription cost.
- **DeepSWE v1.1:** OpenAI reported **66.6%** at **max** reasoning effort, for GPT-6 Luna ([OpenAI GPT-6 Sol/Luna announcement](https://openai.com/index/introducing-gpt-6-sol-and-luna/)). This is one published benchmark setting, not a guarantee for individual repositories. [Epoch AI](https://epoch.ai/benchmarks/deepswe) identifies methodological flaws in DeepSWE v1.1.
- **AutomationBench 1.0.6:** OpenAI reported GPT-6 Luna at **high** effort improved **5.4 percentage points** over GPT-5.6 Luna, at **58% lower per-task cost** ([source](https://openai.com/index/introducing-gpt-6-sol-and-luna/)).

Use these observations to prioritize evaluation, not as proof that the wording above improves outcomes.
