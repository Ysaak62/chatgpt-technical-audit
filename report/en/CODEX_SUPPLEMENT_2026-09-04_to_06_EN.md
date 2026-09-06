# Codex Supplemental Evidence Package

**Suggested placement:** `openai/codex` issue #41851 or the linked public audit repository  
**Suggested comment/title:** `Supplemental evidence, 4–6 Sep 2026: abrupt degradation in correction recovery and functional workflow blocking`  
**Format:** GitHub/Codex-compatible Markdown  
**Language:** English only  

> This document is an English-only Codex-ready version of the bilingual supplement prepared on 6 September 2026. It preserves the evidence boundaries of the source report: observable facts are separated from localized actions, and internal OpenAI causes remain `UNVERIFIED` unless telemetry exists.

## Supplement to the Public Technical Audit
## 4–6 September 2026: constraint binding, tool-action reliability, and abrupt workflow degradation in GPT-5.6 Sol

*Codex-ready English-only supplement for the public technical audit*

**Prepared:** 6 September 2026

## Executive summary

This supplement documents three consecutive days of work, 4–6 September 2026, in a long-running multimodal portrait-reconstruction project. By this stage the task was already highly specified: the source photographs, age anchors, identity constraints, protected features, left-eye geometry, wardrobe restrictions, and fail-closed rules had been repeatedly established and acknowledged.

The central finding is not that GPT-5.6 Sol cannot understand the specification. In many critical moments it restated the active rules correctly, diagnosed earlier violations correctly, and proposed technically appropriate corrections. The recurrent failure occurred when the acknowledged state had to govern the next executable action.

A sharp behavioral change was observed on 5–6 September, and especially on 6 September. Earlier failures were intermittent and often recoverable after correction. During the last two days, errors became serial and recovery became unreliable: the model could acknowledge a correction, restate the same rule, and then violate it again in the next or subsequent tool action. On 6 September the workflow became functionally blocked despite continued access to ChatGPT and despite switching between separate chats.

This report uses the ‘Applause Principle’ as a causal-discipline rule: temporal sequence is not proof of causation. The persistence of a failure after a tool call, a chat change, or a generator output does not by itself prove which internal OpenAI component caused it. Internal root cause remains UNVERIFIED without telemetry.

## 1. Scope and evidence standard

The observations concern a benign, long-running portrait workflow involving one real adult male subject across multiple ages. The user’s goal was to reconstruct a coherent age series while preserving identity and several stable facial asymmetries, including a damaged anatomically left eye.

By 4 September, the workflow was not an open-ended creative prompt. It already had a detailed specification, known source photographs, age anchors, explicit prohibited transformations, and a DEFAULT DENY / FAIL-CLOSED operating rule. Consequently, these three days are useful for evaluating state retention and execution fidelity rather than basic instruction comprehension.

Evidence is separated into three levels: (1) observable fact — user instruction, assistant statement, tool action, file or visible output; (2) localized action — an action attributable to a component because the action itself is visible or otherwise evidenced; and (3) internal cause — an OpenAI-side mechanism that cannot be established from client-visible behavior alone. Level (3) is marked UNVERIFIED unless telemetry exists.

## 2. 4 September: non-generative left-eye work and the verification gap

Work on 4 September focused primarily on strictly non-generative local editing of the damaged left eye. The established order of operations was: iris/pupil → sclera → complete eye audit → checkpoint/fixation → mouth corner → cheek → lower eyelid → eyebrow if necessary → upper eyelid/squint.

The rationale had already been learned from prior failures: final iris work performed after changing the eyelids risked conflict with the lash margin and eye-slit geometry. The assistant understood this logic and explicitly stated that the iris and sclera should be finalized before eyelid/squint work, with no renewed edge intervention in the iris after the squint was fixed.

The assistant also made precise-sounding statements about local edits, changed-pixel counts, zero changes outside a mask, and checkpoint/HOLD states. These statements are useful as a record of what the assistant believed or claimed it had done, but they are not equivalent to independent raster verification. Without a direct file diff, ‘0 pixels outside the mask’ remains a tool/self-report claim rather than machine-proven evidence.

This distinction became important later: throughout the audit, the ability to describe a compliant operation and the ability to prove that the operation was actually compliant must remain separate.

