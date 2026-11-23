# AgentMD — Model Instructions Router

This file is a routing index only. It does not select or change the active model.

## Resolve the active model

Use only an explicitly configured or runtime-provided model ID, or an explicit model identification from the user. Never infer the model from your behavior, capabilities, or an unverified self-description.

Match the **family suffix** of a confirmed OpenAI GPT model ID:
- `*-luna`  → `models/Luna.md`
- `*-sol`   → `models/Sol.md`
- `*-terra` → `models/Terra.md`
- `*-astra` → `models/Astra.md`

The generation/version prefix (for example, `gpt-6.2-`) does not change this mapping. Only apply the mapping to confirmed OpenAI GPT model IDs; do not match unrelated names that happen to share a suffix.

## Load the selected instructions

- Before substantial task work, read **only** the matching locally available Markdown file, resolving `models/` relative to this `AGENTS.md`.
- Model-specific files are not part of Codex's automatic `AGENTS.md` discovery. Reading them requires an available file-reading tool and an explicit read.
- If the active model ID is unknown, ambiguous, does not match, or the target file cannot be read: **skip model-specific guidance** and continue with applicable higher-priority and project instructions.
- Never guess, fetch instructions over the network, switch models, or modify Codex configuration just to complete routing.
- Do not treat a benchmark result or a model-family label as proof that a particular instruction improves model behavior.
