# 🩺 AI for Medical Diagnosis  
## Course 1 — Evaluation, Thresholds, and Clinical Decision-Making

---

# ============================
# WEEK 1 — DIAGNOSTIC METRICS
# ============================

## Clinical Context

In medical diagnosis, **not all prediction errors carry the same risk**.

- A **false negative** may delay treatment for a serious disease  
- A **false positive** may cause anxiety, unnecessary testing, or overtreatment  

Because of this, evaluating AI models in healthcare requires **more than accuracy**.  
This notebook explores diagnostic metrics and explains what they mean **from a clinical perspective**.

---

## Objective

- Compute standard diagnostic metrics
- Understand how metrics map to real-world clinical decisions
- Learn why different diseases require different evaluation priorities

---

## Key Assumptions

- Binary classification (disease vs. no disease)
- Reliable ground truth labels
- AI supports — not replaces — clinicians

---

## Confusion Matrix Refresher

| Outcome | Meaning |
|------|------|
| True Positive (TP) | Sick patient correctly identified |
| False Negative (FN) | Sick patient missed |
| False Positive (FP) | Healthy patient incorrectly flagged |
| True Negative (TN) | Healthy patient correctly cleared |

In medicine, **false negatives often carry the highest risk**.

---

## Accuracy

Accuracy measures overall correctness.

However, in medical datasets with class imbalance, accuracy can be **deeply misleading**.  
A model can appear accurate while failing to detect disease entirely.

➡️ Accuracy should never be used alone in medical diagnosis.

---

## Sensitivity (Recall)

**Question answered:**  
> If a patient has the disease, how likely is the model to detect it?

High sensitivity is critical for:
- Cancer screening
- Life-threatening conditions
- Early intervention scenarios

---

## Specificity

**Question answered:**  
> If a patient is healthy, how likely is the model to say so?

High specificity reduces:
- Unnecessary testing
- Patient anxiety
- Healthcare system overload

---

## Precision (Positive Predictive Value)

**Question answered:**  
> When the model predicts disease, how often is it correct?

Precision strongly influences clinician trust and workflow efficiency.

---

## Negative Predictive Value

**Question answered:**  
> When the model predicts no disease, how reliable is that reassurance?

Critical for safely ruling out disease.

---

## Metric Trade-offs

| Clinical Scenario | Priority Metric |
|------|------|
| Screening | Sensitivity |
| Confirmation | Specificity |
| Limited resources | Precision |
| Patient reassurance | NPV |

---

## Week 1 Takeaways

- Accuracy is insufficient
- Metrics represent **clinical risk**
- Metric choice reflects **medical priorities**

---

# ============================
# WEEK 2 — ROC CURVES & THRESHOLDS
# ============================

## Clinical Context

Most medical AI models output **probabilities**, not decisions.

Turning probabilities into diagnoses requires choosing a **decision threshold** — a choice that directly impacts patient outcomes.

---

## Objective

- Understand ROC curves and AUC
- Analyze threshold trade-offs
- Connect threshold choice to clinical decision-making

---

## ROC Curve Intuition

An ROC curve shows the trade-off between:
- Sensitivity (True Positive Rate)
- False Positive Rate (1 − Specificity)

The **top-left corner** represents strong clinical performance:
- High sensitivity
- Low false positives

---

## AUC (Area Under the Curve)

AUC measures how well a model separates sick from healthy patients **across all thresholds**.

Important:
- High AUC ≠ clinically deployable
- AUC does not encode real-world costs

---

## Threshold Selection as a Clinical Decision

Choosing a threshold determines:
- How many sick patients are missed
- How many healthy patients are falsely flagged

Lower threshold:
- ↑ Sensitivity
- ↑ False positives

Higher threshold:
- ↑ Specificity
- ↑ False negatives

---

## Clinician’s Perspective

A screening model may tolerate false positives to avoid missed disease.  
A confirmatory test must minimize false alarms.

➡️ Thresholds must align with **clinical intent**, not mathematical convenience.

---

## Week 2 Takeaways

- ROC curves visualize trade-offs, not decisions
- Threshold choice is a **medical judgment**
- Model evaluation must reflect deployment context

---

# ============================
# WEEK 3 — MODEL EVALUATION IN PRACTICE
# ============================

## Clinical Context

Deploying a medical AI model requires understanding **how it behaves in real clinical workflows**, not just how it performs in isolation.

---

## Objective

- Apply metrics to a trained model
- Interpret confusion matrices
- Translate model behavior into clinical consequences

---

## Confusion Matrix as a Clinical Tool

Each cell represents a patient outcome:
- Missed diagnoses
- Unnecessary interventions
- Correct reassurance
- Effective detection

Understanding these outcomes is essential before deployment.

---

## Interpreting Results Clinically

Model performance should be evaluated in terms of:
- Patient safety
- Follow-up burden
- Trustworthiness
- Resource impact

A “better” model numerically may be **worse clinically**.

---

## What This Model Would Mean in Practice

If deployed, this model would:
- Reduce missed diagnoses by X%
- Increase follow-up testing by Y%
- Shift workload for clinicians

These trade-offs must be explicitly acknowledged.

---

## Cross-Week Synthesis

Across all three weeks, we learn that:

- Medical AI success is **context-dependent**
- Metrics are proxies for patient outcomes
- Ethical responsibility is inseparable from evaluation

---

## Final Reflection

Medical AI is not about maximizing scores — it is about **minimizing harm**.

Effective models align technical performance with clinical reality, patient safety, and healthcare system constraints.

---

## Portfolio Note

This work is part of a learning portfolio focused on the **responsible application of machine learning in healthcare**, emphasizing interpretability, evaluation rigor, and ethical deployment.
