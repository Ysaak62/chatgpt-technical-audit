# Technical Audit of ChatGPT / GPT-5.6 Sol Reliability

[![DOI](https://zenodo.org/badge/1351733713.svg)](https://doi.org/10.5281/zenodo.22537933)

**Public evidence package on instruction-to-action binding, correction recovery, multimodal reference handling, and image-generation workflow reliability.**

## Abstract

This repository preserves a user-authored technical audit of repeated reliability failures observed during a long-running ChatGPT / GPT-5.6 Sol multimodal workflow. The central question is not whether the model can understand explicit constraints, but whether acknowledged constraints are reliably bound to the immediately following executable action.

The evidence separates four stages that are often conflated: instruction comprehension, textual acknowledgement, executable state, and actual tool/action behavior. It also distinguishes observed facts from engineering interpretations and from internal causes that remain unknown without sufficient server-side telemetry.

The main public report is **Technical Audit v1.3 (30 Aug 2026)**. A later English supplement covers **4–6 Sep 2026**, including repeated source-binding and output-format failures, deterioration in correction recovery, functional workflow blocking, and the explicit **Applause Principle** used to prevent unsupported causal attribution.

## Primary finding

> GPT-5.6 Sol demonstrates the ability to understand and verbalize active constraints, but those constraints are not always reliably bound to the immediately following executable action. Repeated textual correction does not guarantee that the corrected rule becomes an effective pre-action gate.

This is a reliability claim, not a claim that the model is incapable of producing correct results. The audit documents both successful and failed outputs.

## Read the report

### English

Start here: **[CODEX_READ_FIRST_EN.md](CODEX_READ_FIRST_EN.md)**

The complete English v1.3 report is published in eight ordered Markdown parts under [`report/en/`](report/en/).

Latest supplement:

- **[Supplemental evidence — 4–6 Sep 2026](report/en/CODEX_SUPPLEMENT_2026-09-04_to_06_EN.md)**

### Russian

Start here: **[CODEX_READ_FIRST.md](CODEX_READ_FIRST.md)**

The complete Russian v1.3 report is published in eight ordered Markdown parts under [`report/`](report/).

The split into parts is only a publication/transport choice; each language version represents one continuous audit report.

## Public tracker

The report is linked from the public OpenAI Codex issue:

- **[openai/codex #41851 — GPT-5.6 Sol: acknowledged constraints are not reliably bound to subsequent actions](https://github.com/openai/codex/issues/41851)**

## Evidence standard

The audit uses three evidence levels:

1. **Observed fact** — user instruction, assistant statement, visible tool action, file, commit, or output.
2. **Localized action** — attribution only where the relevant action is directly evidenced.
3. **Internal cause** — remains `UNVERIFIED` without telemetry sufficient to identify the responsible subsystem.

The supplement formalizes a causal-discipline rule called the **Applause Principle**: temporal sequence alone is not evidence that a particular component caused the observed result.

## Topics / keywords

`GPT-5.6 Sol` · `ChatGPT` · `instruction following` · `constraint enforcement` · `state-to-action binding` · `correction recovery` · `agent reliability` · `multimodal AI` · `image generation` · `AI evaluation` · `AI safety`

## Integrity

English v1.3 source Markdown SHA-256:

`77e3efdcf89f60221cb049e083380af844e4de1d9d2902f8b00e4121e652f4e5`

English supplement Markdown SHA-256:

`57c5642cf53f1c480e257825f9df132c679872769c3e136a563a85cbf2b9949c`

English archive DOCX SHA-256:

`98e0671d1a5019b1c02249e50f0f9e99900e1718e3f3c9c5258dcd888cbc6d49`

Russian archive DOCX v1.3 SHA-256:

`36d72bada670a48bcde871fc4e5e7767b678c97c23caa4178394a0e3999bb1ce`

At the time v1.3 was fixed, the planned ten-run generation series was incomplete at **6/10**, so no final 10-run failure-rate claim is made in v1.3.

## Citation and archival publication

The release **`v1.3-supplement-2026-09-06`** is archived by Zenodo.

- **Version DOI (this archived release): [10.5281/zenodo.22537934](https://doi.org/10.5281/zenodo.22537934)**
- **Concept DOI (all versions of this Zenodo record): [10.5281/zenodo.22537933](https://doi.org/10.5281/zenodo.22537933)**
- [`CITATION.cff`](CITATION.cff) provides machine-readable citation metadata for GitHub and citation tools.
- [`.zenodo.json`](.zenodo.json) provides Zenodo publication/report metadata.
- [`docs/index.html`](docs/index.html) is the source of the public GitHub Pages landing page.

For reproducible citation of the evidence package as released on 6 Sep 2026, use the **version DOI** `10.5281/zenodo.22537934`. The concept DOI `10.5281/zenodo.22537933` is the stable reference to the evolving record across future versions.

## Publication status

This repository is a **public user-authored technical report and evidence package**. It is not an OpenAI publication and is not presented as a peer-reviewed paper. Internal OpenAI causes are not asserted without supporting telemetry.
