# Mikko Tarkiainen

**Full-breadth AI Engineer** · Agentic systems, deterministic safety layers, accessibility-first

Based in Finland · Open to freelance, remote roles, and partnerships

**Accessibility consulting & WCAG 2.2 AA audits:** [wpsaavutettavuus.fi](https://wpsaavutettavuus.fi)

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

### Kopilotti — Real-Time AI Sales Co-Pilot for Automotive Retail
Real-time conversation intelligence for car sales: browser-based speech-to-text feeds a Claude-powered intent analysis pipeline that surfaces buying signals (price hesitation, financing interest, trade-in) and a live purchase-readiness score mid-conversation. Structured JSON output is designed to trigger CRM/ERP workflows (follow-up tasks, financing pre-fill, trade-in valuation). Built on 20 years of hands-on automotive retail experience — the signal taxonomy reflects real sales-floor patterns, not generic assumptions.

`Vanilla JS · Web Speech API · Node.js · Express · Server-Sent Events · Claude API · Railway`

→ [kopilotti-demo](https://github.com/mikko-lab/kopilotti-demo) · [live demo](https://mikko-lab.github.io/kopilotti-demo/)

### Provenanssi — Provenance Layer for Generative Image Restoration
A deterministic layer that labels every pixel of a restored image as *measured* or *invented* — separating what the input forces from what the model's prior fabricates (range–null space decomposition). Built as open research: pre-registered hypotheses, locked thresholds, and honest null results. Confirmed finding: calibration slope is content-dependent, verified pre-registered and robust to leave-one-out. One-command falsification test; WCAG AA accessible demo; full research log — including every retraction — public.

`Python · PyTorch · ResShift (diffusion) · Range–null decomposition · Pre-registered statistical analysis`

→ [provenanssi](https://github.com/mikko-lab/provenanssi)

### Luukku AI — LLM-Powered Document Intelligence & Risk Scoring
LLM-based system that converts unstructured Finnish real-estate documents into reliable 0–10 risk scores and automated summaries. A 2-pass extraction architecture: the first stage gathers raw data, the second validates facts, assigns confidence scores, and enforces JSON-schema compliance — eliminating hallucination in production with zero manual oversight.

`Python · Claude API · Next.js · Prisma · LLM pipelines`

→ [live demo](https://luukkuai.win)

### Karikko — Crowdsourced Geospatial System for Finnish Waters
Production mobile app and serverless backend orchestrating seven public APIs (SYKE, Finnish Transport Infrastructure Agency, Traficom, FMI, Digitraffic AIS, EMODnet, Cloudflare) into a unified real-time situational picture for boaters. Crowdsourced hazard map with community confirmations, offline-first design (SQLite), GDPR-compliant storage, Cloudflare Turnstile abuse protection.

`React Native · Expo · TypeScript · MapLibre · Next.js 15 · Neon PostgreSQL · Vercel Edge`

→ [frontend](https://github.com/mikko-lab/karikko) · [backend](https://github.com/mikko-lab/karikko-api) · [live demo](https://demo.nordicmarinedata.com)

### A11Y Lead Engine — Automated Audit & Outreach Pipeline
Production TypeScript WCAG 2.2 AA scanner that discovers Finnish business sites, runs accessibility audits, and enriches leads with business-registry data. Claude-powered summaries enable personalised outreach. Hardened infrastructure following a production compromise: Redis authentication, API middleware, SSRF/DNS-rebinding protection, root-execution removal, Vitest coverage, GitHub Actions CI.

`Node.js · TypeScript · Playwright · axe-core · Redis · BullMQ · Claude API`

→ [a11y-lead-engine](https://github.com/mikko-lab/a11y-lead-engine)

### FieldComm — Post-Quantum Communication Protocol (PoC)
Proof of concept for a quantum-resistant communication protocol: a 50-byte command frame optimised for low-bandwidth links, Shamir's Secret Sharing (3/5) key management, and a duress-vault pattern for coercion resistance. Targeted conceptually at the EU Iris² satellite constellation and LoRa mesh as transport. The README openly documents the PoC's known limitations and a realistic production path — with NCSC-FI / Common Criteria certification framed as a future phase, not a current state.

`Node.js · ML-KEM-768 (FIPS 203) · ML-DSA-65 (FIPS 204) · AES-256-GCM`

→ [fieldcomm](https://github.com/mikko-lab/fieldcomm)

### STRATUM — High-Performance 3D Simulation Engine
Zero-dependency (0 npm packages) 3D simulation demonstrating real-time routing and collision avoidance for 150 vehicles in-browser at 60 FPS. Hamiltonian energy minimisation and repulsive safety-potential fields. Accessibility at the core: prefers-reduced-motion support and semantic ARIA mapping for the 3D environment.

`Vanilla JavaScript · Three.js · Hamiltonian mechanics · WCAG 2.2 AA`

## Tech Stack

**LLM & AI:** Claude API · Anthropic SDK · Agentic orchestration · RAG architectures · Multi-pass extraction · Deterministic validation
**ML research:** Model calibration · Uncertainty quantification · Range–null decomposition · Pre-registered design · Statistical analysis
**Languages:** TypeScript · Node.js · Python · PyTorch · React · React Native
**Backend:** Next.js 15 · BullMQ · Redis · PostgreSQL · Prisma · Neon serverless
**Infrastructure:** Vercel Edge · Docker · Hetzner · Linux · Cloudflare · OAuth 2.0 · System hardening
**Real-time & voice:** Web Speech API · Server-Sent Events · Real-time streaming pipelines
**Accessibility:** WCAG 2.2 AA · ARIA · Semantic HTML · NVDA/VoiceOver testing · Mobile accessibility (React Native)

## Principle

LLM systems fail in production when reliability, validation, and operational constraints are treated as afterthoughts. I work where probabilistic reasoning meets deterministic logic — where hallucination must be eliminated, not just monitored; where accessibility is engineered into the architecture, not audited at the end; and where the same discipline applies to my own research as to my code: pre-register before the data, flag what's uncertain, retract what doesn't hold.
