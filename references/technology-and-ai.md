# References: Technology and AI

Verified facts about engines, platforms, servers, speech, security, accessibility and AI that the technical specs rely on, and what this game takes from each.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Design lead
>
> **Related:** [Reference Library](README.md) · [Tech Watch](../docs/08-technology/tech-watch.md) · [AI Architecture](../docs/06-ai/architecture.md)

**Grades:** **P** primary source · **S** secondary · **W** weak or vendor. These facts move fast, so [Tech Watch](../docs/08-technology/tech-watch.md) re-checks them before any decision depends on one. The S table records facts only; each spec that cites an S entry says what it takes from it.

## S: engine and platforms

| ID | Grade | Verified fact | Source |
| --- | --- | --- | --- |
| S1 | P | UE 5.8 release notes: Iris "production-ready for licensees"; PS4 SDK still listed | <https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-5-8-release-notes> |
| S2 | P | UE 5.8 (17 Jun 2026) is "the last planned major Unreal Engine 5 release" before UE6 | <https://www.unrealengine.com/en-US/news/unreal-engine-5-8-is-now-available> |
| S3 | P | Lumen: not on PS4/Xbox One, no VR support; targets PS5, Xbox Series and Switch 2 | <https://dev.epicgames.com/documentation/en-us/unreal-engine/lumen-technical-details-in-unreal-engine> |
| S4 | P | Lumen on mobile: Android Vulkan, experimental on high-end Android | <https://dev.epicgames.com/documentation/en-us/unreal-engine/using-lumen-global-illumination-on-mobile-in-unreal-engine> |
| S5 | S | Meta Quest UE5 support launched without Nanite or Lumen | <https://www.roadtovr.com/meta-quest-unreal-engine-5-support-lumen-nanite/> |
| S6 | P | Large World Coordinates (double precision; default WORLD_MAX 88 million km) | <https://dev.epicgames.com/documentation/en-us/unreal-engine/large-world-coordinates-in-unreal-engine-5> |
| S7 | P | Iris replication: filtering and prioritization for larger worlds (docs still marked Experimental) | <https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine> |
| S8 | P | World Partition: grid streaming, Data Layers, Level Instances, server streaming settings | <https://dev.epicgames.com/documentation/en-us/unreal-engine/world-partition-in-unreal-engine> |
| S9 | P | Dedicated servers need a source build | <https://dev.epicgames.com/documentation/en-us/unreal-engine/setting-up-dedicated-servers-in-unreal-engine> |
| S10 | P | Chaos Destruction (no networking guidance in its docs) | <https://dev.epicgames.com/documentation/en-us/unreal-engine/chaos-destruction-in-unreal-engine> |
| S11 | P | Replay System (DemoNetDriver) | <https://dev.epicgames.com/documentation/en-us/unreal-engine/using-the-replay-system-in-unreal-engine> |
| S12 | S | Epic "Launch Everywhere": 3.5% royalty (from 2025) | <https://www.mediapost.com/publications/article/399903/epic-games-gives-unreal-engine-developers-a-bigger.html> |
| S13 / S14 | S | CDPR's new Witcher on UE5; Witcher 4 demo at 60fps on a base PS5 (2025) | <https://www.gamedeveloper.com/press-release/new-witcher-saga-announced> · <https://www.pushsquare.com/news/2025/06/the-witcher-4-gameplay-revealed-running-on-ps5-at-60fps-with-ray-tracing> |
| S15 | S | Halo Studios moved to UE5 (2024) | <https://www.purexbox.com/news/2024/10/halo-enters-new-dawn-with-new-studio-name-engine-and-games> |
| S16 | P | Infinity Nikki: UE5 open world on PS5, PC, iOS and Android (Dec 2024) | <https://store.epicgames.com/news/how-infinity-nikki-became-the-ultimate-dress-up-game-and-so-much-more> |
| S17 | P | Wuthering Waves on UE4, including mobile | <https://www.unrealengine.com/developer-interviews/exploring-the-post-apocalyptic-charm-of-asg-open-worlds-in-wuthering-waves> |
| S18 | P | Genshin Impact runs on Unity | <https://docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi> |
| S19 / S20 | S | Cyberpunk 2077 pulled from the PS Store (2020); Phantom Liberty dropped last-gen | <https://www.videogameschronicle.com/news/sony-has-removed-cyberpunk-2077-from-the-playstation-store-and-is-offering-refunds> · <https://www.thesixthaxis.com/2022/09/06/cyberpunk-2077-phantom-liberty-dlc-not-on-ps4-xbox-one/> |
| S21 | P | Switch 2 specifications | <https://www.nintendo.com/us/gaming-systems/switch-2/tech-specs/> |
| S22 | P | PS5: some scenes are blocked from capture | <https://www.playstation.com/en-us/support/games/capture-ps5-gameplay-screenshots/> |
| S23 | P | Xbox GDK `XAppCaptureDisableRecord` | <https://learn.microsoft.com/en-in/gaming/gdk/docs/reference/system/xappcapture/functions/xappcapturedisablerecord> |
| S24 | P | Steam Game Recording timeline API | <https://partner.steamgames.com/doc/features/timeline> |
| S25 | P | iOS ReplayKit: system consent required | <https://developer.apple.com/documentation/replaykit/rpscreenrecorder> |
| S26 | P | Meta Quest capture can be disabled; secure layers | <https://developers.meta.com/horizon/documentation/android-apps/drm> |
| S27 | P | Meta comfort guidance: keep accelerations brief and infrequent | <https://developers.meta.com/horizon/resources/locomotion-comfort-usability/> |
| S28 | P | Meta Quest 3 (2023, Snapdragon XR2 Gen 2) | <https://about.fb.com/news/2023/09/meet-meta-quest-3-mixed-reality-headset/> |
| S29 / S30 | S | MSFS 2024 launch overwhelmed its streaming cache; MSFS 2020 streams cloud terrain | <https://www.pcgamer.com/games/sim/microsoft-flight-simulator-2024-crashes-on-takeoff-thanks-to-massive-server-woes-and-microsofts-advice-isnt-great-just-keep-waiting-until-something-happens/> · <https://en.wikipedia.org/wiki/Microsoft_Flight_Simulator_(2020_video_game)> |

