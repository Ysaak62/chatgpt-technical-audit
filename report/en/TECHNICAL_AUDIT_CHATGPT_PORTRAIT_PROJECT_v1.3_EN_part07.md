# 27. Addendum v1.3: Repeated Reliability Experiment on 30 Aug 2026

## 27.1. Purpose and Design of the Experiment

On 30 August 2026, the user proposed not another single attempt to "get a good portrait," but a series of ten independent generative runs as a test of behavioral reproducibility.

The user's condition was to preserve **the same task and the same source images as in the first experiment of that day**. The user deliberately declined to re-ask before each run which ORIGINAL files, which task specification, and which task were being used: the object of the test was the assistant-controller's ability to preserve the already established state across consecutive actions on its own.

This matters for interpretation: the experiment tested not only pixel/output quality, but the stability of the binding **approved state → next action**.

A critical evidence boundary remains. The user interface does not provide an independent backend receipt showing the conditioning refs actually attached for each run. This section therefore distinguishes among:

- **the invariant state specified by the user**;
- **the observable result of each run**;
- **the internal reference-binding state that is not verifiable from the user interface**.

## 27.2. Observed Sequence of Runs 1–6

The series was planned as 10 runs, but six had been completed when v1.3 was fixed. The statistical test is therefore **incomplete**; only events already observed are recorded below.

### Run 1

The first run produced a package of ten separate formal studio portraits of a mature man in a suit. The results varied in composition, hair, tie, and facial shape, but generally remained within the expected class "mature man / formal portrait" and reproduced pronounced asymmetry of the left eye.

Available gen_id values:

- `b1b9ab74-6aaa-43c0-bd7a-986eec9edf4b`
- `5542516f-8582-45bf-928b-65a31e93fcff`
- `06f0a104-eb93-4e8f-a090-60b2d979fb59`
- `05e6fd42-68aa-4097-b0e4-d24a4d8c0e03`
- `7b35e5ae-f9af-4d1b-96eb-401524bd0149`
- `bcd2d2cd-19ba-49d2-b7cc-caf4d4dd1404`
- `d24f7413-d3b8-4633-8e1d-40b97b029cc8`
- `fe21500f-71a2-43b5-8b4f-15dc6ef076c9`
- `c52d637c-f8c4-46e3-a25f-fe08796d6864`
- `28089036-09e8-4c42-8ab8-cff630760d5b`

### Run 2

The next run abruptly changed output class: instead of the mature man from the previous portrait family, it produced a substantially younger man with dark hair, a black crewneck/sweater, and a beige background, without the characteristic left-eye pathology/asymmetry and without a formal suit.

- gen_id: `04801613-9b8f-4424-a7c3-eeadb5838da4`

This deviation cannot reasonably be described as only a small stochastic variation in facial traits: age interpretation, clothing, background, eye structure, and the overall morphological family all changed at the same time.

### Run 3

The third run essentially continued the same new young-man template: dark hair, black crewneck, beige studio background, and absence of the required left-eye asymmetry.

- gen_id: `ece06e9e-730d-468f-907a-61765f0343d5`

This is not a single random outlier, but repetition of the same incorrect output family in two consecutive actions.

### Run 4

The fourth run returned to a mature man in a suit with pronounced left-eye asymmetry.

- gen_id: `76290fc5-d619-473d-a1fb-6db98a81c641`

The fact of this return matters: the system was not in a state of permanent inability to generate the expected output class. The failure was episodic.

### Run 5

The user instructed the system not to economize on the number of candidates and to provide at least four images per run. Instead of four separate candidates, the system produced one 2×2 contact sheet/collage labeled "GENERATION 5/10," containing four nearly identical images of the young man from the incorrect template seen in runs 2–3.

- gen_id: `82076528-d1fb-428e-bc82-5d6f436555e7`

This output contains two deviation classes at once: return to the wrong morphological family and transformation of the requirement for multiple candidates into one collage/contact sheet.

### Run 6 and Direct Corrective Feedback

Before the sixth run, the user explicitly instructed: **"do not repeat yourself anymore."** Despite this, the sixth result was again a 2×2 contact sheet with essentially the same young man, the same clothing, the same background type, and the same layout.

- gen_id: `b807f70e-5fff-4886-8858-9280018dfe9e`

This is a particularly strong observable event: explicit corrective feedback directed specifically against repetition of the previous result **did not change the next class of action/output**.

## 27.3. What This Experiment Confirms and What It Does Not Yet Confirm

**Confirmed by observable results:**

1. Behavior is not continuously defective: the expected output class appeared in run 1 and again in run 4.
2. Sharp transitions into a different, persistent output family can occur between successful/relatively compliant results.
3. An incorrect output family can repeat across multiple consecutive runs.
4. Direct user corrective feedback does not necessarily change the next tool result.
5. Additional verbal checks and assistant confirmations are not hard enforcement by themselves; this is consistent with the previously documented failure of state-to-action binding.

**Not confirmed at this stage:**

1. That GPT-5.6 Sol "irreversibly deteriorates" over time.
2. That there is medically or mathematically established "progression" of the defect.
3. Which specific internal component produced each deviating output.
4. Which conditioning refs the backend actually accepted in each of the six runs.
5. The statistical frequency of this failure across the user population: six runs from one workflow do not provide a population estimate.

The correct engineering formulation for the current evidence state is therefore: **intermittent failure of control/execution behavior, with episodes of persistent repetition of an incorrect trajectory and inadequate recovery after explicit correction**.

# 28. Refinement of the Causal Model: User Verification Had Already Been Maximally Strengthened

Throughout the project, the user repeatedly applied a sequence of control questions and moved to the next step only after receiving a positive answer from the assistant. Therefore, the recommendation "just verify each step" is not a sufficient correction for this case: that mode had already been tested in practice.

The strongest practical conclusion can now be formulated as follows:

> The problem was not merely the absence of checking. The assistant could successfully pass a verbal state check, confirm the correct sources/rules/constraints, and then execute an action incompatible with the state it had just confirmed.

Critical constraints therefore require not assistant self-report, but technical enforcement: machine-readable state, source/reference receipt, a hard pre-action gate, fail-closed status, and independent post-action verification.

# 29. Correction of the Hypothesis That "One Successful Result Was a Random Exception"

A subsequent provenance audit recovered several independent successful or partially successful generative episodes, including the historical v1-v4 series and new individual candidates from the same broad morphological family before the later failure. The 30 Aug 2026 series itself also contains a return to the expected output class after two severely deviating runs.

Therefore, the stronger formulation that "a similar/successful generation was the only random exception produced by an incapable system" is no longer supported by the available evidence.

A narrower conclusion remains supported:

> The existence of one or several successful results establishes the presence of the corresponding capability, but does not establish reproducibility. In this workflow, a gap is observed between capability and reliability.
