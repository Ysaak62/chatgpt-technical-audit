## 20.6. Simplifying the Sources: Two Non-Generative Single-Person Crops

To eliminate ambiguity from the first two multi-person ORIGINAL files, two new primary source images were created on the user's direct instruction using only direct rectangular cropping of the original pixels:

- `ORIGINAL_48_49_MAN_ONLY_PIXEL_CROP.png`;

- `ORIGINAL_AROUND55_MAN_ONLY_PIXEL_CROP.png`.

No generation, inpainting, retouching, scaling, or interpolation was used; PNG was chosen to avoid additional JPEG compression. The user then explicitly designated these two files as the primary sources for the corresponding age stages.

## 20.7. Repeat with Two Single-Person Crops: Failure Persists with Lower Input Complexity

After simplifying the inputs, the user requested four new candidates using only the two crop files and the same `TZ_FIRST_LAUNCH_RECOVERED_BASELINE.txt`. The assistant explicitly confirmed in text: "only the two new primary sources," "I am not connecting any other ORIGINAL, TEST, V19, v4, later candidates, or materials from other chats," and "I am launching four independent candidates."

The actual output was again an infographic, and the upper panels labeled as sources were synthetically recreated by the model rather than literally displaying the two crop files. The result was immediately rejected by the assistant as incorrect.

Available gen_id:

- `a10bb8ca-09cb-4735-9e1f-66cd0555a60a`.

This test strengthens two conclusions:

1. The presence of multiple people inside the first ORIGINAL files is not a sufficient explanation for the observed failure, because the failure recurred after switching to two single-person crops.

2. Even a very simple current command — "two specific refs + one task specification + four separate candidates" — did not guarantee the corresponding output type.

The exact internal failure point still remains unestablished: possibilities include orchestration/tool-preparation error, reference-binding failure, task transformation in the tool layer, or generator interpretation.

# 21. Updated Causal Assessment of the Generative Pipeline

## 21.1. File Visibility Is Not Conditioning Acceptance

The new experiment provides stronger empirical grounds for separating the following states:

FILE_FOUND → FILE_MATERIALIZED → FILE_VISUALLY_OPENED → TOOL_CALL_CREATED → REF_ATTACHED_TO_PAYLOAD → BACKEND_REF_ACCEPTED → REF_USED_AS_CONDITIONING → OUTPUT_MATCHED_TASK.

In the current user interface, the first three states could be established. REF_ATTACHED_TO_PAYLOAD, BACKEND_REF_ACCEPTED, and REF_USED_AS_CONDITIONING are not independently observable.

## 21.2. A Generated Source Panel Is Invalid Evidence of Source Fidelity

If the generator is allowed to create an entire comparison sheet, it can synthesize not only target candidates but also panels labeled "ORIGINAL." Therefore, any source/reference panels inside generative output should be treated as non-evidentiary by default.

A correct audit should display real input files outside the generative canvas or insert them using a deterministic non-generative method.

## 21.3. Simplification Did Not Eliminate Failure

The failure recurred after:

- a new chat;

- a clean package;

- removal of TEST/V19/v4 from the input;

- a change from four age-diverse ORIGINAL files to two single-person crops;

- an explicit instruction to produce four independent portraits.

This makes explanations such as "only the long context," "only extra Library files," and "only a second person in the frame" insufficient as standalone causes.

## 21.4. Face Reproducibility and Pipeline Reproducibility Are Different Properties

Strong differences between historical v1-v4 and the new three candidates before the failure should not automatically be classified as a technical error. Image generation is stochastic, and the exact historical prompt was not preserved. However, the pipeline is non-reproducible at a more fundamental level when not only the face but the output class changes: four candidates → age collage / technical sheet / synthetic source panel.

# 22. Lack of Full Generator Logs as a Separate Audit Gap

The assistant and user do not have direct access to the internal trace of the image-generation backend. The available tool metadata in this workflow contained limited fields, including gen_id, but did not provide a verifiable list of:

- image refs actually attached to the final payload;

- refs accepted by the backend as conditioning inputs;

- weights/priorities of each reference image;

- internal moderation/safety decision trace;

- model/routing version for the specific call;

- seed and full sampling parameters, if they were stored at all;

- reasons for ignoring or blending reference inputs.

The absence of such a log prevents an external user from independently localizing a reference-binding failure. At the same time, one cannot assert that OpenAI necessarily maintains a detailed step-by-step log of exactly this structure: the composition of internal telemetry/logging data is not disclosed publicly or through the available interface.

# 23. Additional Requirements for an External Quality Audit

The following should be added to the v1.0 requirements:

1. Use gen_id to reconstruct the actual image-generation request payload for problematic calls, if such payloads are retained.

2. Compare user-visible reference files with the refs actually attached by the tool layer to the request.

3. Establish which refs the backend confirmed as conditioning inputs.

4. Determine whether the task "4 independent candidates" was internally transformed into an infographic/reference-sheet request before sampling.

5. Review the moderation event that interrupted the series after three candidates and determine whether it affected the state of the subsequent retry.

6. Compare model/routing/configuration between the historically successful v1-v4 run and the new run, if such data are available.

7. Introduce a source-fidelity gate: a generated panel labeled ORIGINAL must never be treated as evidence; real refs should be displayed separately or verified by byte/hash identity.

8. For multi-reference identity tasks, preserve a machine-readable receipt: input_file_id/hash → attached_ref_id → backend_accepted=true/false.

9. On retry after partial generation, explicitly record whether the retry continues the previous trajectory or is a new independent call.

10. If no reference receipt is available, prohibit the assistant from claiming "the generator used exactly these refs"; the only permissible status should be "the refs were prepared/opened before the call."
