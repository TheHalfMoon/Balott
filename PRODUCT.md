# Balott Product Context

## Product statement

Balott is the definitive home of Baloot: a Saudi-born platform where people play online, gather in persistent majlis, build a competitive career, play and record real-table games, learn, watch, organize clubs, and qualify through the 152 competitive circuit.

The product is not a casino wrapper around a card game and not a feature-for-feature clone of Kammelna, VIP Baloot, or Tarbi3ah. Those products establish category expectations; Balott must win on trust, table realism, social permanence, competitive integrity, product quality, and the ability to carry Saudi Baloot culture globally without flattening it into a generic card game.

## Primary audiences

### Everyday majlis players

People who already play Baloot with friends and want the fastest, most natural digital table without clutter.

### Competitive players

Players who care about measurable skill, partner chemistry, fair matchmaking, seasons, tournaments, and a career record that means something.

### Real-table players

People who prefer physical cards but still need scoring, history, voice-assisted score entry, club/majlis records, tournament check-in, and a durable player identity.

### Clubs and organizers

Captains, community organizers, universities, companies, families, and tournament directors who need scheduling, teams, brackets, rulesets, check-in, referee tools, results, and public standings.

### Spectators and learners

People who want to watch top matches, follow friends, review replays, solve hands, and improve without using assistance during competitive play.

### Global Baloot learners and diaspora players

People who may not be fluent in Arabic but want to learn and play authentic Saudi Baloot without losing the original terminology, table culture, and competitive identity of the game.

## Core jobs

Balott must let a player:

- start a fair match quickly;
- play with real-table freedom instead of computer-assisted handholding;
- trust that the deck is not manipulated;
- trust that a bot is not reading hidden cards;
- keep rank when a random teammate abandons;
- reconnect without destroying the match;
- build a durable identity, partner history, club history, and rivalry history;
- move naturally between online and physical-table Baloot;
- enter competition that progresses from daily play to 152 events;
- understand and improve decisions after the match;
- watch meaningful games without enabling ghosting;
- organize friends without leaving Balott to coordinate everything in another app;
- use Balott naturally in a preferred supported language without receiving a reduced or second-class gameplay experience;
- learn authentic Baloot terminology even when the surrounding explanation is localized.

## Product pillars

1. **Table** — best-in-class core Baloot gameplay.
2. **Trust** — verified dealing, transparent rules, replayability, integrity controls.
3. **Career** — ranked identity, Passport, seasons, achievements, real history.
4. **People** — partners, majlis, clubs, rivals, presence, voice, scheduling.
5. **Competition** — Ranked, club leagues, 152 Circuit, official event tooling.
6. **Mastery** — replay, academy, Daily Hand, post-match Coach, bot training.
7. **Everywhere** — online, weak-network recovery, real-table mode, local/private play, spectator surfaces.
8. **Global** — Arabic-first authenticity with first-class multilingual, RTL/LTR, terminology, accessibility, and support quality.

## Globalization law

Balott is **Saudi by origin and global by quality**.

The launch-target language set is:

- Arabic (`ar-SA`);
- English (`en`);
- Urdu (`ur-PK`);
- French (`fr-FR`);
- Spanish (`es-ES`);
- German (`de-DE`);
- Simplified Chinese (`zh-Hans`);
- Persian (`fa-IR`);
- Portuguese (`pt-BR` initially, with architecture ready for `pt-PT`).

Arabic is the canonical cultural/product reference. Localization must not erase Baloot-specific concepts. Where a game term has no precise native equivalent, preserve the authentic Baloot term and localize the explanation.

Arabic, Urdu, and Persian are first-class RTL experiences. A feature that works only in English/LTR is not globally complete.

Locale must not change shuffle, rules, matchmaking skill, rank authority, tournament outcomes, or bot information boundaries. The deterministic game and match ledger remain language-neutral.

Detailed requirements live in `docs/LOCALIZATION_AND_GLOBALIZATION.md`.

## Retention philosophy

Balott should become a strong daily habit because the player has meaningful reasons to return, not because the product uses dark patterns.

The compounding loop is:

`good match -> rank/career -> partner -> team -> majlis/club -> rivalry -> 152 qualification -> live audience -> history -> return`

Healthy retention primitives include:

- friends and partners online;
- a table invitation from a real person;
- current rank and personal best;
- ongoing rivalry;
- club league commitments;
- Daily Hand and skill mastery;
- 152 qualification progress;
- permanent tournament trophies and match history.

Avoid manipulative retention primitives such as fake scarcity, forced ad gates, random reward boxes, meaningless daily login streak punishments, or monetized competitive advantage.

## Monetization law

Core Baloot, Ranked access, friends, foundational social play, and ordinary competitive eligibility must remain viable without payment.

Allowed revenue categories:

- Balott Pro convenience and advanced analysis;
- premium table/card visual themes;
- profile and club cosmetics;
- broadcast/organizer packages;
- premium Coach depth;
- optional season cosmetics;
- sponsorships and branded events that do not alter competitive outcomes.

Forbidden:

- better or worse card distribution by payment state;
- paid hidden information;
- paid MMR protection;
- paid bot strength inside competitive matches;
- paid matchmaking preference that changes competitive fairness;
- energy systems that charge to continue ordinary Ranked play;
- loot-box dependency for core progression.

## Product voice

Balott should sound confident, concise, Saudi-native, and respectful of experienced players. It should not over-explain obvious table actions. Errors should be specific and useful. Competitive outcomes should be described precisely rather than emotionally manipulated.

Localization should preserve that voice rather than translate word-for-word. Serious rule, safety, support, and tournament copy requires native review before a locale is considered release-ready.

Examples of desired product language:

- `Your rank is protected. Your teammate left the match.`
- `Connection unstable: 8% packet loss. Quick Play is recommended.`
- `Deal verification passed.`
- `Qayd claim invalid.`
- `152 Grand qualification: 38 / 50 points.`

## Non-goals for the first product era

- becoming a multi-game casino lobby;
- adding Jackaroo/Ludo/mini-games before Baloot leadership is established;
- building a general social network unrelated to Baloot;
- live AI assistance during Ranked;
- crypto/token economies;
- gambling-style paid entry mechanics without explicit legal and regulatory clearance;
- generic metaverse/3D lobby scope;
- importing every authorized source merely because permission exists;
- shipping machine-translated locales as if they were native-quality supported products;
- replacing authentic Baloot terminology with generic card-game language solely to simplify translation.

## North-star statement

> **Balott is where Baloot lives — online, in the majlis, in competition, and in your history.**
