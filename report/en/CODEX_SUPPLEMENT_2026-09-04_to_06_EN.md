# Codex Supplemental Evidence Package

**Suggested placement:** `openai/codex` issue #41851 or the linked public audit repository  
**Suggested comment/title:** `Supplemental evidence, 4–6 Sep 2026: abrupt degradation in correction recovery and functional workflow blocking`  
**Format:** GitHub/Codex-compatible Markdown  
**Language:** English only

> Privacy-redacted public version. Medical diagnosis, cause, functional impairment, treatment history, and other health information concerning the portrait subject are intentionally excluded. A stable identity-relevant visual characteristic is referred to only as **FEATURE-F1**.

## Supplement to the Public Technical Audit
## 4–6 September 2026: constraint binding, tool-action reliability, and abrupt workflow degradation in GPT-5.6 Sol

**Prepared:** 6 September 2026

## Executive summary

This supplement documents three consecutive days of work, 4–6 September 2026, in a long-running multimodal portrait-reconstruction project. By this stage the task was highly specified: source photographs, age anchors, identity constraints, protected visual features, wardrobe restrictions, and fail-closed rules had repeatedly been established and acknowledged.

The central finding is not that GPT-5.6 Sol could not understand the specification. In critical moments it correctly restated active rules, diagnosed earlier violations, and proposed technically appropriate corrections. The recurrent failure occurred when the acknowledged state had to govern the next executable action.

A sharp behavioral change was observed on 5–6 September, especially on 6 September. Earlier failures were intermittent and often recoverable after correction. During the last two days, errors became serial and recovery became unreliable: the model could acknowledge a correction, restate the same rule, and then violate it again in the next or subsequent tool action. On 6 September the workflow became functionally blocked despite continued access to ChatGPT and despite switching between separate chats.

This report applies the **Applause Principle** as a causal-discipline rule: temporal sequence is not proof of causation. Internal root cause remains `UNVERIFIED` without telemetry.

## 1. Scope and evidence standard

The observations concern a benign portrait workflow involving one real adult male subject across multiple ages. For privacy, public discussion of the subject's stable identity-relevant visual characteristic uses the neutral code **FEATURE-F1**. The public report does not disclose diagnosis, medical cause, treatment history, functional impairment, or other health information.

Evidence is separated into three levels:

1. **Observable fact** — user instruction, assistant statement, tool action, file, or visible output.
2. **Localized action** — an action attributable to a component because the action itself is visible or otherwise evidenced.
3. **Internal cause** — an OpenAI-side mechanism that cannot be established from client-visible behavior alone and is therefore `UNVERIFIED` unless telemetry exists.

## 2. 4 September: non-generative local work and the verification gap

Work on 4 September focused on strictly non-generative local editing of FEATURE-F1 and adjacent protected geometry. The established order of operations was fixed in advance so that later edits would not invalidate earlier geometry.

The assistant made precise-sounding statements about local edits, changed-pixel counts, zero changes outside a mask, and checkpoint/HOLD states. These statements are useful as records of what the assistant believed or claimed it had done, but they are not equivalent to independent raster verification. Without a direct file diff, a claim such as “0 pixels outside the mask” remains a tool/self-report claim rather than independently machine-proven evidence.

This distinction is central to the audit: the ability to describe a compliant operation and the ability to prove that the operation was actually compliant must remain separate.

## 3. 5 September: age-chain reconstruction and source-set integrity failure

On 5 September the project shifted toward reconstructing the subject's age chain and preparing a new 79–80-year portrait stage. The immediate task was to identify an intermediate reference point and generate 5–6 candidates of the same man while preserving identity and avoiding specified wardrobe/color exclusions.

A critical failure concerned source-set integrity. Subsequent review established that a generation had not been executed from the agreed real-image set: previously generated images entered the effective input state while a required real reference was absent or not properly bound.

The observable problem was therefore upstream: the input package used for execution did not match the source set agreed in the conversation. This directly illustrates the core pattern:

**constraint acknowledged → constraint not reliably bound to the next action.**

