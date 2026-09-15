# AI Baloot and Sports-Simulation Reference Addendum

**Reviewed:** 2026-09-15  
**Status:** research/provenance addendum

This document adds exact AI-Baloot and sports-simulation references discovered after the initial Balott planning package. A reference is not an adoption decision.

## AI Baloot references

| Reference | URL / identity | Classification | Why it matters to Balott |
| --- | --- | --- | --- |
| Baloot - AI (iOS) | https://apps.apple.com/us/app/baloot-ai/id6760992309 | PRODUCT_REFERENCE | Hard mode publicly describes Monte Carlo simulation, card tracking, opponent-void detection, partner-signal reading, probability-based decisions, offline play, realistic animations/haptics |
| Baloot AI - بلوت (Android) | https://play.google.com/store/apps/details?id=com.balootai.baloot_ai | PRODUCT_REFERENCE | separate Android product reference advertising adaptive AI, difficulty levels, stats, tutorial/hints, local/offline privacy posture |
| Hakim / AIBaloot | https://github.com/osos3lom/AIBaloot | HIGH_VALUE_SOURCE_CANDIDATE | Baloot-specific open research/code source spanning card vision and a stated broader architecture of rules engine, search/self-play agent, Arabic Coach, and physical-table computer vision |
| Hakim observed revision | `a167a09ab2a390d84a1f14a6f8320e1c84b92794` | IMMUTABLE_RESEARCH_SNAPSHOT | observed `master` revision during this research pass; reverify before adoption |
| Hakim observed license | MIT at repository metadata on 2026-09-15 | PUBLIC_LICENSE_SIGNAL | exact path/embedded asset/model terms still require implementation-time qualification |
| ElBlot PAL AI | https://www.elblot.com/ | PRODUCT_REFERENCE | live Baloot product with AI difficulty/model concepts; useful competitive behavior reference |

### Hakim-specific adoption interest

High-value areas to study independently:

- authoritative Baloot rules/scoring engine direction;
- information-set search / self-play research direction;
- frozen bot evaluation fixtures;
- Arabic post-match Coach concepts;
- card-detection / synthetic-data pipeline for later Real Table experiments;
- CoreML/TFLite/ONNX edge inference patterns when physical-table vision becomes justified.

Do **not** copy Hakim wholesale. Balott already has canonical constraints that remain authoritative:

- server authority for official digital competition;
- human-only Qayd;
- bots never intentionally commit catchable violations;
- bots never consume privileged hidden-card state;
- AI Coach never assists active Ranked/official play;
- card vision is a later Real Table research leaf, not a launch dependency.

## EA SPORTS FC / FIFA product references

These are behavior/product references. They do not imply access to EA source code or brand/asset rights.

| Reference | URL | Balott lesson |
| --- | --- | --- |
| FC 26 Gameplay Deep Dive | https://www.ea.com/games/ea-sports-fc/fc-26/news/pitch-notes-fc26-gameplay-deep-dive | separate Competitive and Authentic tuning; fundamentals before feature count; community feedback loop |
| FC 25 Gameplay Deep Dive | https://www.ea.com/games/ea-sports-fc/fc-25/news/pitch-notes-fc-25-gameplay-deep-dive | real-world data, roles, tactics, player differentiation |
| FC PlayStyles guide | https://help.ea.com/en/articles/ea-sports-fc/playstyles-guide/ | make participants legibly unique; Balott adapts this as non-power `Balott DNA` |
| FC Clubs | https://www.ea.com/games/ea-sports-fc/clubs | persistent social team identity, seasons, stats, leaderboards, public club identity |
| FC 26 Clubs Deep Dive | https://forums.ea.com/blog/ea-sports-fc-game-info-hub-en/ea-sports-fc%E2%84%A2-26--clubs-deep-dive/12400115 | group progression, live events, lobby state, multiple persistent clubs |
| Ultimate Team Rivals | https://help.ea.com/en/articles/ea-sports-fc/ultimate-team-rivals/ | visible ladder, divisions, checkpoints, seasonal competitive rhythm |
| FC Career Mode Deep Dive | https://www.ea.com/nb/games/ea-sports-fc/fc-26/news/pitch-notes-fc26-career-mode-deep-dive | long-term personal story, identity, progression, authentic simulation |

## Community research references

These are qualitative signals, not representative population estimates.

### Baloot

- https://www.reddit.com/r/saudiarabia/comments/owymki — challenge, calculation, focus, social play.
- https://www.reddit.com/r/saudiarabia/comments/ov497g — memory, teamwork, skill/luck balance, cutting/Qayd culture.
- https://www.reddit.com/r/saudiarabia/comments/1mtwfe1 — learning difficulty and need for patient practice.
- https://www.reddit.com/r/saudiarabia/comments/u2uu0m — real-table teaching versus app practice.
- https://www.reddit.com/r/saudi_gamers/comments/1uc56rz/ — recent ad frustration and use of apps to practice card prediction.
- https://apps.apple.com/sa/app/%D9%83%D9%85%D9%84%D9%86%D8%A7-kammelna/id537025426?see-all=reviews — competitor friction, fairness perception, reliability, continuous-play signals.
- https://www.arabnews.com/node/1397896/saudi%E2%80%91arabia — long-running partner/majlis/social ritual evidence.

### EA SPORTS FC

- https://www.reddit.com/r/EASportsFC/comments/154f249 — Pro Clubs social/friend appeal and persistent team meaning.
- https://www.reddit.com/r/EASportsFC/comments/13wc486 — play-for-fun/social-team value versus reward grind.
- https://www.reddit.com/r/EASportsFC/comments/ntnve8 — community concern about compulsive pack/objective grind.
- https://www.reddit.com/r/EASportsFC/comments/10rvz9b — enjoyment when playing the sport rather than optimizing rewards.

## Research references

- Saudi gaming/localization/card-game context: https://www.mdpi.com/2076-328X/16/2/202
- Social multiplayer, competence/relatedness and enjoyment: https://www.sciencedirect.com/science/article/pii/S1875952119300370
- Persistence, self-determination and social identity: https://www.sciencedirect.com/science/article/pii/S0747563214002684
- Feedback/rules/social interaction and enjoyment: https://doi.org/10.1016/j.chb.2017.03.048
- 2026 competence/flow/continuance study: https://pmc.ncbi.nlm.nih.gov/articles/PMC13455236/

## Adoption law

For source-code projects, founder permission makes direct reuse eligible but does not replace exact-revision/path/license/third-party/security qualification.

For products where source bytes are unavailable, product observation remains `REFERENCE` only. Permission does not create source bytes, brand rights, assets, models, or third-party rights that are not actually available to Balott.
