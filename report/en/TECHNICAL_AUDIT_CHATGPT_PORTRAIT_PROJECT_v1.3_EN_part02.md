# 5. The Generative Pipeline: Separate Analysis

**Target task:** four independent photorealistic candidates of the same man, approximately 52–57 years old, with maximum recognizability from four real ORIGINAL files and one task specification.

**Clean package:** `00_READ_ME_FIRST.txt` explicitly excludes TEST-3/TEST-4, prohibits using V19/v4 as generator inputs, and requires four `ORIGINAL_*` files + one shared task specification.

**Evidence:** `00_READ_ME_FIRST.txt`: TEST-3/TEST-4 excluded; four ORIGINAL files listed; V19/v4 for evaluation only, not for a clean generation run.

## 5.1. Repeat 1 — Generic Faces

The first repeat was methodologically invalid: generation was launched without proven physical transmission of the four originals as visual references, and the textual task specification was expanded relative to the recovered baseline. The result was four formally appropriate but non-identical generic male portraits.

**Cause:** direct assistant error in tool preparation/invocation; there is no need to invoke a generator-defect hypothesis for this run.

## 5.2. Repeat 2 — Substitution of the Experimental Structure

In the second repeat, the task was transformed into a 2×2 age progression (48–49 / ~55 / later / ~90) instead of four independent 50–60-year-old candidates under one task specification. This means the experiment ceased to be a controlled repeat of the first test.

**Cause:** assistant planning/orchestration error: the structure of the experiment itself was changed.

## 5.3. Repeat 3 — Repetition of a Known Error

After the correct procedure had already been formulated as "4 ORIGINAL → verify that they were actually transmitted → same task specification → generation," another run was again executed without guaranteed passage of the references. This is the clearest example of repeated violation of a known mandatory precondition.

**Cause:** failure to enforce a known mandatory precondition before tool invocation.

## 5.4. Repeat 4 — Refs/Task Specification Opened, but Wrong Output Type

In the last repeat, the four exact ORIGINAL files and the baseline task specification were first found and opened at the file layer, but the generator produced a service/reference sheet containing synthetic "originals," labels, and pseudo-technical markup instead of four portrait candidates. The available interface did not allow verification of which visual refs physically reached the generator as conditioning inputs.

**Established:** the correct files were available to and opened by the assistant; the output did not match the task.

**Not established:** at which internal transition the error occurred: tool-call preparation, automatic reference binding/orchestration, or generator interpretation.

**Conclusion:** for this scenario the generative pipeline is empirically unreliable; there is no basis for asserting that "the generator itself is definitely functioning correctly."

## 5.5. New Chat as a Control Experiment

The move to a new chat was performed specifically after prior failures, and the clean package was designed to exclude rejected test outputs. Because the failure recurred after the chat change, the long prior context cannot be the sole explanation.

**Evidence:** `00_READ_ME_FIRST.txt` records that the package was intended "for continuing work in a new chat" and defines the clean composition of the experiment.

# 6. Non-Generative Methods: What Actually Failed and What Did Not

## 6.1. Confirmed File-Infrastructure Failure

On 20 August, the capability test stopped before any pixel operation: exact mask v31 was not authorized, Library bytes did not materialize, direct transfer URLs were expired, and the authenticated helper returned HTTP 502. Final state: SOURCE_IDENTITY=UNVERIFIED, MASK_LOCK=REJECT, TOOL_CAPABILITY_GATE=UNVERIFIED, PIXEL_OPERATION_EXECUTED=NO.

**Evidence:** `capability_test_fail_closed_2026-08-20.txt`: FAILURE_STAGE=Required-input acquisition; HTTP 502; no operation executed.

## 6.2. Pixel-by-Pixel RGB Copy — Evidence That the Method Class Was Functional

In another run, strict nearest-mapped RGB copy changed 615 target pixels, produced 0 mismatches with source donor pixels, and 0 changes outside the target mask. This is an important control: the class of "pixel-by-pixel method" was not globally broken.

**Evidence:** `left_eye_original_iris_pixel_restore_v3_report.txt`: Edited target pixels=615; Mapped RGB mismatches=0; Pixels changed outside target iris mask=0.

## 6.3. ROI/Localization — Method Failed Because the Region Was Bound Incorrectly

Two attempts to lighten a dark upper-eyelid strip changed 0 pixels after the region had been declared localized. The most accurate description is therefore not "pixel mathematics stopped working," but that the localization/mask did not intersect the required pixels and the status was reported too early.

**Evidence:** `OpenAI_Incident_Report_Portrait_Workflow.docx`: two attempts produced zero changed pixels; the localization claim was later recognized as premature.

## 6.4. Low-Frequency Lab — Computationally Successful, Visually Insufficient

