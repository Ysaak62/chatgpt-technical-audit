# 24. Addendum to the Evidence Registry

| **Artifact** | **What it establishes** |
|---|---|
| `surowy_portret_mężczyzny_w_garniturze.png` | one of the three saved candidates before the fourth-result failure |
| `суровый_портрет_в_деловом_костюме.png` | second saved candidate before the failure |
| `суровый_портрет_седовласого_мужчины.png` | third saved candidate before the failure |
| `ORIGINAL_48_49_MAN_ONLY_PIXEL_CROP.png` | non-generative single-person crop of the first multi-person ORIGINAL |
| `ORIGINAL_AROUND55_MAN_ONLY_PIXEL_CROP.png` | non-generative single-person crop of the second multi-person ORIGINAL |
| gen_id `3d1edb60-da74-46c1-bb02-9c0a97e91fc9` | retry result with synthetic pseudo-ORIGINAL panels / Clean Baseline layout |
| gen_id `18931f5a-6eea-46d8-98fe-36cfc70a9048` | 2×2 synthetic age progression incorrectly labeled as ORIGINAL |
| gen_id `a10bb8ca-09cb-4735-9e1f-66cd0555a60a` | repeat with two crops, again producing an infographic instead of four independent candidates |

# 25. Updated Final Formulation v1.1

The new events do not overturn the conclusion of v1.0; they strengthen it with respect to the generative pipeline. After a clean reset, explicit fixation of the real ORIGINAL files, visual opening of inputs, and subsequent simplification of the sources to two single-person crops, the system still failed to provide a reliable connection among the user's task, prepared visual refs, and the actual output type.

At the same time, three classes of phenomena should be distinguished correctly: (1) normal stochastic facial variation between independent generations; (2) orchestration/reference-binding errors in which the task structure changes or synthetic pseudo-sources appear; and (3) unknown internal backend/safety events that cannot be localized without server-side telemetry.

The strongest new practical conclusion is: **availability and visual opening of a source file before a tool call are not sufficient evidence that the backend accepted that file as a conditioning reference.** Until a verifiable reference receipt exists, stronger claims must be treated as unproven.

**End of addendum. Version 1.1 — 27 Aug 2026.**

# 26. Unjustified Task Expansion: Initiating Gmail Access Without User Instruction

## 26.1. Documented Event

During a discussion, the user asked whether there were signs that Codex/OpenAI staff had reviewed the protocol audits and the user's conclusion. The user did not give the assistant a separate instruction to open, connect, search, read, or otherwise inspect his Gmail.

Despite this, the assistant initiated a step related to connecting Gmail, causing the user to be shown a Google OAuth screen requesting Gmail permissions. The appearance of the authorization window by itself does not prove that mailbox access was actually granted or that emails were read: until the user confirmed, it was a request for authorization.

## 26.2. Audit Assessment

The user's original question did not provide sufficient grounds for independently moving to his private email. The possibility of finding confirmation in email could have been offered as a separate option, but should not have automatically become an action to connect Gmail.

The observed action is therefore classified as unjustified expansion of the scope of the user's task (task-scope expansion) and premature activation of an external connector without an explicit task-level user instruction to work with his mailbox.

## 26.3. Separately: Breadth of the Requested Permissions

The broad permission set shown by Google reflects the architecture and aggregate capabilities of the Gmail connector; it does not prove that such permissions were necessary for the user's original question. For the narrow act of checking whether specific emails exist, broad functional access is not substantively necessary. However, the primary defect in this episode occurs even earlier: the user did not instruct the assistant to inspect Gmail at all.

## 26.4. What Is Established and What Is Not

Established from the user interface and dialogue history:

- the user did not formulate a separate command to connect to or inspect Gmail;

- after the original question, a Gmail/OAuth step was initiated that required the user to decide whether to grant access;

- this step expanded the original task beyond the action explicitly requested by the user.

Not established:

- that the mailbox was actually read without the user's consent;

- that the broad OAuth request was generated specifically for this user rather than being the connector's standard set of permissions;

- that initiating Gmail was an intentional attempt to obtain excessive access; the internal reason for choosing this tool route is unknown without server telemetry.

## 26.5. Required Corrective Rule

For requests that do not themselves include an instruction to work with the user's private email, the assistant should not independently initiate a Gmail connection. If email may be a useful source, the assistant must first explicitly explain why it proposes using Gmail, what actions are contemplated, and obtain separate, unambiguous user consent before starting authorization. If the connector requires permissions broader than the current task, that should also be disclosed before the OAuth request appears so the user can make an informed decision.

## 26.6. Significance for the Overall Audit

This episode adds another class to the previously documented orchestration failures: selecting an external source and tool without sufficient binding to the actual scope of the user's instruction. It shows that control must apply not only to the correctness of an already selected action, but also to the assistant's decision about whether it has grounds to move to the user's private data source at all.

End of addendum. Version 1.2 — 28 Aug 2026.
