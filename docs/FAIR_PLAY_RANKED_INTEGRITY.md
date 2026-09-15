# Fair Play, Ranked, Abandonment, and Integrity

**Status:** canonical planning contract

## 1. Trust objective

A Balott player should be able to distinguish three questions:

1. `Was the deck generated fairly?`
2. `Was the match outcome governed by the bound rules?`
3. `Was my competitive rating treatment fair given disconnects, abandonment, and integrity evidence?`

These require separate systems and separate evidence. A cryptographically fair deck does not prove fair matchmaking; a correct rules engine does not prove the absence of collusion.

## 2. The deck-never-knows-you invariant

The shuffle boundary must not receive or derive any of the following:

- rank or MMR;
- win/loss streak;
- subscription/payment state;
- store purchases;
- account age;
- engagement/retention score;
- geography beyond what is strictly required for infrastructure routing outside the shuffle boundary;
- player identity except opaque match/deal identifiers and cryptographic contributions needed by the protocol;
- predicted churn;
- preferred outcome;
- tournament narrative state.

The shuffle API should be narrow enough that violating this rule requires an explicit contract change visible in review.

## 3. Verified Deal protocol

### Goals

- unbiased digital shuffle;
- server cannot alter the deal after committing to its secret;
- players cannot predict live hidden cards;
- proof can be independently reproduced after the safe reveal point;
- protocol is versioned and bound to the match manifest.

### Candidate protocol

For each deal:

1. server generates 256-bit cryptographically secure secret `S`;
2. server publishes commitment `H(protocol_version || match_id || deal_id || S)` before collecting player entropy;
3. each seated client contributes a fresh random nonce `C_i` where supported; missing contribution uses an explicit protocol-defined fallback and is recorded, never a hidden retry;
4. final seed is derived with a cryptographic KDF/hash over `S`, ordered player contributions, deal identity, and ruleset/shuffle protocol identity;
5. a deterministic unbiased Fisher-Yates shuffle uses a cryptographic stream PRNG such as a ChaCha-family construction or an equivalently reviewed primitive;
6. live play receives only each seat's allowed cards/state;
7. the secret/proof material is revealed only when it can no longer expose live hidden information;
8. a public verifier recomputes the commitment, final seed, shuffle, and deal proof.

The exact primitive set must be frozen by an implementation specification and cryptographic review; this document freezes the behavior, not a hand-written cryptographic implementation.

### No invisible re-roll

The server must never silently reject a random shuffle because the hand is `boring`, `too strong`, `too weak`, `bad for retention`, or visually undesirable.

A protocol-level retry may occur only for an explicit technical failure defined before seeing gameplay desirability, with the failed attempt recorded.

## 4. Fairness Observatory

Balott should publish privacy-safe aggregate fairness evidence, for example:

- deals verified successfully;
- verification failures/incidents;
- card/suit/rank frequency distributions;
- seat-position distributions;
- project frequency;
- contract/deal distributions where meaningful;
- anomaly-test results;
- shuffle protocol versions in service;
- known fairness incidents and remediation.

Public dashboards must not expose individual hidden hands before safe reveal or create a tool for live cheating.

## 5. Matchmaking and rating separation

### Skill Rating

Purpose: estimate playing strength for matchmaking. Use a rating family that represents uncertainty and team outcomes (for example Glicko/TrueSkill-like ideas) after simulation and calibration.

Do not use hidden MMR as a punishment bucket.

### Rank Points

Purpose: visible seasonal progression and divisions. Rank Points may apply explicit competitive consequences such as abandon penalties, but every policy must be documented.

### Integrity Rating

Purpose: reliability and trust. Inputs may include:

- confirmed abandonment;
- repeated AFK;
- confirmed collusion/win trading;
- verified multi-account abuse;
- griefing;
- severe communication-policy violations;
- abuse of protection systems.

Integrity state may affect cooldowns, queue eligibility, review thresholds, tournament eligibility, or pairing pools. It must not become an unexplained social credit score.

## 6. Teammate abandonment protection

### Core law

> An innocent player does not lose visible rank solely because a teammate abandoned the match.

### Solo/random teammate

When player A abandons and player B is the innocent random teammate:

- B receives `RANK_PROTECTED` for the abandonment-caused loss;
- B's visible streak/promotion/qualification state is not broken solely by the abandonment;
- B may continue with a stand-in bot;
- if B wins, B receives the documented normal win treatment unless an anti-abuse policy explicitly applies;
- A receives the abandonment consequence;
- opponents receive match/win credit, while MMR/RP treatment is calibrated to avoid inflation through abandonment farming.

### Premade teammate

The default should still protect honest players from genuine partner disconnects, but repeated reciprocal abandonment patterns require abuse controls.

Possible states:

- `PROTECTED` — ordinary credible disconnect/abandonment;
- `PROVISIONALLY_PROTECTED` — result protected while repeated-pattern review is pending;
- `PROTECTION_WITHHELD_FOR_PAIR_PATTERN` — only under an explicit rule with evidence and appeal path;
- `SERVER_FAULT_VOID` — no competitive loss because Balott infrastructure failed materially.

Do not remove protection based on a single weak heuristic such as shared IP address; households and majlis naturally share networks.

## 7. Leaver treatment

A disconnect is not automatically malicious abandonment.

Distinguish:

- transient network loss;
- client crash followed by return;
- OS interruption;
- server fault;
- explicit leave action;
- timeout after no return;
- repeated pattern suggesting intentional avoidance.

The player should have a meaningful incentive to reconnect even after the grace interval begins. Do not tell a player `you are already punished, so returning no longer matters` through the policy design.

Consequences can escalate with verified pattern:

`warning -> short cooldown -> longer cooldown -> Ranked restriction -> tournament restriction/review`

The skill estimate should not be artificially crushed as punishment because that produces worse matchmaking later.

## 8. Stand-in bot

When policy activates a bot replacement:

- bot inherits the seat, hand, public match history, score, and seat-visible context;
- bot never receives other hands;
- bot strength is chosen from a frozen policy appropriate to the match/tournament;
- bot never calls Qayd;
- returning human can reclaim the seat at a safe transition according to policy;
- bot actions remain canonical match events.

## 9. Connection readiness

Before Ranked/152 queue admission, measure enough network health to warn users about obvious instability:

- round-trip latency;
- jitter;
- packet loss;
- recent reconnect instability;
- service-region health.

A warning should be useful, not punitive. Example:

`Connection unstable: 8% packet loss. Quick Play is recommended.`

Network health is not used as hidden skill manipulation.

## 10. Integrity graph

Balott should model relationships among:

- accounts;
- matches;
- teammate/opponent pairings;
- devices/installation identities under privacy policy;
- network/coarse technical signals where justified;
- abandonment events;
- protection awards;
- tournament results;
- reports and confirmed enforcement.

Use cases:

- reciprocal abandon-to-protect abuse;
- win trading;
- boosting rings;
- repeated suspicious opponent pools;
- multi-account abuse;
- impossible-information decision patterns when statistically supportable.

Graph evidence raises risk; it does not automatically prove guilt.

## 11. Impossible-information analysis

A strong anti-cheat signal may come from decisions that consistently depend on information the seat could not legally know.

This requires great care:

- evaluate large samples, not one clever play;
- compare against plausible inference from public history;
- calibrate against expert human behavior;
- preserve the exact analysis model/version;
- do not claim proof from opaque AI scoring alone;
- serious enforcement requires corroborating evidence or a documented threshold/appeal process.

The same information-boundary test used for bots can help define what information was legally observable at each event.

## 12. Voice and collusion

Open social voice can enable signaling in a 2v2 hidden-information game. Competitive policies therefore differ by queue:

- private/casual Majlis: room owner policy;
- solo Ranked: default should avoid teammate free voice that creates unequal signaling conditions;
- premade competitive: explicit symmetric policy for both teams;
- official 152 events: tournament manifest defines communication permissions.

Do not pretend automated moderation can solve strategic signaling by itself.

## 13. Tournament manifest

Every official event freezes:

- ruleset digest;
- game-core version;
- shuffle protocol/version;
- bot version/policy if stand-ins are permitted;
- disconnect/abandonment policy;
- Qayd/referee policy;
- matchmaking/seeding/bracket policy;
- qualification/ranking formula;
- spectator delay;
- client minimum compatibility version;
- event start/end and emergency suspension policy.

A live emergency defect should suspend/void/resume under a documented process rather than silently changing the rules mid-event.

## 14. Support and appeals

`Report Match` should automatically bind:

- match/deal IDs;
- ruleset/tournament manifest;
- relevant ledger range;
- connection events;
- client/server/game-core versions;
- report category;
- user-provided note/optional media when permitted.

Serious integrity enforcement should have a review/appeal path. The user should not need to manufacture screenshots of facts the platform already owns.

## 15. Privacy boundary

Anti-cheat must be proportionate. Prefer behavioral/game evidence over invasive surveillance.

Any device/network signals require documented purpose, retention, access control, and deletion policy. Do not collect unrelated contacts, microphone content, files, or location merely because anti-cheat is important.

## 16. Release evidence

Before claiming competitive fairness, prove at minimum:

- deterministic shuffle verifier fixtures;
- cryptographic commitment negative tests;
- millions of simulated deals with distribution tests appropriate to the protocol;
- replay determinism;
- rank-protection state-machine tests;
- reconnect fault injection;
- premade abuse simulations;
- bot hidden-information firewall tests;
- server-fault voiding tests;
- property tests for no player-commercial data entering shuffle inputs;
- independent review of the rules/fairness critical path.
