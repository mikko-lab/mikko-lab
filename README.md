# Mikko Tarkiainen

Applied AI & Systems Engineer building production-grade systems around LLM
orchestration, backend architecture, and real-world API integrations.

Based in Finland · Open to freelance, remote roles, and partnerships

---

## Focus

I design and implement systems where language models operate reliably in production:

- **LLM orchestration with Claude & the Anthropic SDK** — multi-pass extraction, structured output enforcement, schema validation
- **Hybrid systems** — probabilistic LLM reasoning combined with deterministic
  validation layers to eliminate hallucinations and ensure production-safe outputs
- **Event-driven backend architecture** (BullMQ, Redis, PostgreSQL) and
  serverless infrastructure
- **API orchestration** across heterogeneous data sources (REST, GraphQL,
  WMTS, WFS)
- **Accessibility (WCAG 2.2 AA)**, security hardening, and observability as
  engineering constraints embedded into system design

No overlays. No superficial fixes. Code-level implementation.

---

## Selected Production Systems

### [Luukku AI](https://luukkuai.win/) — LLM-Powered Document Intelligence & Risk Scoring

LLM-based system that converts unstructured Finnish real-estate documents into
reliable 0–10 risk scores and automated executive summaries. Built on a 2-pass
extraction architecture: the first stage gathers raw data, the second validates
facts, assigns confidence scores, and enforces JSON schema compliance —
eliminating hallucinations in production with zero manual oversight.

`Python` · `Claude API` · `Next.js` · `Prisma` · `LLM pipelines`

---

### [Karikko](https://github.com/mikko-lab/karikko) — Crowdsourced Geospatial System for Finnish Waters

Production mobile app and serverless backend orchestrating seven public APIs
(SYKE, Finnish Transport Infrastructure Agency, Traficom, FMI, Digitraffic AIS,
EMODnet, Cloudflare) into a unified real-time situational picture for boaters.
Crowdsourced hazard map with community confirmations, offline-first design
(SQLite), GDPR-compliant data storage, Cloudflare Turnstile abuse protection.

`React Native` · `Expo` · `TypeScript` · `MapLibre` · `Next.js 15` ·
`Neon PostgreSQL` · `Vercel Edge`

Backend repo: [karikko-api](https://github.com/mikko-lab/karikko-api)

---

### [A11Y Lead Engine](https://github.com/mikko-lab/a11y-lead-engine) — Automated Audit & Outreach Pipeline

Production TypeScript-based WCAG 2.2 AA scanner that discovers Finnish business
sites, performs accessibility audits, and enriches leads with YTJ/Kauppalehti
business data. Claude-powered summaries enable personalized outreach.
Hardened infrastructure following a production compromise: Redis authentication,
API middleware, SSRF/DNS rebinding protection, root execution removal,
Vitest test coverage, GitHub Actions CI.

`Node.js` · `TypeScript` · `Playwright` · `axe-core` · `Redis` · `BullMQ` ·
`Claude API`

---

### FieldComm — Post-Quantum Field Command Protocol (PoC)

Proof-of-concept for a quantum-resistant communication protocol designed for
high-resilience environments such as the EU Iris² satellite constellation and
LoRa-mesh networks. 50-byte command structure optimized for low-bandwidth and
high-latency links. Shamir's Secret Sharing (3/5) key management and Duress
Vault pattern for physical coercion protection.

`Node.js` · `ML-KEM (FIPS 203)` · `ML-DSA (FIPS 204)` · `AES-256-GCM`

---

### STRATUM — High-Performance 3D Simulation Engine

Zero-dependency (0 npm packages) 3D simulation demonstrating real-time routing
and collision avoidance for 150 vehicles in-browser at 60 FPS. Hamiltonian
energy minimization and repulsive safety potentials. Accessibility at the core
of design: prefers-reduced-motion support and semantic ARIA mapping for the
3D environment.

`Vanilla JavaScript` · `Three.js` · `Hamiltonian mechanics` · `WCAG 2.2 AA`

---

## Tech Stack

**LLM & AI:** Claude API · Anthropic SDK · OpenAI · RAG architectures ·
Multi-pass extraction · Deterministic validation

**Languages:** TypeScript · Node.js · Python · React · React Native

**Backend:** Next.js 15 · BullMQ · Redis · PostgreSQL · Prisma · Neon serverless

**Infrastructure:** Vercel Edge · Docker · Hetzner · Linux · Cloudflare ·
OAuth 2.0 · System hardening

**Accessibility:** WCAG 2.2 AA · ARIA · Semantic HTML · NVDA/VoiceOver testing
· Mobile accessibility (React Native)

---

## Principle

LLM systems fail in production when reliability, validation, and operational
constraints are treated as afterthoughts.

I work at the intersection where probabilistic LLM reasoning meets
deterministic backend logic — where hallucinations must be eliminated, not
just monitored; where accessibility is engineered into the architecture, not
audited at the end; and where systems must be both intelligent and dependable.

---

📫 [LinkedIn](https://www.linkedin.com/in/mikko-tarkiainen-accessibility/)