No speculative downstream substitution mechanism is required to explain this specific failure.

## 4. 6 September: controlled 79–80 generation attempt

The intended package was:

- three real age references no older than 82;
- the full approved specification;
- strict AGE LOCK 79–80;
- strict IDENTITY LOCK;
- six separate independent generations;
- no generated candidates as conditioning references;
- explicit wardrobe/context exclusions.

### 4.1. Wrong input package despite prior agreement

In an early run, execution did not match the agreed package. Subsequent review established that the first generation call used only one real reference instead of all three intended real references, and the prompt was shortened/adapted rather than the full approved specification.

Subsequent images in that series then used a newly generated result as an anchor/reference, directly violating the prohibition on generated candidates entering the conditioning chain.

The series was therefore reclassified as **INVALID / WRONG INPUT** before aesthetic or identity assessment.

### 4.2. Output-format failure: collage instead of six independent images

The user repeatedly required six separate independent generations — not a collage, contact sheet, or six variants embedded in one image.

Several retries nevertheless produced 3×2 grids or comparison sheets, including after the assistant had correctly restated the requirement for six separate portraits.

This is a clean verbal-state-to-action failure: the constraint was represented correctly in text and then violated at execution.

### 4.3. Identity drift despite strict IDENTITY LOCK

Multiple retries produced a generic elderly man or a synthetic face family rather than the specific subject represented by the supplied photographs. The assistant subsequently recognized these outputs as violating the IDENTITY LOCK.

The identity requirement existed before generation; it was not added after observing the result.

### 4.4. Contextual-prop leakage into identity

One age reference contained visually salient contextual clothing/accessories that were not stable markers of ordinary appearance. The specification was therefore sharpened so that such props could not automatically transfer into an ordinary indoor portrait.

This illustrates a multimodal conditioning risk: visually salient but incidental source features can receive disproportionate weight unless the controller preserves the distinction between identity and context.

### 4.5. FEATURE-F1: improved specification, incomplete stability

A separate experiment focused on preserving FEATURE-F1 as a stable identity-relevant geometric characteristic. The feature was promoted to **HIGHEST PRIORITY / HARD CONSTRAINT** and decomposed into explicit geometry and occlusion requirements.

Some outputs improved after this reinforcement, demonstrating capability. However, simultaneous compliance across FEATURE-F1 geometry, identity, age, and output format remained unstable.

The relevant conclusion is capability versus reliability: successful local compliance did not imply stable multi-constraint compliance.

### 4.6. Final agreed package and repeated non-compliance

By the end of the work period, the user issued a compact command fixing the three real references, full specification, six separate generations, strict identity/age locks, FEATURE-F1 preservation, wardrobe/context exclusions, and the prohibition on generated candidates as references.

A subsequent run produced four separate images rather than six. After another retry, the real reference files were explicitly prepared, yet the next image-generation result again appeared as a single 3×2 collage.

Thus the same requirement — **SIX SEPARATE GENERATIONS** — was correctly restated, violated, corrected, and then violated again in a different way within the same working period.

## 5. Abrupt behavioral change on 5–6 September and functional workflow blocking

Earlier failures were serious but generally intermittent: a wrong result could be followed by correction and then a useful or acceptable result. On 5–6 September, especially 6 September, the pattern shifted toward serial non-recovery:

**error → correction → acknowledgement → repeated or adjacent error → another correction → new deviation.**

The user retained normal chat/tool access, so there is no evidence of a formal account-level platform block. The narrower and supported term is **FUNCTIONAL WORKFLOW BLOCKING**: the established task became practically non-executable because repeated actions did not converge on the already-agreed target.

Persistence across separate chats makes a single-chat contamination explanation insufficient by itself, but does not prove a global model defect, account-specific intervention, or intentional block.

## 6. The Applause Principle

If event B follows event A, that sequence alone does not establish that A caused B.

A wrong generator output after an assistant action does not prove that the generator independently substituted a source. Persistence across chats does not prove an account-level or model-wide block. A visible downstream symptom does not identify the hidden subsystem responsible for it.

The practical audit rule is:

