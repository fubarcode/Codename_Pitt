# Feature Specification: Phase 1 Predictor

## Status
Draft

## Feature Summary
Build Phase 1 of Codename Pitt: a deterministic research analyst workflow for Indian listed equities. The system will combine user-provided equity context, manually positioned corporate disclosures, market price telemetry, and bounded external research to produce structured multi-horizon prediction outputs.

## User Goals

- Evaluate an Indian listed equity using a ticker symbol such as `RELIANCE` or `TCS`.
- Provide a risk profile, investment horizon, and baseline investment thesis.
- Supply quarterly corporate disclosures manually instead of relying on fragile scraping.
- Receive a structured prediction with price target boundaries, supporting evidence, and a clear investment thesis summary.
- Ensure recursive research cannot run without deterministic limits.

## Functional Requirements

1. The system must accept an exchange ticker symbol as the primary asset identifier.
2. The system must accept contextual user inputs, including risk constraints, investment horizon, and baseline thesis.
3. The system must read manually supplied corporate disclosure content for the target ticker.
4. The system must incorporate market price telemetry, including last traded price and opening benchmark data.
5. The system must select an execution mode from a deterministic routing matrix.
6. The system must support new-stock evaluation, routine polling, anomaly analysis, and recursive search scenarios.
7. The system must enforce a maximum of three recursive search hops per execution block.
8. The system must write prediction outputs in a schema-validated, machine-readable format.
9. The system must preserve raw or normalized inputs sufficiently for audit and debugging.
10. The system must make clear that predictions are research aids and not financial advice.

## Non-Functional Requirements

- Prefer deterministic control flow over unconstrained multi-agent behavior.
- Prefer human-inspectable file storage for Phase 1.
- Keep interfaces compatible with future evaluation and LangGraph migration.
- Make external API usage bounded and observable.
- Keep ingestion boundaries explicit to reduce scraping fragility.

## Out of Scope

- Automated order placement.
- Portfolio management.
- Live intraday trading recommendations.
- Database-backed persistence.
- Unbounded autonomous agent swarms.
- Exchange website scraping as a primary ingestion mechanism.

## Success Criteria

- A user can request a ticker evaluation using declared inputs.
- The system can determine the correct execution mode using explicit state and price context.
- The system can produce a valid prediction artifact for 3, 6, or 12 month horizons.
- Recursive search stops at or before the configured hop limit.
- Generated artifacts can be inspected locally as files.
