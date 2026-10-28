# Platform Support

Which platforms the Oasis runs on, how support is decided by policy rather than a frozen device list, and what changes between capability tiers: presentation only, never rules.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Platform team
>
> **Horizons:** H0 Windows PC, one current console and one tier C device as test targets · H1 every family in D-009, launching together · H2 new generations added by policy · H3 full VR mode
>
> **Related:** [D-009](../../DECISIONS.md#d-009) · [D-002](../../DECISIONS.md#d-002) · [D-028](../../DECISIONS.md#d-028) · [Engine and Stack](../08-technology/engine-and-stack.md) · [Controls, Camera and Accessibility](controls-camera-and-accessibility.md) · [World Model](../07-multiplayer/world-model.md)

## 1. Player experience

- A player starts on their phone during a commute, continues on a Switch 2 on the sofa, and finishes a Convergence front on their PC. It is the same avatar, inventory, friends, layer rules and world throughout.
- Their phone draws fewer distant players in full detail and a shorter view distance. It never shows them a different world, and it never gives them a weaker hand in a fair fight.

The system must make every device feel like a first-class way into the same Oasis.

## 2. Scope

- **Covers:** support policy, platform families, capability tiers and the feature matrix, performance targets, cross-play and cross-progression, certification, mobile thermals and storage, launch readiness, removed platforms and the VR plan.
- **Leaves to other specs:** control schemes and accessibility ([Controls, Camera and Accessibility](controls-camera-and-accessibility.md)); rendering techniques per tier ([Engine and Stack: Rendering across tiers](../08-technology/engine-and-stack.md#4-rendering-painted-realism-across-tiers)); arena input pools ([World Model: Arena matchmaking](../07-multiplayer/world-model.md#610-arena-matchmaking)).

## 3. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| Cyberpunk 2077 pulled from the PlayStation Store; Phantom Liberty dropped last-generation consoles [S19] [S20] | Old hardware can sink a launch | PS4 and Xbox One are not supported |
| Infinity Nikki: a UE5 open world on PS5, PC, iOS and Android [S16] | A UE5 open world can span mobile and console | Tier C is a first-class tier, not a port |
| MSFS 2024's streaming cache was overwhelmed at launch [S29]; MSFS 2020 streams terrain from the cloud [S30] | Streaming at scale fails at launch if under-provisioned | Streaming install with local fallbacks, and CDN load tests at three times forecast demand |
| Sony opened Fortnite cross-play in 2018 [T32] | Cross-play across console families is achievable | Cross-play and cross-progression are the default from H1 |
| Star Wars: Squadrons, with VR and flat-screen players together in 5v5 [M40] | VR can match flat-screen play in cockpits | VR starts with cockpit and seated activities |

## 4. Terms

| Term | Meaning |
| --- | --- |
| **Capability tier** | A, B, C or X (VR). Set by a benchmark run on first launch, not by brand ([Glossary](../../GLOSSARY.md)). |
| **Minimum capability tier** | The published lowest device performance a family must meet to be supported. Tier C is the floor. |
| **Reference console tier** | The base tier A console (PS5 or Xbox Series X class). Acceptance tests that name the reference console tier run there. |

## 5. Entities and state

| Family | Includes | Default tier | Notes |
| --- | --- | --- | --- |
| **Windows PC** | Windows versions inside Microsoft's security support | A (scales down to B) | Minimum specification published |
| **Linux and SteamOS** | Steam Deck-class handhelds, SteamOS and Linux desktops | B for handhelds, A for desktops | Anti-cheat must work here ([SAF-083](../07-multiplayer/safety-and-moderation.md#69-anti-cheat-and-anti-bot), TW-14) |
| **macOS** | Apple silicon only | A or B, by chip benchmark | None |
| **PlayStation** | PS5 and later | A | None |
| **Xbox** | Series X (A), Series S (B) and later | A or B | None |
| **Nintendo** | Switch 2 and later [S21] | B | A named Lumen target [S3] |
| **iOS and iPadOS** | Devices that meet the tier C benchmark | C (high-end iPads may reach B) | None |
| **Android** | Devices that meet the tier C benchmark, whatever the brand | C | Lumen is experimental on high-end Android only [S4] |
| **VR** | H3 | X | [VR plan](#68-vr-plan-h3) |

A device's tier is stored locally and re-benchmarked after major OS or game updates. Account, avatar and progress are held on the server and never depend on the device.

## 6. Rules

### 6.1 Support policy

- **PLT-001 [H1]** At launch we support the platform generations their makers still support, and OS versions inside each vendor's security-support window, provided the device meets the published minimum capability tier ([D-009](../../DECISIONS.md#d-009)).
- **PLT-002 [H1]** The minimum specification for every family is published at least 6 months before launch, and again after every change.
- **PLT-003 [H2]** New generations are added by policy during the decade. An old generation is retired only when its maker ends support and players have had at least 12 months' notice, with cross-progression keeping everything.

### 6.2 Capability tiers

There are four capability tiers. Lighting and geometry per tier are set in [Engine and Stack: Rendering across tiers](../08-technology/engine-and-stack.md#4-rendering-painted-realism-across-tiers).

| Feature | A · high-end PC, current consoles | B · Switch 2, handhelds, Series S class | C · high-end mobile | X · VR [H3] |
| --- | --- | --- | --- | --- |
| Gameplay view distance (threats, players, interactables) | 1,000 m | 600 m | 400 m | 400 m |
| Scenic view distance (terrain, landmarks, colossus silhouettes) | Full horizon | Full horizon, as impostors | Full horizon, as impostors | Full horizon, as impostors |
| Ambient crowd density | 100% | 60% | 35% | 35% |
| Players drawn in full detail | Up to 200 (a full H1 layer) | 100 | 50 | 32 |
| Players beyond the full-detail budget | Impostors | Impostors | Impostors | Impostors |
| Recording ([D-037](../../DECISIONS.md#d-037)) | Local re-render up to 4K | Local re-render at 1080p | Cloud re-render, then download | Cloud re-render |
| Voice | Full | Full | Full, push-to-talk by default | Full, spatial |
| On-device Loom tier | Where the hardware allows [T22] | Cloud | Where the hardware allows [T24] | Cloud |
| **Gameplay rules** | **Identical** | **Identical** | **Identical** | **Identical** |

- **PLT-010 [H1]** Gameplay rules, tick rate, hit validation, timing windows, damage and rewards are identical on every tier and family ([MP-080](../07-multiplayer/world-model.md#69-simulation-parity-across-platforms)).
- **PLT-011 [H1]** Every hostile player, threat, Bounty hunter and interactable within 50 m is always drawn as a full, targetable character on every tier ([MP-081](../07-multiplayer/world-model.md#69-simulation-parity-across-platforms)). Tier C's gameplay view distance is longer than the range of any attack in the game.
- **PLT-012 [H1]** Gameplay-critical signals ([ART-002](../01-vision/art-and-audio-direction.md#1-visual-direction-painted-realism)) look the same on every tier ([TEC-011](../08-technology/engine-and-stack.md#4-rendering-painted-realism-across-tiers)).
- **PLT-013 [H1]** No tier exists below C. Devices that can't meet the tier C benchmark are not supported, so that parity holds.
- **PLT-014 [H1]** Tier C uses the probe lighting path on every mobile family, including iOS, so its look doesn't depend on Lumen reaching mobile ([TEC-010](../08-technology/engine-and-stack.md#4-rendering-painted-realism-across-tiers)).

### 6.3 Performance targets

| Tier | Frame rate | Resolution | Notes |
| --- | --- | --- | --- |
| A, consoles | 60 fps performance mode; optional 30 fps quality mode | 4K output, upscaled | The reference console tier |
| A, PC | Scalable; 60 fps at the recommended specification | Scalable | Uncapped option |
| B | 30 fps locked minimum; 40 or 60 fps where possible | 1080p docked, native in handheld mode, upscaled | None |
| C | 30 fps sustained for at least 30 minutes, never below 25 fps from heat | 720p to 1080p, scaled from native | [Mobile thermals](#65-mobile-thermals-storage-and-streaming-install) |
| X | The headset's native refresh rate (72 or 90 Hz class), never lower | Per headset | Comfort comes first [S27] |

### 6.4 Cross-play, cross-progression and certification

- **PLT-020 [H1]** One account and one avatar work across every family, and platform accounts link to it ([Social, Voice and Clans](../07-multiplayer/social-voice-and-clans.md)).
- **PLT-021 [H1]** Cross-play is on by default. Where a platform requires an opt-out, it removes the player from arena cross-play pools only. The open world is one world for everyone ([D-028](../../DECISIONS.md#d-028)).
- **PLT-022 [H1]** Cosmetic purchases follow each store's rules [L27] [L28].
- **PLT-023 [H1]** Certification is budgeted in the schedule. It covers platform technical requirements (suspend and resume, account switching, network loss, full storage), parental-control integration ([Safety and Moderation](../07-multiplayer/safety-and-moderation.md)), age-rating submissions per region [L19] [L20], capture restrictions [S22] [S23] [S24] [S25] [S26] and store rules for digital goods [L27] [L28].
- **PLT-024 [H1]** Patches ship to every family together. A family delayed by certification keeps playing the previous version only if it is compatible with the live servers; otherwise the servers hold the change until every family is certified.
- **PLT-025 [H1]** Store cosmetics are bound to the account and usable on every family. If a platform's agreement forbids showing an item bought on another store, the item is hidden on that platform only and is never lost ([D-039](../../DECISIONS.md#d-039)).
- **PLT-026 [H2]** Cloud-streamed play is offered through partner cloud services as a way in for devices below the minimum specification. It runs the same rules as any other client and joins the controller or touch arena pool by input. It is not offered at H1.

### 6.5 Mobile thermals, storage and streaming install

Every family installs by streaming; on mobile it is mandatory.

- **PLT-030 [H1]** The first download on tier C is no more than 8 GB and holds Halcyon, the opening hours and the core of every system. World regions, moons and high-resolution assets stream in as packs before they are needed, in the order the player is likely to travel.
- **PLT-031 [H1]** The local cache has a player-chosen budget of at least 4 GB. Least recently visited regions are removed first; the current region and Halcyon never are.
- **PLT-032 [H1]** If streaming is slow, the game holds the player at an in-world pause point (attuning at a Wayshrine, boarding a Skyferry) rather than showing missing gameplay content. CDN capacity is load-tested at three times forecast launch demand [S29].
- **PLT-033 [H1]** On tier C, a thermal governor lowers presentation (resolution, crowd density, effects) before frame rate when the device heats up.
- **PLT-034 [H1]** Battery saver mode on mobile and handhelds caps the frame rate at 30 fps and reduces effects. Gameplay is unchanged.

### 6.6 Launch readiness gates

Every family targets the same launch day. A family that fails a gate launches later.

| Gate | Pass condition |
| --- | --- |
| Performance | Tier targets met on the minimum device for 95% of a standard 2-hour soak route |
| Stability | At least 99.5% of sessions crash-free in the final beta |
| Parity | The automated parity suite gives identical outcomes for 1,000 scripted combat and economy scenarios on every family |
| Certification | Platform approval received |
| Safety settings | The default-settings audit passes ([SAF-010](../07-multiplayer/safety-and-moderation.md#62-defaults-by-age), [VIS-006](../01-vision/vision.md#4-experience-goals-observable-testable)) |
| Streaming | Install-streaming tests pass at three times forecast demand ([PLT-032](#65-mobile-thermals-storage-and-streaming-install)) |

- **PLT-040 [H1]** A family that fails a gate launches later into the same live world, with no wipe and no separate realm. The delay is announced honestly.
- **PLT-041 [H1]** No H2 or H3 platform, including VR, is ever announced as a launch platform [M32].

### 6.7 Removed platforms

- **PLT-050 [H1]** PS4 and Xbox One are not supported ([D-009](../../DECISIONS.md#d-009)). Lumen doesn't run on them [S3], and Cyberpunk 2077 shows the cost of launching on the previous generation [S19] [S20]. UE 5.8 still lists a PS4 SDK [S1], but neither console will be a supported generation by a mid-2030s launch.

### 6.8 VR plan [H3]

| Step | Content | Evidence |
| --- | --- | --- |
| Foundations (H1) | Camera and input kept apart from the engine; first-person fully supported ([D-020](../../DECISIONS.md#d-020)); UI that can render as panels in the world; probe-path lighting for tier X | [S3] [S5] |
| First VR activities (H3 at the earliest) | Seated, cockpit-framed play: Frames, the Skyferry, personal ships, piloting | Squadrons cross-play [M40] |
| Full VR mode (H3) | On-foot exploration, social spaces and combat, with comfort options | Meta comfort guidance [S27]; Quest 3-class hardware [S28] |

- **PLT-060 [H3]** VR players share the same world and rules. In arenas, VR is its own input pool unless parity testing shows it can join another.
- **PLT-061 [H3]** VR follows the comfort rules in [TRV-021](../04-gameplay/traversal-and-flight.md#66-comfort): brief, infrequent accelerations, vignettes, snap turns and cockpit frames for flight.

## 7. Edge cases

| Case | Behaviour |
| --- | --- |
| A device falls below its tier after an OS update | It is re-benchmarked and moves down a tier; if it falls below tier C, the player is told and can keep playing on another family |
| A family fails a launch gate | It launches later into the same world ([PLT-040](#66-launch-readiness-gates)) |
| A family's certification delays a patch | [PLT-024](#64-cross-play-cross-progression-and-certification) applies: compatible clients keep playing, otherwise the servers wait |
| A platform's maker ends support mid-decade | At least 12 months' notice, and everything carries over ([PLT-003](#61-support-policy)) |
| Streaming stalls on a slow connection | The player waits at an in-world pause point ([PLT-032](#65-mobile-thermals-storage-and-streaming-install)) |

## 8. Multiplayer and platforms

Every family plays in one world with one set of rules ([World Model: Simulation parity across platforms](../07-multiplayer/world-model.md#69-simulation-parity-across-platforms)). Arena pools are set by input and perspective, never by platform alone.

## 9. Safety and abuse

Platform parental controls and communication settings are honoured, and the strictest setting wins ([SOC-061](../07-multiplayer/social-voice-and-clans.md#67-cross-platform-communication)). Every family's build passes the default-settings audit before launch.

## 10. Performance

Frame-rate and resolution targets are in [Performance targets](#63-performance-targets).

## 11. Examples

| Allowed | Not allowed |
| --- | --- |
| A phone draws a distant crowd as impostors | A phone hides a hostile player within 50 m |
| A Switch 2 switches to the probe lighting path in a dense city to hold 30 fps | A Switch 2 player gets a shorter attack range |
| A family launches a month late into the same world | A family launches on its own realm |

## 12. Acceptance criteria

| ID | Test |
| --- | --- |
| [PLT-002](#61-support-policy) | Launch checklist: minimum specifications published at least 6 months before launch |
| [PLT-010](#62-capability-tiers) | Parity suite: 1,000 scripted scenarios give identical server outcomes on every family |
| [PLT-011](#62-capability-tiers) | On the minimum tier C device in a 200-player layer, every hostile within 50 m is drawn and targetable, and no weapon or Art outranges the gameplay view distance |
| [PLT-025](#64-cross-play-cross-progression-and-certification) | A cosmetic bought on each store appears on every other family, or is hidden without loss where an agreement requires it |
| [PLT-030](#65-mobile-thermals-storage-and-streaming-install) | A fresh tier C install is 8 GB or less, and the player reaches gameplay in Halcyon without any further download |
| [PLT-033](#65-mobile-thermals-storage-and-streaming-install) | 30-minute soak on the minimum tier C device at 30 °C ambient: the frame rate never drops below 25 fps |
| [PLT-040](#66-launch-readiness-gates) | Staged-launch drill: a late family joins the live world with no data migration |

<!-- citation links: generated, do not edit by hand -->

[L19]: ../../references/legal-and-policy.md
[L20]: ../../references/legal-and-policy.md
[L27]: ../../references/legal-and-policy.md
[L28]: ../../references/legal-and-policy.md
[M32]: ../../references/industry-and-live-service.md
[M40]: ../../references/industry-and-live-service.md
[S1]: ../../references/technology-and-ai.md
[S3]: ../../references/technology-and-ai.md
[S4]: ../../references/technology-and-ai.md
[S5]: ../../references/technology-and-ai.md
[S16]: ../../references/technology-and-ai.md
[S19]: ../../references/technology-and-ai.md
[S20]: ../../references/technology-and-ai.md
[S21]: ../../references/technology-and-ai.md
[S22]: ../../references/technology-and-ai.md
[S23]: ../../references/technology-and-ai.md
[S24]: ../../references/technology-and-ai.md
[S25]: ../../references/technology-and-ai.md
[S26]: ../../references/technology-and-ai.md
[S27]: ../../references/technology-and-ai.md
[S28]: ../../references/technology-and-ai.md
[S29]: ../../references/technology-and-ai.md
[S30]: ../../references/technology-and-ai.md
[T22]: ../../references/technology-and-ai.md
[T24]: ../../references/technology-and-ai.md
[T32]: ../../references/technology-and-ai.md
