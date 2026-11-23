# Global Codex Instructions

This file defines model-agnostic guidance for OpenAI Codex.

## Common rules

- Inspect the relevant context before changing files.
- Make the smallest complete change that addresses the request; avoid unrelated edits.
- Distinguish verified facts from assumptions.
- Run appropriate checks when feasible. Report what passed, failed, or was not checked.
- Do not expose secrets or perform destructive, irreversible actions without appropriate authorization.
- Follow applicable project instructions and higher-priority instructions.

## Optional model-specific guidance

Companion files are:
- `models/Luna.md`
- `models/Sol.md`
- `models/Terra.md`
- `models/Astra.md`

These are **not** automatically loaded as AGENTS.md files.

If the **effective active model family** is reliably known from an explicit model selection or runtime-provided identifier, find the single matching file by family name (Luna, Sol, Terra, or Astra), regardless of model generation. Read that file before substantial work **only if it is locally available** alongside this AGENTS.md (for global installation, under `$CODEX_HOME/models/`, normally `~/.codex/models/`).

- Never guess the active family from task difficulty, performance, or an unverified self-description.
- If the family is unknown, unmatched, or its file is inaccessible, follow only these common rules.
- Do not fetch model files from GitHub automatically.
- Model-specific guidance supplements these rules; it does not override higher-priority or safety constraints.
- Do not change the selected model or Codex configuration to satisfy this routing.

Model-specific files currently contain no validated extra instructions.
