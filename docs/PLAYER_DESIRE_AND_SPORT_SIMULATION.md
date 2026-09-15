# Balott Player Desire and Sport-Simulation Doctrine

**Status:** CANONICAL PRODUCT INPUT  
**Research date:** 2026-09-15  
**Scope:** what players actually value in Baloot, what digital products damage that value, and what Balott should learn from the FIFA -> EA SPORTS FC model without importing its exploitative patterns.

## 1. Executive conclusion

Balott must not digitize only the deck.

It must digitize the reasons people love Baloot:

- mastery;
- memory and reading;
- uncertainty without manipulation;
- partner understanding;
- social ritual;
- rivalry;
- table freedom;
- meaningful wins and losses;
- repeated play with people who become known to one another;
- a career/history that becomes part of the player's identity.

The closest useful sports-game analogy is not `Ultimate Team for Baloot`. It is the deeper lesson behind FIFA/EA SPORTS FC: the successful simulation transfers the **world around the sport** into the game — player identity, clubs, seasons, competition structure, presentation, rivalries, progression, real-world reference points, and different experiences for authentic and competitive play.

Balott should therefore become a **digital twin of Baloot culture and competition**, not a casino-style card app.

## 2. What the player evidence says

### 2.1 Baloot is loved because it is cognitively demanding

Community discussions repeatedly describe the appeal as challenge, attention, calculation, card memory, inference, fast thinking, and learning how to extract value from imperfect hands.

Observed themes:

- remembering what has been played;
- reading what cards are likely left;
- knowing when and what to buy;
- minimizing damage when the hand is poor;
- understanding a partner;
- predicting opponents;
- improving over months rather than mastering the game immediately.

This means Balott must protect its skill ceiling. Features that automatically solve table awareness, expose hidden implications, or over-assist experienced players destroy part of the product's core value.

### 2.2 Baloot is a relationship game, not merely a four-seat game

Saudi cultural reporting and player discussions consistently emphasize the same table, same partner, same group, repeated over years. Players describe social interaction, known partners, shared plans, teasing, rivalry, and weekly ritual as central to the experience.

This validates first-class product objects for:

- Partner;
- Team;
- Majlis;
- Club;
- Rivalry;
- season/history;
- Real Table.

A generic friends list is not enough.

### 2.3 Freedom and table awareness are part of the game

Player discussion treats cutting/catchable violations, Qayd, observation, and accepting a caught mistake as part of real Baloot culture. The product should not silently remove these human layers by disabling every illegal action.

This supports the existing Open Table doctrine:

> Humans play the table. Humans police the table. Bots do neither for them.

### 2.4 Players want to become better, but onboarding is genuinely difficult

New-player discussions show a recurring pattern:

1. rules feel complicated;
2. explanation alone is insufficient;
3. repeated practice is necessary;
4. existing apps can help practice but often do not explain mistakes well;
5. patient humans are still considered one of the best ways to learn.

Therefore Academy and Coach must teach progressively:

`card order -> buying -> projects -> legal play -> scoring -> escaping points -> partner reading -> opponent inference -> advanced table awareness`.

Do not dump the entire rulebook into a tutorial.

### 2.5 Good opponents and continuity make people keep playing

Positive app reviews and community comments often describe the fun of playing continuously with good players. This implies a major product opportunity beyond matchmaking:

- `Stay at Table` after a completed match;
- rematch with one tap;
- `Keep Partner` after a good solo-queue pairing;
- challenge the same opponents;
- create a Rivalry from repeated high-quality matches;
- turn a temporary group into a Majlis.

A match should be able to become a relationship.

### 2.6 Fairness perception is existential

Card-game players are extremely sensitive to perceived scripting. Public Kammelna reviews include recurring complaints that the deal appears to help a losing side or create artificial closeness, whether or not the perception is technically correct.

Balott should not answer this with marketing language. It should answer with architecture:

- Verified Deal;
- public shuffle specification;
- no engagement/rank/spend input at the shuffle boundary;
- reproducible deal verification;
- fairness observatory;
- public incident disclosure when fairness is affected.

The desired player belief is not `Balott says it is fair`.

It is:

> `Balott can prove the deck did not know who I was.`

### 2.7 Reliability is part of game feel

Slow loading, reconnect loops, inability to enter a desired match, glitches, and server failures appear repeatedly in competitor reviews. In a card game, technical friction is especially damaging because the real-world baseline is instant: four people sit down and play.

Balott must treat these as gameplay quality metrics:

- launch-to-table time;
- queue-to-first-action time;
- reconnect recovery;
- no lost match state;
- no accidental card commits;
- stable 60/120 fps presentation where device support allows;
- predictable input latency.

## 3. Motivation model: make Balott magnetic without dark patterns

The product should optimize six intrinsic reasons to return.

### Competence

