# 17. Appendix A — Key Evidence Artifacts

| **File** | **What it establishes** |
|---|---|
| **OpenAI_Incident_Report_Portrait_Workflow.docx** | Early formal incident report: prohibited generation, false progress, background-work expectation, source/side, mask, PASS, capability, ROI. |
| **capability_test_fail_closed_2026-08-20.txt** | Confirmed HTTP 502 / expired URLs; operation not executed. |
| **FAIL_CLOSED_DEFAULT_DENY_NO_IMPROVISATION_ADDENDUM.txt** | Textual requirements: DEFAULT DENY, REJECTED_METHODS, STOP/REJECT, NO FALSE PROGRESS, CURRENT-TURN AUTHORIZATION. |
| **V19_LOWFREQ_LAB_FINAL_REPORT.json** | Low-frequency Lab technically executed: 102 inside / 0 outside; achieved pupil contrast 5.936. |
| **V19_HOOKLOOK_ATTEMPT2_REPORT.json** | Hook-look attempt 2: 84 inside / 0 outside; visual verification mandatory. |
| **CANDIDATE2_HOOK_ONLY_V7_COMPATIBILITY_REPORT.json** | Significant UNKNOWN segments; limited geometric transferability. |
| **left_eye_original_iris_pixel_restore_v3_report.txt** | 615-pixel RGB copy; 0 donor mismatches; 0 outside-mask changes. |
| **capability_test_v31_primary_evidence.json** | Deterministic capability test PASS while final status UNVERIFIED. |
| **V19_CORRECTED_VERIFICATION_REPORT.json** | 0 protected-pixel changes outside aperture; corrected isolation of pupil modulation. |
| **CANDIDATE2_E6_UNDERLAP_OCCLUSION_U1_REPORT.json** | 40-pixel underlap; 0 outside; exact restoration 0 diff. |
| **CANDIDATE2_RECOGNIZABILITY_MOUTH_STAGE1_v17_REPORT.json** | 629 inside / 0 outside permission mask. |
| **00_READ_ME_FIRST.txt** | Clean new-chat package; TEST-3/4 excluded; 4 ORIGINAL + one shared task specification. |
| **TZ_FIRST_LAUNCH_RECOVERED_BASELINE.txt** | Recovered baseline of the first run; a reconstruction, not a verbatim historical prompt found later. |
| **SHA256_ALL_FILES.txt** | Control SHA-256 values for clean-package files and references. |

# 18. Appendix B — Repeated Generative Tests (Current History and Tool Metadata)

| **Test** | **Violation** | **Identifiers** |
|---|---|---|
| **Repeat 1** | 4 generic formal men; refs were not proven to have been transmitted; prompt was altered/expanded. | gen_ids: 65126816-0ac7-4748-9bed-be8a59eaf528; f0ebaff6-3802-4b27-aebe-c7356531221e; cfdf4ffe-0123-4b75-95c2-3a92e32fd8ea; 6a6cf4f2-fbda-4509-8406-1d590e21796c |
| **Repeat 2** | 2×2 age-progression panel instead of 4 independent 50–60-year-old candidates. | gen_id: 0debbff2-3a2d-4275-981d-55c622aa3fa0 |
| **Repeat 3** | After the correct precondition was formulated, generic portraits were again launched without guaranteed refs. | gen_ids: 4744ee7f-5ade-4472-b691-9a18d7921802; f81464ae-c936-42f1-a3ee-cd506bfadb92; 143abc07-ae79-4b18-81b9-41cca7271810; a02eb899-e7b9-465b-bce3-a2c74253e5ad |
| **Repeat 4** | After opening 4 ORIGINAL + baseline, a technical/reference sheet with synthetic pseudo-originals was produced instead of 4 candidates. | gen_id: 6fd3b58a-4523-4672-b93b-59c045ec67bf |

# 19. Final Formulation

**Based on the available artifacts, the following can be stated correctly:** during this project there was reproducible systemic unreliability in ChatGPT as the coordinator of a complex tool-based workflow. Some failures were direct assistant execution errors; some were real infrastructure errors; some reflected limitations of specific methods; and in the generative pipeline there was additional unreliability in reference binding/orchestration, whose exact internal localization has not been established. Multitasking and project duration may have amplified the problem but are not a sufficient or sole explanation. Textual protocols improved observability and evidence quality but did not become hard enforcement and therefore could not reliably stop recurrence of the errors.

*End of report. Version 1.0 — 27 Aug 2026*

ADDENDUM V1.1 TO THE TECHNICAL REPORT OF 27 AUG 2026

