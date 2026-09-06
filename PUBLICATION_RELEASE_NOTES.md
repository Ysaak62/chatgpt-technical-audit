# Prepared GitHub Release Notes

## Recommended tag

`v1.3-supplement-2026-09-06`

## Recommended release title

**Technical Audit v1.3 + Supplemental Evidence (4–6 Sep 2026)**

## Historical-release privacy note

The GitHub tag/release `v1.3-supplement-2026-09-06` is a historical snapshot that predates the privacy-redacted public package now maintained on `main` and in the active Zenodo record.

For the current canonical public presentation, use the latest `main` snapshot and the current Zenodo version. Earlier wording may contain subject-specific descriptive details that were subsequently removed or neutralized as a privacy-minimization measure. The privacy redaction does not alter the audit's technical findings, evidence boundaries, or causal conclusions.

The historical snapshot is retained for provenance and version-history purposes; this notice does not remove or conceal the earlier text.

## Release description

This release preserves a versioned public evidence package for the technical audit of ChatGPT / GPT-5.6 Sol reliability, instruction-following, state-to-action binding, multimodal reference handling, correction recovery, and image-generation workflow incidents.

The release contains:

- the complete English v1.3 audit in eight ordered Markdown parts;
- the complete Russian v1.3 audit in eight ordered Markdown parts;
- English and Russian entry-point files;
- the English Codex-ready supplement covering 4–6 September 2026;
- machine-readable citation metadata (`CITATION.cff`);
- Zenodo-ready publication metadata (`.zenodo.json`);
- a GitHub Pages-ready public landing page under `docs/`.

The 4–6 September supplement extends v1.3 and does not replace or rewrite the earlier eight-part report.

### Central finding

The evidence does not show that GPT-5.6 Sol is unable to understand complex specifications. In multiple incidents the model correctly restated active constraints, recognized previous violations, and proposed appropriate corrections. The recurring reliability failure appeared when those acknowledged constraints had to govern the next executable action.

A concise formulation is:

> GPT-5.6 Sol demonstrates the ability to understand and verbalize active constraints, but those constraints are not always reliably bound to the immediately following executable action. Repeated textual correction does not guarantee that the corrected rule becomes an effective pre-action gate.

### Evidence boundary

The audit separates:

1. observable facts;
2. localized actions supported by direct evidence;
3. internal causes, which remain `UNVERIFIED` without sufficient OpenAI telemetry.

The report does not infer a hidden component as the cause of an observed failure merely because the failure followed that component in time. This causal-discipline rule is referred to in the supplement as the **Applause Principle**.

### Public tracker

OpenAI Codex issue #41851:

https://github.com/openai/codex/issues/41851

### Integrity

English v1.3 source Markdown SHA-256:

`77e3efdcf89f60221cb049e083380af844e4de1d9d2902f8b00e4121e652f4e5`

English supplement Markdown SHA-256:

`57c5642cf53f1c480e257825f9df132c679872769c3e136a563a85cbf2b9949c`

English archive DOCX SHA-256:

`98e0671d1a5019b1c02249e50f0f9e99900e1718e3f3c9c5258dcd888cbc6d49`

Russian archive DOCX v1.3 SHA-256:

`36d72bada670a48bcde871fc4e5e7767b678c97c23caa4178394a0e3999bb1ce`

### Publication status

This is a public user-authored technical report and evidence package. It is not an OpenAI publication and is not presented as peer-reviewed research. A Zenodo archival DOI is intended for this versioned release after repository integration is enabled by the repository owner.
