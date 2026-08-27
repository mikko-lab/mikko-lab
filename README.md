**English** | [Suomi](./README.fi.md)

# Mikko Tarkiainen

**AI Systems Engineer** · Deterministic decision systems · Production reliability

Based in Finland · Open to freelance work, remote roles, and software partnerships

Language models interpret and communicate, while deterministic software controls decisions, permissions, and escalation. Systems and reference implementations are built to be testable and auditable, with their operating boundaries clearly documented.

## Start Here

- **[DDN Reference](https://github.com/mikko-lab/ddn-reference)** — a verifiable deterministic decision network with quorum validation and signed receipts
- **[Kopilotti Sales](https://app.kopilotti.online/en/)** — deterministic used-car price negotiation, live demo
- **[Ruuhkavahti](https://github.com/mikko-lab/ruuhkavahti)** — a Kafka-scale guardrail layer, load-tested at 8,000 messages per second
- **[Contact](#contact)** — open to freelance work, remote roles, and software partnerships

## Current Focus

- **Agentic systems** — structured orchestration, tool use, and schema-enforced outputs
- **Deterministic decision systems** — explicit PASS, ESCALATE, BLOCK, ACCEPT, COUNTER, and REJECT outcomes decided outside the language model
- **Production reliability and AI systems security** — verifiable execution, signed receipts, prompt-injection protection, and SSRF protection
- **Accessibility by architecture** — WCAG 2.2 AA, semantic interfaces, and screen-reader testing

## Selected Work

### DDN Reference — Verifiable Deterministic Decision Network

An open-source reference implementation for independently verifiable automated decisions. Versioned business rules execute inside three isolated validator processes, each running the same WebAssembly policy package; a decision is accepted only with a 2-of-3 quorum. Accepted decisions receive cryptographically signed receipts that can be independently checked, batched into a Merkle tree, and anchored to an EVM-compatible smart contract.

This is a reference implementation, not a claim of an active public production deployment.

`Rust · WebAssembly · TypeScript · Solidity · Ed25519 · Merkle trees`

→ [Repository](https://github.com/mikko-lab/ddn-reference)

### Kopilotti Sales — Deterministic Used-Car Price Negotiation

A customer-facing digital sales channel for used-vehicle price negotiation. The language model handles the conversation, but it never determines the price — dealer-defined business rules control acceptance, counteroffers, rejection, and escalation, while the backend separately enforces vehicle reservation, tenant and customer ownership, contract progression, and payment-state permissions.

After an accepted price, the reference implementation can demonstrate a concept contract and payment-status tracking. Customers cannot confirm payments, and Kopilotti does not receive, hold, or transfer funds. The public demo contains no payable bank details, and the full invoice-to-PAID flow is not active in public production traffic; the DDN integration boundary exists but is not active there.

`Node.js · Express · PostgreSQL · JavaScript · Claude API · Playwright`

→ [Repository](https://github.com/mikko-lab/kopilotti-sales-demo) · [Live demo](https://app.kopilotti.online/en/)

### Ruuhkavahti — Kafka-Scale Guardrails Under Load

A deterministic PASS / ESCALATE / BLOCK layer running inside a scalable Kafka consumer group; load-tested against a simulated live-TV traffic spike of 8,000 messages per second.

The dashboard makes real consumer lag, duplicate handling, and Kafka consumer-group rebalances visible through a 3D visualization, a reduced-motion 2D view, a semantic HTML table, and accessible live status updates.

`Python · TypeScript · Apache Kafka · Docker Compose · axe-core`

→ [Repository](https://github.com/mikko-lab/ruuhkavahti)

### A11Y Lead Engine — Automated Accessibility Audit Pipeline

A TypeScript-based accessibility audit pipeline that discovers Finnish business websites, runs WCAG audits, enriches results with business-registry data, and creates structured outreach material.

It combines Playwright and axe-core scanning with queue-based processing and Claude-assisted summaries; the infrastructure includes Redis authentication, API middleware, SSRF and DNS-rebinding protection, automated tests, and GitHub Actions CI.

`TypeScript · Node.js · Playwright · axe-core · Redis · BullMQ · Claude API`

→ [Repository](https://github.com/mikko-lab/a11y-lead-engine)

## Additional Work

<details>
<summary>Show additional projects</summary>

- **[osCommerce Checkout Refactor](https://github.com/mikko-lab/sap-checkout-refactor/tree/poc/checkout-modernization)** — AI-assisted modernization of a legacy checkout flow; a failing test exposed an inverted inventory rule, resulting in 34 passing tests with preserved runtime behaviour
- **[Prompt Injection Gate](https://github.com/mikko-lab/prompt-injection-gate)** — a deterministic boundary that quarantines untrusted tool output, emits PASS / ESCALATE / BLOCK outcomes, and records a hash-chained audit trail
- **[refuse-dont-guess](https://github.com/mikko-lab/refuse-dont-guess)** — a zero-dependency Python guardrail for VAT classification, with deterministic escalation and prompt-injection regression tests
- **[claude-code-invoice-guard](https://github.com/mikko-lab/claude-code-invoice-guard)** — the same guardrail principle implemented with Claude Code runtime primitives
- **[Provenanssi](https://github.com/mikko-lab/provenanssi)** — open research separating measured image information from model-generated reconstruction
- **[Karikko](https://github.com/mikko-lab/karikko)** — offline-first geospatial hazard reporting for Finnish waters, with a [backend](https://github.com/mikko-lab/karikko-api) and [live demo](https://demo.nordicmarinedata.com)

</details>

## Technology

TypeScript · JavaScript · Node.js · Python · Rust · Solidity · PostgreSQL · Redis · Apache Kafka · Docker · WebAssembly · Claude API

## Engineering Principle

LLM applications become reliable when probabilistic reasoning is separated from authoritative decision-making. I use language models where interpretation, synthesis, and interaction are valuable; deterministic software remains responsible whenever correctness, permissions, money, security, or user safety are involved. This boundary is designed into the architecture from the beginning — not added after the model reaches production.

## Contact

Open to software partnerships, architecture consulting, selected freelance projects, and remote roles.

**[Get in touch →](mailto:hello@kopilotti.online?subject=Software%20partnership%20inquiry)**
