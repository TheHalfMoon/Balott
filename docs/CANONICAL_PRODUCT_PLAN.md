# Balott Canonical Product Plan

**Status:** PLANNING_ONLY  
**Planning date:** 2026-09-15

## 1. Product thesis

Balott should not compete by accumulating a larger checklist than incumbent Baloot apps. Cutting/Qayd, AI opponents, tournaments, spectators, sessions, friends, clubs, rewards, and cross-platform play already exist in the market in some form.

Balott wins by making these systems coherent around four assets competitors cannot cheaply manufacture after the fact:

1. **trust** — verifiable dealing, explicit rules, replay evidence, bounded bots;
2. **identity** — durable career/Passport across online, real-table, and official competition;
3. **relationships** — partner, majlis, club, rivalry, history;
4. **competitive legitimacy** — ranked design, abandonment justice, integrity graph, 152 circuit, tournament manifests.

The desired category position is not `another Baloot app` but `the operating system for Baloot life`.

## 2. Product system

### Balott Play

Core digital play:

- Quick Play;
- Ranked;
- private table;
- persistent Majlis table;
- practice versus bots;
- training/assisted mode;
- reconnect-safe server state;
- Open Table rules for competitive/authentic play.

### Balott Passport

Durable identity:

- current and peak rank;
- season history;
- online matches;
- real-table records;
- tournament history;
- partner/team history;
- club membership/history;
- trophies and 152 placements;
- Fair Play / Integrity state;
- important career records and statistics.

Passport creates switching cost through earned history, not lock-in through inaccessible data. Players should be able to export a meaningful personal history.

### Balott Partner and Team

Baloot is a 2v2 relationship game. Partnering is first-class:

- add a preferred partner;
- duo rating/history distinct from solo-queue skill evidence;
- team identity and name;
- partner chemistry analysis;
- shared trophy/152 history;
- challenge/rematch another team;
- partner reliability / abandonment history used carefully and privately for integrity, not public shaming.

### Balott Majlis

A persistent social room rather than an ephemeral game lobby:

- named majlis;
- members and roles;
- saved rule preset;
- voice lounge;
- active/current table;
- invitations and `call to the table`;
- recent results;
- majlis leaderboard;
- best duos;
- rivalry history;
- monthly champion;
- physical Real Table games included in majlis history when participants choose to record them.

### Balott Clubs

Structured competitive communities:

- captain/vice-captain/moderator/coach/tournament-manager roles;
- multiple teams;
- announcements;
- internal seasons/leagues;
- scheduling and availability polls;
- club vs club challenges;
- club trophies and standings;
- tryouts and optional public recruitment;
- organizer analytics;
- private club voice/chat surfaces.

Do not turn Clubs into a general enterprise collaboration suite. Every capability must serve playing or organizing Baloot.

### Balott Real Table

Bridge physical and digital Baloot:

- fast scorekeeper;
- voice-assisted score entry;
- QR join for participants;
- saved majlis/players;
- real-table match record;
- tournament check-in;
- rule preset;
- optional local/private session support;
- later wearable companion and camera-assisted experiments only if they prove reliable.

The objective is that even people who prefer real cards still want Balott on the table.

### Balott Live

Watch Baloot:

- spectate friends where permitted;
- delayed competitive spectator feed;
- live 152 events;
- broadcast overlay;
- bracket/standings integration;
- replay timeline;
- post-match all-hands reveal;
- auto-detected highlight candidates;
- shareable clips derived from replay events, not invasive continuous screen recording.

### Balott Academy and Coach

Mastery without live cheating:

- rules lessons;
- buying/contract scenarios;
- scoring/projects training;
- Daily Hand;
- replay review;
- post-match decision analysis;
- personal weakness trends;
- Ask Balott analytical questions over the player's own history;
- strong bot challenge modes.

Coach is never available as move-selection assistance during Ranked/official live play.

### Balott 152

`152` is the prestige competitive brand inside Balott, not the product name.

Recommended structure:

- `152 Daily` — low-friction scheduled cups or qualifiers;
- `152 Grand` — flagship weekly event;
- `152 Masters` — monthly qualification target;
- `152 Major` — seasonal high-prestige event;
- `152 Championship` — annual online-to-live culmination.

Qualification should reward competitive results, not spending or raw grind volume alone.

## 3. Real-table game philosophy

### Open Table

Authentic competitive play allows human mistakes/violations that can be caught by other humans.

The digital system therefore separates:

- **action acceptance** — what was actually played on the table;
- **rules validation** — whether a human claim proves a catchable violation.

In Open Table:

- the client does not disable every Qayd-relevant illegal card;
- the system does not announce a violation automatically;
- a human claimant chooses to call Qayd;
- a time/continuation boundary closes the claim window;
- if nobody catches it in time, play continues and the missed violation does not retroactively rewrite the result;
- post-match learning may reveal missed violations without changing history.

### Assisted/Table Training

New players may choose a learning mode where invalid choices are blocked/explained. This must be visibly different from Open Table and must never leak assistance into competitive play.

## 4. Trust as product

### Verified Deal

Official play uses:

- cryptographically secure randomness;
- deterministic unbiased shuffle algorithm;
- pre-deal server commitment;
- player entropy/nonces where protocol complexity is justified;
- immutable match/deal identifiers;
- reveal only after the information can no longer affect live play;
- independently reproducible verification tool/specification;
- public statistical fairness monitoring.

