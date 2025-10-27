# LCAC Metrics and Evaluation Framework

This document defines the quantitative measures used to evaluate compliance with LCAC (Least-Context Access Control) principles.  
Each metric is operationalized within the LCAC runtime and aligns with its core pillars - Cognitive Least Privilege, Reasoning Isolation, and Cognitive Integrity.

---

## 1. Cognitive Trust Score (CTS)

**Purpose:**  
Quantifies the overall trustworthiness of an AI reasoning session.

**Formula:**
CTS = (ReasoningIntegrity × ContextAlignment × PolicyAdherence) - DriftPenalty

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

**Formula:** IIR = VerifiedInferences / TotalInferences

**Thresholds:**  
| Range | Classification |
|--------|----------------|
| ≥ 0.9 | High integrity |
| 0.7–0.9 | Acceptable |
| < 0.5 | Trust violation — invoke audit hooks |

---

## 4. Context Boundary Compliance (CBC)

**Purpose:**  
Ensures reasoning does not cross or blend isolated trust zones.

**Policy Enforcement:**  
CBC = True only if all cognitive sessions remain bounded by authorized context IDs.  
Violations trigger:

on_violation: [“halt_reasoning”, “trigger_audit”]

---

## 5. Ethical Alignment Score (EAS)

**Purpose:**  
Quantifies system reasoning alignment with defined ethical and regulatory constraints.

**Formula:** EAS = EthicalCompliantInferences / TotalInferences

**Target Threshold:** ≥ 0.8 (certified safe operational range)  

**Evaluation Criteria:**  
- Compliance with enterprise and regulatory ethics policies  
- Adherence to LCAC runtime governance controls  
- Integrity of reinforcement feedback alignment  

---

## 6. LCAC Compliance Index (LCI)

**Purpose:**  
Aggregated compliance indicator summarizing LCAC performance across reasoning layers.

**Formula:** LCI = (CTS + IIR + EAS) / (1 + RDI)

**Classification:**
| LCI | Interpretation |
|------|----------------|
| ≥ 2.5 | Fully compliant cognitive system |
| 1.5–2.5 | Partially compliant — requires optimization |
| < 1.5 | Non-compliant — initiate governance response |

---

## Summary Table

| Metric | Description | Ideal Range | Response |
|--------|--------------|--------------|-----------|
| CTS | Cognitive Trust Score | ≥ 0.85 | Adjust trust scaling |
| RDI | Reasoning Drift Index | ≤ 0.25 | Redact reasoning scope |
| IIR | Inference Integrity Ratio | ≥ 0.9 | Audit verification |
| CBC | Context Boundary Compliance | 100% | Enforce isolation |
| EAS | Ethical Alignment Score | ≥ 0.8 | Trigger policy review |
| LCI | LCAC Compliance Index | ≥ 2.5 | Certified trusted state |

---

## Calibration Reference

| Metric | Source of Calibration | Description |
|--------|------------------------|--------------|
| CTS ≥ 0.85 | Derived from SOC2 and ML reliability thresholds | Cognitive trust stability |
| RDI ≤ 0.25 | Mirrors anomaly-detection tolerance bands | Acceptable reasoning drift |
| IIR ≥ 0.9 | Based on enterprise data-integrity SLAs | Verified inference confidence |
| EAS ≥ 0.8 | Aligned with IEEE and UNESCO AI ethics frameworks | Ethical adherence |
| LCI ≥ 2.5 | Aggregated LCAC compliance benchmark | Fully governed cognition |

---

## Integration and Validation

All metrics are measured and reported through the LCAC telemetry layer within the **Vanta Autonomous Intelligence System**.  
Validation occurs continuously across reasoning events, generating trust-state logs for audit and adaptive governance.  
The resulting telemetry feeds back into LCAC’s cognitive control plane to dynamically adjust context limits, ethical constraints, and reasoning boundaries in real time.

---

**Author:** Quinton Stackfield  
**Organization:** Atom Labs  
**License:** MIT
