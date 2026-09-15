# Balott Execution Master Roadmap

**Status:** canonical dependency-ordered plan  
**Implementation authority:** none until a bounded SpecGrain leaf is explicitly authorized

## Program rule

Balott is a competitive hidden-information game. Core correctness, fairness, and recovery must be proven before growth features can mask defects.

The roadmap therefore orders work as:

`rules -> shuffle/ledger -> runtime/reconnect -> Open Table/Qayd -> premium table -> identity/social -> ranked/integrity -> bot/voice -> replay/live -> clubs/152 -> real-table -> Coach/business -> launch hardening`

A later phase may be researched early, but implementation must not bypass dependencies that establish authority or trust.

## P00 — Foundation and measurable targets

### G0001 — Repository/toolchain foundation

Establish the minimal monorepo/toolchain needed by the first implementation leaves. Do not create speculative services.

**Gate:** reproducible clean build/test path on supported developer platforms.

### G0002 — CI, provenance, and proof policy

Add SpecGrain state/workflow, Diffcipline policy, source-adoption templates, dependency/SBOM direction, and exact-revision CI evidence.

**Gate:** a trivial bounded change can be independently proven at exact HEAD.

### G0003 — Product/table interaction prototype

Use Impeccable to shape and prototype the mobile table, hand, score, bidding, Qayd affordance, reconnect state, and Arabic typography before locking UI architecture.

**Gate:** usability review establishes a direction that supports Open Table without accidental-play chaos.

### G0004 — Performance/threat budgets

Freeze initial budgets and threat model for command latency, frame pacing, reconnect, hidden-card isolation, spectator leakage, voice, auth, and tournament roles.

**Gate:** measurable acceptance thresholds exist before optimization claims.

## P01 — Deterministic Baloot core

### G0101 — Card/deck/seat primitives

Pure deterministic domain model with serialization/test fixtures.

### G0102 — Bid/contract state machine

Sun/Hokum/Ashkal/pass and supported contract lifecycle.

### G0103 — Trick/legal-action engine

Strict legality and card ordering independent from Open Table action acceptance.

### G0104 — Projects/scoring/match completion

Versioned scoring and match target.

### G0105 — Ruleset versioning

Immutable ruleset identity/digest and official/custom/training profiles.

### G0106 — Rules property/fuzz corpus

Property tests, edge cases, replay determinism, parser/state-machine fuzzing.

**P01 gate:** the core can deterministically replay a complete synthetic match with zero UI/network/database dependency.

## P02 — Verified dealing and canonical match ledger

### G0201 — CSPRNG shuffle protocol prototype

Freeze candidate primitives and unbiased deterministic shuffle.

### G0202 — Commit/entropy/reveal protocol

Server commitment, client contribution/fallback policy, safe reveal timing.

### G0203 — Public deal verifier

Independent verifier library/CLI or equivalent deterministic surface.

### G0204 — Canonical event schema

Versioned match/deal events with ordering/idempotency/digests.

### G0205 — Projection/snapshot model

Derived state for reconnect/read performance without becoming authority.

### G0206 — Fairness simulation harness

Large-sample distribution tests and negative tests for hidden reroll/personalization inputs.

**P02 gate:** every test match deal can be verified and reconstructed from frozen protocol + events.

## P03 — Authoritative real-time match runtime

### G0301 — Session/authenticated command envelope

Authenticated, ordered, retry-safe command boundary.

### G0302 — Single-owner match runtime

One authoritative owner, deterministic command application, event append/fanout.

### G0303 — WebSocket client protocol

Reconnect-safe live transport and protocol compatibility rules.

### G0304 — Durable reconnect

Snapshot + event catch-up, grace state, safe rejoin.

### G0305 — Ownership/fault recovery

No split-brain; explicit lease/owner loss semantics and server-fault void path.

### G0306 — Network fault harness

Packet loss, jitter, disconnect, delayed duplicate command, process restart scenarios.

**P03 gate:** a match survives representative client/network faults without card duplication, state divergence, or ambiguous authority.

## P04 — Open Table and Qayd

### G0401 — Permissive human action acceptance

Separate physically attempted action from strict legal-action set for catchable violations.

### G0402 — Historical Qayd validator

Validate human-selected claims against pre-action hidden state and frozen ruleset.

### G0403 — Claim window/false claim semantics

Deterministic claim lifecycle and consequence.

### G0404 — Bot Qayd prohibition

Structural/test proof that bots cannot claim or consume violation flags.

### G0405 — Assisted training profile

Explicit beginner mode with guidance that cannot leak into competitive queues.

**P04 gate:** human can commit a catchable violation, another human can correctly claim it, a bot cannot detect/claim it, and a missed claim remains missed.

## P05 — Premium mobile table

### G0501 — Design tokens and Arabic typography

