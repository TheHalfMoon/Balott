# Balott Target Architecture

**Status:** architecture direction; implementation choices remain subject to Grain-level benchmarks and qualification.

## 1. Architecture principles

- server-authoritative competition;
- deterministic shared game core;
- append-oriented canonical match ledger;
- explicit information boundaries;
- mobile-first premium interaction;
- local-first where it improves private/voice experiences without weakening official authority;
- no premature microservice fleet;
- no hidden gameplay-affecting experiments;
- reproducible rules/shuffle/bot/tournament versions;
- privacy-minimized observability.

## 2. Recommended repository shape

```text
apps/
  mobile/           # React Native / Expo app, production native builds
  web/              # web game/spectator/replay where appropriate
  admin/            # operations/tournament/support surface
packages/
  design/           # tokens, icons, shared design contracts
  contracts/        # versioned network/event schemas
  analytics/        # event taxonomy and privacy rules
crates/
  balott-core/      # pure deterministic rules/state/scoring
  balott-shuffle/   # verified deal protocol and public verifier core
  balott-bot/       # seat-bounded bot logic/simulation interfaces
  balott-replay/    # event/replay verification utilities
services/
  platform/         # initial Rust modular backend
  workers/          # isolated non-authoritative async/AI jobs
infra/
  ...               # deployment definitions after runtime direction is proven
docs/
```

Do not create every directory before an authorized implementation Grain needs it.

## 3. Client direction

### Mobile

Recommended starting direction:

- React Native with Expo development tooling/native builds;
- React Native Skia or equivalent measured rendering path for the card table if normal views do not meet frame/gesture targets;
- Reanimated/native animation primitives;
- native modules only where voice/audio/haptics/platform capability requires them;
- shared TypeScript design tokens generated from the design system.

Why:

- premium touch/haptics/native integration;
- strong iOS/Android ecosystem;
- TypeScript product surfaces remain compatible with Impeccable-driven web/design workflows;
- card game does not require a full 3D engine.

The final rendering choice must be validated on representative low/mid/high devices, including Arabic UI, large cards, voice active, and poor network conditions.

### Web

Use a React web surface for:

- web play if latency/input evidence is acceptable;
- replay/spectator;
- 152 broadcast/event pages;
- support/admin/organizer operations;
- marketing.

Do not force pixel-identical mobile/web UI if platform ergonomics differ.

## 4. Game core

`balott-core` should be Rust and free from UI/network/database dependencies.

Responsibilities:

- deck/card primitives;
- contract/bid state;
- deterministic transitions;
- scoring/projects;
- ruleset interpretation;
- strict legal-action generation;
- Qayd historical validation;
- state/event digests;
- replay/simulation hooks.

Compile/use through:

- native Rust server directly;
- UniFFI/C-ABI/native binding for mobile where justified;
- WASM for web/replay verification where practical.

The server remains authoritative even when clients share the deterministic core for prediction/rendering.

## 5. Backend direction

Start as a **Rust modular monolith**, not dozens of microservices.

Suggested runtime:

- Tokio async runtime;
- Axum or equivalently mature HTTP/WebSocket framework;
- WebSocket as the first live match/control transport because payloads are small and ecosystem support is excellent;
- benchmark before replacing structured JSON with binary protocol on the hot path.

Modules:

- identity/session;
- social/presence;
- matchmaking;
- authoritative match runtime;
- ranked/integrity;
- tournament/152;
- replay/spectator publication;
- support/reporting;
- commerce/cosmetics separated from gameplay authority.

Split services only when scaling/failure-domain evidence justifies it.

## 6. Match runtime

Each active match has one authoritative owner at a time.

Conceptual flow:

`client command -> session/auth -> match owner -> balott-core -> canonical event append -> projection -> fanout`

Requirements:

- monotonic event sequence;
- idempotent command identity where retries can occur;
- reconnect from durable snapshot + later events;
- explicit ownership/lease loss handling;
- no dual-authority split brain;
- match completion does not depend on analytics/Coach workers.

For early scale, sticky match ownership plus a durable database is simpler than a distributed actor framework. Introduce specialized orchestration only after load/failure evidence.

## 7. Canonical storage

### PostgreSQL

System of record for:

- accounts/identity bindings;
- social relationships;
- teams/majlis/clubs;
- tournaments;
- rank/integrity records;
- match metadata;
- append-oriented match events or the authoritative index to immutable event segments;
- support/dispute state.

Use partitioning/materialized projections when measured volume requires it.

### Redis

Ephemeral, rebuildable state only:

- presence;
- queue coordination;
- short-lived rate limiting;
- match routing hints;
- caches.

