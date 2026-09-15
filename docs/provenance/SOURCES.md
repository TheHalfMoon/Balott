# Balott Source, Donor, and Reference Registry

**Planning snapshot:** 2026-09-15  
**Purpose:** preserve every source family discussed during Balott shaping, plus the relevant TheHalfMoon source landscapes that may materially help Balott.

A listing is not an implementation dependency. Direct adoption follows `SOURCE_USE_AUTHORIZATION.md` and exact-path/revision qualification.

## Classification

- `CORE_METHOD` — delivery/design method used by Balott.
- `COMPETITOR_REFERENCE` — product/market behavior reference; source code may not be available.
- `HIGH_VALUE_CANDIDATE` — likely worth direct qualification for a bounded subsystem.
- `REFERENCE_CANDIDATE` — useful patterns; native Balott implementation may be better.
- `LANDSCAPE_ONLY` — preserved because it was part of the reviewed source landscape, but not currently justified for Balott runtime.
- `DEFER` — later use only after a concrete need.

## A. Core method and design sources

| Source | URL | Classification | Balott role |
| --- | --- | --- | --- |
| SpecGrain | https://github.com/TheHalfMoon/SpecGrain | CORE_METHOD | recursive specs, bounded WorkPackets, independent evidence |
| Diffcipline | https://github.com/TheHalfMoon/Diffcipline | CORE_METHOD | proof-before-done, exact diff/risk/verification discipline |
| Impeccable | https://github.com/pbakaus/impeccable | CORE_METHOD | UI direction, critique, design-system/detector workflow |
| Impeccable docs | https://impeccable.style | CORE_METHOD | current design workflow/reference |
| GitHub Spec Kit | https://github.com/github/spec-kit | REFERENCE_CANDIDATE | optional spec workflow reference/import path; SpecGrain is selected |

## B. Baloot competitors and behavior references

| Source | URL | Classification | Why tracked |
| --- | --- | --- | --- |
| Kammelna | https://www.kammelna.com | COMPETITOR_REFERENCE | category incumbent, cutting/Qayd, sessions, tournaments, AI, cross-platform |
| Kammelna Google Play | https://play.google.com/store/apps/details?id=com.remalit.kammelna | COMPETITOR_REFERENCE | current public feature/subscription evidence |
| Kammelna App Store | https://apps.apple.com/sa/app/id537025426 | COMPETITOR_REFERENCE | current releases/event/spectator evidence |
| VIP Baloot | https://play.google.com/store/apps/details?id=co.tamatem.vipbaloot | COMPETITOR_REFERENCE | large social/team/event competitor |
| VIP Baloot App Store | https://apps.apple.com/sa/app/id1136146687 | COMPETITOR_REFERENCE | current release/product evidence |
| Tarbi3ah Baloot | https://apps.apple.com/sa/app/id1461692005 | COMPETITOR_REFERENCE | clubs, public club tournaments, rewards/mini-game density |
| Tarbi3ah Google Play | https://play.google.com/store/apps/details?id=com.badambiz.saubaloot | COMPETITOR_REFERENCE | current Android feature evidence |
| Baloot Majlis | https://apps.apple.com/sa/app/id6777370876 | COMPETITOR_REFERENCE | fairness/product reference |
| Baloot Royale | https://apps.apple.com/sa/app/id1407214532 | COMPETITOR_REFERENCE | market naming/product reference |
| Baloot Pro | https://play.google.com/store/apps/details?id=com.balootpro.app | COMPETITOR_REFERENCE | market/product reference |
| ElBlot | https://www.elblot.com | COMPETITOR_REFERENCE | rules/fairness reference |
| Balotk | https://balotk.com | COMPETITOR_REFERENCE | multi-game/product reference |
| Kaboot Games | https://kabootgames.com | COMPETITOR_REFERENCE | market/name reference |
| Saudi Press Agency Baloot reporting | https://www.spa.gov.sa/N2622884 | COMPETITOR_REFERENCE | organized competition ecosystem |
| SPA tournament regulation/referee reporting | https://www.spa.gov.sa/N2495561 | COMPETITOR_REFERENCE | real-event rules/referees/camera adjudication reference |

Additional named product references from shaping that require exact live/source identity before code adoption: Sakka Baloot, Hakam Al Sakkah, and Baloot AI.

## C. Voice, audio, local AI, and bot-adjacent candidates

