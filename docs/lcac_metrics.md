# LCAC Metrics and Evaluation Framework

This document defines the quantitative measures used to evaluate compliance with LCAC (Least-Context Access Control) principles.  
Each metric is operationalized within the LCAC runtime and aligns with its core pillars - Cognitive Least Privilege, Reasoning Isolation, and Cognitive Integrity.

---

## 1. Cognitive Trust Score (CTS)

**Purpose:**  
Quantifies the overall trustworthiness of an AI reasoning session.

**Formula:**
CTS = (ReasoningIntegrity × ContextAlignment × PolicyAdherence) − DriftPenalty

**Components:**
- **ReasoningIntegrity:** Verifiable trace of reasoning chains and justifications.  
- **ContextAlignment:** Degree to which reasoning remains within authorized contextual bounds.  
- **PolicyAdherence:** Compliance with LCAC runtime policies and governance rules.  
- **DriftPenalty:** Weighted deduction applied when inference deviates from the authorized trust boundary.

**Operational Target:** ≥ 0.85 (safe and stable cognitive state)

---

## 2. Reasoning Drift Index (RDI)

**Purpose:**  
Measures cross-context reasoning contamination or unauthorized contextual blending.

**Formula:** RDI = CrossContextInferences / TotalInferences

**Interpretation:**
| Value | Meaning |
|--------|----------|
| 0.00 | Fully isolated reasoning (ideal) |
| 0.25 | Minor contextual overlap |
| 0.50 | Moderate contamination - review required |
| ≥ 0.75 | Critical — automatic LCAC termination trigger |

---

## 3. Inference Integrity Ratio (IIR)

**Purpose:**  
Evaluates whether reasoning outputs remain traceable, auditable, and verifiable throughout execution.

**Formula:**