`I am becoming a better Baloot player.`

Use:

- Ranked skill evidence;
- Coach;
- replay;
- Daily Hand;
- advanced stats;
- visible improvement over time.

### Autonomy

`I can play my table my way.`

Use:

- Open Table;
- Majlis rules;
- private table presets;
- multiple serious/casual contexts;
- touch and voice inputs;
- no unnecessary forced flows.

### Relatedness

`My people are here.`

Use:

- Partner;
- Majlis;
- Club;
- presence;
- call to table;
- voice;
- rivalry;
- persistent history.

### Identity

`This is my Baloot career.`

Use:

- Passport;
- peak rank;
- trophies;
- seasons;
- partner history;
- Real Table records;
- official competition history;
- shareable player card.

### Tension and uncertainty

`I do not know how this hand ends, but my decisions matter.`

Protect:

- real randomness;
- imperfect information;
- comeback possibility through skill and chance, never scripted balancing;
- meaningful Qayd/table-awareness moments.

### Ritual

`This is what we do together.`

Use:

- weekly Majlis habits;
- recurring club night;
- 152 Grand rhythm;
- persistent table identity;
- season archive;
- Real Table bridge.

## 4. The FIFA / EA SPORTS FC lesson

### 4.1 What FC actually transfers from football

EA SPORTS FC does not stop at eleven players, a ball, and football rules. Its product model translates many layers of the real sport:

| Real football layer | FC translation | Balott translation |
| --- | --- | --- |
| player identity | ratings, PlayStyles, archetypes | Passport + Balott DNA |
| unique way of playing | PlayStyles / roles | descriptive play-style profile based on real match data |
| teams | Clubs / Ultimate Team / licensed clubs | Partner, Team, Club, Majlis |
| league ladder | divisions / Rivals | Ranked divisions |
| elite competition | Champions / Playoffs | 152 Grand / Masters / Major / Championship |
| career | Player/Manager Career | persistent Balott career and season archive |
| stadium / atmosphere | stadiums, cameras, presentation | premium table, sound, haptics, Majlis/tournament presentation |
| matchday | broadcast presentation | Balott Live + rivalry/tournament presentation |
| real football data | roles, ratings, motion/data | player history, table data, official tournament records |
| social football | Clubs | Majlis + Clubs + fixed partners |
| different player intents | Competitive vs Authentic presets | Competitive Table vs Authentic Majlis |

The central lesson is **translation of meaning**, not copying UI.

### 4.2 Competitive Table and Authentic Majlis

FC 26 separates Competitive and Authentic gameplay because online competitors prioritize responsiveness/consistency while simulation players prioritize realism/immersion.

Balott should adopt the principle without splitting game truth.

#### Authentic Majlis

Optimized for the feeling of a real table:

- Open Table freedom;
- saved house-rule profile;
- natural pacing;
- generous social time;
- voice-first optional interaction;
- premium deal/card sounds and haptics;
- table themes and local presence;
- flexible rematch/team shuffle;
- Real Table continuity;
- no ranking pressure unless explicitly enabled by an organizer.

#### Competitive Table

Optimized for skill comparison and tournament integrity:

- same fundamental Baloot rules truth;
- same fair deck;
- Open Table and human-only Qayd remain intact;
- standardized official ruleset;
- fixed timers;
- verified dealing;
- stronger reconnect/integrity policy;
- spectator isolation;
- tournament manifest;
- low-latency presentation;
- no gameplay assistance.

Competitive must never mean `less fair`, and Authentic must never mean `scripted for drama`.

### 4.3 Balott DNA — the PlayStyles lesson without gameplay boosts

FC uses PlayStyles to make footballers feel distinct. Balott should make **players** distinct without granting purchased or artificial powers.

`Balott DNA` is a descriptive, evidence-derived identity layer.

Possible dimensions:

- Buy Selectivity;
- Sun Confidence;
- Hokum Confidence;
- Risk Profile;
- Card Memory / inference proxy;
- Partner Support;
- Escape Efficiency;
- Closing Performance;
- Comeback Performance;
- Qayd Awareness;
- Pace;
- Consistency.

Rules:

- no attribute changes gameplay authority;
- no purchased boosts;
- no hidden matchmaking advantage;
- sample size and uncertainty are shown;
- sensitive integrity signals remain private and separate;
- the player can hide public style fields;
- style labels are descriptive, not insulting.

Example share card:

```text
ALSHEHRI
Master II
Reader / Partner-First
Hokum 78 | Sun 71
Escape Efficiency 82
Peak #391 Saudi Arabia
152 Grand x3
```

This can become a recognizable social identity surface in the same way player cards make football identities legible — without creating Ultimate Team power economics.

### 4.4 Matchday presentation

A football game makes ordinary matches feel like events through presentation. Balott needs its own native equivalent, not stadium cosplay.