| Source | URL | Classification | Candidate role |
| --- | --- | --- | --- |
| Meetily | https://github.com/Zackriya-Solutions/meetily | HIGH_VALUE_CANDIDATE | capture/lifecycle/local speech integration patterns |
| Anarlog | https://github.com/fastrepl/anarlog | REFERENCE_CANDIDATE | modular Rust/local/mobile/watch/CLI patterns |
| OpenWhispr | https://github.com/OpenWhispr/openwhispr | HIGH_VALUE_CANDIDATE | cross-platform local/private voice UX/capture |
| OpenSuperWhisper | https://github.com/Starmel/OpenSuperWhisper | HIGH_VALUE_CANDIDATE | lightweight local transcription/control UX |
| VoiceStudio | https://github.com/debpalash/VoiceStudio | HIGH_VALUE_CANDIDATE | engine registry, diagnostics, model orchestration |
| whisper.cpp | https://github.com/ggml-org/whisper.cpp | HIGH_VALUE_CANDIDATE | portable local ASR baseline |
| sherpa-onnx | https://github.com/k2-fsa/sherpa-onnx | HIGH_VALUE_CANDIDATE | ASR/VAD/KWS/speaker runtime |
| Argmax OSS Swift | https://github.com/argmaxinc/argmax-oss-swift | HIGH_VALUE_CANDIDATE | Apple-native speech acceleration |
| Moonshine | https://github.com/moonshine-ai/moonshine | REFERENCE_CANDIDATE | low-latency edge speech challenger |
| Sonora | https://github.com/dignifiedquire/sonora | HIGH_VALUE_CANDIDATE | Rust-oriented AEC/NS/AGC |
| WebRTC Audio Processing wrapper | https://github.com/tonarino/webrtc-audio-processing | HIGH_VALUE_CANDIDATE | mature audio conditioning baseline |
| Silero VAD | https://github.com/snakers4/silero-vad | HIGH_VALUE_CANDIDATE | VAD baseline |
| TEN VAD | https://github.com/TEN-framework/ten-vad | HIGH_VALUE_CANDIDATE | low-latency VAD challenger |
| DeepFilterNet | https://github.com/Rikorose/DeepFilterNet | REFERENCE_CANDIDATE | neural noise suppression |
| RNNoise | https://github.com/xiph/rnnoise | REFERENCE_CANDIDATE | lightweight noise suppression |
| NeMo-Speech.cpp | https://github.com/NVIDIA/NeMo-Speech.cpp | REFERENCE_CANDIDATE | native speech challenger |
| NVIDIA NeMo Speech | https://github.com/NVIDIA-NeMo/Speech | DEFER | heavyweight speech/model research |
| pyannote-audio | https://github.com/pyannote/pyannote-audio | DEFER | diarization research if social voice needs it |
| MOSS Transcribe+Diarize | https://github.com/OpenMOSS/MOSS-Transcribe-Diarize | DEFER | joint ASR/diarization research |
| Omnilingual ASR | https://github.com/facebookresearch/omnilingual-asr | DEFER | Arabic/multilingual benchmark challenger |
| Omi medical STT runtime | https://github.com/Omi-Health/omi-med-stt-runtime | LANDSCAPE_ONLY | inherited Himsat source; no current Balott need |
| Google MedASR | https://github.com/Google-Health/medasr | LANDSCAPE_ONLY | inherited Himsat source; no current Balott need |
| openWakeWord | https://github.com/dscripka/openWakeWord | DEFER | later opt-in hands-free wake-word research |
| mistral.rs | https://github.com/EricLBuehler/mistral.rs | DEFER | local Coach/model runtime candidate |
| llama.cpp | https://github.com/ggml-org/llama.cpp | DEFER | local Coach/model runtime candidate |
| fastembed-rs | https://github.com/Anush008/fastembed-rs | DEFER | local embeddings for private history search |
| thewh1teagle/vibe | https://github.com/thewh1teagle/vibe | REFERENCE_CANDIDATE | local transcription job/model lifecycle patterns |

## D. Local transport, storage, sandbox, and execution candidates

