# Balott Localization and Globalization Contract

**Status:** CANONICAL PRODUCT INPUT  
**Date:** 2026-09-15

Balott is Saudi-born and Arabic-first, but it is intended to become a global home for Baloot. Internationalization is therefore an architectural requirement from the first implementation grain, not a post-launch translation project.

## 1. Launch-target languages

Balott must be designed to support these launch-target languages:

| Language | Primary locale target | Direction | Notes |
| --- | --- | --- | --- |
| Arabic | `ar-SA` | RTL | Primary cultural/product reference; Saudi Baloot terminology is authoritative. |
| English | `en` | LTR | Global fallback and repository-adjacent product language. |
| Urdu | `ur-PK` | RTL | Full RTL support; terminology must be reviewed by native speakers rather than machine-translated from Arabic. |
| French | `fr-FR` | LTR | Full product localization. |
| Spanish | `es-ES` | LTR | Full product localization; architecture must permit later regional Spanish variants. |
| German | `de-DE` | LTR | Full product localization with long-string layout testing. |
| Chinese | `zh-Hans` | LTR | Simplified Chinese initial target; architecture must permit `zh-Hant` later without redesign. |
| Persian | `fa-IR` | RTL | Full RTL support; do not assume Arabic copy can be reused because the script is related. |
| Portuguese | `pt-BR` | LTR | Initial Portuguese target; architecture must permit `pt-PT` later. |

The locale list is a product requirement, not a promise that every language ships on the same calendar day. A locale is release-ready only when its product, gameplay, support, accessibility, and linguistic QA gates pass.

## 2. Product-language hierarchy

Balott must preserve three different concepts:

1. **Canonical game terminology** — Saudi Baloot concepts and rule identities.
2. **Localized explanation** — how those concepts are explained in another language.
3. **Player-facing preferred terminology** — a localized display term where one is natural and unambiguous.

Do not translate game terms mechanically.

Terms such as `Sun`, `Hokum`, `Ashkal`, `Qayd`, `Dabl`, `Kahwa`, `Kaboot`, projects, and other Baloot-specific concepts require a maintained terminology glossary. A locale may preserve the Arabic/transliterated game word while translating the explanation.

Example pattern:

```text
Qayd — rule challenge
حكم — Hokum / trump contract
صن — Sun contract
```

The exact glossary is a research and native-review artifact, not something generated once by an LLM and frozen without review.

## 3. Internationalization architecture

Implementation must satisfy the following from P00 onward:

- no user-facing copy hard-coded inside gameplay/UI components;
- locale resources are versioned and testable;
- ICU/CLDR-style plural, number, date, relative-time, and list formatting or an equivalent standards-based approach;
- message identifiers are semantic and stable enough for translation workflows;
- server protocol/game events carry semantic values, not already-localized presentation strings;
- canonical match ledger remains language-neutral;
- client localization may change without changing match authority or replay truth;
- fallback is explicit and observable;
- missing keys fail visibly in development/test rather than silently shipping mixed-language screens;
- remote translation updates may never alter rules, scoring, matchmaking, fairness, or tournament authority.

The game engine must never branch on display language except where a genuinely locale-specific input parser is required outside deterministic game truth.

## 4. RTL is a first-class layout mode

Arabic, Urdu, and Persian require full RTL support.

RTL support means more than right-aligning text:

- directional layout mirroring where semantically appropriate;
- hand/card order must follow gameplay semantics, not blind UI mirroring;
- score, timer, rank, and mixed-script numeral behavior must remain readable;
- bid/action rows must be intentionally ordered;
- icons that imply direction must mirror only when meaning requires it;
- mixed Arabic/Latin/player-name strings must be tested for bidi isolation;
- usernames, IDs, room codes, hashes, URLs, and deal-verification values need safe mixed-direction rendering;
- voice/transcript surfaces need correct punctuation and speaker layout;
- broadcast overlays must support RTL and LTR without separate product architectures.

No feature is considered UI-complete if it was tested only in English/LTR.

## 5. Layout stress testing

Every major surface must be tested against:

- Arabic RTL;
- Persian or Urdu RTL as a non-Arabic-script-language variant;
- German long strings;
- Chinese compact CJK strings;
- mixed player names and Latin IDs;
- large text/accessibility scaling.

Do not solve overflow by shrinking text below accessibility targets. Prefer responsive composition, wrapping, truncation only where loss is acceptable, and content-aware layout.

## 6. Typography and glyph coverage

The design system must choose type families/fallback stacks with proven coverage for:

- Arabic;
- Urdu-specific glyph shaping;
- Persian-specific glyph shaping;
- Latin Extended for French, Spanish, German, Portuguese;
- Simplified Chinese;
- numerals and symbols used in scoring, timers, rankings, cards, and verification.

Font decisions are implementation/design decisions and must be evaluated for license, rendering quality, device performance, and readability. Do not rely on one Latin-first typeface and assume platform fallback will produce a premium result.

## 7. Search, names, and social identity

Players may use names in any supported script.

Requirements:

- Unicode-safe storage and normalization policy;
- preserve the player's chosen display name rather than transliterating it automatically;
- search should support exact/native-script names and reasonable normalized matching;
- mention/autocomplete must be bidi-safe;
- moderation tooling must display original text and any machine-assisted translation separately;
- club/majlis names may use any supported script;
- profanity/abuse systems require locale-specific evaluation and cannot be copied from English-only filters.

## 8. Matchmaking and language

