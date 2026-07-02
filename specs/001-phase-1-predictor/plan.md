# Implementation Plan: Phase 1 Predictor

## Status
Draft

## Technical Direction
Phase 1 will implement a single-agent Stateful ReAct-style reasoning loop with deterministic routing and bounded tool usage. Runtime code should not be added until this plan and the companion task list are reviewed. The implementation should avoid tightly coupled monolithic code while also avoiding premature distributed microservices; modules should run in-process behind service-oriented contracts until a later specification justifies separate deployment.

## Architecture Areas

### Data Ingestion
- Ticker and user context input.
- Manual corporate disclosure ingestion.
- Broker-backed market price telemetry abstraction.

### Orchestration
- Unified agent context.
- Deterministic execution-mode router.
- Stateful ReAct loop.
- Circuit breaker for recursive search and budget controls.

### Search
- Exa-backed research abstraction.
- Search mode selection based on execution mode.
- Normalized search results with source metadata.

### Persistence
- File-based repository pattern.
- Local JSON artifacts for raw news, market prices, prediction outputs, and state.
- Cache directory for redundant request avoidance.

### Prediction
- Schema-validated output writer.
- Multi-horizon target boundaries.
- Investment thesis and risk summary.

## Proposed Runtime Structure

```text
src/
  predictor/
    config.py
    context.py
    schemas.py
    ingestion/
    orchestration/
    search/
    persistence/
    prediction/
database/
  raw_news/
  fundamental_data/
  market_prices/
  predictions/
cache/
state.json
```

## Constraints

- Do not hard-code API credentials.
- Do not use unbounded recursive search.
- Do not persist invalid prediction outputs.
- Do not introduce database infrastructure during Phase 1 unless the spec changes.
- Do not pass provider-specific SDK objects or raw file paths into core prediction logic.
- Do not implement distributed microservices in Phase 1 without a reviewed specification change.
- Use Python as the default Phase 1 language unless a future benchmark-backed spec introduces a lower-level component.
