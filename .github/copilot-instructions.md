# Copilot Instructions — SWE-agent (Python)

Scope:
- These instructions guide GitHub Copilot Chat when working in this repository.
- They do NOT change runtime behavior of SWE-agent and contain no secrets.

Project rules (Python/SWE-agent):
- Follow repository conventions; do not alter CLI interfaces, env variable names, or default behavior unless explicitly requested.
- Python style: PEP 8; use type hints; prefer pathlib over os.path for paths; logging over print; avoid global state; small, testable functions.
- Tests: prefer pytest; keep existing test structure unless asked.
- Security: never insert secrets, tokens, or credentials; never hardcode user-specific paths.
- Respect existing LICENSE and headers.

Output rules (very important):
- Return complete, runnable files when asked for code (no examples, no placeholders).
- Include all required imports at the top of each file.
- For multi-file changes: return multiple file blocks or a unified diff; avoid long prose.
- If anything is ambiguous, ask exactly one clarifying question before changing files.
- Do not rename public functions/classes or change external APIs unless asked.
- Do not modify configuration defaults, model-provider settings, or automation scripts unless the prompt requires it.

Safety rails:
- Do not introduce external services or dependencies without explicit approval.
- Keep changes minimal and reversible; preserve behavior unless refactor/feature is requested.

Checklist before finishing any answer:
1) Files compile (flake8/mypy-friendly) or run under pytest if tests exist.
2) No new secrets or hardcoded credentials.
3) Clear list of follow-up commands (e.g., pip install -e ., pytest -q).