**OBSERVED FACT → LOCALIZED ACTION IF DIRECTLY EVIDENCED → INTERNAL CAUSE ONLY WITH TELEMETRY.**

Everything else remains `UNVERIFIED`.

## 7. Evidence classification matrix

| Observation | Evidence status | What can be concluded |
|---|---|---|
| Assistant correctly restates a rule, then performs an incompatible action | Observed | Instruction comprehension can coexist with action-level non-compliance. |
| A generated image enters the next reference chain despite an explicit prohibition | Observed/localized when call state is visible | The controller/tool-call path violated source provenance. |
| A 3×2 collage is returned after a request for six separate files | Observed | Output-format constraint was not bound to execution. |
| Failure persists after switching chats | Observed | Single-chat context alone is not a sufficient explanation; root cause remains unverified. |
| The generator independently substituted a source | Unverified unless telemetry proves it | Do not assert as fact. |
| OpenAI deliberately blocked the user | Unverified | Do not assert as fact; use “functional workflow blocking” for the observed operational effect. |

## 8. Main finding

The 4–6 September evidence does not support the claim that GPT-5.6 Sol was unable to understand the task. In multiple critical moments it correctly summarized restrictions, correctly identified previous violations, and correctly proposed remedies.

The recurrent problem appeared after comprehension: accepted constraints were not reliably converted into effective pre-action gates and were not reliably bound to the next tool/action state.

The strongest concise formulation remains:

> **GPT-5.6 Sol demonstrates the ability to understand and verbalize active constraints, but those constraints are not always reliably bound to the immediately following executable action. Repeated textual correction does not guarantee that the corrected rule becomes an effective pre-action gate.**

## 9. Recovery reliability

During 5–6 September, especially 6 September, the ability to recover after direct correction deteriorated sharply **within the observed workflow**. The model could accurately acknowledge a correction yet fail to operationalize it in the next relevant action.

For production use, this distinction matters: a system with a non-zero first-pass error rate may remain useful if one correction restores the specification; it becomes operationally expensive when the user repeatedly has to act as external orchestrator, state store, specification owner, QA layer, and continuation trigger.

## 10. Telemetry required for internal localization

A definitive internal diagnosis would require an auditable chain such as:

**approved source identifiers → references selected by assistant/controller → actual tool request payload → references accepted downstream → request/generation ID → resulting output.**

Without that chain, claims about an internal model snapshot, orchestration layer, reference-binding service, downstream generator, account-level intervention, or other hidden subsystem must remain `UNVERIFIED`.

## 11. Requested safeguards and metrics

Suggested safeguards include:

- fail closed when source binding cannot be verified;
- preserve source-set provenance;
- separate user-authored hard constraints from model-inferred preferences;
- prevent generated outputs from silently entering forbidden reference chains;
- require target-level evidence before declaring completion;
- treat direct user correction as a trigger to refresh executable state rather than merely produce verbal agreement.

Useful metrics include Correction Binding Rate, Requirement Coverage at First Delivery, Unauthorized Reference Substitution Rate, Output-Format Compliance, Identity Preservation Rate, Interventions per Accepted Deliverable, and Recovery-to-Accepted-State after one explicit correction.

## 12. What this supplement does not claim

This supplement does not claim intentional sabotage, deliberate blocking, malicious behavior, universal model failure, or a single hidden root cause.

It does not claim that a downstream image generator independently replaced references unless such substitution is directly evidenced.

It claims a documented client-visible reliability pattern: comprehension and verbal acknowledgement were repeatedly stronger than subsequent constraint binding, tool-action fidelity, and correction recovery.

## Appendix A. Public tracker context as of 6 September 2026

The public OpenAI Codex issue #41851 remained open when checked on 6 September. It carried the labels `bug`, `model-behavior`, and `imagen`. Automated duplicate matching and independent user corroboration were visible; no public human OpenAI staff response or assignment was visible at that time.

Absence of a public reply does not establish absence of internal review.

Public references:
- https://github.com/openai/codex/issues/41851
- https://github.com/Ysaak62/chatgpt-technical-audit