Language is not a hidden skill or engagement variable.

Default competitive matchmaking should optimize competitive quality and latency rather than fragmenting the pool by UI language.

Language may be used only through explicit player-facing preferences where justified, for example:

- voice-chat language preference;
- social/majlis discovery;
- coach/commentary language;
- tournament broadcast language.

Never manipulate opponent difficulty based on language or nationality.

## 9. Voice localization

Voice Command and Voice Chat localization are separate concerns.

### Voice Command

Each supported spoken-command locale requires its own qualified vocabulary and benchmark corpus. Do not assume related scripts or borrowed Baloot terms produce equivalent speech recognition performance.

Candidate command locales should eventually cover the launch languages where speech quality is proven, but a UI locale may ship before voice-command support for that locale.

Every locale-specific voice recognizer must test:

- native pronunciation;
- Baloot loanwords/transliterations;
- dialect/accent variation;
- code-switching with Arabic Baloot terms;
- noisy-room conditions;
- low-confidence abstention;
- destructive/high-impact command false-execution rate.

No silent cloud fallback is allowed without an explicit product/privacy policy.

### Voice Chat

Voice Chat remains ordinary human communication. Optional transcription/translation, if introduced later, must be clearly identified as machine-generated and must never become gameplay authority or Qayd evidence by itself.

## 10. Coach, Academy, and explanation quality

The Academy and AI Coach must be localized for meaning, not only words.

Requirements:

- explanations preserve the exact information available to the player at the decision time;
- rule terminology follows the locale glossary;
- examples remain valid across languages;
- generated explanations cannot invent localized rule names;
- localized Coach quality receives native-speaker evaluation before release;
- machine translation may assist production but is not final authority for rules, tournament text, safety text, or high-impact competitive explanations.

## 11. Competitive and tournament localization

Official competition requires deterministic rules independent of language.

Tournament manifests contain language-neutral policy identifiers and versioned rules. Localized tournament presentation may include:

- registration copy;
- schedules;
- bracket labels;
- referee UI;
- rules explanations;
- spectator/broadcast overlays;
- support and dispute instructions.

A translation correction must never silently change the underlying tournament rule. If localized wording materially changes interpretation, the issue is treated as a rules/documentation defect and corrected with explicit version/evidence handling.

## 12. Safety, moderation, and support

Multilingual launch requires multilingual operational readiness, not only localized buttons.

For each released locale, Balott needs an explicit plan for:

- reporting categories;
- abuse/harassment terminology;
- support articles or translated support paths;
- privacy/consent language;
- age/safety notices where applicable;
- tournament/referee communication;
- moderation translation assistance with original-text preservation.

Machine translation can help operators, but serious enforcement should not rely solely on an opaque translation where meaning is contested.

## 13. Analytics and experimentation

Locale is a diagnostic dimension, not a reason to lower product quality.

Track, with privacy-aware aggregation:

- locale adoption;
- missing/fallback strings;
- overflow/layout defects;
- crash/error rates by locale;
- voice-command accuracy by locale;
- tutorial completion by locale;
- support/report rates by locale;
- queue quality only to detect unintended fragmentation.

Do not run gameplay-affecting experiments by locale.

## 14. Impeccable design requirements

Every Impeccable-shaped major user-facing surface must be reviewed in at least:

1. `ar-SA` RTL;
2. `en` LTR;
3. one long-string Latin locale (`de-DE`);
4. one non-Arabic RTL locale (`ur-PK` or `fa-IR`);
5. `zh-Hans` where the surface is intended for global release.

Design critique must include localization as part of hierarchy, spacing, readability, and accessibility rather than as a later content pass.

## 15. Roadmap integration

Localization is cross-cutting across the existing roadmap:

- **P00:** choose i18n library/resource format, locale negotiation, pseudo-localization, bidi strategy, translation validation, and CI checks.
- **P01–P04:** keep deterministic game/rules/event identities language-neutral; create canonical terminology keys.
- **P05:** prove RTL/LTR table layouts, long-string resilience, glyph coverage, accessibility, and card/score clarity.
- **P06–P08:** multilingual names/social surfaces; bot/Passport text remains semantic/localized at presentation time.
- **P09:** benchmark voice-command locales independently.
- **P10:** multilingual replay, captions, and broadcast overlays.
- **P11–P13:** multilingual clubs, tournaments, Real Table, invitations, and QR flows.
- **P14:** localized Academy/Coach quality gates.
- **P15:** multilingual support/store/legal/notification operations.
- **P16:** localization regression matrix is part of release readiness.

No phase may claim completion for a global user-facing surface if the localization requirements applicable to that phase are knowingly broken.

## 16. Release gates per locale

A locale is `RELEASE_READY` only when applicable gates pass:

- translation completeness;
- native linguistic review;
- terminology glossary review;
- RTL/bidi review where applicable;
- layout/accessibility regression;
- input/search/name handling;
- core gameplay terminology comprehension;
- support/safety readiness;
- voice benchmark if voice command is advertised for that locale;
- no critical locale-specific crash or input defect.

It is acceptable to stage languages. It is not acceptable to label a machine-translated, unreviewed locale as fully supported.

## 17. Global product principle

> **Saudi by origin. Global by quality.**

Balott should preserve the cultural identity and vocabulary of Baloot while making the game understandable, playable, and socially natural for people around the world.

Localization must never flatten Baloot into generic card-game language. The product should teach the culture of the game while speaking the player's language.