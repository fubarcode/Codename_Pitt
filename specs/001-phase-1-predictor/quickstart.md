# Quickstart: Phase 1 Predictor

## Current Status
This feature is in specification stage. Runtime commands will be added after the implementation tasks are reviewed and accepted.

## Intended MVP Flow

1. Place manually collected corporate disclosure files under the ticker-specific fundamental data folder.
2. Provide ticker, horizon, risk profile, and baseline thesis.
3. Fetch or load current market price telemetry.
4. Route the request to the correct execution mode.
5. Run bounded research and synthesis.
6. Write a schema-validated prediction output.

## Intended Local Storage

```text
database/
  raw_news/
  fundamental_data/
  market_prices/
  predictions/
cache/
state.json
```

## Safety Notice
Prediction outputs are research aids only and must not be treated as financial advice or automated trading instructions.
