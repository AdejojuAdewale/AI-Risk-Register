# AI-Risk-Register
AI risk assessment for a hospital network, mapped to OWASP LLM Top 10 and NIST AI RMF
# AI Risk Register For Ashwood General Health Network

An AI risk assessment for a (illustrative) multi-site Nigerian hospital network running three AI systems where errors can directly affect patient safety. Each risk is tied to a real-world incident and mapped to the **OWASP Top 10 for LLM Applications** and the **NIST AI Risk Management Framework**.

> Ashwood General Health Network is an illustrative case study. The risks, frameworks and cited incidents are real.

**Read the story version:** *[Three AI Systems, One Hospital, One Very Long Day](https://medium.com/@jojuwale/three-ai-systems-one-hospital-one-very-long-day-010dba040d57)* (Medium)

---

## The company

- 4 hospitals and 11 outpatient clinics across Lagos and Ogun State
- 2,200+ employees, roughly 500,000 patients a year

## The AI systems assessed

| System | What it does | Users |
|---|---|---|
| **Scriba** | Ambient AI scribe: listens to visits and drafts clinical notes, diagnoses and medication orders into the EHR | Physicians, clinical staff |
| **TriageAI** | Patient-facing symptom checker advising ER, urgent care or self-care | Patients |
| **CareAuth** | Decision support recommending approve/deny/limit on inpatient stays and treatment authorizations | Utilization review / case management staff |

## Risk summary

| ID | Risk | System | Framework mapping | Priority |
|---|---|---|---|---|
| R-01 | PHI leakage via AI documentation tool | Scriba | OWASP LLM06 | Critical |
| R-02 | Hallucinated content in clinical notes | Scriba | NIST AI RMF (Measure) | Critical |
| R-03 | Unsafe or incorrect triage recommendations | TriageAI | NIST AI RMF (Measure); OWASP LLM09 | Critical |
| R-04 | Harmful advice via adversarial manipulation | TriageAI | OWASP LLM01 | Critical |
| R-05 | Biased or harmful coverage denials | CareAuth | NIST AI RMF (Govern, Map) | Critical |
| R-06 | Model extraction of authorization logic | CareAuth | OWASP LLM10 | Medium |
| R-07 | Drift or poisoning from adversarial symptom reporting | TriageAI | OWASP LLM03; NIST AI RMF (Manage) | Medium |
| R-08 | Insecure handling of AI output in the EHR | Scriba | OWASP LLM02 | High |

**Core finding:** nearly every mitigation reduces to one principle: place a human confirmation point wherever AI output flows into a patient record or a decision about a patient.

## Full register

See [`risk-register.md`](./risk-register.md) for the complete entries: description, related incident, likelihood, impact, priority and recommended mitigation for each risk.

## Repo structure

```
ai-risk-register/
├── README.md
└── risk-register.md
```

## Frameworks

- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
