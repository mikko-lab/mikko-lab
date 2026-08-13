# Mikko Tarkiainen

**AI Systems Engineer** · Deterministic decision systems · Production reliability

Based in Finland · Open to freelance work, remote roles, and partnerships

I build AI systems in which language models handle interpretation and interaction, while deterministic software controls decisions, validation, permissions, and escalation.

My work focuses on building systems and reference implementations that are testable, auditable, accessible, and explicit about their operating boundaries.

> The model may interpret, propose, and communicate. Deterministic software decides what the system is allowed to do.

## Focus

- **Agentic systems** — structured orchestration, tool use, state machines, and schema-enforced outputs
- **Deterministic decision systems** — explicit PASS, ESCALATE, BLOCK, ACCEPT, COUNTER, and REJECT outcomes outside the language model
- **Verifiable execution** — signed receipts, reproducible builds, independent validators, and tamper-evident audit trails
- **Backend and reliability** — Node.js, TypeScript, Python, PostgreSQL, Redis, BullMQ, Kafka, and Docker
- **AI security** — prompt-injection containment, output validation, SSRF protection, authentication, and network isolation
- **Accessibility by architecture** — WCAG 2.2 AA, semantic interfaces, keyboard support, and screen-reader testing

## Selected Work

### DDN Reference — Verifiable Deterministic Decision Network

An open-source reference implementation for independently verifiable automated decisions.

Versioned business rules execute in three isolated WebAssembly validators. A decision is accepted only when a 2-of-3 quorum produces the same result. Accepted decisions receive cryptographically signed receipts that can be independently checked, batched into a Merkle tree, and optionally anchored to an EVM-compatible smart contract.

The repository includes Rust validators, TypeScript APIs and SDKs, Solidity contracts, a standalone receipt verifier, reproducible Linux/arm64 builds, SBOM generation, security scanning, and a history-free public release process.

This is a reference implementation, not a claim of an active public production deployment.

`Rust · WebAssembly · TypeScript · Solidity · Ed25519 · Merkle trees`

→ [Repository](https://github.com/mikko-lab/ddn-reference)

### Kopilotti Sales — Deterministic Used-Car Price Negotiation

A customer-facing digital sales channel for used-vehicle price negotiation.

The language model handles the conversation, but it never determines the price. Dealer-defined business rules control acceptance, counteroffers, rejection, and escalation. The backend also enforces vehicle reservation, tenant and customer ownership, contract progression, and payment-state permissions.

After an accepted price, the reference implementation can demonstrate a concept contract and payment-status tracking. Customers cannot confirm payments, and Kopilotti does not receive, hold, or transfer funds. The public demo contains no payable bank details, and the full invoice-to-PAID flow is not active in public production traffic. The DDN integration boundary exists but is not active there.

`Node.js · Express · PostgreSQL · JavaScript · Claude API · Playwright`

→ [Repository](https://github.com/mikko-lab/kopilotti-sales-demo) · [Live demo](https://app.kopilotti.online/)

### Ruuhkavahti — Kafka-Scale Guardrails Under Load

A deterministic PASS / ESCALATE / BLOCK layer running inside a scalable Kafka consumer group.

The system was load-tested against a simulated live-TV traffic spike of 8,000 messages per second. Its dashboard exposes real consumer lag, duplicate handling, and Kafka rebalance behaviour through a 3D visualization, a reduced-motion 2D view, a semantic HTML table, and accessible live status updates.

`Python · TypeScript · Apache Kafka · Docker Compose · axe-core`

→ [Repository](https://github.com/mikko-lab/ruuhkavahti)

### A11Y Lead Engine — Automated Accessibility Audit Pipeline

A TypeScript-based accessibility audit pipeline that discovers Finnish business websites, runs WCAG audits, enriches results with business-registry data, and creates structured outreach material.

The system combines Playwright and axe-core scanning with queue-based processing and Claude-assisted summaries. Its infrastructure includes Redis authentication, API middleware, SSRF and DNS-rebinding protection, automated tests, and GitHub Actions CI.

`TypeScript · Node.js · Playwright · axe-core · Redis · BullMQ · Claude API`

→ [Repository](https://github.com/mikko-lab/a11y-lead-engine)

## Additional Work

- **[osCommerce Checkout Refactor](https://github.com/mikko-lab/sap-checkout-refactor/tree/poc/checkout-modernization)** — AI-assisted modernization of a legacy checkout flow; a failing test exposed an inverted inventory rule, with 34 passing tests and preserved runtime behaviour
- **[Prompt Injection Gate](https://github.com/mikko-lab/prompt-injection-gate)** — deterministic boundary that quarantines untrusted tool output, emits PASS / ESCALATE / BLOCK outcomes, and records a hash-chained audit trail
- **[refuse-dont-guess](https://github.com/mikko-lab/refuse-dont-guess)** — zero-dependency Python guardrail for VAT classification, with deterministic escalation and prompt-injection regression tests
- **[claude-code-invoice-guard](https://github.com/mikko-lab/claude-code-invoice-guard)** — the same guardrail principle implemented with Claude Code runtime primitives
- **[Provenanssi](https://github.com/mikko-lab/provenanssi)** — open research separating measured image information from model-generated reconstruction
- **[Karikko](https://github.com/mikko-lab/karikko)** — offline-first geospatial hazard reporting for Finnish waters, with a [backend](https://github.com/mikko-lab/karikko-api) and [live demo](https://demo.nordicmarinedata.com)

## Technology

**AI and orchestration:** Claude API · Anthropic SDK · LangGraph · Structured outputs · Tool use · Agent workflows · Prompt-injection defence

**Languages and application development:** TypeScript · JavaScript · Node.js · Python · Rust · Solidity · PHP · React · React Native · Next.js

**Backend and data:** PostgreSQL · Redis · BullMQ · Apache Kafka · Prisma · Neon

**Infrastructure and security:** Docker · WebAssembly · Vercel · Hetzner · Linux · Cloudflare · OAuth 2.0 · GitHub Actions · Application hardening

**Accessibility:** WCAG 2.2 AA · Semantic HTML · ARIA · Keyboard interaction · VoiceOver · NVDA · axe-core · Playwright

## Engineering Principle

LLM applications become reliable when probabilistic reasoning is separated from authoritative decision-making.

I use language models where interpretation, synthesis, and interaction are valuable. I use deterministic software where correctness, permissions, money, security, or user safety are involved.

That boundary is designed into the architecture from the beginning — not added after the model reaches production.
