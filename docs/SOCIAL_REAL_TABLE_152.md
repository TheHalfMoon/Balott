# Social, Real Table, Live, and the 152 Circuit

**Status:** canonical planning contract

## 1. Social thesis

Balott's strongest retention should come from people, history, and competition. The product should become the place where a player's Baloot identity accumulates.

The key relationship objects are:

- Player;
- Partner;
- Team;
- Majlis;
- Club;
- Rivalry;
- Tournament participation;
- Real Table participation.

## 2. Balott Passport

Passport is the durable career surface.

Recommended sections:

- current visible rank and peak;
- season history;
- solo/partner/team context;
- matches and win/loss summaries;
- Sun/Hokum splits where statistically useful;
- partner history;
- club history;
- 152 qualification and placements;
- official/verified tournament trophies;
- Real Table record when recorded by participants/organizers;
- Fair Play/Integrity standing in user-understandable form;
- notable records such as comeback/streaks;
- replay/highlight showcase selected by the player.

Do not expose internal anti-cheat features or risk scores that help evasion.

## 3. Partner and Team

A player can mark preferred partners and form an official team.

Track relationship evidence such as:

- matches together;
- win rate with confidence/sample context;
- highest rank/152 result together;
- contract-specific performance;
- comeback rate;
- reliability;
- recent form.

### Partner Chemistry

Chemistry is an explainable derived view, not a mystical engagement score. If a single number is shown, its components must be inspectable enough to avoid misleading users.

Examples:

- experience together;
- performance relative to expected strength;
- consistency;
- contextual strengths.

Do not use private voice sentiment or unrelated social data.

## 4. Rivalries

Repeated meaningful team-vs-team history can produce a Rivalry surface:

- head-to-head record;
- recent meetings;
- biggest comeback;
- 152/tournament meetings;
- replay highlights;
- challenge/rematch.

Rivalry should emerge from actual play, not manufactured hostility. Safety controls still apply.

## 5. Majlis

A Majlis is a persistent home for a known group.

Capabilities:

- name/avatar/identity;
- owner/moderator/member roles;
- saved rules preset;
- member presence;
- `Call to Table` invitation;
- current/open table;
- voice lounge;
- recent matches;
- all-time/monthly standings;
- duo statistics;
- rivalry and record book;
- Real Table matches;
- event calendar;
- lightweight announcements.

Majlis should remain faster and more intimate than a Club.

## 6. Clubs

A Club is a structured competitive organization.

Roles may include:

- owner;
- captain;
- vice captain;
- coach;
- tournament manager;
- moderator;
- player.

Capabilities:

- multiple teams;
- internal ladder/league;
- club-vs-club challenges;
- public/private profile;
- trophies;
- training schedule;
- tryouts;
- announcements;
- private communication;
- organizer statistics;
- 152 club qualification where future rules support it.

Use fine-grained authorization patterns only as complexity justifies them; avoid enterprise IAM complexity in early consumer flows.

## 7. Scheduling and availability

Borrow the best behavior from scheduling/poll tools without building a calendar product.

Example flow:

1. captain proposes `Thursday evening`;
2. team members mark availability;
3. Balott identifies the strongest overlap;
4. captain confirms;
5. participants receive a meaningful reminder;
6. table/event opens from the schedule.

Integrations with external calendars are optional later.

## 8. Real Table

Real Table makes Balott useful around physical cards.

### V1 behavior

- create/select Majlis;
- select four players/teams;
- choose rules/scoring preset;
- fast touch score entry;
- optional voice score entry;
- undo with explicit local score history before finalization;
- record final result into participant history only with clear participant/organizer authority;
- QR join/check-in;
- share result/replay-equivalent scorecard.

### Local/private connectivity

Private Majlis experiences should explore local/LAN/P2P transport so weak internet does not destroy a nearby social session.

Important boundary:

- Ranked/official/152 remains server-authoritative;
- local/P2P mode cannot manufacture official competitive results;
- when offline/local results later sync, provenance identifies them as Real Table/private rather than official online events.

`n0-computer/iroh` is a candidate transport source for authenticated Rust P2P/QUIC patterns, subject to qualification.

### Future experiments

Only after core reliability:

- Apple Watch / wearable score companion;
- camera-assisted score/card recognition;
- venue/table display;
- tournament desk mode.

Computer vision must not become a launch dependency.

## 9. Balott Live

### Spectating

Modes:

- friend spectate when match policy permits;
- public top-match spectate;
- delayed Ranked/152 feed;
- tournament broadcast feed;
- post-match replay with all hands revealed after safe point.

The spectator pipeline must be distinct from player state so hidden information cannot leak through API/UI bugs.

### Broadcast mode

Provide organizer/caster surfaces:

- team/player cards;
- score/contract/current trick;
- bracket and standings;
- safe observer state;
- replay bookmark;
- statistics;
- sponsor placements isolated from gameplay controls.

### Highlights

Generate highlight candidates from canonical events and match context:

- comeback;
- decisive project;
- unusual score swing;
- match point;
- rivalry win;
- 152 qualification.

A highlight is a presentation of replay evidence, not a new match authority.

## 10. 152 brand architecture

`152` represents elite competition inside Balott.

Recommended naming:

- Balott 152 Daily;
- Balott 152 Grand;
- Balott 152 Masters;
- Balott 152 Major;
- Balott 152 Championship.

Use 152 sparingly so it retains prestige.

## 11. 152 Circuit

### Weekly loop

Ranked/qualifier results generate documented qualification points. A weekly `152 Grand` provides a recurring high-value event.

### Monthly loop

Top qualified teams/players enter `152 Masters`.

### Seasonal loop

Masters/Grand performance contributes to `152 Major` qualification.

### Annual loop

`152 Championship` becomes the top event, ideally online qualification leading to a live final once operational/legal/event readiness is proven.

### Competitive laws

- qualification cannot be purchased;
- raw match volume alone must not dominate skill/results;
- rules/tournament manifest frozen before event;
- anti-collusion and identity requirements increase with prize/prestige;
- sponsor money does not alter gameplay fairness;
- cash prizes/paid entry require separate Saudi legal/regulatory review before launch.

## 12. Tournament Director

For Balott-operated and approved organizer events:

- registration;
- eligibility;
- identity/check-in;
- team formation;
- seeding/draw;
- table assignment;
- match manifest;
- referee roles;
- dispute queue;
- result confirmation;
- bracket/standings;
- live/broadcast designation;
- incident/suspension workflow;
- trophy/result publication to Passport.

A physical tournament may use Balott Passport QR for check-in and identity while preserving event-specific requirements.

## 13. Notifications

Meaningful examples:

- `Faisal called you to the table.`
- `Your club match starts in 30 minutes.`
- `You qualified for 152 Grand.`
- `Al-Majd challenged your team.`
- `Tournament table changed to Table 18.`

Avoid fake urgency and unrelated store spam.

## 14. Habit without dark patterns

Balott should support different time budgets:

- 30 seconds: Daily Hand;
- 5–10 minutes: Academy/replay/highlight;
- short session: Quick Play;
- competitive session: Ranked;
- social evening: Majlis;
- scheduled commitment: club/152 event.

The goal is to make Balott consistently valuable, not to maximize involuntary screen time.