Impeccable-shaped system, accessibility roles, score/tabular numerals.

### G0502 — Hand/table render and gestures

Fast card selection/commit, large-card/readability options, reduced motion.

### G0503 — Bid/project/score UI

Clear contract state with no casino clutter.

### G0504 — Reconnect/rank-protection UX foundation

Explicit connectivity states and failure messaging.

### G0505 — Audio/haptic language

Physical card/turn/score/Qayd cues with independent controls.

### G0506 — Device performance matrix

Low/mid/high iOS/Android frame, memory, thermal, startup, accessibility evidence.

**P05 gate:** four humans can complete repeated private matches with excellent table readability and measured responsiveness.

## P06 — Identity, Passport, friends, and Majlis

### G0601 — Account/session identity

Minimal consumer identity and secure session lifecycle.

### G0602 — Player Passport foundation

Career identity, privacy controls, export direction.

### G0603 — Friends/presence/invite

Fast presence and invite/call-to-table flow.

### G0604 — Persistent Majlis

Roles, saved rules, members, table, history.

### G0605 — Majlis memory projections

Champions, duo history, records, rivalry seeds.

### G0606 — Social safety

Block/report/privacy/moderation boundaries.

**P06 gate:** a known group can live in Balott without relying on an external chat just to recreate the table every time.

## P07 — Ranked, matchmaking, and integrity

### G0701 — Skill rating simulation

Evaluate team-aware rating candidates and uncertainty handling.

### G0702 — Rank Points/divisions/seasons

Visible progression separated from hidden skill estimate.

### G0703 — Integrity Rating

Explainable reliability/enforcement states and retention policy.

### G0704 — Matchmaking

Latency/region/skill/party constraints with measurable queue-quality tradeoffs.

### G0705 — Abandonment protection state machine

Random teammate protection, server-fault void, premade abuse states.

### G0706 — Stand-in policy

Activation, strength selection, human return, ranking implications.

### G0707 — Connection readiness

Pre-Ranked network health warning and region/service health.

### G0708 — Integrity graph v1

Pair/opponent/device/match pattern analysis for boosting/reciprocal abandon abuse.

**P07 gate:** simulations and fault tests show innocent teammate protection works without a trivial repeatable rank-farming exploit.

## P08 — Balott Bot

### G0801 — Seat observation firewall

Compile/runtime/test boundary that excludes hidden hands/validator state.

### G0802 — Baseline legal bot

Perfect mechanical legality, deterministic fixtures.

### G0803 — Belief/card-memory engine

Public-history inference.

### G0804 — Partner-aware imperfect-information search

Monte Carlo/information-set planning under compute budget.

### G0805 — Difficulty/style profiles

Measured profiles without cheating.

### G0806 — Bot Lab tournament harness

Immutable candidate identity, seeds, metrics, negative evidence.

### G0807 — Replacement bot qualification

Prove stand-in does not create systematic strategic advantage.

**P08 gate:** strong candidate beats baseline under frozen protocol; hidden-information and Qayd violations remain zero.

## P09 — Voice

### G0901 — Capture and push-to-command UX

Explicit microphone state and low-friction invocation.

### G0902 — Audio conditioning/VAD benchmark

Compare minimal candidate pipeline on Saudi noisy-room corpus.

### G0903 — Constrained Arabic command recognizer

Bids/cards/score vocabulary with confidence gate.

### G0904 — On-device runtime router

Device capability/model package/integrity/fallback policy.

### G0905 — Voice command gameplay integration

Voice becomes the same user command path as touch after recognition/commit semantics.

### G0906 — Voice chat

Separate WebRTC social audio with queue/tournament policy and moderation controls.

**P09 gate:** false execution rate and latency meet frozen thresholds across representative Arabic accents/devices; no silent cloud fallback.

## P10 — Replay, spectator, and Balott Live

### G1001 — Replay package

Portable event/ruleset/proof identity with deterministic playback.

### G1002 — Post-match all-hands reveal

Only after safe reveal point.

### G1003 — Spectator isolation

Dedicated delayed/safe observer projection with hidden-state leakage tests.

### G1004 — Live/broadcast surface

Score, teams, bracket, safe current state, caster tools.

### G1005 — Highlight extraction

Event-derived clips/bookmarks without changing canonical history.

### G1006 — Evidence-linked support report

Match report with automatic ledger/version/connectivity context.

**P10 gate:** replay reproduces official result exactly and spectator clients cannot obtain player-hidden state.

## P11 — Partners, teams, clubs, and rivalry

### G1101 — Preferred partner/team identity

Duo history and official team object.

### G1102 — Partner chemistry

Explainable sample-aware metrics.

### G1103 — Rivalry

Head-to-head series generated from meaningful history.

### G1104 — Club roles/teams

Bounded competitive organization model.