| Source | URL | Classification | Candidate role |
| --- | --- | --- | --- |
| Iroh | https://github.com/n0-computer/iroh | HIGH_VALUE_CANDIDATE | private/local Majlis P2P/QUIC prototype |
| SQLCipher | https://github.com/sqlcipher/sqlcipher | REFERENCE_CANDIDATE | local encrypted storage where needed |
| sqlite-vec | https://github.com/asg017/sqlite-vec | DEFER | local vector search for Coach/history |
| Extism | https://github.com/extism/extism | DEFER | bounded Wasm extension/model tooling |
| Wasmtime | https://github.com/bytecodealliance/wasmtime | DEFER | lower-level Wasm isolation runtime |
| OpenSandbox | https://github.com/opensandbox-group/OpenSandbox | DEFER | isolated AI/tool evaluation workers, not core gameplay |
| LocalStack | https://github.com/localstack/localstack | REFERENCE_CANDIDATE | local integration testing patterns |

## E. Analytics, observability, identity, authorization, and support

| Source | URL | Classification | Candidate role |
| --- | --- | --- | --- |
| PostHog | https://github.com/PostHog/posthog | REFERENCE_CANDIDATE | analytics/event taxonomy patterns |
| Apache Superset | https://github.com/apache/superset | REFERENCE_CANDIDATE | operations/fairness dashboard patterns |
| Umami | https://github.com/umami-software/umami | REFERENCE_CANDIDATE | privacy-aware analytics patterns |
| Nao | https://github.com/getnao/nao | REFERENCE_CANDIDATE | analytics/data interaction reference |
| OpenTelemetry Collector | https://github.com/open-telemetry/opentelemetry-collector | HIGH_VALUE_CANDIDATE | observability standard/runtime |
| Prometheus | https://github.com/prometheus/prometheus | REFERENCE_CANDIDATE | metrics/alerting patterns |
| SigLens | https://github.com/siglens/siglens | DEFER | telemetry/search landscape |
| Uptime Kuma | https://github.com/louislam/uptime-kuma | LANDSCAPE_ONLY | service monitoring reference |
| Checkmate | https://github.com/bluewave-labs/Checkmate | LANDSCAPE_ONLY | monitoring landscape |
| ZITADEL | https://github.com/zitadel/zitadel | REFERENCE_CANDIDATE | identity/OIDC patterns |
| Keycloak | https://github.com/keycloak/keycloak | REFERENCE_CANDIDATE | identity/OIDC patterns |
| OpenFGA | https://github.com/openfga/openfga | REFERENCE_CANDIDATE | fine-grained organizer/club auth patterns |
| Open Policy Agent | https://github.com/open-policy-agent/opa | REFERENCE_CANDIDATE | policy authorization patterns |
| Infisical | https://github.com/Infisical/infisical | REFERENCE_CANDIDATE | secret management patterns |
| Papercups | https://github.com/papercups-io/papercups | REFERENCE_CANDIDATE | evidence-linked support UX patterns |
| Chatwoot | https://github.com/chatwoot/chatwoot | REFERENCE_CANDIDATE | player support/operations patterns |
| Zammad | https://github.com/zammad/zammad | REFERENCE_CANDIDATE | support workflow patterns |
| Chaskiq | https://github.com/chaskiq/chaskiq | LANDSCAPE_ONLY | support/messaging landscape |
| UVDesk | https://github.com/uvdesk | LANDSCAPE_ONLY | support landscape |
| Peppermint | https://github.com/Peppermint-Lab/peppermint | REFERENCE_CANDIDATE | support/ticket patterns |
| Flagsmith | https://github.com/Flagsmith/flagsmith | REFERENCE_CANDIDATE | non-gameplay feature flag patterns; gameplay config must remain manifest-bound |

## F. Collaboration, clubs, scheduling, and community references

| Source | URL | Classification | Candidate role |
| --- | --- | --- | --- |
| Huly Platform | https://github.com/hcengineering/platform | REFERENCE_CANDIDATE | structured club/team collaboration patterns |
| Mattermost | https://github.com/mattermost/mattermost | REFERENCE_CANDIDATE | team communication/moderation patterns |
| Element | https://github.com/element-hq | REFERENCE_CANDIDATE | real-time community/messaging patterns |
| Zulip | https://github.com/zulip/zulip | REFERENCE_CANDIDATE | structured conversation patterns |
| Outline | https://github.com/outline/outline | LANDSCAPE_ONLY | knowledge/community UX reference |
| AppFlowy | https://github.com/AppFlowy-IO/AppFlowy | REFERENCE_CANDIDATE | local-first collaborative UX patterns |
| AFFiNE | https://github.com/toeverything/AFFiNE | REFERENCE_CANDIDATE | persistent workspace/memory UX patterns |
| Block Buzz | https://github.com/block/buzz | REFERENCE_CANDIDATE | communication/audio/product patterns |
| Cal.com organization | https://github.com/calcom | REFERENCE_CANDIDATE | scheduling patterns |
| Rallly | https://github.com/lukevella/rallly | HIGH_VALUE_CANDIDATE | simple availability poll behavior |
| Flarum | https://github.com/flarum | LANDSCAPE_ONLY | community/forum patterns |
| HumHub | https://github.com/humhub/humhub | LANDSCAPE_ONLY | social/community landscape |