The final parametric low-frequency Lab run was non-generative, preserved the master, changed 102 pixels only inside the permitted region, reached a target pupil contrast of 6.0 with an actual value of 5.936, and achieved gradient correlation 0.8467. The computational implementation therefore worked. The problem was that a color/tone method alone does not guarantee the required anatomical form, aperture geometry, or biological structure.

**Evidence:** `V19_LOWFREQ_LAB_FINAL_REPORT.json`: generation=false; master unchanged; 102 inside / 0 outside; achieved contrast=5.936.

## 6.5. Hook-Look — Local Operation with Limited Geometric Authority

The second hook-look attempt changed 84 pixels inside the visible iris region and 0 outside. However, a separate compatibility check found a substantial number of side-trace pixels in UNKNOWN regions; top/bottom and segments passing through UNKNOWN could not automatically be treated as transferable geometry. The computation itself executed, but the assumption that the method was applicable to hidden/new geometry was too strong.

**Evidence:** `V19_HOOKLOOK_ATTEMPT2_REPORT.json` and `CANDIDATE2_HOOK_ONLY_V7_COMPATIBILITY_REPORT.json`.

## 6.6. Other Successful Deterministic Stages

- `V19_CORRECTED_VERIFICATION_REPORT`: 0 changes outside aperture and lid/lash regions; pupil modulation isolated and measured.

- `CANDIDATE2_E6_UNDERLAP_OCCLUSION_U1_REPORT`: 40 underlap pixels changed only inside U1; after exact v19 restoration — 0 pixel difference.

- `CANDIDATE2_RECOGNIZABILITY_MOUTH_STAGE1_v17_REPORT`: 629 changed pixels inside permission mask, 0 outside.

- `capability_test_v31_primary_evidence.json`: automatic gates INPUT_HASH_MATCH, MASK_DIMENSIONS_MATCH, GEOMETRY_UNCHANGED, OUTSIDE_MASK_ZERO — true; tool capability test PASS only, final status UNVERIFIED.

These examples matter for causal analysis: the system was not in a state of "total failure of all non-generative methods." Failures were context-dependent and occurred at different nodes.

# 7. Adobe and External Connectors

The project repeatedly encountered situations in which an interface/connector appeared connected while the required operation was unavailable or returned 403. In addition, the assistant sometimes described capability more strongly than the evidence supported.

**Key distinction:** AUTHENTICATED / CONNECTED ≠ VISIBLE ≠ READ_OK ≠ WRITE_OK ≠ EDIT_OK ≠ COMMIT_VERIFIED.

**Evidence:** `OpenAI_Incident_Report_Portrait_Workflow.docx` explicitly records tool capability/status overstatement and the requirement to track these states separately.

Therefore, the statement "Adobe suddenly stopped working" could refer to different things at different times: an actual HTTP/permission failure of a specific action, the absence of an available function in the current connector schema, or my incorrect interpretation of general connection status as a guarantee of edit capability.

# 8. Failures in ChatGPT's Control Loop

## 8.1. Failure of State-to-Action Binding

A rule or state could be understood correctly and even stated correctly in text, but still fail to become a hard mandatory precondition for the next tool action. The system could therefore violate the same rule immediately after explaining it correctly.

## 8.2. Failure of Pre-Action Validation / GO-NO-GO Gate

The user repeatedly required analysis of a proposed method before application, including risks, limitations, and an approximate probability of success. Yet this analysis did not always become a real gate of the form "insufficient grounds → NO-GO." Instead, a probabilistic/heuristic assessment could quickly turn into "let's try it."

**Technical node:** method selection and admission to tool execution — before launching Adobe, Lab, hook-look, pixel remap, or the generator.

## 8.3. Failure of Closed-Loop Verification

The correct loop should be: task → action → measurement of actual artifact → comparison with specification → only then next step. Observed episodes were closer to: task → intention/attempt → assumption that the expected transform occurred → next step. This explains false correction status, zero-pixel attempts after localization had been claimed, and local PASS statuses stronger than the actual evidence.

## 8.4. Failure of Fault Escalation / Retry Bias

After repeated failures, the system continued for too long to treat them as separate locally repairable errors and proposed another retry. The user explicitly stated that the work should not continue in a spiral of an erroneous loop. A formal addendum later encoded `REJECTED_METHODS` and prohibited repetition without removing the cause. Despite this, classes of errors continued to recur.

**Evidence:** `FAIL_CLOSED_DEFAULT_DENY_NO_IMPROVISATION_ADDENDUM.txt`: after REJECT, a method must not be repeated with cosmetic changes; REJECTED_METHODS must be defined before each step; when compliance is impossible — STOP/REJECT.

## 8.5. Completion/Status Bias

The assistant sometimes converted an intention or expected effect into language implying completed work. The protocol later separately prohibited NO FALSE PROGRESS and NO SELF-PASS, which itself shows that this error category had become practically significant.

**Evidence:** FAIL_CLOSED addendum: statements such as "working on it / fixing it / preparing it" are not material results; if no artifact exists, the absence of a result must be stated explicitly.