### G1105 — Club league/challenge

Internal standings and club-vs-club match lifecycle.

### G1106 — Scheduling/availability

Rallly/Cal.com-inspired lightweight availability flow.

**P11 gate:** a club can organize a season and players gain durable team/rivalry history without enterprise-workspace bloat.

## P12 — 152 Circuit and Tournament Director

### G1201 — Tournament manifest

Immutable rules/core/shuffle/bot/disconnect/Qayd/spectator policy identity.

### G1202 — Registration/eligibility/check-in

Player/team identity and event-specific requirements.

### G1203 — Seeding/bracket/table assignment

Deterministic auditable competition flow.

### G1204 — Referee/dispute workflow

Role-scoped adjudication with evidence.

### G1205 — Qualification engine

Skill/result-weighted points that cannot be purchased.

### G1206 — 152 Grand

Weekly flagship operational slice.

### G1207 — Masters/Major/Championship model

Monthly/seasonal/annual progression.

### G1208 — Live-event bridge

Physical venue check-in/result/broadcast integration.

**P12 gate:** a simulated end-to-end 152 event can register, qualify, run, dispute, publish, and bind trophies to Passport under one frozen manifest.

## P13 — Real Table and local/private play

### G1301 — Real Table scoring

Fast touch score/history/finalization.

### G1302 — Voice score entry

Constrained local commands optimized for physical majlis noise.

### G1303 — QR guest/participant join

Low-friction nearby table identity.

### G1304 — Real Table career binding

Clear provenance distinguishes private physical results from official online/tournament results.

### G1305 — Local/P2P prototype

Iroh/equivalent candidate for private/nearby coordination only.

### G1306 — Offline/sync conflict model

No local result can impersonate official authority.

**P13 gate:** four people can use Balott during a physical-card evening with unreliable internet and preserve honest history.

## P14 — Academy, Coach, and Ask Balott

### G1401 — Academy curriculum

Rules, score, bidding, table awareness.

### G1402 — Daily Hand

Small repeatable mastery loop.

### G1403 — Post-match Coach v1

Decision pivots using information available at the time.

### G1404 — Personal analytics

Sample-aware trends and partner/context splits.

### G1405 — Ask Balott

Structured history query + explanation layer; SQL/analytics first, retrieval/LLM only where needed.

### G1406 — Coach isolation/privacy

No active-match assistance; bounded model workers and user-data controls.

**P14 gate:** Coach improves explanation/learning in blinded evaluation without active-match access or fabricated statistics.

## P15 — Business, support, and operations

### G1501 — Cosmetics/store boundary

Store separated from game authority.

### G1502 — Balott Pro

Premium analysis/convenience scope with no competitive power.

### G1503 — Organizer/broadcast business surfaces

Commercial value for events/clubs without changing results.

### G1504 — Support console

Evidence-linked reports, privacy, role controls.

### G1505 — Notification policy

Meaningful social/competitive notifications, no fake urgency.

### G1506 — Financial/legal controls

Refunds, prizes/sponsorship, age/regulatory reviews where applicable.

**P15 gate:** monetization cannot alter shuffle, skill matching, hidden information, or official qualification.

## P16 — Public launch and championship-grade hardening

### G1601 — Security review

Auth, hidden-card leakage, admin/referee privilege, voice, supply chain.

### G1602 — Accessibility qualification

Large-card/high-contrast/reduced-motion/input/accessibility task evidence.

### G1603 — Scale/load/chaos qualification

Peak queues, match ownership, reconnect storms, tournament fanout.

### G1604 — Fairness independent review

Shuffle/verifier/rules/ranked policy review and public documentation.

### G1605 — Store/release operations

Signed builds, rollback, minimum compatible versions, incident playbook.

### G1606 — 152 operational rehearsal

Full simulated high-stakes event with support/referee/broadcast/failure drills.

### G1607 — Launch decision

Release only when required evidence is complete; distinguish `feature complete` from `release ready`.

## Milestone framing

### M0 — Playable Truth

P00–P04: deterministic correct Baloot, verified dealing, ledger, runtime, Open Table/Qayd.

### M1 — Premium Private Alpha

P05–P06: exceptional mobile table + real social home.

### M2 — Competitive Beta

P07–P09: Ranked justice, integrity, qualified Bot, voice.

### M3 — Public Balott Platform

P10–P12: Live/replay, clubs/teams, 152.

### M4 — Baloot Everywhere

P13–P15: Real Table, Coach, business/operations.

### M5 — Championship Ready

P16: security, accessibility, scale, independent fairness, operational rehearsal.

## Critical-path principle

The roadmap may be shortened by proving that a proposed component is unnecessary. It may not be shortened by skipping evidence for rules, fairness, hidden-information boundaries, reconnect, abandonment justice, or competitive authority.
