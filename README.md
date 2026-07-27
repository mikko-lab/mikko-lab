# Mikko Tarkiainen

**AI Systems Engineer · Deterministic decision systems · Production reliability**

Based in Finland · Open to freelance work, remote roles, and partnerships

I build AI systems in which language models handle interpretation and interaction, while deterministic software controls decisions, validation, security, and escalation.

My work focuses on moving LLM applications beyond demos: into systems that are testable, auditable, accessible, and safe to operate on real business-critical paths.

## Focus

- **Agentic systems** — structured orchestration, tool use, state machines, and schema-enforced outputs
- **Deterministic guardrails** — explicit PASS, ESCALATE, BLOCK, ACCEPT, COUNTER, and REJECT decisions outside the language model
- **Production backends** — Node.js, TypeScript, Python, PostgreSQL, Redis, BullMQ, Kafka, and Docker
- **AI security** — prompt-injection containment, output validation, SSRF protection, authentication, and network isolation
- **Accessibility by architecture** — WCAG 2.2 AA, semantic interfaces, keyboard support, and screen-reader testing
- **Verification-first development** — tests, audit trails, measured failure modes, and execution-based validation

> **The model may interpret, propose, and communicate.
> Deterministic software decides what the system is allowed to do.**

---

# Selected Work

## Kopilotti Sales — Deterministic Digital Car Salesperson

A customer-facing digital sales channel for used-vehicle price negotiation.

The language model handles the conversation, but it never determines the price. Dealer-defined business rules control offer acceptance, counteroffers, rejection, and escalation.

The system includes:

- deterministic negotiation states
- database-level vehicle reservation locking
- fail-safe external availability checks
- mandatory condition-report acknowledgement
- multi-tenant DMS import with dry-run, approval, and atomic application
- audit trails for commercial decisions
- security controls verified against the deployed application

**Node.js · Express · PostgreSQL · JavaScript · Claude API**

→ [Repository](https://github.com/mikko-lab/kopilotti-sales-demo) · [Live demo](https://kopilotti-sales-demo.vercel.app/)

---

## Ruuhkavahti — Kafka-Scale Guardrails Under Load

A deterministic PASS / ESCALATE / BLOCK layer operating inside a scalable Kafka consumer group.

The system was load-tested against a simulated live-TV traffic spike of 8,000 messages per second. Consumer capacity scales from one to four workers while the dashboard exposes real consumer lag, duplicate handling, and Kafka rebalance behaviour.

The same operational data is available through:

- a 3D visualization
- a reduced-motion 2D view
- a semantic HTML table
- accessible live status updates

**Python · TypeScript · Apache Kafka · Docker Compose · axe-core**

→ [Repository](https://github.com/mikko-lab/ruuhkavahti)

---

## A11Y Lead Engine — Automated Accessibility Audit Pipeline

A production TypeScript system that discovers Finnish business websites, runs WCAG audits, enriches results with business-registry data, and creates structured outreach material.

The system combines Playwright and axe-core scanning with queue-based processing and Claude-assisted summaries.

Infrastructure hardening includes:

- Redis authentication
- API authentication middleware
- SSRF and DNS-rebinding protection
- removal of root execution
- automated Vitest coverage
- GitHub Actions CI

**TypeScript · Node.js · Playwright · axe-core · Redis · BullMQ · Claude API**

→ [Repository](https://github.com/mikko-lab/a11y-lead-engine)

---

## SAP Checkout Refactor — AI-Assisted Legacy Modernization

A proof of concept for applying an AI-native development workflow to unfamiliar legacy commerce code (an osCommerce checkout flow, not SAP software).

Before modifying the implementation, I mapped the checkout process and its business rules into a context document. The first interpretation contained an inverted inventory rule inherited from a stale comment. A failing test exposed the mistake before the refactor progressed.

Further investigation with `git blame` traced the inconsistency to a historical database-layer migration.

The result:

- four independently tested units
- 34 passing tests
- preserved runtime behaviour
- documented legacy defect
- no unsupported claim that the old behaviour was correct

**PHP · PHPUnit · Composer · Claude Code · Git**

→ [Repository](https://github.com/mikko-lab/sap-checkout-refactor)

---

## Prompt Injection Gate — Tool-Output Security Boundary

A deterministic security layer that quarantines untrusted tool output before it reaches the language model, containing prompt-injection attempts hidden inside tool results instead of relying on the model to recognise and resist them.

The design separates:

- untrusted tool output
- a structural quarantine boundary the content cannot forge
- best-effort pattern scanning for known injection techniques
- PASS, ESCALATE, and BLOCK outcomes
- a hash-chained, tamper-evident audit log

**Python · LLM security · Deterministic policy enforcement**

→ [Repository](https://github.com/mikko-lab/prompt-injection-gate)

---

## Qubit Harness — Agentic Experimental Control Loop

An agent-driven experimental harness in which the language model proposes the next measurement, but bounded software executes and validates it.

The workflow follows a controlled loop:

```text
Propose → Execute → Analyse → Decide next → Iterate
```

The model cannot bypass the harness's amplitude bounds, rate limit, or measurement budget. LangGraph manages the workflow, Pydantic enforces typed state, and Langfuse traces every LLM call and tool invocation.

**Python · LangGraph · Pydantic · Claude · Langfuse**

→ [Repository](https://github.com/mikko-lab/qubit-harness)

---

# Additional Work

## refuse-dont-guess

A zero-dependency Python guardrail for VAT classification on a critical invoice-processing path. Includes a 1,000-run determinism check and prompt-injection regression tests.

→ [Repository](https://github.com/mikko-lab/refuse-dont-guess)

## claude-code-invoice-guard

The same guardrail principle implemented through Claude Code runtime primitives: skill, subagent, MCP server, and PreToolUse hook.

→ [Repository](https://github.com/mikko-lab/claude-code-invoice-guard)

## Provenanssi

Open research into separating measured image information from model-generated reconstruction using range–null space decomposition and pre-registered statistical analysis.

→ [Repository](https://github.com/mikko-lab/provenanssi)

## Karikko

An offline-first geospatial hazard-reporting system for Finnish waters, integrating public environmental, navigation, weather, and vessel-data sources.

→ [Frontend](https://github.com/mikko-lab/karikko) · [Backend](https://github.com/mikko-lab/karikko-api) · [Live demo](https://demo.nordicmarinedata.com)

---

# Technology

**AI and orchestration**
Claude API · Anthropic SDK · LangGraph · Structured outputs · Tool use · Agent workflows · Prompt-injection defence

**Languages and application development**
TypeScript · JavaScript · Node.js · Python · PHP · React · React Native · Next.js

**Backend and data**
PostgreSQL · Redis · BullMQ · Apache Kafka · Prisma · Neon

**Infrastructure and security**
Docker · Vercel · Hetzner · Linux · Cloudflare · OAuth 2.0 · GitHub Actions · Application hardening

**Accessibility**
WCAG 2.2 AA · Semantic HTML · ARIA · Keyboard interaction · VoiceOver · NVDA · axe-core · Playwright

---

# Engineering Principle

LLM applications become reliable when probabilistic reasoning is separated from authoritative decision-making.

I use language models where interpretation, synthesis, and interaction are valuable. I use deterministic software where correctness, permissions, money, security, or user safety are involved.

That boundary is designed into the architecture from the beginning — not added after the model reaches production.
