# Mikko Tarkiainen

**AI Systems Engineer** · Deterministic decision systems · Production reliability

Based in Finland · Open to freelance work, remote roles, and partnerships

I build AI systems in which language models handle interpretation and interaction, while deterministic software controls decisions, validation, permissions, and escalation.

My work focuses on moving AI applications beyond demos into systems that are testable, auditable, accessible, and safe to operate on business-critical paths.

> The model may interpret, propose, and communicate. Deterministic software decides what the system is allowed to do.

## Focus

- **Agentic systems** — structured orchestration, tool use, state machines, and schema-enforced outputs
- **Deterministic decision systems** — explicit PASS, ESCALATE, BLOCK, ACCEPT, COUNTER, and REJECT outcomes outside the language model
- **Verifiable execution** — signed receipts, reproducible builds, independent validators, and tamper-evident audit trails
- **Production backends** — Node.js, TypeScript, Python, PostgreSQL, Redis, BullMQ, Kafka, and Docker
- **AI security** — prompt-injection containment, output validation, SSRF protection, authentication, and network isolation
- **Accessibility by architecture** — WCAG 2.2 AA, semantic interfaces, keyboard support, and screen-reader testing

## Selected Work

### DDN Reference — Verifiable Deterministic Decision Network

An open-source reference implementation for independently verifiable automated decisions.

Versioned business rules execute in three isolated WebAssembly validators. A decision is accepted only when a 2-of-3 quorum produces the same result. Approved decisions receive cryptographically signed receipts that can be verified independently and anchored through Merkle roots to an EVM-compatible smart contract.

The repository includes Rust validators, TypeScript APIs and SDKs, Solidity contracts, a standalone receipt verifier, reproducible Linux/arm64 builds, SBOM generation, security scanning, and a history-free public release process.

This is a reference implementation, not a claim of an active public production deployment.

`Rust · WebAssembly · TypeScript · Solidity · Ed25519 · Merkle trees`

→ [Repository](https://github.com/mikko-lab/ddn-reference)

### Kopilotti Sales — Deterministic Digital Car Salesperson

A customer-facing digital sales channel for used-vehicle price negotiation.

The language model handles the conversation, but it never determines the price. Dealer-defined business rules control acceptance, counteroffers, rejection, and escalation. The backend also enforces vehicle reservation, tenant and customer ownership, contract progression, and payment-state permissions.

The customer can continue from an accepted offer to a concept contract and payment-status tracking in the same experience. Only the dealer can confirm a bank-transfer payment. Public production demos remain non-payable, and the DDN verification boundary is implemented but not active in public production traffic.

`Node.js · Express · PostgreSQL · JavaScript · Claude API · Playwright`

→ [Repository](https://github.com/mikko-lab/kopilotti-sales-demo) · [Live demo](https://kopilotti-sales-demo.vercel.app)

### Ruuhkavahti — Kafka-Scale Guardrails Under Load

A deterministic PASS / ESCALATE / BLOCK layer running inside a scalable Kafka consumer group.

The system was load-tested against a simulated live-TV traffic spike of 8,000 messages per second. Its dashboard exposes real consumer lag, duplicate handling, and Kafka rebalance behaviour through a 3D visualization, a reduced-motion 2D view, a semantic HTML table, and accessible live status updates.

`Python · TypeScript · Apache Kafka · Docker Compose · axe-core`

→ [Repository](https://github.com/mikko-lab/ruuhkavahti)

### A11Y Lead Engine — Automated Accessibility Audit Pipeline

A production TypeScript system that discovers Finnish business websites, runs WCAG audits, enriches results with business-registry data, and creates structured outreach material.

The system combines Playwright and axe-core scanning with queue-based processing and Claude-assisted summaries. Its infrastructure includes Redis authentication, API middleware, SSRF and DNS-rebinding protection, automated tests, and GitHub Actions CI.

`TypeScript · Node.js · Playwright · axe-core · Redis · BullMQ · Claude API`

→ [Repository](https://github.com/mikko-lab/a11y-lead-engine)

### SAP Checkout Refactor — AI-Assisted Legacy Modernization

A proof of concept for applying an AI-native development workflow to an unfamiliar legacy osCommerce checkout flow — not SAP software.

Before implementation changes, the checkout process and its business rules were mapped into a context document. A failing test exposed an inverted inventory rule inherited from a stale comment, and `git blame` traced the inconsistency to a historical database-layer migration.

The result: four independently tested units, 34 passing tests, preserved runtime behaviour, and a documented legacy defect without claiming that the old behaviour was correct.

`PHP · PHPUnit · Composer · Claude Code · Git`

→ [Repository](https://github.com/mikko-lab/sap-checkout-refactor/tree/poc/checkout-modernization)

### Prompt Injection Gate — Tool-Output Security Boundary

A deterministic security layer that quarantines untrusted tool output before it reaches the language model. The design separates untrusted content from the control boundary, applies best-effort detection for known injection techniques, produces PASS / ESCALATE / BLOCK outcomes, and records decisions in a hash-chained audit log.

`TypeScript · LLM security · Deterministic policy enforcement`

→ [Repository](https://github.com/mikko-lab/prompt-injection-gate)

## Additional Work

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
