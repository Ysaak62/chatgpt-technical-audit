# 9. Why the Protocols Did Not Eliminate the Defects

The protocols were useful as specifications, checklists, a status vocabulary, and an audit trail. But in ordinary chat they remained text. They did not become a server-side policy engine that physically blocks a tool call when SHA, mask lock, rejected method, or current-turn authorization requirements are violated.

- A rule could require STOP, yet the model could still propose an alternative path.

- A rule could require REJECTED_METHODS, yet that field was not a system validator for a tool call.

- A rule could require 0 outside-mask diff, but without executed code this remained a requirement, not a fact.

- A rule could prohibit generation, yet on one occasion the generator was still called after NO GENERATION.

Thus, increasing the complexity of textual controls improved formal precision and observability, but did not remove the architectural gap between "I know the rule" and "I am technically unable to violate it."

# 10. Role of Multitasking and Long Context

Multitasking and long context are not the sole root cause, but they are a plausible load factor: the number of files, branches, masks, tool states, exceptions, protected regions, and intermediate artifacts increases. This raises the probability of state-tracking errors and incorrect binding.

However, clean routine repeats and a new chat showed that the error could persist after simplifying the immediate task and after changing chats. Therefore, "it is all caused by a long chat" is refuted as a sufficient explanation.

**Most accurate relationship:** multitasking/long history → increased state-management load → higher probability of more fundamental state/action binding, pre-action gate, and verification failures. But the same defects can also appear in a simple current operation.

# 11. Most Defensible Causal Model

| **Node** | **Essence** | **Evidence status** |
|---|---|---|
| **A. Infrastructure** | 403/502, expired transfer URLs, isolated unavailability of an external action. | Confirmed for individual episodes. |
| **B. State/orchestration** | Unstable preservation of the tuple source + working copy + mask + coords + tool capability + last verified result. | Strongly supported by multiple error classes, but internal implementation unknown. |
| **C. State-to-action binding** | A known rule does not become a mandatory precondition for the next action. | Behaviorally confirmed; internal mechanism is a hypothesis. |
| **D. Pre-action GO/NO-GO** | A method is admitted to execution without sufficient prior validation or without stopping at low confidence. | Supported by method repeats after objections and unresolved causes. |
| **E. Closed-loop verification** | The next step is built on expected rather than measured actual state. | Supported by false progress, zero-pixel ROI, partial PASS. |
| **F. Fault escalation/retry** | A sequence of errors is treated for too long as isolated local failures, leading to repetition. | Supported by the history of repeats and the user's need to manually prohibit the loop. |
| **G. Capability interpretation** | Connected/authenticated is treated as proof of edit/write capability. | Confirmed by the incident report. |
| **H. Generator reference binding** | Files visible to the model/Library do not necessarily become visual conditioning refs for the generator; a semantic meta-task can take control. | Strong hypothesis from the last test; exact point not established. |
| **I. Method limitation** | Lab/hook-look may execute technically yet fail to solve the specific anatomical task. | Confirmed by reports. |
| **J. Long context** | Increases state-tracking complexity, but does not explain failures after clean reset/new chat. | Risk factor, not the root of all failures. |

# 12. Control Loop: How It Should Have Worked and How It Sometimes Worked

**Normal engineering loop:** task → input verification → method analysis → GO/NO-GO → action → measurement of actual result → comparison with task specification → PASS/REJECT → only then next step.

**Observed failed loop:** task → intention/plausible method → action/attempt → assumption of expected result → local explanation of failure → retry/new variant → accumulation of new rules → recurrence of the same error class.

This is why the system could be strong at post-hoc analysis of its own error while remaining weak at preventing repetition.

# 13. What Can Be Stated Confidently, and What Cannot

## 13.1. Confirmed

- The error series affected both generative and non-generative methods.

- Some non-generative methods worked strictly and measurably; there was no total failure of all deterministic operations.

- There were real infrastructure failures in data access (HTTP 502) and episodes of 403 for an external tool.

- There were assistant execution errors: wrong side/source, retry without a mandatory precondition, alteration of the experiment structure, false or overly strong status, and zero-pixel ROI after localization had been claimed.

- The protocols were textual and were not hard enforcement.

- A new chat and clean package did not remove the generative failure, so the long old context is not a sufficient cause.

- The last generative test ended with the wrong output type even after the four ORIGINAL files and task specification had been opened to the assistant.

## 13.2. Cannot Be Established from Available Data

- That one specific backend component is the root cause of every failure.

- That the image generator is globally "defective" across all scenarios.

- That the four opened ORIGINAL files in the last test physically reached the generator as visual refs in the required binding.

- That multitasking by itself produced all errors.

- That deliberate sabotage or subjective system motivation existed.

- That all success percentages previously stated by the assistant were statistically calibrated; such estimates were usually heuristic.

# 14. Impact on the User and the Project

- Repeated verification of source files and anatomical side.

- Repeated construction and checking of masks and geometry.

- Repeated attempts to connect/check Adobe and other tools.

- Growth in protocol volume as a response to prior violations.

- Need for the user to independently audit assistant claims of PASS/readiness/completion.

- Zero progress in some branches while background work was expected but was not actually taking place.

- Repetition of clean generative experiments to separate user error from system error.

An early incident report documents at least one session on 18 August lasting approximately 6 h 18 min as a lower bound for one session, not as the total project time. The full workflow continued for more than 11 days; the exact amount of time directly lost because of system errors cannot be calculated from the available materials without server logs.

# 15. Final Engineering Assessment

**Final classification:** for this class of long-running tool-based workflow, ChatGPT demonstrated systemic unreliability. This does not mean every component was continuously malfunctioning. It means the system as a whole did not provide a reproducible cycle of "understand correctly → select the correct method → verify admissibility → execute over the exact state → measure the actual result → do not repeat a rejected path."

**Practical defect for the user:** the system could know a rule, explain the rule, save the rule in Library, and still fail to guarantee compliance with it in the next tool action. Textual protocols therefore made violations diagnosable, but did not reliably prevent them.

**Most important system risk:** not one isolated filter or generator error, but unreliable coordination among project state, rules, files, external tools, generator, and result verification.

# 16. What an External Quality Audit Should Examine

1. Logs of all image-generation tool calls: which image refs actually entered the payload and which conditioning refs the backend accepted.

2. The difference among assistant context, file-layer visibility, and the generator's actual payload.

3. Causes of the specific Adobe 403 and file-materialization 502 events.

4. The mechanism by which explicit user constraints and saved protocols do or do not influence tool-call gating.

5. Why a generative tool call occurred after explicit NO GENERATION.

6. Why, after a known mandatory precondition ("four refs first"), a repeated run occurred without refs.

7. Why a zero-pixel ROI could be accompanied by a localization claim.

8. Why a partial/local PASS was expressed more strongly than the actual FINAL_STATUS.

9. Why a clean new-chat reset did not eliminate generator failure.

10. Whether trajectory-level metrics could detect a repeated-failure loop and automatically move the system into STOP/diagnostic mode.
