# Balott Bot, Voice, and AI Plan

**Status:** canonical planning contract

## 1. Separation of concerns

Balott uses AI in three distinct contexts:

1. **Bot player** — makes card/bid decisions under the same hidden-information boundary as its seat.
2. **Voice runtime** — converts intentional speech into commands or social audio.
3. **Coach/Academy** — analyzes completed or explicitly training-state games.

These systems must not share privileges merely because all may use machine learning.

## 2. Bot information firewall

The production bot receives a seat observation, never the authoritative full match object.

Conceptual observation contract:

```text
BotObservation
- seat_id
- own_hand
- public_bids
- public_projects
- played_cards
- current_trick
- score
- contract
- turn_order
- legal_actions
- public_connection/stand-in state when relevant
```

Forbidden bot inputs:

- opponents' hands;
- partner hand unless a real human seat would legally know it;
- unrevealed deck order;
- hidden Qayd validator flags;
- future random state;
- anti-cheat risk scores;
- private voice/transcripts;
- client telemetry unavailable to a human seat.

Enforce this architecturally with a narrow interface and tests, not a prompt or convention.

## 3. Bot intelligence roadmap

### Layer 0 — perfect mechanical legality

- deterministic rules knowledge;
- scoring knowledge;
- legal action generation;
- never intentionally produce a catchable illegal move;
- never call Qayd.

### Layer 1 — card memory and belief state

- remember public cards/actions;
- track suit void evidence;
- update probability distributions for unseen cards;
- interpret bid/contract signals only from public action history.

### Layer 2 — partner-aware search

- expected-value reasoning;
- partner lead/support decisions;
- risk based on score/contract;
- information-set Monte Carlo search or equivalent imperfect-information planning;
- bounded compute budget appropriate to device/server role.

### Layer 3 — self-play candidate models

Train/evolve policy/value components only after a deterministic simulator and benchmark exist. A new model becomes production only if it beats the frozen benchmark without violating rules, latency, resource, reproducibility, or information-boundary gates.

Do not make `latest model` synonymous with `better bot`.

## 4. Difficulty and personalities

Difficulty should come from reasoning depth, belief quality, planning horizon, and deliberate bounded imperfections — never cheating.

Candidate profiles:

- Beginner;
- Majlis;
- Expert;
- Master;
- 152 Challenge.

Style can vary independently:

- aggressive buyer;
- conservative;
- partner-first;
- high-variance risk taker;
- patient reader.

Do not misrepresent personality randomness as human intelligence.

## 5. Replacement bot policy

A stand-in bot exists to preserve the match when a human leaves/disconnects.

Requirements:

- frozen bot version/policy for official competition;
- strength calibrated to avoid making disconnection a strategic advantage;
- only seat-visible observation;
- seamless handover back to human at a safe boundary;
- no Qayd claims;
- actions in canonical match ledger;
- clear UI that a stand-in is active.

## 6. Bot Lab

Build an offline evaluation harness around the deterministic game core.

Every bot candidate gets immutable identity:

- source revision;
- model/weights digest where applicable;
- configuration;
- ruleset;
- simulation protocol;
- random seeds;
- compute limits.

Evaluate:

- win rate under symmetric seats;
- performance by Sun/Hokum and score state;
- exploitability/challenger performance;
- rule violation count (must be zero);
- hidden-information boundary violations (must be zero);
- latency and resource use;
- deterministic/reproducible benchmark properties where expected;
- partner quality and behavior under stand-in scenarios.

Preserve losing/negative results. Do not rerun only losing seeds until a desired candidate wins.

## 7. Coach

Coach is post-match or training-only intelligence.

Possible capabilities:

- identify major decision pivots;
- compare action alternatives under the information available at the time;
- summarize repeated personal weaknesses;
- distinguish `bad outcome` from `bad decision`;
- show what was inferable then versus what became known later;
- query personal history such as `show my Hokum losses after early buys`;
- generate Daily Hand scenarios from consented/anonymized or synthetic positions.

Coach must not leak future/hidden information into an active competitive match.

## 8. Voice Command

Voice Command is an input surface, not chat.

Examples:

- Sun / Hokum / Pass / Ashkal;
- Dabl / escalation actions supported by ruleset;
- selected card names;
- Real Table score entry;
- navigation commands outside high-risk live actions.

### Local-first runtime

Preferred pipeline:

`push-to-command -> capture -> audio conditioning -> VAD -> constrained ASR/command grammar -> confidence gate -> command binding`

Use full transcription only when it improves accuracy. The command vocabulary is small enough that constrained decoding/classification may outperform generic dictation.

### Confidence policy

- high confidence + unambiguous legal command: execute under the same commit semantics as touch;
- medium confidence: show/announce bounded alternatives or require confirmation when time policy permits;
- low confidence: fail explicitly, do not guess;
- no hidden local-to-cloud fallback if local-only mode is selected.

Voice processing should be benchmarked on Saudi Arabic accents, Arabic-English code switching, background television/conversation, Bluetooth devices, cheap microphones, and low-end phones.

## 9. Voice Chat

Separate system using WebRTC-class real-time media architecture.

Requirements:

- independent mute/deafen controls;
- explicit microphone state;
- room/queue policy;
- report/block;
- moderation policy and evidence handling;
- bandwidth adaptation;
- no recording by default merely because voice exists;
- tournament communication policy bound to manifest.

Do not reuse social voice transcripts as Coach/ads/profile data without explicit product/legal consent.

## 10. Voice source candidates

High-value sources already present in the founder's TheHalfMoon source landscapes include:

- `OpenWhispr/openwhispr` — local/private cross-platform voice UX/capture patterns;
- `Starmel/OpenSuperWhisper` — lightweight local transcription/control UX;
- `debpalash/VoiceStudio` — engine registry, diagnostics, model orchestration patterns;
- `ggml-org/whisper.cpp` — portable ASR baseline;
- `k2-fsa/sherpa-onnx` — cross-platform ASR/VAD/KWS/speaker capabilities;
- `argmaxinc/argmax-oss-swift` — Apple-native speech acceleration patterns;
- `moonshine-ai/moonshine` — low-latency edge speech challenger;
- `dignifiedquire/sonora` and `tonarino/webrtc-audio-processing` — AEC/NS/AGC candidates;
- `snakers4/silero-vad` and `TEN-framework/ten-vad` — VAD candidates;
- `Rikorose/DeepFilterNet` and `xiph/rnnoise` — noise-conditioning challengers;
- `dscripka/openWakeWord` — later opt-in wake-word research.

Do not adopt all engines. Benchmark and select the smallest set that wins Balott's command latency, Arabic accuracy, battery, package size, and offline requirements.

## 11. AI runtime isolation

Heavy optional Coach/model workers must not run inside the authoritative gameplay transition process.

If a model requires custom/remote code, Python packages, dynamic download, or untrusted model artifacts:

- pin source/model revisions;
- verify digests;
- isolate the worker;
- restrict filesystem/network capability;
- bound CPU/RAM/time;
- validate outputs as untrusted;
- never let worker failure block canonical match completion.

## 12. Safety and fairness gates

Before production bot/voice claims:

- bot hidden-state access tests;
- legal-action invariant tests;
- Qayd non-participation tests;
- voice false-execution benchmarks;
- noisy-room Arabic benchmark;
- latency/device-class benchmark;
- no-silent-cloud-fallback test;
- replacement-bot advantage analysis;
- Coach active-match access denial test.
