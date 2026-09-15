# Balott Design System Direction

This document is the authoritative design context for Impeccable and future Balott UI work. It records direction, invariants, and evaluation criteria; detailed production tokens remain subject to prototype evidence.

## Design thesis

Balott should feel like a premium Saudi competitive sport carried through a real majlis table — not a casino, not a generic gaming dashboard, and not an AI-generated fintech app with cards added afterward.

The interface has two personalities that must coexist:

- **Table mode:** quiet, physical, immediate, focused, low-chrome.
- **World mode:** competitive, social, editorial, broadcast-grade, legible.

The cards and the people are the heroes. UI furniture stays subordinate.

Balott is Arabic-first, but its visual system must be genuinely multilingual. Globalization must preserve the Saudi identity of the game while making every supported language feel intentionally designed rather than bolted on.

## Character

Keywords:

`precise` · `warm` · `confident` · `competitive` · `Saudi-native` · `tactile` · `quiet under pressure` · `broadcast-ready` · `global without losing origin`

Avoid:

`casino` · `neon arcade` · `children's game` · `fake luxury gold everywhere` · `purple AI gradient` · `glass dashboard` · `loot-box lobby`

## Visual direction: Tournament Majlis

Use the visual logic of a real playing surface combined with modern sports broadcasting:

- dark, low-glare table environment for gameplay;
- high-contrast, physically believable cards;
- restrained warm surfaces outside gameplay;
- one strong accent family for actions/status, not rainbow state coding;
- numbers and score states readable at a glance;
- Arabic typography given equal or greater design attention than Latin;
- Urdu, Persian, CJK, and Latin-Extended languages treated as design inputs, not fallback cases;
- celebratory moments feel earned and short, not slot-machine-like.

### Provisional palette roles

Do not treat these as immutable final brand hex values before visual prototyping.

- `ink` — near-black primary background/text anchor;
- `table` — deep desaturated green/charcoal playing surface, tuned for card contrast;
- `paper` — warm off-white for light surfaces and card-adjacent UI;
- `accent` — confident emerald/green family used sparingly for positive/primary state;
- `signal` — amber/red families reserved for warnings, live tournament states, Qayd/disconnect integrity events;
- `muted` — neutral gray/brown range, never blue-gray SaaS by default.

No gameplay state may depend on color alone.

## Typography

Arabic-first type must be tested on actual devices at small sizes and score-heavy layouts.

Initial open-source candidate direction:

- Arabic: IBM Plex Sans Arabic or another high-legibility Arabic family proven in prototype;
- Latin/numerals: Inter/IBM Plex Sans or a compatible family with tabular numeral support;
- Urdu/Persian/CJK: use intentional locale-appropriate families or system fallback stacks only after proving shaping, weight balance, glyph coverage, performance, and visual quality.

Requirements:

- tabular numerals for score/timers/rank movement;
- excellent Arabic punctuation and mixed Arabic/Latin handling;
- correct Urdu and Persian shaping;
- Simplified Chinese glyph coverage and readable density;
- Latin Extended support for French, Spanish, German, and Portuguese;
- no all-caps dependency for hierarchy;
- visible distinction between metadata, score, action, and player identity;
- Dynamic Type / font scaling support where the platform permits.

## Multilingual and bidirectional design

Launch-target locales are defined in `docs/LOCALIZATION_AND_GLOBALIZATION.md` and include Arabic, English, Urdu, French, Spanish, German, Simplified Chinese, Persian, and Portuguese.

### RTL

Arabic, Urdu, and Persian are first-class RTL experiences.

Do not implement RTL as a last-minute `row-reverse` pass. Each surface must decide what is linguistic direction and what is gameplay direction.

Examples:

- text flow and many navigation layouts mirror;
- directional icons mirror only when their meaning is directional;
- card order, trick positions, seat identity, dealer direction, and other game semantics do not blindly mirror if that changes game meaning;
- usernames, match IDs, URLs, hashes, room codes, and deal-verification strings require bidi isolation;
- score and timer blocks must remain stable under mixed Arabic/Latin numerals and names;
- broadcast overlays need one component architecture that supports RTL/LTR rather than separate products.

### Layout stress

Major surfaces must be reviewed in at least:

- `ar-SA` RTL;
- `en` LTR;
- `de-DE` for long Latin strings;
- `ur-PK` or `fa-IR` for non-Arabic RTL;
- `zh-Hans` for CJK density.

Do not solve localization overflow by shrinking text below accessibility thresholds. Prefer responsive composition, wrapping, adaptive grouping, and intentional truncation only where information loss is acceptable.

### Product terminology

Baloot-specific terms are cultural game objects, not ordinary UI nouns. The interface must be able to preserve authentic terms such as Sun, Hokum, Qayd, Dabl, Kahwa, and Kaboot while localizing explanation around them.

