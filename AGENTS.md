# Balott Agent and Engineering Rules

## Repository language

All repository-facing technical content is English: code, comments, specifications, plans, evidence, commit messages, PR bodies, issue text, agent prompts, architecture records, and source-adoption records.

The product itself is Arabic-first and Saudi-native. Arabic UI copy must be treated as product content, not as an exception to the repository language rule.

## Current authority

The repository is currently `PLANNING_ONLY`.

The canonical planning order is:

1. `README.md`
2. `PRODUCT.md`
3. `DESIGN.md`
4. `docs/CANONICAL_PRODUCT_PLAN.md`
5. subsystem plans in `docs/`
6. `docs/ROADMAP.md`
7. `docs/SPECGRAIN_EXECUTION.md`
8. provenance records in `docs/provenance/`

No product implementation is authorized merely because a feature appears in a planning document. Implementation begins only when the relevant SpecGrain leaf is shaped, bounded, dependency-eligible, and explicitly authorized.

## Non-negotiable gameplay laws

- Human Open Table play must not become auto-policed assisted play.
- Human-only Qayd: bots never call Qayd and never reveal a missed violation.
- Bots never intentionally make illegal plays and never receive hidden information unavailable to their seat.
- Ranked and official tournament state is server-authoritative.
- No rank loss is applied to an innocent teammate solely because another player abandoned.
- The shuffle system must not consume player-commercial or engagement attributes.
- No pay-to-win, paid matchmaking advantage, paid card advantage, or paid integrity advantage.
- Gameplay-affecting configuration is versioned and bound to a match/tournament manifest.
- No silent local-to-cloud voice fallback when the selected policy is local-only.

## Delivery discipline

Balott uses SpecGrain for decomposition and Diffcipline for proof-before-done.

For each implementation leaf:

1. Think — restate outcome, invariant, and user consequence.
2. Challenge — look for a smaller, safer, more testable design.
3. Bound — define in-scope/out-of-scope, dependencies, failure modes, and evidence.
4. Change — implement only the bounded surface.
5. Prove — run exact checks against the exact revision.
6. Record — preserve evidence and negative findings.

Agent self-report is never verification authority.

## Source reuse

Founder permission makes listed sources eligible for study and direct reuse. It does not make wholesale copying the default.

Before any `COPY`, `ADAPT`, `DEPEND`, or `VENDOR` action, record:

- exact repository and immutable revision;
- exact source paths;
- intended destination paths;
- public license/notices and any separate-permission basis relied upon;
- embedded third-party/model/data/asset rights;
- security and maintenance implications;
- why reuse is better than a Balott-native implementation;
- Balott-owned tests that prove the transplanted behavior.

Prefer narrow adoption behind Balott-owned contracts.

## UI discipline

Use Impeccable as the UI design discipline. `PRODUCT.md` and `DESIGN.md` are authoritative design context.

Do not ship:

- generic dashboard aesthetics;
- casino/gacha visual language;
- decorative grid backgrounds;
- purple-gradient AI defaults;
- excessive glassmorphism;
- card-inside-card nesting;
- fake urgency or manipulative countdowns;
- motion that delays gameplay or hides state;
- accessibility regressions for visual spectacle.

Game-table readability wins over decoration.

## Evidence rules

Claims such as `fair`, `faster`, `better bot`, `anti-cheat detected`, `rank protected`, `120 fps`, `accessible`, or `release ready` require evidence appropriate to the claim.

A screenshot is evidence of appearance, not correctness. A passing unit test is evidence of that unit test, not production fairness. A simulation result is evidence only for the frozen simulation protocol and exact candidate revision.

## Git discipline

- No force-push or history rewrite on shared branches.
- Keep changes bounded to the active Grain.
- Do not weaken required tests or gates to obtain green status.
- Preserve failures and negative evidence rather than rerunning until a favorable result appears without explanation.
- Gameplay/rules/fairness changes require stronger review than ordinary UI copy changes.