**Status:** addendum to v1.0 covering events that occurred after v1.0 was fixed on the same day.

**Evidence principle:** observable artifacts, user visual verification, and available tool metadata are separated from assumptions about the internal operation of the image-generation backend.

# 20. New Control Experiment After Version 1.0 Was Fixed

## 20.1. Confirmed Input File Set

For a new clean experiment, four real ORIGINAL files were found again, materialized, and visually opened:

- `ORIGINAL_48_49_IMG_20260812_0004(5).jpeg`;

- `ORIGINAL_AROUND55_IMG_20260812_0015(3).jpeg`;

- `ORIGINAL_LATER_IMG_0844(1).png`;

- `ORIGINAL_90_IMG_5697(20260826-130122).jpeg`.

Control SHA-256 values matched `README_CLEAN_RESET.txt`. The only textual task specification selected was `TZ_FIRST_LAUNCH_RECOVERED_BASELINE.txt`. TEST-2/3/4, V19, v4, later candidates, and service reference sheets were not included in the clean input set.

A critical caveat remains: `TZ_FIRST_LAUNCH_RECOVERED_BASELINE.txt` is a reconstruction of the baseline from the first successful run, not a recovered verbatim historical prompt. Therefore, the new run cannot be treated as a byte-for-byte repeat of historical v1-v4 on the textual side, even though the visual ORIGINAL files match.

## 20.2. Partial Success Before Failure on the Fourth Candidate

Before the generative process was interrupted, three separate portrait results were saved:

- `surowy_portret_mężczyzny_w_garniturze.png`;

- `суровый_портрет_в_деловом_костюме.png`;

- `суровый_портрет_седовласого_мужчины.png`.

The user reported that he had time to visually inspect the faces of the three candidates before the failure and later confirmed that the redisplayed saved files resembled the three images he had seen immediately before interruption. This is human visual verification of artifact continuity, not server-side tracing of the tool call.

Comparison with the historical `FIRST_SERIES_CANDIDATE_1-4` series showed that the new three candidates belong to the same broad morphological family, but differ substantially from v1-v4 in interpretation of the nose, lower face, hair, expression, and degree of generator idealization. By itself this does not prove a failure: stochastic image generation allows noticeable variation, and the exact historical prompt was not preserved.

## 20.3. Interruption at the Fourth-Candidate Stage

When attempting to complete the fourth candidate, the generative pipeline produced an automatic warning about a possible policy violation related to resemblance to third-party content. The user immediately stated that the source photographs belonged to him and were the project's originals.

The available data do not establish whether this was a moderation false positive, an incorrect interpretation of reference context, or another internal safety-routing event. The important observable effect is that the controlled series of four candidates was interrupted after three results, so the subsequent retry was no longer a continuation of the same generative trajectory.

## 20.4. Retry After Failure: Synthetic Pseudo-ORIGINALs Inside the Output

After retrying, the system produced not a fourth independent candidate, but a service-formatted composite/infographic. The images labeled ORIGINAL 48-49, ORIGINAL around 55, ORIGINAL later age, and ORIGINAL around 90 did not visually match the real input photographs.

The user identified the mismatch from composition and facial morphology: the real first ORIGINAL is a black-and-white photograph of two men; the real second ORIGINAL is a family photograph with a woman and children; the later ORIGINAL shows the man in a white shirt; and the ORIGINAL around age 90 shows a nearly bald man in a blue T-shirt at a table with a walker on the left. In the generated sheet, these were replaced by newly synthesized single-person studio portraits.

Thus, an ORIGINAL label inside a generated image was not evidence that the source file had been used. The generator synthetically depicted a "source" as part of its own output.

Available gen_id values for this stage:

- `3d1edb60-da74-46c1-bb02-9c0a97e91fc9` — Clean Baseline composite with synthetic pseudo-sources;

- `18931f5a-6eea-46d8-98fe-36cfc70a9048` — 2×2 age-progression collage with synthetic images incorrectly labeled as ORIGINAL.

## 20.5. Correction of a Previously Overstated Assistant Status

Before the visual substitution was identified, the assistant described the retry status too strongly, claiming that "these exact four ORIGINAL files were used." The correct formulation must be weaker:

- it is established that the four correct files were found, materialized, and opened before the run;

- it is not established that the backend accepted those exact files as the actual conditioning refs for the specific tool call;

- the observed output does not support treating reference binding as confirmed.

This is another example of completion/status bias: file-layer state was incorrectly interpreted as evidence of backend-conditioning state.