## 3. 5 September: age-chain reconstruction and a source-set integrity failure

On 5 September the project shifted toward reconstructing the subject’s age chain and preparing a new 79–80-year portrait stage. Earlier anchors included approximately 49, 56–57, 65–66, and later-life real photographs. The immediate task was to identify a realistic intermediate reference point and generate 5–6 candidates of the same man, while avoiding plaid clothing and dominant burgundy/magenta tones.

A critical failure concerned source-set integrity. After the fact, the assistant established that a generation had not been conditioned on the agreed real-image set. Previously generated images had entered the effective input state while the required real reference was absent or not properly bound.

This episode is stronger evidence than the vague statement ‘the generator ignored the original.’ The observable and localized problem was upstream: the input package used for execution did not match the source set that had been agreed in the conversation.

This directly illustrates the core audit pattern: constraint acknowledged → constraint not reliably bound to the next action. No speculative downstream substitution mechanism is needed to explain this specific failure.

## 4. 6 September: controlled 79–80 generation attempt

On 6 September the generation protocol was tightened further. The intended package was: three real age references no older than 82 → the full approved specification → strict AGE LOCK 79–80 → strict IDENTITY LOCK → six separate independent generations.

Generated candidates, rejected portraits, collages, and older-than-82 images were excluded from conditioning. Additional wardrobe/context restrictions were also explicit: no plaid/check patterns, no dominant burgundy/magenta palette, and no automatic carry-over of a cap or long scarf from a contextual family photograph into an ordinary indoor seated portrait.

### 4.1. Wrong input package despite prior agreement

In an early 6 September run, the actual execution did not match the agreed package. Subsequent review established that the first generation call used only one real reference instead of all three intended real references, and the prompt was a shortened/adapted version rather than the full approved specification.

Worse, subsequent images in that series used a newly generated result as an anchor/reference. This directly violated the explicit rule that no generated candidate could become a conditioning reference for the next candidate.

The series was therefore correctly reclassified as INVALID / WRONG INPUT. This invalidity existed before any aesthetic or identity assessment of the resulting portraits.

### 4.2. Output-format failure: collage instead of six independent images

The user repeatedly required six separate independent generations — not a collage, not a contact sheet, and not six variants embedded in one image.

Nevertheless, several retries produced 3×2 grids or comparison sheets. This occurred even after the assistant itself had correctly restated the requirement for six separate portraits.

This is a particularly clean example of a verbal-state-to-action failure: the model could state the format constraint correctly and then execute an incompatible image-generation action immediately afterward.

### 4.3. Identity drift despite strict IDENTITY LOCK

Multiple retries produced a generic elderly man or a synthetic face family rather than the specific man represented in the supplied real photographs. The user repeatedly clarified that the task was not to create ‘a plausible man of that age’ but to reconstruct this particular man.

The assistant subsequently recognized several outputs as another or overly generalized man and acknowledged that they violated the IDENTITY LOCK. Again, the identity requirement was not added after the result; it was a primary constraint before generation.

### 4.4. Cap and long scarf: contextual-prop leakage into identity

One exact 82-year reference showed the man wearing a cap and a long scarf. The user explained that these were part of a family joke/try-on episode, not stable markers of his ordinary indoor appearance or identity.

The specification was therefore sharpened: for a normal indoor seated portrait, no cap, no hat, and no long scarf unless explicitly requested by scene context. These items must be treated as contextual props, not identity features.

This episode illustrates a multimodal conditioning risk: a visually salient but incidental feature of a source photograph can receive disproportionate weight unless the controller reliably preserves the distinction between identity and context.

### 4.5. Damaged left iris: improved specification, incomplete stability

A separate 6 September experiment focused on the damaged anatomically left eye. Before specification reinforcement, a frequent failure pattern was: narrow eye slit → elongated pale capsule/oval. The required anatomy was different: circular iris → central pupil → eyelids partially occlude the iris → chronic leukoma overlays the anatomy.

The iris block was promoted to HIGHEST PRIORITY / HARD CONSTRAINT. The required sequence became: (1) circular or near-circular iris; (2) central weak pupil; (3) eyelid occlusion while preserving the characteristic squint; (4) diffuse leukoma; (5) color and texture.

