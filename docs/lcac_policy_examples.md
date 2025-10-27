# LCAC Policy Examples

## Example 1 - Cognitive Boundary for Regulated AI
```yaml
lcac_policy:
  id: legal_reasoning_001
  context: "Contract Review"
  authorized_domains: ["legal_db", "precedent_summary"]
  memory_scope: "transient"
  reasoning_limits:
    trust_threshold: 0.95
    max_context_depth: 4
  compliance_hooks:
    - GDPR
    - SOC2
    - InternalPolicy.LAW-ETH-01
  actions:
    on_violation: ["halt_reasoning", "trigger_audit"]

```

Example 2 - Financial Reasoning Containment Policy
lcac_policy:
```yaml
  id: trading_reasoning_084
  context: "Equity Market Analysis"
  authorized_sources:
    - "market_feed_alpha"
    - "risk_model_v5"
  isolation_zones:
    - "short_term_forecast"
    - "portfolio_risk"
  cognitive_controls:
    prevent_cross_zone_reasoning: true
    require_context_proof: true
  actions:
    on_low_trust: "limit_scope"
    on_context_drift: "invalidate_output"lcac_policy:
  id: trading_reasoning_084
  context: "Equity Market Analysis"
  authorized_sources:
    - "market_feed_alpha"
    - "risk_model_v5"
  isolation_zones:
    - "short_term_forecast"
    - "portfolio_risk"
  cognitive_controls:
    prevent_cross_zone_reasoning: true
    require_context_proof: true
  actions:
    on_low_trust: "limit_scope"
    on_context_drift: "invalidate_output"
    ```
```

Example 3 - Cognitive Red Team Configuration
```yaml
    lcac_policy:
    lcac_policy:
  id: cognitive_redteam_sim
  context: "Security Testing"
  test_modes: ["prompt_injection", "reasoning_poison", "context_steal"]
  validation_metrics:
    - "reasoning_integrity"
    - "context_boundary_score"
  thresholds:
    alert: 0.85
    fail: 0.75
  actions:
    on_fail: ["log_event", "halt_session", "notify_security_team"]
  id: cognitive_redteam_sim
  context: "Security Testing"
  test_modes: ["prompt_injection", "reasoning_poison", "context_steal"]
  validation_metrics:
    - "reasoning_integrity"
    - "context_boundary_score"
  thresholds:
    alert: 0.85
    fail: 0.75
  actions:
    on_fail: ["log_event", "halt_session", "notify_security_team"]
    ```
    
