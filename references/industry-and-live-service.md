# References: Industry and Live Service

What persistent online games have proven, what has broken them, and what this game takes from each.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Design lead
>
> **Related:** [Reference Library](README.md) · [World Model](../docs/07-multiplayer/world-model.md) · [Scope and Horizons](../docs/11-production/scope-and-horizons.md)

**Grades:** **P** primary source · **S** secondary · **W** weak. IDs are permanent.

## Persistent worlds and scale

| ID | Grade | Verified fact | Lesson: what we take, and what we change | Source |
| --- | --- | --- | --- | --- |
| M1 | S | Improbable sold its games unit (The Multiplayer Group) for $97M (2023) and moved to MSquared and Morpheus | Middleware for persistent worlds is commercially fragile, so we own the core simulation layer | <https://www.cnbc.com/2023/12/18/metaverse-firm-improbable-sells-gaming-unit-for-97-million.html> |
| M2 | S | Unity's January 2019 terms-of-service change blocked SpatialOS; Epic and Improbable set up a $25M fund to help developers move | Vendor dependency is a risk that can arrive overnight, so every vendor has an exit plan | <https://www.engadget.com/2019-01-10-unity-improbable-epic-games-spatial-os.html> |
| M3 | S | *Worlds Adrift* (SpatialOS) shut in July 2019 | A game built on one vendor's world technology can close with it | <https://www.pcgamesinsider.biz/news/69671/bossa-doesnt-blame-improbable-for-worlds-adrifts-cancellation/> |
| M4 | S | Star Citizen crowdfunding passed $1B (May 2026); still no 1.0 | Scale ambition without scope control never ships; ours sits in tagged horizons | <https://gameworldobserver.com/2026/05/25/the-developers-of-star-citizen-have-already-raised-over-a-billion-dollars> |
| M5 | W | Star Citizen Alpha 4.0 (December 2024): static server meshing, 500-player shard target | Meshing is real but arrives in steps, which is why our H1 target is layered regions | <https://starcitizen.tools/Update:Star_Citizen_Alpha_4.0.0> |
| M6 | S | Squadron 42 delayed to Q2 2027 | Dates slip when scope keeps growing; our published dates only ever move later, with notice ([D-018](../DECISIONS.md#d-018)) | <https://pcgamer.com/games/fps/star-citizens-squadron-42-delayed-again-this-time-to-avoid-the-attention-buzz-saw-of-gta-6-says-chris-roberts> |
| M7 | P | EVE Time Dilation (2011) slows the game clock under load; CCP called it a "band-aid" | We take graceful slowdown in mass battles for Convergence Confronts, with a floor and normalised contribution | <https://www.eveonline.com/news/view/introducing-time-dilation-tidi> |
| M8 | P | EVE Guinness records: 8,825 players, 6,557 concurrent (October 2020) | The ceiling of proven single-system scale | <https://www.eveonline.com/news/view/two-guinness-world-records-titles-broken> |
| M41 | P | PlanetSide 2: 1,158 players in one FPS battle (Guinness, 2015) | The ceiling of proven action-combat scale | <https://www.guinnessworldrecords.com/news/2015/1/planetside-2-gamers-aiming-for-fps-battle-world-record-this-weekend-370414> |
| M42 | P | Destiny's shared-world networked mission architecture (GDC 2015) | Public and private spaces that overlap, as our layers and phases do | <https://gdcvault.com/play/1022246/Shared-World-Shooter-Destiny-s> |
| M43 | P | Destiny 2: all activities hosted on Bungie servers (2017) | Server authority for everything that matters | <https://www.bungie.net/en/News/Article/45919> |
| M44 | W | Warframe Relays: social hubs of up to 50 players | A hub density reference | <https://wiki.warframe.com/w/Hub> |
| M18 | W | WoW phasing (per-player world state) and sharding (copies of crowded zones) | We take layers and phases ([D-028](../DECISIONS.md#d-028)), and keep friends, parties and clans in the same layer | <https://warcraft.wiki.gg/wiki/Sharding_(term)> |
| M19 | S | WoW Classic layering (2019): realm-wide copies of about 2,000 to 3,000 players | A layer sizing precedent; our city layers are smaller and more numerous | <https://www.wowhead.com/news=294589/blizzard-clears-up-layering-tech-misconceptions-in-classic-wow> |

## Economy, PvP and population

| ID | Grade | Verified fact | Lesson: what we take, and what we change | Source |
| --- | --- | --- | --- | --- |
| M9 | P | EVE PLEX (2008): a sanctioned bridge from real money to ISK | No real-money bridge to Omnis ([D-045](../DECISIONS.md#d-045)) | <https://www.eveonline.com/news/view/the-way-of-the-plex> |
| M10 | P | CCP hired an economist (2007) and publishes economic reports | We take an economy role and public reports ([D-046](../DECISIONS.md#d-046)) | <https://www.eveonline.com/news/view/monthly-economic-report-january-2019> |
| M20 | S | WoW Token (2015), modelled on PLEX | No real-money bridge, as with PLEX | <https://gameinformer.com/b/news/archive/2015/04/07/world-of-warcraft-subscription-tokens-now-live> |
| M11 | S | New World moved from open PvP to opt-in before launch (2020) | We take opt-in PvP from the start ([D-025](../DECISIONS.md#d-025)) | <https://massivelyop.com/2020/01/18/new-world-just-took-a-hard-turn-away-from-a-pvp-slugfest-hardcore-pvpers-are-not-happy/> |
| M12 | S | New World disabled all wealth transfers over a gold-duplication exploit (November 2021) | Server-authoritative items and duplication audits from day one | <https://www.nme.com/news/new-world-disables-all-forms-of-wealth-transfers-to-combat-gold-exploit-3085160> |
| M13 | S | New World servers close on 31 January 2027 | Live games end; ours plans its end and leaves Archive Mode behind ([D-047](../DECISIONS.md#d-047)) | <https://www.gameinformer.com/2026/01/16/new-world-aeternum-will-be-shut-down-in-january-2027> |
| M14 / M15 | W/S | Ultima Online's Trammel and Felucca split (2000); Walton: Trammel "doubled the playerbase" | Most players choose protection by default, so ours is the default | <https://wiki.ultimacodex.com/wiki/Ultima_Online:_Renaissance> · <https://www.engadget.com/2015-02-02-crowfalls-gordon-walton-on-how-trammel-impacted-classic-ultima.html> |
| M16 | P | Raph Koster, *Laws of Online World Design* | Required reading for the social design | <https://www.raphkoster.com/games/laws-of-online-world-design/the-laws-of-online-world-design/> |

## Progression and design

| ID | Grade | Verified fact | Lesson: what we take, and what we change | Source |
| --- | --- | --- | --- | --- |
| M17 | P | WoW: no flying in Draenor (2015), then reversed with the Pathfinder gate | Flight is earned and licensed, and Natural Law limits it by region ([D-023](../DECISIONS.md#d-023)) | <https://worldofwarcraft.blizzard.com/en-us/news/23818251/> |
| M21 | W | ESO One Tamriel (2016): world-wide level scaling | Friends at different levels can play together anywhere | <https://en.uesp.net/wiki/Online:One_Tamriel> |
| M22 / M23 | W/S | Guild Wars 2: "no gear treadmill" and horizontal progression; Ascended gear criticised as vertical creep | Low caps and horizontal depth ([D-021](../DECISIONS.md#d-021)), with no later tier added above level 10 | <https://wiki.guildwars2.com/wiki/Endgame> · <https://www.engadget.com/2012-11-26-guild-wars-2-staff-tackles-the-ascended-gear-controversy-head-on.html> |
| M26 | S | FFXIV Duty Support: solo the main-story dungeons with NPC parties | Everything personal can be done solo, with NPC allies ([D-024](../DECISIONS.md#d-024)) | <https://videogameschronicle.com/news/final-fantasy-14s-latest-patch-adds-npc-support-for-solo-players> |
| M27 | W | FFXIV: one Eorzean day lasts 70 real minutes | We take a short in-game day; ours lasts 100 minutes so NPC schedules matter ([D-013](../DECISIONS.md#d-013)) | <https://ffxiv.consolegameswiki.com/wiki/Eorzea_Time> |
| M45 / M46 | P/S | Monster Hunter: the Smithy forges gear from monster materials; ecology-first monster design | Artisans who forge from gathered materials; colossi designed as ecology | <https://game.capcom.com/manual/MH_Gen/en/page-71.html> · <https://www.siliconera.com/interview-preparing-monster-hunter-wilds-monsters-and-environments> |

## Failures and recoveries

| ID | Grade | Verified fact | Lesson: what we take, and what we change | Source |
| --- | --- | --- | --- | --- |
| M24 / M25 | P/S | FFXIV 1.0 failed and was relaunched as A Realm Reborn; Yoshida blamed an obsession with graphical fidelity | Fun and stability before fidelity | <https://gdcvault.com/play/1032358/Behind-the-Realm> · <https://www.engadget.com/2014-03-20-gdc-2014-final-fantasy-xivs-naoki-yoshida-explains-what-tanked.html> |
| M28 / M29 | S | Anthem servers closed on 12 January 2026; most of it was built in its final 18 months or so | Prove the core loop early, at a hard H0 gate | <https://www.thesixthaxis.com/2025/07/03/ea-is-pulling-the-plug-on-anthems-servers-in-2026/> · <https://kotaku.com/how-biowares-anthem-went-wrong-1833731964> |
| M30 | S | Concord went offline about two weeks after launch (2024) | Market risk is real; prove fun with players before launch | <https://shacknews.com/article/141292/concord-shutdown-purchases-refunded> |
| M31 | S | Skull and Bones took more than ten years to ship | Scope discipline and a kill criterion | <https://www.cnbc.com/2024/02/21/singapores-first-major-video-game-title-launches-to-mixed-reviews.html> |
| M32 / M33 | S | No Man's Sky: a 2016 backlash over missing features, then recovery through free updates | Never announce H2 or H3 as launch features | <https://www.techradar.com/news/no-mans-sky-didnt-mislead-consumers-rules-the-asa> · <https://www.gamereactor.eu/more-than-eight-years-after-launch-no-mans-skys-redemption-arc-is-finally-complete-1461193/> |

## Netcode

| ID | Grade | Verified fact | Lesson: what we take, and what we change | Source |
| --- | --- | --- | --- | --- |
| M34 | P | Overwatch gameplay architecture and netcode (GDC 2017): ECS, prediction, deterministic command frames | The foundation for combat netcode | <https://gdcvault.com/play/1024001/-Overwatch-Gameplay-Architecture-and> |
| M35 | P | Rocket League physics networking (GDC 2018) | Networked physics for vehicles and Frames | <https://www.rocketleague.com/news/rocket-league-at-gdc-2018> |
| M36 | P | GGPO rollback, open-sourced in 2019 | Rollback for arena duels [H2] | <https://github.com/pond3r/ggpo> |
| M37 | P | Glenn Fiedler, *Networked Physics* | Physics synchronisation | <https://gafferongames.com/post/introduction_to_networked_physics> |
| M38 | P | For Honor moved from peer-to-peer to dedicated servers (2018) | Server-authoritative melee from the start | <https://www.ubisoft.com/en-ca/game/for-honor/news-updates/2HayRoZjbJzSEJAhJMpeF7/for-honor-now-on-dedicated-servers-on-all-platforms> |
| M39 | S | Fortnite input-based matchmaking (2018) | Competitive pools by input device | <https://mp1st.com/news/fortnite-kbm-vs-controller-epic-rolling-out-input-based-matchmaking-for-each> |
| M40 | S | Star Wars: Squadrons: VR and flat-screen players cross-play in 5v5 (2020) | VR parity is possible in cockpit play, which informs the H3 VR mode | <https://www.thesixthaxis.com/2020/06/19/star-wars-squadrons-gameplay-trailer-reveal-multiplayer-modes-psvr-customisation/> |