This reinforcement materially improved some results: several outputs began to read as a circular iris hidden by the lids rather than a capsule-shaped light patch. However, a compensatory failure emerged — the pupil could become too dark/visible, while the leukoma could become too smooth and uniform.

The important conclusion is capability versus reliability: the system demonstrated that it could move toward the correct anatomy when the constraint was strongly prioritized, but it did not demonstrate stable simultaneous compliance across iris geometry, pupil visibility, squint, leukoma texture, identity, age, and output format.

### 4.6. Final agreed package and repeated non-compliance on 6 September

By the end of the work period, the user issued a compact, unambiguous command: three real age photographs ≤82 years, the full specification, six separate generations, strict IDENTITY LOCK, AGE 79–80, reinforced circular-iris/central-weak-pupil geometry, no cap or long scarf indoors, no plaid clothing, and no generated candidates as references.

A subsequent run produced four separate images rather than six. After another retry, the three real reference files were explicitly materialized into the working environment, yet the next image-generation result again appeared as a single 3×2 collage rather than six independent files.

Thus the same formal requirement — SIX SEPARATE GENERATIONS — was correctly restated, violated, corrected, and then violated again in a different way within the same working period.

## 5. Abrupt behavioral change on 5–6 September and functional workflow blocking

The most important new observation is a qualitative change in model behavior during the last two days, especially on 6 September.

Earlier in the project, failures were serious but generally intermittent: a wrong result could be followed by a correction, then a useful or acceptable result. In the last two days, the pattern shifted toward serial non-recovery: error → correction → acknowledgement → repeated or adjacent error → another correction → new deviation.

On 6 September the user remained able to send messages and invoke tools, so there is no evidence of a formal account-level platform block. However, the established task became practically non-executable because repeated model actions did not converge on the already-agreed target. This report therefore uses the narrower term FUNCTIONAL WORKFLOW BLOCKING.

The user also attempted to escape the failure state by changing chats. The same general inability to reliably preserve and execute the agreed constraints persisted across chat boundaries. This makes a single-chat contamination explanation less sufficient, but it does not prove a global model defect, an account-specific intervention, or an intentional block.

The observable fact is narrower: the same established task, with a stable specification, failed to recover reliably across multiple successive chats during the same time period. The internal cause remains UNVERIFIED.

## 6. The ‘Applause Principle’: causal discipline

The audit now explicitly applies a methodological rule referred to here as the ‘Applause Principle.’ Its purpose is to prevent post hoc causal attribution.

If event B follows event A, that sequence alone does not establish that A caused B. A wrong generator output after an assistant action does not by itself prove that the generator independently replaced the source. Persistence across chats does not by itself prove an account-level or model-wide block. A visible downstream symptom does not prove the hidden subsystem responsible for it.

Causal attribution requires evidence that the proposed component had the relevant mechanism and, ideally, a trace that the mechanism was actually exercised in the case being analyzed.

The practical audit rule is: OBSERVED FACT → LOCALIZED ACTION IF DIRECTLY EVIDENCED → INTERNAL CAUSE ONLY WITH TELEMETRY. Everything else remains UNVERIFIED.

This principle also prevents the reverse error: the assistant must not explain its own demonstrably incorrect source selection or tool call by invoking an unknown downstream component when the upstream action itself is already visible.

## 7. Evidence classification matrix

The following distinctions should be preserved in any public discussion of these incidents.

| Observation | Evidence status | What can be concluded |
|---|---|---|
| Assistant correctly restates a rule, then performs an incompatible action | Observed | Instruction comprehension can coexist with action-level non-compliance. |
| A generated image enters the next reference chain despite an explicit prohibition | Observed/localized when the call state is visible | The controller/tool-call path violated source provenance. |
| A 3×2 collage is returned after a request for six separate files | Observed | Output-format constraint was not bound to execution. |
| Failure persists after switching chats | Observed | Single-chat context alone is not a sufficient explanation; root cause still unverified. |
| The generator independently substituted a source | Unverified unless telemetry proves it | Do not assert as fact. |
| OpenAI deliberately blocked the user | Unverified | Do not assert as fact; use ‘functional workflow blocking’ for the observed operational effect. |

## 8. Main finding from the three-day period

