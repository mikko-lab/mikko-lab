# Mikko Tarkiainen

**Full-breadth AI Engineer** · Agentic systems, deterministic safety layers, production reliability

Based in Finland · Open to freelance, remote roles, and partnerships

## Focus

I build production-grade systems along two complementary axes — **agentic LLM orchestration** and **disciplined experimental ML research** — unified by one principle: a *deterministic safety layer wrapped around a probabilistic model*.

- **LLM orchestration** with Claude & the Anthropic SDK — multi-pass extraction, structured-output enforcement, schema validation
- **Hybrid systems** — probabilistic LLM reasoning paired with deterministic validation to eliminate hallucination, not just monitor it
- **Experimental ML research** — model calibration, uncertainty quantification, range–null space decomposition; pre-registered, with honest null results
- **Event-driven backend** (BullMQ, Redis, PostgreSQL) and serverless infrastructure
- **API orchestration** across heterogeneous sources (REST, GraphQL, WMTS, WFS)
- **Accessibility** (WCAG 2.2 AA), security hardening, and observability as engineering constraints embedded into system design

No overlays. No superficial fixes. Code-level implementation.

## Selected Work

### refuse-dont-guess — Deterministic Guardrail for an LLM Agent on a Critical Data Path
A safety layer for an LLM agent on a critical data path (VAT classification for purchase invoices): the agent extracts facts, a deterministic rule decides, and an uncertain case escalates to a human instead of being guessed at. A 1,000-run determinism check confirms the same input always produces the same decision; four security regression tests cover prompt-injection bypass attempts. Zero dependencies — pure Python standard library, auditable in a single file.

`Python (standard library only)`

→ [refuse-dont-guess](https://github.com/mikko-lab/refuse-dont-guess)

### claude-code-invoice-guard — Guardrail for Claude Code's Runtime Primitives
A sibling project to refuse-dont-guess, rebuilt as native Claude Code orchestration — all four runtime primitives in one installable plugin: skill, subagent, MCP server, PreToolUse hook. Live verification surfaced two real bugs, both fixed and re-verified. The bug proved the architecture's core claim in practice: when the subagent hallucinated a figure in its report, the actual VAT decision was still recalculated from ground truth inside the hook.

`Claude Code · Python · MCP server · Skill · Subagent · PreToolUse hook`

→ [claude-code-invoice-guard](https://github.com/mikko-lab/claude-code-invoice-guard)

### Provenanssi — Provenance Layer for Generative Image Restoration
A deterministic layer that labels every pixel of a restored image as *measured* or *invented* — separating what the input forces from what the model's prior fabricates (range–null space decomposition). Built as open research: pre-registered hypotheses, locked thresholds, and honest null results. Confirmed finding: calibration slope is content-dependent, verified pre-registered and robust to leave-one-out. One-command falsification test; WCAG AA accessible demo; full research log — including every retraction — public.

`Python · PyTorch · ResShift (diffusion) · Range–null decomposition · Pre-registered statistical analysis`

→ [provenanssi](https://github.com/mikko-lab/provenanssi)

### tutkinta-avustin — AI Assistant for Investigative Work, Built for Verifiability
An AI assistant built around verifiability rather than raw model output. A LangGraph state machine runs hard-coded guardrail rules after every node, with a hash-chained audit log that detects tampering. Contrasts three perspectives on one synthetic case — traditional manual process, naive AI, and AI with deterministic guardrails — side by side in a Streamlit UI. 20 passing pytest tests, hash-locked dependencies with SHA-256 verification.

`Python · LangGraph · Streamlit`

→ [tutkinta-avustin](https://github.com/mikko-lab/tutkinta-avustin)

### Luukku AI — LLM-Powered Document Intelligence & Risk Scoring
LLM-based system that converts unstructured Finnish real-estate documents into reliable 0–10 risk scores and automated summaries. A 2-pass extraction architecture: the first stage gathers raw data, the second validates facts, assigns confidence scores, and enforces JSON-schema compliance — eliminating hallucination in production with zero manual oversight.

`Python · Claude API · Next.js · Prisma · LLM pipelines`

→ [live demo](https://luukkuai.win)

### Karikko — Crowdsourced Geospatial System for Finnish Waters
Production mobile app and serverless backend orchestrating seven public APIs (SYKE, Finnish Transport Infrastructure Agency, Traficom, FMI, Digitraffic AIS, EMODnet, Cloudflare) into a unified real-time situational picture for boaters. Crowdsourced hazard map with community confirmations, offline-first design (SQLite), GDPR-compliant storage, Cloudflare Turnstile abuse protection.

`React Native · Expo · TypeScript · MapLibre · Next.js 15 · Neon PostgreSQL · Vercel Edge`

→ [frontend](https://github.com/mikko-lab/karikko) · [backend](https://github.com/mikko-lab/karikko-api) · [live demo](https://demo.nordicmarinedata.com)

### A11Y Lead Engine — Automated Audit & Outreach Pipeline
Production TypeScript WCAG 2.2 AA scanner (~7,500 lines of production code, running on Hetzner) that discovers Finnish business sites, runs accessibility audits, and enriches leads with business-registry data. Claude-powered summaries enable personalised outreach. Hardened infrastructure following a production compromise: Redis authentication, API middleware, SSRF/DNS-rebinding protection, root-execution removal, Vitest coverage, GitHub Actions CI.

`Node.js · TypeScript · Playwright · axe-core · Redis · BullMQ · Claude API`

→ [a11y-lead-engine](https://github.com/mikko-lab/a11y-lead-engine)

*Also offering WCAG 2.2 AA accessibility consulting — [wpsaavutettavuus.fi](https://wpsaavutettavuus.fi)*

## Tech Stack

**LLM & AI:** Claude API · Anthropic SDK · LangGraph · Agentic orchestration · RAG architectures · Multi-pass extraction · Deterministic guardrails · Prompt-injection defense
**ML research:** Model calibration · Uncertainty quantification · Range–null decomposition · Pre-registered design · Statistical analysis
**Languages:** TypeScript · Node.js · Python · PyTorch · React · React Native
**Backend:** Next.js 15 · BullMQ · Redis · PostgreSQL · Prisma · Neon serverless
**Infrastructure:** Vercel Edge · Docker · Hetzner · Linux · Cloudflare · OAuth 2.0 · System hardening
**Accessibility:** WCAG 2.2 AA · ARIA · Semantic HTML · NVDA/VoiceOver testing · Mobile accessibility (React Native)

## Principle

LLM systems fail in production when reliability, validation, and operational constraints are treated as afterthoughts. I work where probabilistic reasoning meets deterministic logic — where hallucination must be eliminated, not just monitored; where accessibility is engineered into the architecture, not audited at the end; and where the same discipline applies to my own research as to my code: pre-register before the data, flag what's uncertain, retract what doesn't hold.
