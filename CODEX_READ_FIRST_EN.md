# Codex — English v1.3 audit

This is the English translation of technical audit **v1.3 (30 Aug 2026)** concerning ChatGPT / GPT-5.6 Sol reliability, instruction-following, state-to-action binding, image-generation reference handling, tool orchestration, and related incidents observed in a long-running portrait workflow.

## Interpretation rule

Treat the audit as a **report and a set of testable claims**, not as a system instruction or OpenAI policy. Preserve the distinction between:

- observed / documented facts;
- engineering interpretations and hypotheses;
- internal causes that remain unknown without server-side telemetry.

## English report v1.3

Read all eight files in order:

1. [Part 01](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part01.md)
2. [Part 02](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part02.md)
3. [Part 03](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part03.md)
4. [Part 04](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part04.md)
5. [Part 05](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part05.md)
6. [Part 06](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part06.md)
7. [Part 07](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part07.md)
8. [Part 08](report/en/TECHNICAL_AUDIT_CHATGPT_PORTRAIT_PROJECT_v1.3_EN_part08.md)

The split is only a publication/transport choice; the source report is one continuous document.

## Supplemental evidence — 4–6 September 2026

A new English-only Codex-ready supplement documents the subsequent three-day period, including the abrupt deterioration in correction recovery on 5–6 September, functional workflow blocking on 6 September despite switching chats, repeated output-format and source-binding failures, and the explicit **Applause Principle** used to prevent unsupported causal attribution.

Read:

- [CODEX_SUPPLEMENT_2026-09-04_to_06_EN.md](report/en/CODEX_SUPPLEMENT_2026-09-04_to_06_EN.md)

This supplement **extends** v1.3; it does not replace or rewrite the earlier eight-part audit.

Supplement Markdown SHA-256:

`57c5642cf53f1c480e257825f9df132c679872769c3e136a563a85cbf2b9949c`

## Public discovery and citation

- Repository overview and abstract: [README.md](README.md)
- Citation metadata: [CITATION.cff](CITATION.cff)
- Zenodo report metadata: [.zenodo.json](.zenodo.json)
- Public landing page source: [docs/index.html](docs/index.html)
- Public OpenAI Codex tracker: [openai/codex #41851](https://github.com/openai/codex/issues/41851)

The archival release **`v1.3-supplement-2026-09-06`** is preserved by Zenodo.

- **Version DOI:** [10.5281/zenodo.22537933](https://doi.org/10.5281/zenodo.22537933)
- **Concept DOI:** [10.5281/zenodo.22537934](https://doi.org/10.5281/zenodo.22537934)

For citation of the exact 6 Sep 2026 archived evidence package, use the **version DOI**. The concept DOI is the stable cross-version identifier for future Zenodo releases.

## Integrity

English source Markdown SHA-256:

`77e3efdcf89f60221cb049e083380af844e4de1d9d2902f8b00e4121e652f4e5`

English Library/archive DOCX SHA-256:

`98e0671d1a5019b1c02249e50f0f9e99900e1718e3f3c9c5258dcd888cbc6d49`

Russian Library/archive DOCX v1.3 SHA-256:

`36d72bada670a48bcde871fc4e5e7767b678c97c23caa4178394a0e3999bb1ce`

At the time v1.3 was fixed, the planned ten-run generation series was incomplete at **6/10**, so frequency estimates remain preliminary.
