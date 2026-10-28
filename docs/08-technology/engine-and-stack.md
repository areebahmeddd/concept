# Engine and Stack

What we use from Unreal Engine 5.8, what we build ourselves, how Painted Realism renders on every tier, how we move to UE6, and which middleware and pipelines carry the decade.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Technical Director
>
> **Horizons:** H0 UE 5.8 source build, World Partition slice, Iris prototype, static cells, one Loom NPC · H1 full stack on every launch family, custom mesh and global services · H2 UE6 migration once its gate passes, dynamic cells · H3 VR renderer, per-entity authority
>
> **Related:** [D-003](../../DECISIONS.md#d-003) · [D-044](../../DECISIONS.md#d-044) · [D-047](../../DECISIONS.md#d-047) · [Server and Backend](server-and-backend.md) · [Platform Support](../09-platforms/platform-support.md) · [Tech Watch](tech-watch.md) · [AI Architecture](../06-ai/architecture.md)

## 1. Principles

1. **The design is never limited by the engine** ([D-003](../../DECISIONS.md#d-003)). Where Unreal lacks something we need (server meshing at our scale, a global world state, AI under rule zero), we build it.
2. **We own the core simulation.** Persistent-world middleware has failed its users before: SpatialOS, Worlds Adrift and the Unity terms change [M1] [M2] [M3]. The mesh, world state, ledger and Loom are ours.
3. **Gameplay is kept apart from engine networking**, so a move to UE6 or a change to Iris doesn't mean rewriting the game.
4. **Fun and stability come before fidelity.** FFXIV 1.0 failed on an obsession with graphics and was relaunched [M24] [M25]. Rendering ambition never costs frame-time stability on the reference tier.
5. **Everything can run offline for Archive Mode.** Every custom service has a single-machine version, so a legacy build can exist ([D-047](../../DECISIONS.md#d-047); precedents [R19] [R20] [T41]).

## 2. UE 5.8 baseline

UE 5.8, released on 17-06-2026, is "the last planned major Unreal Engine 5 release" [S2].

| Feature | Verified state | How we use it | Risk |
| --- | --- | --- | --- |
| **World Partition**, Data Layers, Level Instances [S8] | Grid streaming, Data Layers, Level Instances, server streaming settings | Each world region is a World Partition world. Data Layers carry eras (a Domain before and after its Celestial is freed) and phases (personal story variants). Level Instances hold reusable settlements and Wayshrines. | Server streaming must line up with our static cells |
| **Large World Coordinates** [S6] | Double precision; default WORLD_MAX of 88 million km | The planet's surface, low orbit and Lumen share one coordinate space ([Cosmology: Scale](../02-world/cosmology.md#7-scale)) | Shader and physics precision at moon distances is tested in H0 |
| **Iris replication** [S1] [S7] | The 5.8 release notes call it "production-ready for licensees" [S1]; its documentation is still marked Experimental [S7] | Relevance filtering and prioritisation inside a cell server | The two sources disagree, so the classic replication path stays buildable until Iris passes its H0 gate ([TEC-003](#2-ue-58-baseline)) |
| **Mass Entity** [T7] | Data-oriented entity system (MassCrowd, ZoneGraph) | Ambient crowds, wildlife herds and Iron Meridian traffic. Named NPCs with Minds stay full actors. | Handing a Mass agent over to a full actor when a player engages |
| **Chaos** physics and destruction [S10] | Its documentation gives no networking guidance | Destruction that matters to gameplay uses discrete server-held states (intact, damaged, destroyed); fracture detail is cosmetic and runs on the client | Netcode for physics-heavy Frames and colossi ([Server and Backend: Netcode](server-and-backend.md#3-netcode)) |
| **Replay system** (DemoNetDriver) [S11], with file, memory and HTTP streamers [T30] | Supported | Server-side compact replays for replay-first capture ([D-037](../../DECISIONS.md#d-037)), Chronicles ([D-030](../../DECISIONS.md#d-030)) and moderation evidence | Replay size and storage cost per player-hour |
| **Dedicated servers** [S9] | Need a source build | We keep an engine fork from day one, merging each Epic release | Fork drift, kept small by a minimal patch set |
| **MetaHuman** | Unreal's character-creation toolset | Facial capture for main-story performers; final faces are stylised to Painted Realism ([TEC-013](#2-ue-58-baseline)) | Fit with our style and tier C, tested in H0 |
| **Lumen and Nanite** [S3] [S4] [S5] | Not available on every tier | Lighting and geometry on tiers A and B ([rendering across tiers](#4-rendering-painted-realism-across-tiers)) | Tier C and X need another lighting path |

- **TEC-003 [H0]** Iris is the H1 replication path if the H0 prototype meets its bandwidth and stability budgets on every launch family. If it doesn't, H1 ships on classic replication and Iris moves to H2.
- **TEC-013 [H0]** MetaHuman is the facial-capture pipeline for main-story performers, retargeted onto stylised Painted Realism faces. Runtime faces on tier C use reduced rigs and LODs, and the Art Director signs off the look on a tier C device in H0.

## 3. Custom systems we build

| System | Why the engine doesn't cover it | Specified in |
| --- | --- | --- |
| **Capability-tier content pipeline** | One content set cooked for four tiers | [Rendering across tiers](#4-rendering-painted-realism-across-tiers), [Tooling and pipelines](#9-tooling-and-pipelines) |
| **Chronicle service** | Curated replays of global events with participant inscriptions | [Recording and Replays](../05-systems/recording-and-replays.md) |
| **Convergence and shared-pool service** | Global moments merged across layers | [Celestial Convergence](../05-systems/celestial-convergence.md) |
| **Economy ledger** | Double-entry, audited ledger of items and Omnis that prevents duplication [M12] | [Server and Backend: Economy ledger](server-and-backend.md#4-economy-ledger) |
| **Global world-state service** | G- and S-class state across every layer and DC region | [Server and Backend](server-and-backend.md) |
| **Law evaluator** | Natural and Civic Law queries (`can(actor, action, place)`) used by every system | [World Laws](../02-world/world-laws.md), [Law, Crime and Bounties](../05-systems/law-crime-and-bounties.md) |
| **The Loom** (Minds, speech acts, Validator, Weaver) | AI under rule zero ([D-042](../../DECISIONS.md#d-042)) | [AI Architecture](../06-ai/architecture.md) |
| **Mesh and handoff** (cell servers, boundary handoff, layer service) | The engine's multi-server replication is experimental [T6] and dynamic meshing is frontier work [T1] | [World Model](../07-multiplayer/world-model.md), [Server and Backend: Meshing](server-and-backend.md#2-meshing) |

- **TEC-001 [H1]** Each custom system has a versioned interface and a single-process local version used for tests, offline development and Archive Mode.
- **TEC-002 [H1]** Gameplay code calls custom services and the Law evaluator through interfaces, never through engine networking internals, so the replication layer can be swapped.

## 4. Rendering Painted Realism across tiers

Painted Realism ([D-044](../../DECISIONS.md#d-044), [Art and Audio Direction](../01-vision/art-and-audio-direction.md)) suits a wide device range, because a painterly finish hides simplification well. There are two lighting paths: Lumen on tiers A and B, and a probe path for tier B where frame time needs it, and for tiers C and X. Tier definitions are in [Platform Support: Capability tiers](../09-platforms/platform-support.md#62-capability-tiers).

| Tier | Global illumination | Geometry | Why |
| --- | --- | --- | --- |
| **A** high-end PC, current consoles | Lumen | Nanite | Full painterly post-processing |
| **B** Switch 2, handhelds, Series S class | Lumen at reduced settings, or the probe path where frame time requires it | Nanite where supported, otherwise authored LODs | Switch 2 and Xbox Series are named Lumen targets [S3]; the probe path always ships |
| **C** high-end mobile | Probe path: precomputed probe sets for each slice of the 100-minute day, blended over time ([D-013](../../DECISIONS.md#d-013)), plus stylised dynamic lights for Arts | Authored LODs and impostors | Lumen on mobile covers Android Vulkan only and is experimental [S4]; Infinity Nikki shipped a UE5 open world on iOS and Android [S16] |
| **X** VR [H3] | Probe path | Authored LODs | Lumen has no VR support [S3]; Quest's UE5 support launched without Nanite or Lumen [S5] |

- **TEC-010 [H0]** A painterly lighting R&D track proves the probe path on a tier C device during H0.
- **TEC-011 [H1]** Gameplay-critical signals ([ART-002](../01-vision/art-and-audio-direction.md#1-visual-direction-painted-realism) reserved colours, attack tells) look the same on every tier, and automated screenshot comparisons per tier gate content.
- **TEC-012 [H1]** Every asset ships with tier C LODs; a missing LOD fails the build.

## 5. UE6 migration

UE 5.8 is the last planned UE5 major release [S2]. UE6 has no confirmed release date ([Tech Watch](tech-watch.md#2-tracker), TW-01). H0 starts on UE 5.8, and we migrate when a gate passes, not on a date.

| Step | When | Gate |
| --- | --- | --- |
| 1. Enforce the engine-isolation rule ([TEC-002](#3-custom-systems-we-build)) through code review and module boundaries | From H0 | Static check: no gameplay module includes replication internals |
| 2. Run the H0 slice on each UE6 preview in a branch | When previews exist | The slice boots, streams and replicates |
| 3. Choose between starting H1 on UE6 and migrating after launch | End of H0 | UE6 has dedicated servers, World Partition or an equivalent, mobile and Switch 2 support, and a stable replication path |
| 4. Migrate | No later than 18 months before H1 certification | Every launch family passes its performance gates on UE6 |
| 5. Take later major versions | H2 | Only between Convergences, never within 60 days of a Long Night |

## 6. Alternatives considered

| Option | Evidence | Why not chosen |
| --- | --- | --- |
| **Proprietary engine** | CDPR's new Witcher is on UE5 [S13] [S14]; Halo Studios moved to UE5 [S15] | Studios with their own engines are moving to UE5; building one would spend our budget on work that doesn't set us apart |
| **UE4-class mobile-first engine** | Wuthering Waves ships on UE4, including mobile [S17] | A mid-2030s launch needs a current engine |
| **Unity** | Genshin Impact runs on Unity [S18], proving a cross-platform open world | The engine choice is confirmed ([D-003](../../DECISIONS.md#d-003)); our streaming and large-coordinate needs fit UE; the 2019 terms episode is a vendor-risk warning [M2] |

## 7. Middleware and services

| Need | Choice | Notes |
| --- | --- | --- |
| Cross-platform accounts, lobbies and voice | A managed cross-platform service of the Epic Online Services class [T31], with voice included [T26] | Behind our own identity layer and an abstraction; our own voice relays are the exit plan |
| Guard models and structured output | As specified in [AI Architecture](../06-ai/architecture.md) and [AI Safety and Evaluation](../06-ai/safety-and-evaluation.md) | Pinned per release |
| On-device small models | NVIDIA In-Game Inferencing on supporting PCs [T22] [T23]; Apple Foundation Models on Apple devices [T24] | Cloud fallback everywhere else |
| Speech-to-text (player transcripts, voice to NPCs) | On-device recognition where the platform has it [T9]; otherwise Whisper-class open-weight models [T8] in our own DC regions | Under-18 NPC voice never uses the cloud path ([NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md)) |
| Text-to-speech (NPC lines, accessibility) | Licensed, consent-based voice marketplaces [T10] | Replica Studios shut down in 2025 [T11] [T12], so voice rights and models stay portable ([D-043](../../DECISIONS.md#d-043)) |
| Voice moderation | A toxicity classifier run on our relays ([Safety and Moderation](../07-multiplayer/safety-and-moderation.md#63-voice-moderation)) | No vendor keeps audio |

- **TEC-020 [H1]** No middleware is the only holder of player identity, inventory, world state or voice rights. Each integration has a written exit plan before it starts.

## 8. Licensing

- Epic's "Launch Everywhere" programme cites a 3.5% royalty from 2025 [S12]. The business plan budgets the engine royalty at that rate on all revenue (cosmetics and the Patron subscription, [D-045](../../DECISIONS.md#d-045)), plus each store's fee. [Tech Watch](tech-watch.md#2-tracker) re-checks the terms (TW-16).
- Open-weight model licences and voice licences are reviewed with every release ([Legal and Compliance](../12-legal/compliance.md)).

## 9. Tooling and pipelines

| Area | Approach |
| --- | --- |
| AI pipeline | Model versions pinned per release, with Validator regression suites, because model output isn't reproducible [A24] |
| Automated testing | Bot clients for load and gameplay, performance captures per tier, and replay-based regression ([Testing and Acceptance](../10-testing/testing-and-acceptance.md)) |
| Content cooking | One source content set cooked per tier (A, B, C, X), with automated LOD, texture and shader budgets |
| Localisation | String tables and the pipeline for generated content ([Controls, Camera and Accessibility: Localisation](../09-platforms/controls-camera-and-accessibility.md#67-localisation)) |
| Profiling | Unreal Insights captures on every tier in CI; frame-time budgets fail builds |
| Source and build | The engine fork and the game in one monorepo; a build farm producing every family nightly; dedicated servers built from source [S9] |
| World building | World Partition with lint rules: cell-boundary seams, Data Layer naming for eras and phases, Wayshrine density, traversal checks |

## 10. Acceptance criteria

| ID | Test |
| --- | --- |
| [TEC-001](#3-custom-systems-we-build) | Each custom service passes its contract tests against both its cloud and local versions |
| [TEC-002](#3-custom-systems-we-build) | Static analysis: no gameplay module depends on replication internals |
| [TEC-003](#2-ue-58-baseline) | H0 Iris prototype: replication bandwidth and server frame time within budget for a 200-player layer on every launch family |
| [TEC-010](#4-rendering-painted-realism-across-tiers) | H0: a probe-path Hearthlands slice runs at 30 fps for 30 minutes on the reference tier C device, and the Art Director judges it on-style |
| [TEC-011](#4-rendering-painted-realism-across-tiers) | Screenshot comparison per tier: reserved-colour signals within ΔE 3 across tiers |
| [TEC-012](#4-rendering-painted-realism-across-tiers) | The build fails on any asset without tier C LODs |
| [TEC-013](#2-ue-58-baseline) | H0: a captured main-story performance plays on a stylised face at tier A and tier C, and the Art Director signs off both |
| Large worlds | A Skyferry flight from Halcyon to Lumen shows no visible jitter in characters or effects with the camera at 1 m |

<!-- citation links: generated, do not edit by hand -->

[A24]: ../../references/technology-and-ai.md
[M1]: ../../references/industry-and-live-service.md
[M2]: ../../references/industry-and-live-service.md
[M3]: ../../references/industry-and-live-service.md
[M12]: ../../references/industry-and-live-service.md
[M24]: ../../references/industry-and-live-service.md
[M25]: ../../references/industry-and-live-service.md
[R19]: ../../references/ready-player-and-lifecycle.md
[R20]: ../../references/ready-player-and-lifecycle.md
[S1]: ../../references/technology-and-ai.md
[S2]: ../../references/technology-and-ai.md
[S3]: ../../references/technology-and-ai.md
[S4]: ../../references/technology-and-ai.md
[S5]: ../../references/technology-and-ai.md
[S6]: ../../references/technology-and-ai.md
[S7]: ../../references/technology-and-ai.md
[S8]: ../../references/technology-and-ai.md
[S9]: ../../references/technology-and-ai.md
[S10]: ../../references/technology-and-ai.md
[S11]: ../../references/technology-and-ai.md
[S12]: ../../references/technology-and-ai.md
[S13]: ../../references/technology-and-ai.md
[S14]: ../../references/technology-and-ai.md
[S15]: ../../references/technology-and-ai.md
[S16]: ../../references/technology-and-ai.md
[S17]: ../../references/technology-and-ai.md
[S18]: ../../references/technology-and-ai.md
[T1]: ../../references/technology-and-ai.md
[T6]: ../../references/technology-and-ai.md
[T7]: ../../references/technology-and-ai.md
[T8]: ../../references/technology-and-ai.md
[T9]: ../../references/technology-and-ai.md
[T10]: ../../references/technology-and-ai.md
[T11]: ../../references/technology-and-ai.md
[T12]: ../../references/technology-and-ai.md
[T22]: ../../references/technology-and-ai.md
[T23]: ../../references/technology-and-ai.md
[T24]: ../../references/technology-and-ai.md
[T26]: ../../references/technology-and-ai.md
[T30]: ../../references/technology-and-ai.md
[T31]: ../../references/technology-and-ai.md
[T41]: ../../references/technology-and-ai.md
