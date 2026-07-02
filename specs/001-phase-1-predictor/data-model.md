# Data Model: Phase 1 Predictor

## Candidate Entities

### TickerInput
- `symbol`
- `exchange`
- `company_name`

### UserRiskProfile
- `max_risk_level`
- `investment_horizon_months`
- `baseline_thesis`
- `notes`

### MarketPriceSnapshot
- `ticker`
- `last_traded_price`
- `open_price`
- `timestamp`
- `provider`

### FundamentalDisclosure
- `ticker`
- `reporting_period`
- `source_path`
- `disclosure_type`
- `parsed_text`
- `ingested_at`

### SearchResult
- `query`
- `title`
- `url`
- `published_at`
- `summary`
- `source_type`
- `estimated_cost`

### AgentContext
- `ticker_input`
- `risk_profile`
- `market_snapshot`
- `disclosures`
- `execution_mode`
- `search_results`
- `circuit_breaker_state`

### CircuitBreakerState
- `max_search_hops`
- `current_search_hops`
- `estimated_cost`
- `budget_limit`
- `can_continue`

### PredictionOutput
- `ticker`
- `generated_at`
- `horizon_months`
- `current_price`
- `lower_target_boundary`
- `upper_target_boundary`
- `thesis_summary`
- `risk_summary`
- `supporting_evidence`
- `execution_mode`
- `confidence_level`
- `disclaimer`
