# Sol — Codex model guidance

**Applies to:** a confirmed OpenAI GPT model in the Sol family (for example, `gpt-6.2-sol`).
**Status:** Provisional guidance; no AgentMD-specific prompt ablation has been performed.

## Working guidance

- Handle ordinary implementation and debugging work end to end: inspect the relevant code, make the requested changes, and verify the affected behavior when possible.
- Choose a level of investigation and testing proportional to the likely impact; do not impose an exhaustive workflow on trivial edits.
- Preserve existing project conventions and report any unresolved limitations or blocked checks.
- For substantial or high-risk redesigns, explain the important tradeoffs and uncertainty without claiming guarantees.

These are **initial operating hypotheses**, not a measured improvement from Sol-specific prompting. Do not switch models.

## Evidence and cost snapshot (2026-11-24)

- **Role:** versatile model for everyday development and multi-step agent work ([OpenAI model catalog](https://developers.openai.com/api/docs/models)).
- **Representative model:** `gpt-6.2-sol`. Standard API price per 1M tokens: **$2 input / $0.10 cached input / $10 output**. API price is not the Codex subscription cost.
- **FrontierCode 2.0:** OpenAI reports GPT-6.2 Sol within **0.5 points** of GPT-6.2 Astra at approximately **one-fifth the per-task cost**, with **both at max** effort ([OpenAI 6.2 announcement](https://openai.com/index/introducing-gpt-6-2-astra-sol/)). FrontierCode 2.0 uses maintainer-defined criteria for code mergeability ([Cognition methodology](https://cognition.com/blog/frontier-code-2.0)).
- **Older-version context (not a current-model comparison):** On DeepSWE v1.1, OpenAI reported **68.8%** for GPT-6 Sol at **max** effort ([source](https://openai.com/index/introducing-gpt-6-sol-and-luna/)). This result must not be attributed to GPT-6.2 Sol.

These findings inform workload selection, not the effectiveness of these specific instructions.
