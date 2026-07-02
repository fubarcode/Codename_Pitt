# Research Notes: Phase 1 Predictor

## Open Decisions

| Topic | Decision Needed | Notes |
| :--- | :--- | :--- |
| Runtime language | Confirm implementation stack | Python is a likely fit but not yet finalized. |
| Schema library | Confirm validation approach | Pydantic or JSON Schema are likely candidates. |
| Broker API | Choose initial price provider | Zerodha Kite Connect and ICICI Breeze are candidates. |
| Exa usage | Confirm search tier mapping | Must align to execution modes and budget controls. |
| CLI or service | Confirm first interface | A CLI/manual runner may be simplest for MVP validation. |

## Known Constraints

- Indian equity analysis requires careful source handling and disclosure traceability.
- Manual filing placement is preferred in Phase 1 to avoid fragile scraping.
- Recursive research must be capped at three hops.
- Outputs are research aids and not financial advice.
