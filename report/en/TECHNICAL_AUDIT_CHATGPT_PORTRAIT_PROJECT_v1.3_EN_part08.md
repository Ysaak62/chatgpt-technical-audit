# 30. Comparison with Independent Research Literature

The following sources are provided **as external context**, not as proof of the internal mechanism of the specific incidents in this project.

1. Cheng et al. (2026), *Model-Adaptive Tool Necessity Reveals the Knowing-Doing Gap in LLM Tool Use*, separate cognition from execution and report that a substantial share of mismatches concentrates specifically at the cognition → action transition. This is conceptually close to the pattern observed here: "the rule is stated correctly → the next action contradicts it."  
   https://arxiv.org/abs/2605.14038

2. Yao et al., tau-bench, introduce the **pass^k** metric to evaluate not one-time capability but repeated agent reliability across several independent trials. They show a sharp drop in reliability when consecutive successful repetitions are required.  
   https://arxiv.org/abs/2406.12045

3. OpenAI's GPT-5.6 Preview System Card reports that in certain agentic coding evaluations GPT-5.6 showed a greater tendency than GPT-5.5 to go beyond user intent, including taking actions the user had not requested; OpenAI also states that absolute rates in these evals remained low. This is an adjacent, but not identical, behavior class.  
   https://deploymentsafety.openai.com/gpt-5-6-preview

4. METR's independent predeployment evaluation of GPT-5.6 Sol reported an unusually high rate, for their ReAct harness, of prohibited evaluation strategies ("cheating" under METR's definition). This result concerns a different task and does not prove the cause of portrait/reference failures, but it supports the relevance of procedural-compliance questions for this model.  
   https://evals.alignment.org/blog/2026-06-26-gpt-5-6-sol/

The broader academic context supports distinguishing among **capability, instruction comprehension, procedural compliance, and repeated-run reliability**.

# 31. Regulatory Context

Regulatory documents do not contain a separate category named "state-to-action binding failure," but they already require providers of general-purpose AI to document capabilities/limitations and, for models with systemic risk, to perform model evaluation, assess and mitigate systemic risks, track/report incidents, and maintain cybersecurity safeguards.

In the EU, these duties are described in the AI Act and European Commission guidance for providers of general-purpose AI models:  
https://digital-strategy.ec.europa.eu/en/faqs/guidelines-obligations-general-purpose-ai-providers

The NIST Generative AI Profile recommends applying and documenting robust testing, evaluation, validation, and verification (TEVV) throughout the generative-AI lifecycle:  
https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence

For this audit, this supports not a legal conclusion that a law was violated, but a practical question for external quality/safety review:

> Was this class of repeated instruction/reference/action failures known to the provider, how was it measured, what user warnings and safeguards existed, and what corrective measures are applied after reproducible signals?

# 32. Updated Final Formulation v1.3

The events of 30 Aug 2026 strengthen the previous conclusion about unreliability in the binding between confirmed task state and subsequent tool action. The new series showed not permanent incapability, but alternation between compliant and sharply non-compliant results, including repetition of the same incorrect output family after direct corrective feedback.

The strictest formulation supported by the available evidence is:

**GPT-5.6 Sol / ChatGPT, in the workflow examined here, demonstrated a real capability to produce the required class of portrait result, but did not provide reliable and reproducible application of that capability across repeated runs. Textual understanding of a rule and a positive assistant self-report did not guarantee that the next action would comply with that rule. The observed defect class is consistent with an instruction-to-action / state-to-action reliability failure, but the exact internal mechanism cannot be established without server-side telemetry.**

At the time v1.3 was fixed, the planned 10-run series was **incomplete (6/10)**. Any quantitative estimate of failure frequency before completion of the series must therefore be treated as preliminary.

**End of addendum. Version 1.3 — 30 Aug 2026.**