The 4–6 September evidence does not support the claim that GPT-5.6 Sol was unable to understand the task. In multiple critical moments it correctly summarized the restrictions, correctly identified a previous violation, and correctly proposed a remedy.

The recurrent problem appeared after comprehension: accepted constraints were not reliably converted into effective pre-action gates and were not reliably bound to the next tool/action state.

Across the three days, this manifested as source-set corruption or loss, generated material entering a forbidden reference path, incomplete output counts, collages instead of independent files, identity drift, contextual-prop leakage, failure to preserve eye geometry, and correction of one property at the cost of another.

The strongest concise formulation is therefore: GPT-5.6 Sol demonstrates the ability to understand and verbalize active constraints, but those constraints are not always reliably bound to the immediately following executable action. Repeated textual correction does not guarantee that the corrected rule becomes an effective pre-action gate.

## 9. New conclusion: recovery reliability deteriorated, not merely first-pass accuracy

The new material extends the original audit in an important way. The problem is no longer adequately described only as intermittent instruction-following failure.

During 5–6 September, and especially on 6 September, the ability to recover after direct correction deteriorated sharply. The model could acknowledge the correction accurately yet fail to operationalize it in the next relevant action.

For a production user, this distinction is critical. A model with a non-zero error rate can remain useful if a single correction restores the specification. A model becomes operationally expensive when the user must repeatedly act as external orchestrator, state store, specification owner, QA layer, and continuation trigger.

That is the practical significance of the 6 September functional workflow blocking: not loss of chat access, but loss of a reliable path from explicit specification to accepted output.

## 10. Telemetry required for internal localization

A definitive internal diagnosis would require an auditable chain such as: approved source identifiers → references selected by the assistant/controller → actual tool request payload → references accepted downstream → generator/request ID → resulting output.

Without that chain, claims about an internal model snapshot, orchestration layer, reference-binding service, downstream image generator, account-level intervention, or other hidden subsystem must remain UNVERIFIED.

## 11. Requested safeguards and evaluation metrics

The observed failures suggest several safeguards: fail closed when source binding cannot be verified; preserve source-set provenance; separate user-authored hard constraints from model-inferred preferences; prevent generated outputs from silently entering a forbidden reference chain; require target-level evidence before declaring completion; and treat direct user correction as a trigger to refresh the executable state rather than merely produce verbal agreement.

Useful evaluation metrics include Correction Binding Rate, Requirement Coverage at First Delivery, Unauthorized Reference Substitution Rate, Output-Format Compliance, Identity Preservation Rate, Interventions per Accepted Deliverable, and Recovery-to-Accepted-State after a single explicit correction.

The most relevant production-level metric is not peak visual quality alone, but accepted, complete deliverables per unit of human supervision.

## 12. What this supplement does NOT claim

This supplement does not claim intentional sabotage, deliberate blocking, or malicious behavior.

It does not claim that every GPT-5.6 Sol run fails, that the model is incapable of the requested portrait task, or that every failure shares a single internal cause.

It does not claim that the downstream image generator independently replaced references unless such substitution is directly evidenced.

It does not claim that persistence across chats proves an account-level restriction or a global model regression.

It claims a documented client-visible reliability pattern: comprehension and verbal acknowledgement were repeatedly stronger than subsequent constraint binding, tool-action fidelity, and correction recovery.

## Appendix A. Public tracker context as of 6 September 2026

The public OpenAI Codex issue #41851, ‘GPT-5.6 Sol: acknowledged constraints are not reliably bound to subsequent actions,’ remained OPEN when checked on 6 September. It carried the labels bug, model-behavior, and imagen, and showed three comments.

One automated Codex Action comment suggested potentially related/duplicate issues. One independent GitHub user added a public comment reporting severe recent degradation in reasoning, instruction following, and consistency on ChatGPT web / Sol High. This is corroborating user testimony, not proof of a shared internal cause.

No visible human OpenAI staff response or assignment was observed in the issue metadata checked at that time. Absence of a public reply does not establish absence of internal review.

The separate public repository Ysaak62/chatgpt-technical-audit remained public and linked from the issue as the full evidence package.

**Public references checked on 6 September 2026:**
- https://github.com/openai/codex/issues/41851
- https://github.com/Ysaak62/chatgpt-technical-audit
