# Balott

> **Where Baloot lives — online, in the majlis, in competition, and in your history.**

Balott is a Saudi-born, competition-grade Baloot platform. The goal is not to build another mobile card game or a prettier clone of an incumbent. The goal is to build the definitive home of Baloot: the best place to play, master, organize, watch, verify, and remember the game.

## Current status

`PLANNING_ONLY`

This repository is intentionally starting from a clean slate. Product code is not authorized by this planning package. The first objective is to freeze a coherent product, gameplay, trust, architecture, design, source, and execution plan before implementation begins.

## Product laws

1. **Real-table freedom.** Human players may make catchable table violations. The client does not automatically police every legal choice in Open Table play.
2. **Human-only Qayd.** Humans may call Qayd. Bots never call Qayd and never signal a missed violation.
3. **Bots never cheat.** A bot never intentionally makes an illegal play and never receives hidden information unavailable to a human in the same seat.
4. **The deck never knows who you are.** Shuffle inputs never depend on rank, spending, win streak, account age, subscription, or engagement state.
5. **Fairness is verifiable.** Official play uses cryptographically strong, reproducible deal proofs and public statistical fairness monitoring.
6. **No innocent rank loss for abandonment.** A player is not punished in visible rank because a teammate abandoned the match. Abuse protection is handled separately.
7. **Server authority for competition.** Ranked, official tournaments, and 152 events are server-authoritative and replayable from a canonical match ledger.
8. **No pay-to-win.** Money may buy expression, convenience, premium analysis, or presentation — never better cards, matchmaking, hidden information, or competitive power.
9. **No casino UX.** Balott should feel like a premium sport and a real majlis, not a slot machine.
10. **Evidence before claims.** Fairness, bot strength, anti-cheat, accessibility, performance, and readiness claims require measured evidence.

## Canonical planning package

- [`PRODUCT.md`](PRODUCT.md) — audience, product thesis, jobs, positioning, and non-goals.
- [`DESIGN.md`](DESIGN.md) — Impeccable-compatible design direction and UI rules.
- [`docs/CANONICAL_PRODUCT_PLAN.md`](docs/CANONICAL_PRODUCT_PLAN.md) — full product system and feature model.
- [`docs/GAMEPLAY_AND_RULES.md`](docs/GAMEPLAY_AND_RULES.md) — rules engine, Open Table, Qayd, deal lifecycle, scoring, and table semantics.
- [`docs/FAIR_PLAY_RANKED_INTEGRITY.md`](docs/FAIR_PLAY_RANKED_INTEGRITY.md) — verified dealing, ranked, abandonment protection, anti-collusion, and trust.
- [`docs/BOT_VOICE_AI.md`](docs/BOT_VOICE_AI.md) — Balott Bot, voice commands, AI Coach, and strict information boundaries.
- [`docs/SOCIAL_REAL_TABLE_152.md`](docs/SOCIAL_REAL_TABLE_152.md) — Majlis, partners, clubs, real-table mode, live/spectator, and the 152 Circuit.
- [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — target technical architecture and authoritative data boundaries.
- [`docs/COMPETITIVE_LANDSCAPE.md`](docs/COMPETITIVE_LANDSCAPE.md) — incumbent baseline and differentiation strategy.
- [`docs/ROADMAP.md`](docs/ROADMAP.md) — dependency-ordered program from foundation to championship-grade operation.
- [`docs/SPECGRAIN_EXECUTION.md`](docs/SPECGRAIN_EXECUTION.md) — SpecGrain decomposition and Diffcipline proof model.
- [`docs/provenance/SOURCES.md`](docs/provenance/SOURCES.md) — source/donor/reference registry.
- [`docs/provenance/SOURCE_USE_AUTHORIZATION.md`](docs/provenance/SOURCE_USE_AUTHORIZATION.md) — founder source-use authorization record and adoption controls.

## Delivery method

Balott uses **SpecGrain** for recursive specification decomposition and bounded WorkPackets, and **Diffcipline** for proof-before-done verification at the exact implementation revision.

The planning rule is simple:

> Large vision -> bounded specification -> Grain -> implementation -> independent proof -> evidence.

No agent self-report, screenshot, benchmark claim, or green-looking UI is sufficient evidence by itself.

## Design method

Balott uses [Impeccable](https://impeccable.style) as the UI design discipline. `PRODUCT.md` and `DESIGN.md` are authoritative design context. The implementation must avoid generic AI-generated UI, casino/gacha patterns, unnecessary card-inside-card layouts, decorative grid backgrounds, and motion without gameplay meaning.

## Language

Repository, code, specifications, technical plans, evidence, commits, PRs, and implementation-facing content are written in English. The shipped product is Arabic-first and Saudi-native, with excellent English support where useful.