Use:

- short opponent/team introduction;
- partner and rivalry record;
- current season/rank stakes;
- elegant dealer/deal ritual;
- clean score tension;
- meaningful sound/haptic moments for Dabl/Kahwa/Kaboot/Qayd;
- end-of-match summary and pivotal moment;
- instant rematch;
- stronger broadcast layer only for 152 and official events.

Do not over-cinematicize every hand. Serious players need speed.

### 4.5 Club and season meaning

FC Clubs works because a session is attached to a persistent group, a league, and a season. Community discussion around Pro Clubs repeatedly highlights playing with friends, shared improvement, social laughter, and team identity as more enjoyable than reward grinding.

Balott should therefore make the group persistent:

`random teammate -> Keep Partner -> Team -> Majlis -> Club -> Club League -> 152`.

The player should feel that every serious match can contribute to a longer story.

## 5. What Balott must explicitly NOT copy from FIFA/FC

### Packs and randomized monetization

No purchasable chance mechanic may affect competitive play.

### Pay-for-power progression

No player card, style, cosmetic, subscription, or item changes card probability, rules, bot knowledge, matchmaking skill, or tournament qualification.

### FOMO as the main return mechanism

Do not make players schedule life around mandatory weekly chores for fear of losing rewards.

Events may be time-bound because competition requires a schedule, but missing an event must not make a player's account permanently weaker.

### Reward-first gameplay

A player should still enjoy Balott after the weekly reward threshold is complete.

If metrics show that players stop enjoying the actual match and play only to claim a reward, the loop is failing.

### Meta flattening

Do not make one optimal purchased build or one artificial playstyle dominate. Baloot's depth comes from human judgment under uncertainty.

### Perceived scripting

Never alter deal quality or opponent strength invisibly to manufacture drama, engagement, or comeback narratives.

## 6. New canonical product features from this research

### Stay at Table

After a good match:

- Rematch;
- Keep Partner;
- Shuffle Teams;
- Add to Majlis;
- Challenge Later.

The default post-match UX should preserve a good social table rather than destroy it by returning everyone to a lobby.

### Keep Partner

After solo queue, either teammate may signal `Keep Partner`. If both agree, the next match queues them as a temporary duo. Repeated mutual choice can graduate into a preferred Partner relationship.

### Balott DNA

Evidence-derived player style identity as defined above.

### Match Story

Post-match summary focused on gameplay rather than reward confetti:

- turning point;
- comeback probability swing when model confidence supports it;
- best escape;
- key partner sequence;
- Qayd moment;
- result/rank impact;
- rivalry update.

### Rivalry Night

Majalis/clubs can schedule recurring challenge nights. Rivalry history becomes a product object with head-to-head record and event archive.

### Season Archive

Every season becomes permanent history:

- rank finish;
- partner/team;
- club;
- 152 results;
- notable records;
- selected replay moments.

Do not erase identity at reset.

### Player Card / Passport Card

A shareable visual representation of real achievement and style. It is not an item and has no gameplay power.

### Table Quality Matchmaking

Matchmaking quality should eventually consider, within privacy and fairness constraints:

- skill;
- latency/region;
- party state;
- reliability/integrity;
- queue preference where population supports it.

Do not create hidden engagement matchmaking designed to manipulate win/loss emotions.

### Player Council

Create a structured feedback group representing:

- beginners;
- regular Majlis players;
- expert players;
- tournament players/referees;
- competitor-app power users;
- lapsed users;
- different Saudi regions and age groups;
- women who play card/table games;
- accessibility users.

No single loud cohort should define the entire game.

## 7. Player-research program before product assumptions harden

This desk research is directional evidence, not a substitute for direct Balott research.

### Discovery interviews

Target a diverse initial cohort. Ask players to describe their last memorable real game, not a wishlist.

Core questions:

- What makes a table enjoyable enough to keep playing?
- What makes you leave a table/app?
- What makes a partner good?
- What makes a loss feel fair?
- When do you accuse an app of scripting?
- What parts of real Baloot disappear online?
- What do apps help with that the real table does not?
- What should a bot never do?
- What does `professional Baloot` mean to you?

### Real-table observation

With explicit consent, observe real Majlis sessions and record interaction patterns rather than private conversation content:

- time from sitting to first deal;
- how people invite/replace players;
- table talk and voice commands;
- how Qayd happens;
- how disputes resolve;
- rematch/team-shuffle behavior;
- scorekeeping;
- breaks;
- celebrations/frustration;
- how experienced players teach beginners.

### Competitor diary study

Have regular users of major Baloot apps record for several days:

- why they opened the app;
- how long it took to get the match they wanted;
- whether opponent/partner quality was acceptable;
- whether they rematched;
- fairness perception;
- ad/paywall friction;
- disconnect behavior;
- whether they felt better or worse after the session.

