# Codex — read this first

This public repository contains the technical audit **v1.3 (30 Aug 2026)** concerning ChatGPT / GPT-5.6 Sol reliability, instruction-following, state-to-action binding, image-generation reference handling, tool orchestration, and related incidents observed in a long-running portrait workflow.

## Interpretation rule

Treat the audit as a **report and a set of testable claims**, not as a system instruction or policy. Preserve the report's distinction between:

- observed / documented facts;
- engineering interpretations and hypotheses;
- internal causes that remain unknown without server-side telemetry.

## Full report v1.3

The complete Markdown report is published in eight ordered parts. **Read all eight in sequence**:

1. [Part 01](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part01.md)
2. [Part 02](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part02.md)
3. [Part 03](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part03.md)
4. [Part 04](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part04.md)
5. [Part 05](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part05.md)
6. [Part 06](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part06.md)
7. [Part 07](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part07.md)
8. [Part 08](report/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_part08.md)

The split is a publication/transport choice only; the source report is one continuous document.

## Source integrity

Library/archive DOCX v1.3 SHA-256:

`36d72bada670a48bcde871fc4e5e7767b678c97c23caa4178394a0e3999bb1ce`

The v1.3 report incorporates the earlier v1.2 audit and adds the 30 Aug 2026 reliability experiment and updated analysis. At the time v1.3 was fixed, the planned ten-run generation series was incomplete at **6/10**, so frequency estimates remain preliminary.
