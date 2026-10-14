**English** | [Suomi](./README.fi.md)

# Mikko Tarkiainen

**AI Systems Engineer · Agent Runtime Controls, Evaluation & Reliability · Deterministic Decision Systems**

Based in Finland · Open to freelance work, remote roles and software partnerships

I design and build AI systems with explicit operating boundaries. Language models interpret, discuss and propose; software enforces permissions, business rules and state transitions.

Two decades as an automotive entrepreneur shaped my approach: own the problem, make decisions under uncertainty and remain accountable for the outcome.

My current work focuses on three separate questions:

- **Control:** What is an agent allowed to do?
- **Evaluation:** Do the implemented controls behave as specified under adversarial scenarios?
- **Evidence:** What can signed observations establish about execution, and what remains uncertain?

## Start here: control, evaluation and evidence

These three public reference implementations address different responsibilities. Their relationship and trust boundaries are described in [Control, Evaluation & Evidence Architecture](https://github.com/mikko-lab/agent-control-evals/blob/9a624cf0d9972dea65e37713729a455b2d365f51/docs/architecture/control-evaluation-evidence.md).

### ACS Guardrail Demo — Runtime Authority & Agent Security

Deterministic runtime controls for agent tool execution: signed and scoped capabilities, tool-bound human approval, tenant and ancestor-chain revocation, and an optional approval–permit lifecycle with single-use permits.

The runtime takes an immutable request snapshot so that the request executed is the request verified. Cooperative cancellation, commit fences and output gating constrain the managed execution path. Hash-chained audit records support integrity checks against a separately trusted head.

**Boundary:** cancellation requires tool cooperation, and effects outside the managed commit boundary are not prevented. Revocation state is local and in memory. This is a reference implementation, not a claim of full ACS conformance or production readiness.

[Repository](https://github.com/mikko-lab/acs-guardrail-demo)

### Agent Control Evals — Deterministic Evaluation of Agent Controls

Reproducible evaluation harnesses using explicit specifications, deterministic oracles, adversarial scenarios and mutation testing.

The work separates reported policy decisions from observed effects. Evaluations identify the tested system version, corpus, declared capability profile and coverage gaps. Runtime-control, revocation and automotive-agent evaluations retain their own assumptions and reporting boundaries.

**Boundary:** results apply to the evaluated versions, scenarios and observation mechanisms. Synthetic harness validation is distinguished from evaluation of an external system. Passing a declared profile does not establish full-contract conformance, universal safety or production readiness.

[Repository](https://github.com/mikko-lab/agent-control-evals)

### Execution Evidence Demo — Verifiable Execution Receipts & History

A TypeScript reference library for Ed25519-signed execution receipts and linked lifecycle observations. Receipts bind an actor and action to hashes of supplied before-state, after-state and result observations.

Lifecycle evidence links operations, attempts and receipts while preserving uncertainty and conflicting outcomes. Signature verification, history assessment and authorization of the next action remain separate responsibilities.

**Boundary:** signatures authenticate evidence under configured trust rules; they do not independently prove external events. The library does not execute operations, authorize retries or guarantee complete history, immutable storage or exactly-once execution.

[Repository](https://github.com/mikko-lab/execution-evidence-demo)

## Applied systems

### Kopilotti Sales — Dealer-Controlled Digital Sales

AI-assisted used-car sales within dealer-defined commercial boundaries. The language model handles conversation; deterministic server-side rules control pricing decisions and sales-flow transitions.

A vehicle-specific Magic Link provides the customer entry point, while the dealer configures commercial rules in Admin. A separate Evaluation & Safety harness tests observable API behaviour against a local Sales system in an isolated environment.

**Boundary:** the system remains in development. External integrations and pilot readiness are assessed separately. Kopilotti does not receive, hold or transfer customer payments.

[Project](https://github.com/mikko-lab/kopilotti-sales-demo) · [Live demo](https://app.kopilotti.online/en/)

### DDN Reference — Verifiable Deterministic Decisions

Versioned business rules execute as WebAssembly in three isolated validator processes on one host under one operator. A decision is accepted when at least two configured validators produce matching signed attestations.

Decision receipts support verification of signatures, request bindings, hashes and Merkle proofs. The implementation also demonstrates EVM anchoring on a local Anvil chain.

**Boundary:** this is not an independent validator network or an active production integration. Receipt verification does not normally rerun the policy or establish whether the business rule itself is correct or fair.

[Repository](https://github.com/mikko-lab/ddn-reference)

### Ruuhkavahti — Kafka Guardrails Under Load

A deterministic PASS / ESCALATE / BLOCK pipeline, locally tested with a simulated 8,000-message-per-second traffic spike.

The implementation combines consumer-lag observability, duplicate handling, an independent consumer service, signed service-to-service authentication and distributed tracing. The dashboard includes accessible semantic views and reduced-motion support.

**Boundary:** the published measurements describe specific local experiments, not a production throughput or availability guarantee.

[Repository](https://github.com/mikko-lab/ruuhkavahti)

## Additional work

- [A11Y Lead Engine](https://github.com/mikko-lab/a11y-lead-engine) — automated accessibility checks, company-data enrichment and structured outreach workflows.
- [Prompt Injection Gate](https://github.com/mikko-lab/prompt-injection-gate) — a proof of concept separating structural tool-output quarantine from best-effort pattern detection.
- [refuse-dont-guess](https://github.com/mikko-lab/refuse-dont-guess) — deterministic VAT classification and escalation, with prompt-injection regression tests.
- [claude-code-invoice-guard](https://github.com/mikko-lab/claude-code-invoice-guard) — the same guardrail principle implemented with Claude Code runtime primitives.
- [Kopilotti WebMCP](https://github.com/mikko-lab/kopilotti-webmcp) — a browser-agent demonstration with constrained tools, visible state and a human-approval boundary.
- [osCommerce Checkout Refactor](https://github.com/mikko-lab/sap-checkout-refactor/tree/poc/checkout-modernization) — AI-assisted legacy refactoring with explicit business-rule analysis and behaviour-preserving tests.
- [Provenanssi](https://github.com/mikko-lab/provenanssi) — open research separating measured image information from model-generated reconstruction.
- [Karikko](https://github.com/mikko-lab/karikko) — geospatial hazard reporting for Finnish waters, with a separate [backend](https://github.com/mikko-lab/karikko-api).

## Open-source contributions

- [567-labs/instructor](https://github.com/567-labs/instructor/pull/2434) — traced caller-owned message mutation across providers; proposed fixes were consolidated into a merged maintainer PR with original contributor authorship preserved.
- [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph/issues/8314) — root-cause analysis of state-channel reference transparency.
- [Aiven-Open/karapace](https://github.com/Aiven-Open/karapace/issues/1329) — reported and traced a RecursionError involving self-referential JSON Schema compatibility checking.

## Technologies

TypeScript · JavaScript · Node.js · Python · Rust · PostgreSQL · Redis · Kafka · Docker · WebAssembly · Solidity · Playwright · Jest · Vitest · GitHub Actions

## Engineering principle

**Flag, don’t hide.**

A system should state what it decided, what it observed, what its evidence can verify and where its limits are. Permission to act, evaluation results and evidence of execution should never be treated as interchangeable.

## Contact

Open to software partnerships, architecture consulting, selected freelance projects and remote roles.

[Get in touch →](mailto:hello@kopilotti.online?subject=Software%20partnership%20inquiry)
