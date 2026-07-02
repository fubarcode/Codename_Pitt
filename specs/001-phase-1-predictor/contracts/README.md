# Contracts

This directory will contain machine-readable contracts for Phase 1 Predictor inputs, intermediate state, and outputs.

Planned contracts include:

- `ticker-input.schema.json`
- `market-price-snapshot.schema.json`
- `fundamental-disclosure.schema.json`
- `agent-context.schema.json`
- `search-result.schema.json`
- `prediction-output.schema.json`

## Structure

```text
contracts/
  schemas/   # JSON Schema or equivalent machine-readable contracts
  examples/  # Example valid payloads for contract validation
```

Core implementation should depend on these contracts rather than provider-specific payloads or physical storage paths.
