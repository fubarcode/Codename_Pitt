# Architecture Notes

Phase 1 should be modular but not prematurely deployed as distributed microservices.

The preferred shape is service-oriented in-process modules with explicit contracts:

- input ingestion
- manual disclosure ingestion
- market price telemetry
- search/research provider adapters
- deterministic orchestration
- prediction synthesis
- file-based persistence
- evaluation-ready output writing

These boundaries should allow later extraction into independent services or LangGraph nodes without rewriting the domain contracts.