Redis must not become the only copy of completed official match truth.

### Object storage

Use for immutable/large artifacts when needed:

- compact replay archives;
- public verification packages;
- broadcast assets/highlight outputs;
- support attachments with retention controls.

## 8. Event ledger

Prefer append-oriented canonical events and deterministic projections over opaque mutable match state.

Event requirements:

- schema/version;
- match/deal sequence;
- command/action identity where relevant;
- ruleset/tournament manifest identity;
- authoritative timestamp/ordering metadata;
- deterministic payload;
- integrity/digest strategy.

Snapshots are allowed for fast reconnect as derived acceleration. They never erase the ability to establish canonical history.

## 9. Shuffle service boundary

Shuffle should be a narrow library/service boundary owned by Balott, not a generic personalization system.

Inputs are limited to cryptographic protocol identity, match/deal identity, server secret/commitment state, and permitted player entropy.

No analytics/commerce/profile service is allowed as a shuffle dependency.

## 10. Identity and authorization

Consumer login may support platform-native options such as Apple/Google/phone/email according to product/legal needs.

Authorization must model:

- player;
- majlis roles;
- club roles;
- tournament organizer/referee/caster roles;
- support/admin roles;
- service identities.

Study ZITADEL/Keycloak/OpenFGA/OPA patterns, but do not adopt enterprise complexity until Balott's role model justifies it.

High-stakes 152 events may require stronger identity verification than ordinary play. `Balott Verified` is a tier/capability, not a requirement for casual use.

## 11. Voice architecture

### Commands

Prefer on-device/local runtime. Audio does not enter the match authority; only the resulting user-confirmed command does.

### Chat

Use WebRTC-class media transport and isolate it from match state. Competitive communication policy lives in the queue/tournament manifest.

### Moderation

Store the minimum evidence required by policy. Do not continuously transcribe/store every room by default.

## 12. Local/private P2P

Explore `n0-computer/iroh` or equivalent only for:

- local/private Majlis convenience;
- nearby Real Table coordination;
- optional private artifact transfer/sync where justified.

Never let P2P create official Ranked/152 authority or bypass server integrity controls.

## 13. Bot/Coach isolation

Bot decision code may execute in the match process only if it receives the strict seat observation contract and meets latency/reliability requirements.

Heavy Coach/self-play/model workers are separate. Their failure cannot block official match state.

OpenSandbox/Wasmtime/Extism patterns are candidates for future isolated extension/model tooling, not launch dependencies.

## 14. Analytics

Create an explicit event taxonomy rather than recording arbitrary client state.

Separate:

- product analytics;
- operational telemetry;
- fairness statistics;
- anti-cheat/integrity evidence;
- financial events.

Access/retention differ by category.

Study PostHog/Superset/Umami patterns. Prefer Balott-owned minimal events over broad session replay in sensitive gameplay/voice contexts.

## 15. Observability

OpenTelemetry-compatible tracing/metrics/logging direction.

Critical service objectives include:

- match command latency;
- reconnect success/time;
- match ownership failures;
- websocket disconnect rate;
- deal verification failures;
- rules engine panics/invariant failures;
- queue time;
- voice-command latency/error rate;
- server region health.

Logs must not contain hidden hands, raw voice, authentication secrets, or sensitive anti-cheat data unless an explicit secured evidence path requires it.

## 16. Security

High-priority threats:

- hidden-card leakage;
- client trust mistakes;
- replay/spectator leakage;
- account takeover;
- session hijacking;
- collusion/win trading;
- multi-account abuse;
- bot information-boundary regression;
- shuffle manipulation;
- tournament-admin privilege abuse;
- voice harassment/privacy leakage;
- support/admin horizontal access;
- supply-chain compromise.

The client is untrusted for competitive truth.

## 17. Scaling sequence

Do not add Kafka/NATS/service mesh/graph DB/complex workflow engine by default.

Scale in this order:

1. efficient modular monolith;
2. horizontal stateless API/social nodes;
3. explicit match ownership/routing;
4. partitioned event/data storage;
5. dedicated matchmaking/replay/broadcast services when measured;
6. stream/event infrastructure only when database/outbox patterns cease to meet proven needs;
7. specialized graph/search stores only when real queries justify them.

## 18. Release targets

Define device/network performance budgets before implementation freezes:

- touch acknowledgement;
- card animation frame pacing;
- command-to-authoritative acknowledgement;
- reconnect time;
- app startup-to-play path;
- memory/battery under voice;
- package size/model downloads;
- web first-load for spectator/event pages.

No `120 FPS` marketing claim without sustained evidence on named supported device classes.