## G. Search, context, graph, and Coach-query references

| Source | URL | Classification | Candidate role |
| --- | --- | --- | --- |
| OpenRAG | https://github.com/langflow-ai/openrag | DEFER | later Coach/retrieval architecture reference |
| Onyx | https://github.com/onyx-dot-app/onyx | DEFER | enterprise retrieval/search reference |
| AnythingLLM | https://github.com/Mintplex-Labs/anything-llm | DEFER | local knowledge/LLM UX reference |
| Graphify | https://github.com/Graphify-Labs/graphify | REFERENCE_CANDIDATE | graph/context patterns for integrity/social analysis |
| code-graph-rag | https://github.com/vitali87/code-graph-rag | LANDSCAPE_ONLY | graph/RAG reference; not a game-runtime dependency |
| Meilisearch | https://github.com/meilisearch/meilisearch | REFERENCE_CANDIDATE | player/event/search UX if PostgreSQL search is insufficient |

## H. Workflow/rules/organization references

| Source | URL | Classification | Candidate role |
| --- | --- | --- | --- |
| Temporal | https://github.com/temporalio/temporal | DEFER | durable tournament/operations workflow reference |
| Flowable | https://github.com/flowable/flowable-engine | LANDSCAPE_ONLY | workflow landscape |
| Activepieces | https://github.com/activepieces/activepieces | LANDSCAPE_ONLY | automation/integration landscape |
| Apache Camel | https://github.com/apache/camel | LANDSCAPE_ONLY | integration patterns |
| Debezium | https://github.com/debezium/debezium | DEFER | CDC/event infrastructure if scale justifies it |
| GoRules | https://github.com/gorules | REFERENCE_CANDIDATE | rules/policy engine ideas; Balott core rules remain Balott-owned |
| Pretix | https://github.com/pretix/pretix | REFERENCE_CANDIDATE | physical tournament ticket/check-in/event patterns |
| Attendize | https://github.com/Attendize/Attendize | LANDSCAPE_ONLY | event management reference |
| Plane | https://github.com/makeplane/plane | LANDSCAPE_ONLY | planning/admin UX reference |
| OpenProject | https://github.com/opf/openproject | LANDSCAPE_ONLY | operations/planning landscape |
| Kanboard | https://github.com/kanboard/kanboard | LANDSCAPE_ONLY | operations landscape |
| Taiga | https://github.com/taigaio | LANDSCAPE_ONLY | planning landscape |
| Backstage | https://github.com/backstage/backstage | LANDSCAPE_ONLY | internal developer platform reference |
| NetBox | https://github.com/netbox-community/netbox | LANDSCAPE_ONLY | infrastructure/source landscape |
| GLPI | https://github.com/glpi-project/glpi | LANDSCAPE_ONLY | support/operations landscape |
| Frappe Helpdesk | https://github.com/frappe/helpdesk | LANDSCAPE_ONLY | support landscape |
| LiveHelperChat | https://github.com/LiveHelperChat/livehelperchat | LANDSCAPE_ONLY | support landscape |

## I. Enterprise/admin/form/document landscape inherited from TheHalfMoon research

These sources were part of the reviewed Zyara/Qdrat landscape and are preserved because future tournament/club/admin needs may surface. They are not current Balott runtime recommendations.

