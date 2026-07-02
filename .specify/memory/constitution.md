# Codename Pitt Constitution

## Purpose
Codename Pitt is an agentic investing research system for an individual investor. It will evolve through five phases: Predictor, Evaluator, Macros, Selection, and Integration. The constitution defines the non-negotiable engineering and product principles that govern every phase.

## Core Principles

### I. Spec-First Delivery
All meaningful product work must begin with a reviewed specification before implementation. Feature behavior, constraints, success criteria, data contracts, and acceptance checks must be documented under `specs/` before runtime code is added.

### II. Service-Oriented Modularity Before Distributed Services
The system must avoid tightly coupled monolithic code. Components must be separated by explicit contracts across ingestion, search, orchestration, persistence, prediction, evaluation, macro analysis, and selection. Phase 1 may run in-process for MVP simplicity, but boundaries must remain clear enough that components can later become independent services or LangGraph nodes.

### III. Contract-First Phase Boundaries
Core phase logic must accept structured dictionaries or schema-backed objects rather than raw file paths, provider SDK objects, or unnormalized payloads. Inputs, intermediate state, and outputs must remain JSON-compatible wherever practical so Phase 1 outputs can feed Phase 2 evaluation and later graph orchestration without major rewrites.

### IV. Deterministic and Bounded Agent Behavior
Agentic workflows must use deterministic routing, bounded loops, auditable state, and schema-validated outputs. Recursive search and reasoning loops must define maximum hop counts, stopping conditions, and budget controls before execution.

### V. Auditability and Reproducibility
Every prediction and evaluation artifact must preserve enough metadata for later review. Records should include ticker, timestamp, market price snapshot, input disclosures, search evidence, execution mode, prompt or model version where applicable, and generated output.

### VI. Human-Inspectable Persistence First
Early phases must prefer local, human-inspectable files and JSON artifacts over database infrastructure. Storage layouts must remain stable and migration-friendly, but core logic must not be tightly coupled to physical file paths.

### VII. Provider Independence
External services such as Exa, broker APIs, LLM providers, and future data vendors must be accessed through adapters. Provider-specific credentials, SDK objects, and response payloads must not leak into core reasoning, prediction, or evaluation logic.

### VIII. Financial Safety and Non-Advisory Outputs
The system produces research aids, not financial advice or automated trading instructions. Outputs must include uncertainty, downside risks, supporting evidence, and an explicit disclaimer. Automated order placement is out of scope unless introduced by a future reviewed specification.

### IX. Evaluation-Ready Predictions
Phase 1 prediction outputs must be structured so Phase 2 can compare forecasts against realized prices at maturity milestones. Each prediction should include generated timestamp, horizon, current price, target range, confidence, thesis, risk factors, evidence references, and evaluation due date.

### X. Phased Roadmap Discipline
Each phase must stay focused on its declared objective while preserving interfaces needed by later phases. Phase 1 builds the Predictor only; it must not prematurely implement the Evaluator, Macros Engine, Selection Engine, or production orchestration network.

### XI. Language Fit Over Theoretical Performance
The default implementation language should optimize for correctness, inspectability, AI tooling support, schema validation, API integration, and iteration speed. Python is the default for Phase 1 research orchestration. C++ or other lower-level languages may be introduced only for isolated, benchmark-proven performance bottlenecks through a future specification.

## Governance

- Constitution changes require a specification update or dedicated governance change.
- Implementation PRs must reference the relevant spec directory.
- If implementation pressure conflicts with this constitution, the constitution wins until amended.
- New providers, storage engines, agent loops, or trade-execution capabilities require explicit specification and review before implementation.