No designer should replace canonical terms merely because a direct translation looks cleaner.

## Game table hierarchy

The gameplay surface must preserve this priority:

1. own hand;
2. current trick / played cards;
3. active player/turn;
4. score and contract state;
5. player identities / connection state;
6. Qayd and critical actions;
7. optional reactions/voice presence;
8. decorative atmosphere.

Never allow avatars, gifts, ads, banners, or event promotions to compete with the hand or current trick.

## Interaction rules

### Playing a card

Open Table must allow a human to commit a catchable illegal action. Therefore the UI must not disable every card that violates follow-suit/Qayd-relevant rules.

Use an intentional but fast commit gesture consistently for all cards, such as select-then-play or drag-and-release. Do not show `illegal move` warnings in Open Table.

Training/Assisted mode may add guidance because it is explicitly a learning surface.

### Qayd

Qayd must be a deliberate human action. The UI never pre-fills `we detected a violation`. The claimant chooses the player/claim. The system validates only after the human claim.

### Voice commands

Voice command activation must be visible. Low-confidence recognition must not silently choose a high-impact action. Prefer push-to-command as the default; hands-free modes are later explicit opt-in.

A UI locale does not imply that voice command is qualified for that locale. Voice availability must be explicit per language.

### Reconnect

Connection failure should create calm, explicit state:

- reconnecting indicator;
- remaining grace policy where appropriate;
- rank-protection state when established;
- no fake spinner with no explanation.

## Motion

Motion explains physical state and competitive consequence.

Use:

- card deal/play movement;
- score transition;
- turn ownership;
- Qayd resolution;
- reconnect/rejoin;
- rank/qualification movement;
- short earned 152 victory moments.

Avoid:

- continuous ambient motion during a hand;
- reward confetti for trivial actions;
- animation that blocks the next legal action;
- long cinematic transitions between hands.

Target feel:

- ordinary interaction response: immediate, generally <= 100 ms acknowledgement;
- card/score transitions: typically 140–260 ms when readable;
- major tournament/victory moment: brief and skippable/reduced under reduced-motion preferences.

## Audio and haptics

Audio/haptics are part of the interface, not decoration.

Design a restrained physical vocabulary:

- card touch/play;
- deal cadence;
- bid/contract confirmation;
- Qayd claim/resolution;
- match point / 152 finish;
- reconnect/attention state.

No random casino jingles. Users need independent controls for music, effects, voice chat, command listening, and haptics.

## Surfaces

### Home

Primary actions should dominate:

- Play Ranked
- Quick Play
- Join/Create Majlis
- current 152 status when relevant

Presence and invitations are more valuable than promotional banners.

### Ranked

Show skill/rank state clearly, connection readiness, queue scope, and partner mode. Do not clutter with store promotions.

### Majlis

Should feel persistent and inhabited: people, current table, upcoming match, recent result, rivalry/history, voice lounge, rules preset.

### Passport

Career first: current/peak rank, partner/team, 152 history, club, Fair Play/Integrity state, major statistics, online/real-table/tournament record.

### 152

Use sports-event hierarchy: bracket, qualification, schedule, live matches, standings, teams, stories/highlights. Prestige comes from scarcity of achievement, not artificial visual gold everywhere.

### Store

The store is separate from the core play path. It must not interrupt active gameplay or imply that purchases change fairness.

## Accessibility

Release-critical requirements:

- card identity not dependent on color alone;
- high-contrast mode;
- large-card option;
- one-hand layout consideration;
- left-handed accommodation where useful;
- reduced motion;
- readable focus states;
- screen-reader-compatible non-game surfaces;
- subtitles/transcripts for broadcast/voice-dependent informational content where feasible;
- haptic + visual alternatives for audio-only state;
- localization must remain usable under large text and screen-reader settings;
- RTL, bidi, and CJK testing are part of accessibility quality, not separate polish.

## Impeccable workflow

When implementation begins:

1. initialize Impeccable project context from `PRODUCT.md`;
2. read `docs/LOCALIZATION_AND_GLOBALIZATION.md` before shaping any user-facing surface;
3. use `shape` for each major new surface before implementation;
4. prototype high-risk surfaces before locking the design system;
5. review major surfaces in Arabic RTL and the required localization stress locales before design freeze;
6. use `document` after the first coherent design system exists so tokens/components are recorded;
7. use `critique` independently after major surface work;
8. run `detect` in CI or the UI verification path when practical;
9. use Live Mode for web/admin/broadcast surfaces where supported;
10. keep app-specific `DESIGN.md` files only when a surface genuinely needs distinct rules.

Current Impeccable reference: https://impeccable.style
Source repository supplied by founder: https://github.com/pbakaus/impeccable

## Design acceptance question

Every screen should answer:

> Does this help someone play, understand, trust, organize, watch, or remember Baloot — in their supported language without losing the culture of the game — or is it merely visual noise?