| Source | URL | Classification |
| --- | --- | --- |
| Horilla HR | https://github.com/horilla-opensource/horilla | LANDSCAPE_ONLY |
| Odoo | https://github.com/odoo/odoo | LANDSCAPE_ONLY |
| Baserow | https://github.com/bramw/baserow | LANDSCAPE_ONLY |
| EspoCRM | https://github.com/espocrm/espocrm | LANDSCAPE_ONLY |
| Erugo | https://github.com/ErugoOSS/Erugo | LANDSCAPE_ONLY |
| Listmonk | https://github.com/knadh/listmonk | LANDSCAPE_ONLY |
| Kroki | https://github.com/yuzutech/kroki | LANDSCAPE_ONLY |
| Documenso | https://github.com/documenso/documenso | LANDSCAPE_ONLY |
| PostGIS | https://github.com/postgis/postgis | LANDSCAPE_ONLY |
| Label Studio | https://github.com/HumanSignal/label-studio | REFERENCE_CANDIDATE |
| Formbricks | https://github.com/formbricks/formbricks | REFERENCE_CANDIDATE |
| Paperless-ngx | https://github.com/paperless-ngx/paperless-ngx | LANDSCAPE_ONLY |
| Mautic | https://github.com/mautic | LANDSCAPE_ONLY |
| Strapi | https://github.com/strapi/strapi | LANDSCAPE_ONLY |
| Hasura | https://github.com/hasura | LANDSCAPE_ONLY |
| BigCapital | https://github.com/bigcapitalhq/bigcapital | LANDSCAPE_ONLY |
| Corteza | https://github.com/cortezaproject/corteza | LANDSCAPE_ONLY |
| MiroTalk | https://github.com/miroslavpejic85/mirotalk | REFERENCE_CANDIDATE |
| Stirling PDF | https://github.com/Stirling-Tools/Stirling-PDF | LANDSCAPE_ONLY |
| Frappe HRMS | https://github.com/frappe/hrms | LANDSCAPE_ONLY |
| Snipe-IT | https://github.com/snipe/snipe-it | LANDSCAPE_ONLY |
| Teable | https://github.com/teableio/teable | LANDSCAPE_ONLY |
| Gotenberg | https://github.com/gotenberg/gotenberg | LANDSCAPE_ONLY |
| Akaunting | https://github.com/akaunting/akaunting | LANDSCAPE_ONLY |
| Grist Core | https://github.com/gristlabs/grist-core | LANDSCAPE_ONLY |
| Geta organization | https://github.com/Geta | LANDSCAPE_ONLY |
| BookStack | https://github.com/BookStackApp/BookStack | LANDSCAPE_ONLY |
| Frappe Framework | https://github.com/frappe/frappe | LANDSCAPE_ONLY |
| Munder Difflin | https://github.com/chaitanyagiri/munder-difflin | DEFER |
| fullstack-agent | https://github.com/jaredrhod/fullstack-agent | DEFER |

## J. Document/publishing sources mentioned during cross-project source review

Not currently needed for core Balott, but preserved because they were explicitly discussed and may help organizer/report/export surfaces later.

| Source | URL | Classification |
| --- | --- | --- |
| Typst | https://github.com/typst/typst | DEFER |
| docx-rs | https://github.com/bokuweb/docx-rs | DEFER |
| tokimo-package-fileparser | https://github.com/tokimo-lab/tokimo-package-fileparser | LANDSCAPE_ONLY |
| MarkItDown | https://github.com/microsoft/markitdown | LANDSCAPE_ONLY |
| Docling | https://github.com/docling-project/docling | LANDSCAPE_ONLY |
| docling-core | https://github.com/DS4SD/docling-core | LANDSCAPE_ONLY |
| Xberg | https://github.com/xberg-io/xberg | LANDSCAPE_ONLY |
| Kreuzberg LTS | https://github.com/kreuzberg-dev/kreuzberg-lts | LANDSCAPE_ONLY |
| MinerU | https://github.com/opendatalab/MinerU | LANDSCAPE_ONLY |
| Screenpipe | https://github.com/screenpipe/screenpipe | LANDSCAPE_ONLY |

## Adoption priority

Balott should not import this landscape wholesale.

Initial direct qualification priority is deliberately small:

1. SpecGrain / Diffcipline / Impeccable as development methods;
2. voice candidates needed by the chosen benchmark only;
3. Iroh only when Real Table/local networking reaches its Grain;
4. OpenTelemetry-compatible observability;
5. selective behavior references for scheduling/support/identity without inheriting full enterprise stacks.

The game core, verified shuffle, Qayd semantics, ranked policy, match ledger, and 152 authority must remain Balott-owned contracts even when external implementations inform them.
