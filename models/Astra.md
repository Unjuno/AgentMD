# Astra — Codex model guidance

**Applies to:** a confirmed OpenAI GPT model in the Astra family (for example, `gpt-6.2-astra`).
**Status:** Provisional guidance; no AgentMD-specific prompt ablation has been performed.

## Working guidance

- For complex changes, identify important requirements, invariants, and compatibility constraints before editing.
- Consider competing approaches when their tradeoffs materially affect correctness, maintainability, or risk; do not manufacture a lengthy plan for straightforward edits.
- Validate significant edge cases and integration boundaries when feasible, and distinguish checks actually run from checks only proposed.
- State residual risks, failed validations, and blocked work; do not claim completeness without evidence.

These are **initial operating hypotheses**. Greater model capability does not justify unrestricted changes or unnecessary complexity. Do not switch models.

## Evidence and cost snapshot (2026-11-24)

- **Role:** most capable general OpenAI model for challenging reasoning, coding, and professional work ([OpenAI model catalog](https://developers.openai.com/api/docs/models)).
- **Representative model:** `gpt-6.2-astra`. Standard API price per 1M tokens: **$8 input / $0.40 cached input / $40 output**. API price is not the Codex subscription cost.
- **Agents' Last Exam v1:** OpenAI reports GPT-6.2 Astra scoring **5.2 percentage points** above GPT-6 Astra at **less than one-third the per-task cost** ([OpenAI 6.2 announcement](https://openai.com/index/introducing-gpt-6-2-astra-sol/)).
- **Terminal-Bench-Science 0.1:** OpenAI reports GPT-6.2 Astra **9 percentage points** above GPT-6 Astra at **less than one-third the per-task cost** ([source](https://openai.com/index/introducing-gpt-6-2-astra-sol/)).
- **FrontierCode 2.0:** Compared at **max** effort, OpenAI reports GPT-6.2 Sol within **0.5 points** of GPT-6.2 Astra at around **one-fifth the cost** ([source](https://openai.com/index/introducing-gpt-6-2-astra-sol/)). Astra is not automatically the most cost-effective choice.

Use the evidence to scope evaluations; it does not establish that this exact guidance improves Astra.