## T: servers, services, speech, security and accessibility

| ID | Grade | Verified fact | Lesson: what we take, and what we change | Source |
| --- | --- | --- | --- | --- |
| T1 | W | Star Citizen: "Quasi Dynamic Server Meshing" in instancing; persistent territories still static; a "Claims" ownership system in development (2026) | Dynamic handoff of authority is still frontier work, so ours is H2 and H3 | <https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27> · <https://massivelyop.com/2026/02/06/star-citizen-cto-outlines-progress-on-server-meshing/> |
| T3 | S | Improbable Morpheus claimed 10,000+ players in dense spaces (vendor claim); about 4,500 demonstrated (Otherside) | Claims of 10,000 players in one place are unproven, so thousands visible in one place is H3 | <https://www.cnbc.com/2023/06/16/softbank-backed-improbable-outlines-plan-for-msquared-metaverse.html> |
| T4 | S | Hadean *EVE: Aether Wars* (2019): 10,412 combatants, only 3,852 of them human | Headline counts often include bots | <https://bit-tech.net/news/gaming/pc/hadean-hosts-10k-ship-eve-aether-wars-battle/1/> |
| T6 | W | UE MultiServer Replication plugin: experimental (2025) | Not relied on for H1; we build our own meshing | <https://forums.unrealengine.com/t/2648232> |
| T7 | P | UE Mass Entity: data-oriented ECS (MassCrowd, ZoneGraph) | NPC crowds | <https://dev.epicgames.com/documentation/en-us/unreal-engine/overview-of-mass-entity-in-unreal-engine> |
| T8 | P | Whisper (OpenAI, 2022): open-weights speech recognition trained on 680k hours | Speech-to-text option | <https://arxiv.org/abs/2212.04356> |
| T9 | P | Apple SpeechAnalyzer (WWDC25): on-device speech-to-text | On-device speech recognition for privacy | <https://developer.apple.com/videos/play/wwdc2025/277/> |
| T10 | P | ElevenLabs Iconic Marketplace (Nov 2025): consent-based licensed voices | Licensed AI voices ([D-043](../DECISIONS.md#d-043)) | <https://www.businesswire.com/news/home/20251111704426/en> |
| T11 / T12 | P/S | Replica Studios' SAG-AFTRA agreement (Jan 2024); Replica shut down 30 Jun 2025 | Vendor collapse risk; keep voice rights portable | <https://www.sagaftra.org/sag-aftra-and-replica-studios-introduce-groundbreaking-ai-voice-agreement-ces> · <https://multilingual.com/replica-studios-shutdown-2025/> |
| T13 | P | OpenAI Structured Outputs (Aug 2024): schema-constrained output, 100% in OpenAI's own evals | Typed speech acts and proposals | <https://openai.com/index/introducing-structured-outputs-in-the-api/> |
| T14 | P | Anthropic structured outputs and strict tool use (constrained decoding) | Typed speech acts and proposals | <https://platform.claude.com/docs/en/build-with-claude/structured-outputs> |
| T15 | P | llama.cpp GBNF grammars | On-device constrained output | <https://github.com/ggml-org/llama.cpp/blob/master/grammars/README.md> |
| T16 | P | Dual LLM pattern (Willison, 2023): a quarantined model handles untrusted text | The split between the NPC's listener and actor | <https://simonwillison.net/2023/Apr/25/dual-llm-pattern/> |
| T17 | P | Spotlighting (Microsoft, 2024): attack success fell from over 50% to under 2% | Input marking | <https://arxiv.org/abs/2403.14720> |
| T18 | P | CaMeL (Google DeepMind et al., 2025): separates control flow from data flow, with capability checks | Our architectural model for rule zero | <https://arxiv.org/abs/2503.18813> |
| T19 | P | OpenAI omni-moderation (2024) | Output and input moderation | <https://openai.com/index/upgrading-the-moderation-api-with-our-new-multimodal-moderation-model/> |
| T20 | W | Llama Guard 4 (2025, open weights) | Self-hosted guard model | <https://openrouter.ai/meta-llama/llama-guard-4-12b:free> |
| T21 | P | NVIDIA NeMo Guardrails | Programmable rails | <https://github.com/NVIDIA/NeMo-Guardrails> |
| T22 / T23 | P | NVIDIA ACE: Minitron small language models (2–8B) running through the In-Game Inferencing SDK | On-device NPC minds | <https://developer.nvidia.com/ace-for-games> · <https://developer.nvidia.com/blog/bring-nvidia-ace-ai-characters-to-games-with-the-new-in-game-inference-sdk> |
| T24 | P | Apple Foundation Models (2025): ~3B on-device, guided generation, tool calling | On-device tier on Apple platforms | <https://machinelearning.apple.com/research/apple-foundation-models-2025-updates> |
| T25 | S | Riot Vanguard kernel anti-cheat | Anti-cheat option (with privacy trade-off) | <https://wiki.leagueoflegends.com/en-us/Riot_Vanguard> |
| T26 | P | Easy Anti-Cheat and voice free through Epic Online Services | Service option | <https://www.epicgames.com/site/en-US/news/epic-online-services-launches-free-in-game-voice-and-easy-anti-cheat> |
| T27 | W | Valve VACnet (GDC 2018): server-side deep learning on aim data | Server-side behavioural detection | <https://www.pcgamer.com/tag/gdc-2018/> |
| T28 | S | StarCraft replays: inputs plus deterministic re-simulation | Replay-first capture ([D-037](../DECISIONS.md#d-037)) | <https://sc2reader.readthedocs.io/en/latest/articles/whatsinareplay.html> |
| T29 | S | Rocket League replays store replicated state, not inputs | State replays for physics-heavy play | <https://docs.rs/boxcars> |
| T30 | P | UE DemoNetDriver streamers (file, memory, HTTP) | Replay pipeline | <https://dev.epicgames.com/documentation/en-us/unreal-engine/demonetdriver-and-streamers-in-unreal-engine> |
| T31 | P | Epic Online Services: cross-platform accounts, lobbies, voice | Cross-play services | <https://dev.epicgames.com/docs/epic-online-services/eos-overview> |
| T32 | S | Sony opened Fortnite cross-play (Sept 2018) | Cross-play precedent | <https://techcrunch.com/2018/09/26/sony-is-finally-opening-fortnite-cross-play-on-the-ps4> |
| T33 | P | The Last of Us Part II: more than 60 accessibility settings | Accessibility bar | <https://www.playstation.com/en-us/games/the-last-of-us-part-ii/accessibility/> |
| T34 | S | US CVAA: in-game communication must be accessible (since 2019) | Parity between text and voice for every communication feature ([D-041](../DECISIONS.md#d-041)) | <https://www.fenwick.com/insights/publications/cvaa-compliance-waiver-for-video-games-set-to-expire-in-december-2018> |
| T35 | P | Game Accessibility Guidelines | Checklist | <https://gameaccessibilityguidelines.com> |
| T36 | P | Xbox Accessibility Guidelines | Checklist | <https://learn.microsoft.com/en-us/gaming/accessibility/guidelines> |
| T37 | P | Xbox voice reporting (2023): 60-second clip kept on device | Privacy-preserving voice reports | <https://news.xbox.com/en-us/2023/07/12/xbox-voice-reporting-feature/> |
| T38 | P | Riot voice evaluation (2022): audio checked only after a report | Privacy-preserving voice reports | <https://riot.com/3OEJBhl> |
| T39 | P | MAG: 256-player console FPS (Guinness, 2010) | Scale precedent | <https://www.guinnessworldrecords.com/world-records/most-players-online-in-a-console-fps> |
| T40 | S | PlanetSide 2: 2,000-player continent target at launch | Scale precedent | <https://kotaku.com/planetside-2-plays-like-a-first-person-shooter-not-a-m-5917860> |
| T41 | S | *Dual Universe*: official single-shard servers closed Aug 2025; now self-hosted as "myDU" | Single-shard ambition risk; self-hosting as legacy (supports [D-047](../DECISIONS.md#d-047)) | <https://en.wikipedia.org/wiki/Dual_Universe> |
| T42 | P | Ofcom guidance on highly effective age assurance (Jan 2025): self-declaration doesn't comply | Age assurance for voice ([D-008](../DECISIONS.md#d-008)) | <https://www.ofcom.org.uk/siteassets/resources/documents/consultations/category-1-10-weeks/statement-age-assurance-and-childrens-access/guidance-on-highly-effective-age-assurance-and-other-part-5-duties.pdf> |
| T43 | S/W | Facial age estimation: about 2.5 years mean error near 16–18 (UK POST), so a buffer age is needed; vendor claims are better | Buffered age gates | <https://post.parliament.uk/facial-age-estimation/> · <https://www.yoti.com/blog/thoughts-from-our-ceo-february-2026/> |
| T44 | S | *Slay the Spire*: metrics-driven balance (GDC 2019) | Telemetry-led balance | <https://www.gamedeveloper.com/design/learn-i-slay-the-spire-i-s-metrics-driven-approach-to-game-balancing-at-gdc-2019> |
| T45 | S | LEGO Fortnite: 8-player persistent worlds with keys | Contrast with our shared world | <https://primagames.com/gaming/lego-fortnite-squad-and-server-size-explained> |
| T46 | S | Microsoft Windows Resiliency Initiative (2024): security vendors moving out of the kernel | Kernel anti-cheat may become harder on Windows; prefer server-side detection | <https://www.helpnetsecurity.com/2024/11/19/windows-kernel-security-vendors/> |

## A: AI in games, AI research and AI policy

| ID | Grade | Verified fact | Lesson: what we take, and what we change | Source |
| --- | --- | --- | --- | --- |
| A1 | P | *Generative Agents* (2023): memory stream, reflection, planning; costly; documented misretrieval and over-cooperation | NPC memory design and its failure modes | <https://arxiv.org/abs/2304.03442> |
| A2 | P | NVIDIA ACE in NARAKA and inZOI (2025) | On-device AI characters have shipped | <https://www.nvidia.com/en-gb/geforce/news/nvidia-ace-naraka-bladepoint-inzoi-launch-this-month> |
| A3 | P | PUBG Ally: engine data is ground truth; reflexes run in behaviour trees; a 2B on-device model | Rule zero in practice: engine data is the truth, and the model only expresses it | <https://developer.nvidia.com/blog/how-krafton-built-pubg-ally-a-co-playable-character-powered-by-nvidia-ace/> |
| A4 | P | KRAFTON PUBG Ally playtest plans | AI characters need playtests with real players; ours start with invited testers at H0 | <https://press.krafton.com/KRAFTON-REVEALS-PLAYTEST-PLANS-FOR-PUBG-ALLY-BUILT-WITH-NVIDIA-ACE> |
| A5 | S | Ubisoft NEO NPC: writers define the character, the model improvises lines | Writer-defined Minds | <https://pushsquare.com/news/2024/03/ubisofts-neo-npc-prototype-offers-a-glimpse-at-a-generative-ai-future-for-games> |
| A6 | S | Ubisoft Teammates (2025): voice-commanded squadmates | Voice commands to AI allies are an emerging pattern; ours pass through speech acts and rule zero like any NPC conversation | <https://mobilesyrup.com/2025/11/28/ubisoft-unveils-ai-powered-teammates-project/> |
| A7 / A8 | S | Fortnite AI Darth Vader: slurs after launch, hotfix; SAG-AFTRA unfair labor practice charge | Output filtering; union compliance | <https://decrypt.co/320500/fortnite-ai-powered-darth-vader-saying-slurs> · <https://www.thewrap.com/sag-aftra-darth-vader-fortnite-ai-voice/> |
| A9 / A10 | S | SAG-AFTRA 2025 Interactive Media Agreement: consent, disclosure and pay for digital replicas; higher minimums for real-time generation | Consent, disclosure and pay for every voice drawn from a performer ([D-043](../DECISIONS.md#d-043)) | <https://www.thewrap.com/sag-aftra-ratify-interactive-media-agreement-video-game-strike/> · <https://technologylaw.fkks.com/post/102mewu/inside-the-new-sag-aftra-interactive-media-agreement-new-standards-for-ai-and-di> |
| A11 / A12 | S | *Where Winds Meet*: players talked LLM NPCs into completing quests (repeating NPC lines back; bracketed fake actions) | **Rule zero** ([D-042](../DECISIONS.md#d-042)) | <https://automaton-media.com/articles/newsjp/where-winds-meet-20251128-368771/> · <https://www.notebookcheck.net/Players-learn-how-to-outwit-every-NPC-in-Where-Winds-Meet-and-feel-like-gods-in-its-open-world.1170522.0.html> |
| A13 | P | Steam AI disclosure: pre-generated vs live-generated; guardrails must be described | Disclosure | <https://partner.steamgames.com/doc/gettingstarted/contentsurvey> |
| A14 / A15 | P/S | EU AI Act Art. 50: users must be told they're interacting with AI; applies from 2 Aug 2026 | Disclosure UX | <https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-50> · <https://www.aljazeera.com/economy/2026/8/6/what-came-into-force-with-the-eus-ai-act-this-week-and-what-didnt> |
| A16 | S | AI Dungeon (2021): filter crisis | Generated-content safety | <https://www.theregister.com/2021/04/30/ai_dungeon_filter_vulnerabilities/> |
| A17 | P | L4D AI Director: intensity tracking; build-up, peak, fade, relax | The Weaver's pacing | <https://cdn.fastly.steamstatic.com/apps/valve/2009/ai_systems_of_l4d_mike_booth.pdf> |
| A18 | P | Nemesis patent US 10,926,179 (active to ~2036) | Freedom-to-operate review before NPC memory design is final ([Legal and Compliance](../docs/12-legal/compliance.md#2-the-nemesis-patent)) | <https://patents.google.com/patent/US10926179B2/en> |
| A19 / A20 | S/W | Oblivion's Radiant AI dialled back; Skyrim's Radiant Story limited | Bounded emergence | <https://gamesbeat.com/dimming-the-radiant-ai-in-oblivion/> · <https://forums.nexusmods.com/topic/542675-bethesda%E2%80%99s-nesmith-reflects-on-the-difficult-birth-of-skyrim%E2%80%99s-%E2%80%98radian> |
| A21 / A22 | W/S | RimWorld storytellers; Dwarf Fortress history simulation | Pacing personalities; pre-simulated history | <https://rimworldwiki.com/wiki/AI_Storytellers> · <https://en.wikipedia.org/wiki/Dwarf_Fortress> |
| A23 | P | BotW "multiplicative gameplay" and chemistry engine (GDC 2017) | Systemic surprise | <https://gdcvault.com/play/1024562/Change-and-Constant-Breaking-Conventions> |
| A24 | P | LLM output isn't reproducible even at temperature 0 (Thinking Machines, 2025) | Record outputs; don't regenerate | <https://thinkingmachines.ai/blog/defeating-nondeterminism-in-llm-inference> |
| A25 | P | OWASP LLM01:2025 Prompt Injection: no fool-proof prevention | Limit impact by design | <https://genai.owasp.org/llmrisk/llm01-prompt-injection/> |
| A26 | W | Inworld *Death by AI* case study (vendor) | Cost sustainability | <https://inworld.ai/blog/how-inworld-helped-the-ai-game-death-by-ai-with-20-million-players-reach-profitability> |
| A27 | P | Microsoft Muse / WHAM generative game model (Nature, 2025) | Tracked as H3 | <https://www.microsoft.com/en-us/research/project/wham/> |
| A28 | P | Ken Levine, *Narrative Legos* (GDC 2014) | Recombinable story atoms | <https://gdcvault.com/play/1020211/Narrative> |