### Prototype tests

Test behaviors before visual polish:

- Open Table accidental-vs-intentional play;
- Qayd claim flow;
- Keep Partner;
- Stay at Table;
- rank protection after abandonment;
- Verified Deal explanation;
- Balott DNA comprehension;
- voice commands in a noisy Saudi room.

### Alpha telemetry

Measure value rather than raw addiction:

- quality rematch rate;
- Keep Partner mutual acceptance;
- repeat partner rate;
- completed-match rate;
- disconnect recovery;
- fair-loss sentiment micro-survey;
- time to table;
- replay/Coach use after losses;
- voluntary return without reward prompts;
- social return through invitations.

Do not make total minutes played a standalone optimization target.

## 8. Research evidence and references

### Baloot player/culture signals

- Arab News — Baloot as a long-running Saudi social activity: https://www.arabnews.com/node/1397896/saudi%E2%80%91arabia
- Saudi gamer research — `What Drives Saudi Gamers? A Study of Gender, Genre, and Geography`: https://www.mdpi.com/2076-328X/16/2/202
- Reddit — why Baloot is challenging/social: https://www.reddit.com/r/saudiarabia/comments/owymki
- Reddit — luck vs skill, memory, teamwork, Qayd/cutting discussion: https://www.reddit.com/r/saudiarabia/comments/ov497g
- Reddit — learning difficulty and progressive mastery: https://www.reddit.com/r/saudiarabia/comments/1mtwfe1
- Reddit — learning via real people vs apps: https://www.reddit.com/r/saudiarabia/comments/u2uu0m
- Reddit — recent complaint about ads and using apps to practice prediction: https://www.reddit.com/r/saudi_gamers/comments/1uc56rz/
- Kammelna App Store reviews: https://apps.apple.com/sa/app/%D9%83%D9%85%D9%84%D9%86%D8%A7-kammelna/id537025426?see-all=reviews

### EA SPORTS FC product references

- FC 26 Gameplay Deep Dive — Competitive vs Authentic, fundamentals, community feedback: https://www.ea.com/games/ea-sports-fc/fc-26/news/pitch-notes-fc26-gameplay-deep-dive
- FC 25 Gameplay Deep Dive — FC IQ, Player Roles, real-world data, PlayStyles: https://www.ea.com/games/ea-sports-fc/fc-25/news/pitch-notes-fc-25-gameplay-deep-dive
- FC PlayStyles guide: https://help.ea.com/en/articles/ea-sports-fc/playstyles-guide/
- FC Clubs: https://www.ea.com/games/ea-sports-fc/clubs
- FC 26 Clubs Deep Dive: https://forums.ea.com/blog/ea-sports-fc-game-info-hub-en/ea-sports-fc%E2%84%A2-26--clubs-deep-dive/12400115
- Ultimate Team Rivals: https://help.ea.com/en/articles/ea-sports-fc/ultimate-team-rivals/
- FC 26 Career Mode Deep Dive: https://www.ea.com/nb/games/ea-sports-fc/fc-26/news/pitch-notes-fc26-career-mode-deep-dive

### FC community counter-evidence

These references are intentionally retained because Balott should learn what **not** to copy:

- Pro Clubs social appeal: https://www.reddit.com/r/EASportsFC/comments/154f249
- Pro Clubs fun without reward grind: https://www.reddit.com/r/EASportsFC/comments/13wc486
- Ultimate Team compulsion/grind concerns: https://www.reddit.com/r/EASportsFC/comments/ntnve8
- Rivals-for-fun versus reward optimization: https://www.reddit.com/r/EASportsFC/comments/10rvz9b

### Motivation / game research

- Social play, competence, relatedness, and enjoyment: https://www.sciencedirect.com/science/article/pii/S1875952119300370
- Persistence, self-determination, and social identity: https://www.sciencedirect.com/science/article/pii/S0747563214002684
- Feedback/rules/social interaction and game enjoyment: https://doi.org/10.1016/j.chb.2017.03.048
- 2026 flow/retention study: https://pmc.ncbi.nlm.nih.gov/articles/PMC13455236/

## 9. Canonical decision

Balott's retention hierarchy is:

```text
PLAY QUALITY
  -> MASTERY
  -> PARTNER / MAJLIS RELATIONSHIPS
  -> IDENTITY AND HISTORY
  -> MEANINGFUL COMPETITION
  -> SPECTACLE / CONTENT
  -> COSMETIC / COMMERCIAL LAYERS
```

Never invert this hierarchy.

If cosmetics, rewards, content cadence, or monetization are carrying retention because the actual table is no longer enjoyable, Balott has failed its product thesis.

The target behavior is not:

> `I need to log in or I lose a reward.`

It is:

> `The guys are on Balott. We have a table, a rivalry, and a match that matters.`