Critical invariant:

> The shuffle boundary accepts no rank, subscription, spending, streak, engagement, retention, demographic, or matchmaking preference input.

### Match Ledger

Every official match is reconstructable from append-oriented canonical events such as:

`MatchCreated`, `RulesetBound`, `PlayerSeated`, `ShuffleCommitted`, `EntropySubmitted`, `CardsDealt`, `BidMade`, `CardPlayed`, `QaydClaimed`, `QaydResolved`, `Disconnected`, `StandInActivated`, `Rejoined`, `DealCompleted`, `MatchCompleted`.

Derived score, replay, spectator, support, anti-cheat, Coach, and analytics views must not silently become competing authorities.

## 5. Ranked model

Use three distinct concepts:

### Skill Rating

Hidden/technical matchmaking estimate with uncertainty. Its job is to produce fair matches, not punish behavior.

### Rank Points / visible division

Player-facing progression and season status. It may incorporate competitive outcomes and explicitly documented competitive penalties.

### Integrity Rating

Behavior/reliability signal for abandonment, confirmed abuse, collusion evidence, griefing, or other integrity events. It controls queue restrictions, review thresholds, and cooldowns; it is not a substitute for skill.

This separation prevents leaver punishment from corrupting matchmaking skill estimates.

## 6. Abandonment justice

### Random/solo teammate abandonment

If a teammate abandons and the innocent player remains eligible for protection:

- no visible rank loss for the innocent teammate;
- no streak/promotion/qualification destruction caused solely by the abandonment;
- match may continue with a bounded stand-in bot;
- if the protected player wins, award the documented win reward;
- opponents receive victory credit, with rating treatment designed to avoid inflation/farming;
- the leaver receives abandonment consequence through Rank Points/Integrity/cooldown policy, not by making the innocent player pay.

### Premade abuse

Absolute protection is exploitable if partners intentionally take turns leaving losing games. Therefore evaluate repeated pair/device/opponent patterns and hold/reduce protection only under a documented integrity rule.

Do not punish a single normal disconnect as collusion. Risk evidence accumulates; enforcement is explainable and appealable for serious actions.

## 7. Balott Bot

The bot must be strong because of better reasoning, not privileged observation.

Core design:

- perfect rules knowledge;
- legal-action generator;
- card memory from public history;
- belief state over hidden cards;
- probabilistic inference from bids/plays;
- partner-aware expected-value reasoning;
- information-set simulation/Monte Carlo search;
- later self-play policy/value models when they beat the frozen benchmark;
- difficulty through bounded reasoning strength/style, never through hidden-card access.

Rules:

- bot never intentionally commits a Qayd violation;
- bot never calls Qayd on a human;
- bot never signals a missed human violation;
- replacement bot receives only the seat-visible observation contract;
- production bot version is immutable within an official tournament manifest.

## 8. Voice

Two different products:

### Voice Command

A local-first input method for bids/cards/table commands. It should use constrained vocabulary, VAD, noise conditioning, confidence thresholds, and explicit failure rather than guessing.

### Voice Chat

A social communication system with separate privacy/moderation/ranked policies.

Never conflate command recognition with open microphone social chat.

## 9. Social graph and memory

Persistent relationships create the durable Balott network:

- friendship;
- preferred partner;
- official team;
- majlis membership;
- club membership;
- recurring opponents;
- rivalry;
- tournament participation;
- real-table participation.

Derived product experiences:

- partner chemistry;
- rivalry series;
- best partner by Sun/Hokum context;
- majlis champions;
- club history;
- `people online now` and `call to table`.

Use graph-style analysis when valuable, but do not require a graph database until query/performance evidence justifies it.

## 10. Fair monetization

The strongest long-term business is a trusted competitive/social platform, not short-term extraction.

Potential paid value:

- advanced Coach and personal analytics;
- high-quality cosmetics;
- broadcast/organizer features;
- expanded club presentation/operations;
- premium replay storage/export convenience;
- sponsorship inventory;
- optional ad-free/supporter tier if ads ever exist outside gameplay.

The store must never sit between the player and the next ordinary match.

## 11. Notification philosophy

Send events with human meaning:

- partner invited you;
- table is ready;
- club final starts soon;
- 152 qualification achieved;
- challenged by a rival team;
- tournament schedule changed;
- support/dispute resolved.

Avoid emotional spam such as `we miss you`, fake urgency, and reward-claim nags.

## 12. Metrics

North-star metrics should reward quality, not addiction mechanics:

- completed meaningful matches per active player;
- protected-abandonment fairness rate and false-protection abuse rate;
- reconnect success rate;
- verified deal proof success;
- median queue-to-first-action time;
- rematch rate after high-quality completed games;
- partner/majlis return rate;
- club match completion;
- 152 qualifier-to-event completion;
- toxic/abandonment incident rate;
- bot hidden-information violation count = zero;
- rules-engine contradiction count = zero;
- crash-free sessions and gameplay latency;
- accessibility task success.

Do not optimize total time spent independently of player value.

## 13. Launch principle

Architecture should support the full product vision, but the first public experience must be narrow and exceptional.

A feature-rich product with mediocre dealing, reconnect, rules, input latency, or table clarity loses. Core play, trust, and recovery are prerequisites for social scale.
