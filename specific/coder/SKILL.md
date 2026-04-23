📦 SKILL: ENTERPRISE CODE GENERATOR
│
├── TYPE: [Declarative | Executable] ⚙️
│   ├── Declarative: Enforces strict typing, architecture, resilience, and security contracts
│   └── Executable: Outputs production-ready, fully typed, dependency-free code blocks
│
├── ⛔ 0. ABSOLUTE DIRECTIVES (NON-NEGOTIABLE)
│   ├── Output ONLY code (zero external commentary)
│   ├── All code MUST include English comments explaining logic, inputs, outputs
│   ├── No pseudo-code, placeholders (TODO/mock/stub), or partial implementations
│   ├── No unsafe shortcuts, generic try/except, or untyped functions
│   ├── Zero `any` in TypeScript; strict typing mandatory everywhere
│   ├── Every module MUST be production-ready and fully functional
│   ├── High cohesion, low coupling; DRY enforced
│   ├── Explicit naming only (no ambiguous abbreviations)
│   └── Code must be ready to run in production environment
│
├── 1. METADATA
│   ├── Name: enterprise-code-generator
│   ├── Description: Generates strictly typed, resilient, distributed, and observable code across Python, TS/Next.js, and infrastructure
│   ├── Triggers: Microservices, API endpoints, frontend components, config/policy files, stateless agents
│   └── License: Project-specific / Internal
│
├── 2. CORE CONCEPT
│   └── Code is a binding contract. Every system must be strictly typed, stateless by default, independently deployable, resilient to failure, and fully observable.
│
├── 3. OPERATIONS MATRIX
│   ├── Generate: New services, components, policies, or infrastructure configs
│   ├── Refactor: Legacy sync → async, loose → strict typing, monolithic → layered
│   ├── Validate: Schema checks, policy enforcement, contract verification
│   └── Instrument: OpenTelemetry traces, idempotency keys, circuit breakers
│
├── 4. CREATION FLOW
│   ├── 🐍 Python (Enterprise)
│   │   ├── Typing: Mandatory `typing.List`, `Dict`, `Optional`, `Union`, `Tuple` + explicit returns
│   │   ├── Data: `@dataclass(frozen=True)` for immutable models; `pydantic.BaseModel` for API/validation
│   │   ├── Arch: `domain/`, `services/`, `repositories/`, `interfaces/` separation
│   │   ├── SOLID: `typing.Protocol` for interfaces; Dependency Inversion mandatory
│   │   └── Async: `asyncio` + `aiohttp` for all I/O; zero blocking calls
│   │
│   ├── 📘 TypeScript / Node.js / Next.js
│   │   ├── Types: ABSOLUTE `any` ban; interfaces, generics `<T>`, discriminated unions required
│   │   ├── Validation: All external input validated via `zod` (preferred) or `yup` before services
│   │   ├── Arch: Strict `routes → controllers → services → repositories` layering; zero cross-contamination
│   │   ├── Next.js: Server Components (backend logic) vs Client Components (UI) strictly separated
│   │   └── React: Functional only; fully typed props; strict hook rules; explicit state; no hidden mutations
│   │
│   ├── 🌐 Distributed Systems
│   │   ├── Resilience: Mandatory `timeout`, `retry (exponential backoff)`, `circuit breaker`
│   │   ├── Idempotency: All mutations use request IDs/dedup keys; safe retries guaranteed
│   │   └── Messaging: Kafka/RabbitMQ for async workflows; zero sync coupling for heavy tasks
│   │
│   ├── ⚙️ Configuration & Data Formats
│   │   ├── YAML/TOML: Environment config ONLY; NEVER store secrets (use env vars / secret managers)
│   │   ├── JSON: Transport format ONLY; MUST be schema-validated before use
│   │   └── Rego (OPA): Authorization externalized; app enforces OPA decisions only (Policy-as-Code)
│   │
│   ├── 🖥️ Frontend / HTML
│   │   ├── Semantic tags + mandatory ARIA labels for accessibility
│   │   ├── Performance-first rendering; zero layout-blocking operations
│   │   └── Edge-runtime compatible; optimized asset loading
│   │
│   └── 🔍 Observability & System Design
│       ├── Structured logging + OpenTelemetry distributed tracing
│       ├── Correlation IDs propagated across all sync/async boundaries
│       └── Agents/Services: Strictly `Stateless` (Input → Process → Output); horizontal scaling ready
│
├── 5. EDITING FLOW
│   ├── Inject resilience wrappers around all external/network calls
│   ├── Replace inline logic with `Protocol`/`Interface` abstractions
│   ├── Extract hardcoded values → env vars / secret managers
│   ├── Add OPA policy checks before business logic execution
│   └── Ensure all agents/services remain stateless; externalize state explicitly
│
├── 6. INTERNAL STRUCTURE REFERENCE
│   ├── Dependency Inversion: Consumers depend on abstractions, not implementations
│   ├── Idempotency Pattern: `Idempotency-Key` header → cache/dedup store → safe retry
│   ├── Policy Delegation: App queries OPA → OPA returns `allow/deny` → App enforces
│   ├── Trace Propagation: `traceparent` header passed through all boundaries
│   └── Validation Boundary: Zod/Pydantic at system entry; strict types internally
│
├── 7. SKILL LIMITS ⚠️
│   ├── Does NOT auto-migrate legacy monoliths to microservices
│   ├── Does NOT replace manual security, compliance, or penetration testing
│   ├── Requires external infra for OPA, message brokers, and observability collectors
│   └── Stateful workflows require explicit, documented state management layers
│
├── 8. SECURITY & BEST PRACTICES 🔒
│   ├── Zero secrets in code/config (use Vault, AWS Secrets, or env vars)
│   ├── Least privilege for DB, queue, and OPA access
│   ├── OPA centralizes authZ; application code only enforces decisions
│   ├── Idempotent endpoints prevent duplicate writes on network retry
│   └── Agents must be stateless; externalize memory to Redis/DB/cache
│
├── 9. ERROR HANDLING
│   ├── Circuit Breaker trips → graceful degradation or fallback response
│   ├── Validation fails → structured 4xx with Zod/Pydantic error map
│   ├── Timeout/Network → retry with backoff → fail open/closed per policy
│   ├── Distributed failure → OpenTelemetry span captures exact break point
│   └── Fatal crash → structured log + alert + safe exit (explicit exceptions only)
│
├── 10. PRACTICAL EXAMPLES
│   ├── Simple: Python async service with Pydantic + aiohttp + strict typing
│   ├── Intermediate: Next.js route → Controller → Service → OPA check + Zod
│   └── Complex: Distributed flow: API → Kafka → Consumer → gRPC → Trace propagation
│
├── 11. VALIDATION & TESTING
│   ├── Python: Ruff + Mypy + Pydantic runtime checks
│   ├── TS/Node: ESLint + strict TS + Zod schema tests
│   ├── Policy: `opa test` for Rego rules
│   ├── Distributed: Chaos testing, idempotency replay tests
│   └── Contracts: gRPC/GraphQL schema linting + load tests
│
└── 12. DEPENDENCIES
    ├── Docker + Compose (environment parity)
    ├── Linters/Formatters: Ruff, Mypy, ESLint, Prettier, TSC
    ├── Validation: Pydantic, Zod/Yup
    ├── Policy: Open Policy Agent (OPA)
    ├── Messaging: RabbitMQ or Kafka
    ├── Observability: OpenTelemetry SDK + Collector
    └── Contracts: gRPC/protobuf or GraphQL codegen