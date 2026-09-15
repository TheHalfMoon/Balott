# Gameplay, Rules, Open Table, and Qayd

**Status:** canonical planning contract

## 1. Rules engine objective

Balott needs a deterministic, versioned rules engine that can answer four different questions without conflating them:

1. what actions a player may physically attempt in the selected mode;
2. what actions are strictly legal under the bound ruleset;
3. whether a human Qayd claim is valid against historical hidden state;
4. how the score/result changes after the claim or normal play.

A single `isLegalMove()` UI gate is insufficient because authentic Open Table play intentionally allows some catchable violations to occur.

## 2. Ruleset identity

Every match binds an immutable `ruleset_id` and `ruleset_digest` before gameplay begins.

Rulesets must define at least:

- deal structure;
- bidding/contract sequence;
- Sun/Hokum/Ashkal behavior;
- projects and declaration timing;
- Baloot/project scoring;
- Dabl/Three/Four/Gahwa or supported escalation semantics;
- card rank/order by contract;
- follow-suit/trump obligations;
- Qayd claim types;
- Qayd claim window/closure condition;
- false-claim consequence;
- match target / completion rules;
- timeout/disconnect effects that are genuinely part of game rules rather than platform policy.

No tournament changes a ruleset in place. A change creates a new immutable version.

## 3. Modes

### Open Table

For experienced/authentic play.

- human card choices are not automatically filtered to only strict legal choices when the violation is supposed to be catchable by another human;
- the system records the attempted action and enough hidden state to later validate a claim;
- no automatic warning tells an opponent that a violation occurred;
- only human players may initiate Qayd;
- after the claim window closes, the result stands unless the ruleset explicitly defines another mechanism.

### Assisted

For onboarding/training.

- invalid choices may be disabled or explained;
- scoring assistance and rules hints are allowed;
- it must be visibly marked as Assisted;
- results must not be mixed into competitive Open Table rating pools unless the competitive rules explicitly permit that exact assistance profile.

### Tournament Open Table

Open Table plus a frozen tournament manifest. Referee workflows may exist for organizer-authorized events, but ordinary bots remain non-referees.

## 4. Human-only Qayd contract

A Qayd action contains:

- claimant player/team;
- accused player;
- target trick/action/declaration;
- claim type;
- match/deal/ruleset identity;
- timestamp/event sequence within the allowed window.

The claim API must not return a list of detected violations before the human chooses a claim.

Validation uses authoritative historical state and returns a bounded result such as:

- `VALID`;
- `INVALID`;
- `OUT_OF_WINDOW`;
- `NOT_CLAIMABLE_UNDER_RULESET`;
- `AMBIGUOUS_STATE` only when the engine genuinely cannot establish truth, which should fail closed rather than guess.

## 5. Missed means missed

If a claimable violation occurs and no human raises a valid claim before the bound claim window closes:

- gameplay continues;
- the server does not auto-correct history later;
- the result is not rewritten by post-match analysis;
- replay/Academy may label the missed event for learning after the match.

This preserves table awareness as a skill.

## 6. Bot asymmetry

Bots are intentionally different from humans:

- bot action generation includes only strictly legal actions;
- bots never intentionally create Qayd opportunities;
- bots never call Qayd;
- bots do not receive `violation_detected` flags;
- bots do not modify strategy based on hidden validator state unavailable to a human seat.

A replacement bot therefore helps finish a match without becoming an automated referee.

## 7. Input commitment

Open Table freedom must not turn touch mistakes into constant accidental violations.

Use one consistent intentional commit interaction for every card, legal or catchably illegal. Candidate patterns:

- tap to select, tap again to commit;
- drag card beyond a clear commit threshold;
- configurable fast-play gesture for advanced players after usability validation.

Do not add an `Are you sure? This is illegal` warning in Open Table.

Once a card is committed and observed by other seats, ordinary undo is forbidden unless an explicit tournament/referee recovery policy says otherwise. Undo can leak information.

## 8. Deterministic match semantics

The game core should be a pure deterministic transition function where feasible:

`new_state, emitted_events = apply(state, command, ruleset)`

Randomness is externalized through an already committed deal/shuffle result. Networking, UI, database, voice, notifications, and analytics are not allowed to decide game legality.

Benefits:

- cross-platform consistency;
- replay;
- property testing;
- bot simulation;
- server/client prediction checks;
- tournament reproducibility;
- easier independent verification.

## 9. Score authority

Score must derive from canonical deal events and the frozen ruleset. UI counters are projections.

A scoring discrepancy is therefore diagnosable by replaying the deal under the exact ruleset version rather than trusting a client snapshot.

## 10. Rules testing strategy

Required layers:

### Example fixtures

Known hands/actions/outcomes, including edge cases and official/accepted scenarios.

### Property tests

Examples:

- every dealt card appears exactly once in the deck allocation;
- no legal-state transition creates duplicate cards;
- deterministic replay yields identical state/digest;
- score totals obey ruleset invariants;
- a bot legal-action set never contains a strictly illegal action;
- Qayd validation is independent of claimant device/UI.

### Differential tests

When a trustworthy independent implementation/reference exists, compare frozen scenarios. Disagreement is an investigation signal, not automatic proof that either side is correct.

### Fuzzing

Fuzz commands/event sequences against state-machine invariants and parser boundaries.

## 11. Rules governance

Rules are culturally sensitive and can vary by table/event. Balott should distinguish:

- `Balott Official` — the platform's documented default competitive profile;
- `Tournament <version>` — organizer/federation-aligned profile when formally established;
- `Majlis Custom` — bounded private-table variants;
- `Assisted Training` — learning profile.

Never market a rule profile as the single official Saudi rulebook unless the exact authority/source establishes that claim.

## 12. Rule change process

Any change that can alter a historical match outcome is high risk:

1. new ruleset version;
2. migration/compatibility statement;
3. frozen fixtures before implementation where possible;
4. independent review;
5. Diffcipline R3 proof profile when implemented;
6. old replays remain bound to the old ruleset;
7. active official tournaments remain on their frozen manifest unless a documented emergency policy requires suspension/restart.
