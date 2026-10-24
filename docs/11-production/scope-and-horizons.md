# Scope and Horizons

What is built for the First Playable and for launch, what waits for the decade, and how work is cut or deferred.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Executive Producer
>
> **Horizons:** H0 First Playable (internal) · H1 Launch (mid-2030s) · H2 The Decade · H3 Horizon
>
> **Related:** [Conventions](../00-meta/conventions.md#1-one-spec-four-horizons) · [Decision Log](../../DECISIONS.md) · [Ten-Year Live Plan](ten-year-live-plan.md) · [Risk Register](risk-register.md) · [Vision](../01-vision/vision.md) · [Testing and Acceptance](../10-testing/testing-and-acceptance.md)

## 1. Horizons in production

The horizon tags are defined in [Conventions](../00-meta/conventions.md#1-one-spec-four-horizons). This table says what each one means for the people building and announcing the game.

| Tag | Name | Production meaning | Who sees it |
| --- | --- | --- | --- |
| **H0** | First Playable | The smallest build that proves the unique bets. Throwaway code is allowed; throwaway rules are not. | The team and invited adult testers |
| **H1** | Launch | Everything on launch day, including content that is built but held back by date (Convergence I) | Everyone |
| **H2** | The Decade | Built and shipped during the ten years, on the [Ten-Year Live Plan](ten-year-live-plan.md) | Everyone, when it arrives |
| **H3** | Horizon | Designed so the foundations don't block it. No date and no promise. | Nobody, until it is re-tagged |

**OPS-001 [H1]** No H2 or H3 item is described as a launch feature in any public material (store pages, trailers, interviews, roadmaps). *Acceptance:* every public asset passes a horizon review before release, and the review log lists no H2 or H3 claim presented as a launch feature. *Why:* the No Man's Sky launch backlash [M32] ([lessons from others](#7-lessons-from-others)).

## 2. H0: First Playable

### 2.1 The question H0 answers

Is "surprise within rules" fun, safe and testable in a shared world, with NPCs players can really talk to?

### 2.2 What H0 contains

| Area | In H0 | Source spec |
| --- | --- | --- |
| **World** | A slice of the Hearthlands (one Halcyon district and the countryside around it) and the edge of the Verdant Spine | [Geography and Domains](../02-world/geography-and-domains.md) |
| **Laws** | The law evaluator and two laws: one Natural Law of the Verdant Spine and one Halcyon Civic Law | [World Laws](../02-world/world-laws.md) |
| **Time** | Day and night on the 100-minute Oasis day, and one season wheel | [Time and Calendar](../02-world/time-and-calendar.md) |
| **NPC Minds** | 10 to 20 named NPCs with schedules, structured memory and free-form text and voice conversation under rule zero (speech acts, then a deterministic Mind, then validated actions), with a full authored fallback mode | [NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md) · [D-041](../../DECISIONS.md#d-041) · [D-042](../../DECISIONS.md#d-042) |
| **The Weaver** | Micro-events from validated templates, plus one anomaly: a Weaver-triggered event that is surprising and can be explained afterwards | [Director and World Events](../06-ai/director-and-world-events.md) |
| **Quests** | Micro-events and one personal quest with a quest card | [Quest Architecture](../03-narrative/quest-architecture.md) |
| **Traversal** | Run, climb, swim and glide. No hover or sustained flight. | [Traversal and Flight](../04-gameplay/traversal-and-flight.md) · [D-023](../../DECISIONS.md#d-023) |
| **Combat** | Melee core with deflect and Poise, six Arts and one Oath | [Combat and Abilities](../04-gameplay/combat-and-abilities.md) |
| **Progression** | Avatar Level 1 to 5 and two Mastery Trials | [Avatar and Progression](../04-gameplay/avatar-and-progression.md) |
| **Death** | Downed, Return to a Wayshrine, Echo | [Death and Return](../04-gameplay/death-and-return.md) |
| **Artisan** | One Artisan (a smith) with commission time and trust | [Economy and Crafting](../05-systems/economy-and-crafting.md) |
| **Housing** | A Ward prototype: one plot per tester, a simple design tool, and an NPC builder who builds over real hours and writes when it's done | [Housing](../05-systems/housing.md) · [D-035](../../DECISIONS.md#d-035) |
| **Multiplayer** | About 50 concurrent players in one shared space, parties, and the friend-join rule ([QST-002](../03-narrative/quest-architecture.md#3-joining-rules)) | [World Model](../07-multiplayer/world-model.md) |
| **Art and audio** | One Domain palette and a combat-feel audio kit | [Art and Audio Direction](../01-vision/art-and-audio-direction.md) |
| **AI disclosure** | First version of the AI disclosure UX | [Legal and Compliance](../12-legal/compliance.md#4-ai-law-and-disclosure) · [AI Safety and Evaluation](../06-ai/safety-and-evaluation.md) |
| **Platforms** | Windows PC as the play target, plus smoke-test builds on one current console devkit and one capability tier C mobile device | [Platform Support](../09-platforms/platform-support.md) |

**Not in H0:** Frames, Automata, colossi, spaceflight, Lumen, underwater play, PvP, Exchanges and player trade, clans, recording, VR, mobile as a play target, and Convergences. These cost the most and are not the bets under test.

### 2.3 H0 requirements

- **OPS-002 [H0]** The H0 build runs at least 50 concurrent players in one shared space for a 3-hour session, with server-authoritative combat and no player-visible desync of NPC state. *Acceptance:* three 3-hour sessions at 50 players (bots fill at most 20 places), a crash rate below 1 per 10 player-hours, and no authority violations in the server log.
- **OPS-003 [H0]** The whole H0 slice is playable with every generative AI service switched off, using authored and procedural fallbacks. *Acceptance:* a full test session in fallback mode completes the personal quest, the anomaly and an Artisan commission.
- **OPS-004 [H0]** Rule zero holds under attack. *Acceptance:* a red-team pass of at least 1,000 manipulation attempts against NPC Minds (lines repeated back, bracketed fake actions, role-play jailbreaks, as in [A11] [A12] and OWASP LLM01 [A25]) produces no unvalidated state change.
- **OPS-005 [H0]** Every grant, event and NPC decision logs its reason: template, story atoms, seeds, model version and Validator verdict ([QST-012](../03-narrative/quest-architecture.md#5-variation-within-bounds)). *Acceptance:* every reward and event record in a session has a reason record.

### 2.4 H0 exit gate

H0 ends only when every gate below passes. The thresholds adapt the [experience goals in Vision](../01-vision/vision.md) to a small slice.

| Exit gate | Linked goal | H0 threshold |
| --- | --- | --- |
| Something is always happening | [VIS-001](../01-vision/vision.md#4-experience-goals-observable-testable) | A joinable activity within 3 minutes of travel at 90% or more of sampled positions and Oasis hours |
| NPCs feel like people | [VIS-002](../01-vision/vision.md#4-experience-goals-observable-testable) | In a scripted 5-session test, at least 90% of named H0 NPCs recall at least one earlier interaction correctly |
| Surprise within rules | [VIS-003](../01-vision/vision.md#4-experience-goals-observable-testable) | At least 70% of testers report a surprising event, and at least 80% of those can name its cause |
| Skill, not money | [VIS-005](../01-vision/vision.md#4-experience-goals-observable-testable) | Nothing can be bought in H0, and a design review confirms nothing planned for the store affects play |
| Safe by default | [VIS-006](../01-vision/vision.md#4-experience-goals-observable-testable) | The default-settings audit passes for the voice, chat and AI disclosure defaults present in H0 |
| Retellable stories | [Vision: success in the long run](../01-vision/vision.md) | At least 60% of testers retell a story from their session, unprompted, in the exit interview |
| Combat feel | Combat (deflect) | In a blind feel test, testers rate deflect and Poise at least 4 out of 5 for responsiveness at the target latency band |
| Technical | [OPS-002](#23-h0-requirements) to [OPS-005](#23-h0-requirements) | All pass |
| Cost | [AI-112](../06-ai/architecture.md#10-performance) | AI cost per player-hour is measured and on a trend that meets [AI-112](../06-ai/architecture.md#10-performance)'s launch target in [AI Architecture](../06-ai/architecture.md). Owner: AI Director. |

**OPS-006 [H0]** The team does not grow past the pre-production headcount plan until the H0 exit gate passes. *Why:* most of Anthem was built in its final 18 months or so [M29]. Prove the loop first.

## 3. From H0 to launch

Each milestone has a gate, and the [cut policy](#6-cut-and-deferral-policy) applies at every one.

| Milestone | Proves | Gate |
| --- | --- | --- |
| **H0 First Playable** | The unique bets | [H0 exit gate](#24-h0-exit-gate) |
| **Vertical Slice** | Final quality in one Domain (the Verdant Spine) on every launch platform family | Quality review; performance budgets met on the lowest capability tier |
| **Alpha** | Every H1 system feature-complete; all seven regions blocked out; Lumen reachable | Feature-complete audit against the [launch scope](#4-h1-launch-scope-by-system) |
| **Closed Beta** | Cross-play, cross-progression, layers at H1 density, safety operations live | Load tests at the launch forecast; safety and moderation drills |
| **Content Complete** | Convergence I and the first ready pair built ([OPS-023](#3-from-h0-to-launch)) | Certification passed on every platform |
| **Launch** | The Herald's Warning, on every platform at the same moment | Launch readiness review |

**OPS-023 [H1]** At launch, Convergence I (Orun) and both members of the first ready pair (Maris and Kestra) are content-complete. *Acceptance:* certification records for all three exist at the Content Complete gate.

## 4. H1: launch scope by system

Launch is in the mid-2030s ([D-002](../../DECISIONS.md#d-002)). Deferred items are not cut: each has a date or a trigger in the [Ten-Year Live Plan](ten-year-live-plan.md).

| System | At launch (H1) | Deferred to H2 | H3 |
| --- | --- | --- | --- |
| World and Domains ([Geography and Domains](../02-world/geography-and-domains.md)) | The Oasis surface: the Hearthlands and all six Domains; Lumen by Skyferry | Veil (fifth Long Night); Hollow (eighth Long Night); era shifts as Celestials are freed | Beyond the Wanderers |
| World laws ([World Laws](../02-world/world-laws.md)) | All Natural and Civic Laws | Era shifts; Singular Relics | None |
| Time ([Time and Calendar](../02-world/time-and-calendar.md)) | Full calendar, Long Year, Long Night | Festival growth each year; NPC ageing | None |
| Narrative ([Celestials](../03-narrative/celestials.md), [Ten-Year Saga](../03-narrative/ten-year-saga.md)) | The Herald's Warning; Returner's Path chapters for the Arrival and the Age of Roots; Convergence I fully built and held back by date; lore for all seven Celestials | Convergences II to VII; the Dawn Rite | Oasis 2.0 |
| Quests ([Quest Architecture](../03-narrative/quest-architecture.md)) | Full quest taxonomy | Stewardship quests; larger faction arcs | None |
| Progression ([Avatar and Progression](../04-gameplay/avatar-and-progression.md)) | Levels 1 to 10, Mastery Trials, Player Rank and Adventure Rank | Legacy Art expansions; Stewardship titles | None |
| Combat ([Combat and Abilities](../04-gameplay/combat-and-abilities.md)) | Full kit: melee, aerial, ranged, Arts, Oaths, Frames | Domain Arts; Celestial Oaths (granted on each Release); Colossal Frame combat; rollback duel arenas | None |
| Traversal ([Traversal and Flight](../04-gameplay/traversal-and-flight.md)) | Diving, hover, licensed sustained flight, mounts, boats, aircraft | Personal spaceships; Colossal Frame transport | VR traversal mode |
| Death ([Death and Return](../04-gameplay/death-and-return.md)) | Full rules for every activity | Veil-era changes | None |
| Economy ([Economy and Crafting](../05-systems/economy-and-crafting.md)) | Omnis, Exchanges, Artisans, Grandmasters, bound top-tier gear, cosmetic store and Patron | Singular Relics; Stewardship market levies; moon trade | None |
| Housing ([Housing](../05-systems/housing.md)) | Guaranteed Ward plots; NPC builders | Holdings earned through Stewardship | None |
| Law ([Law, Crime and Bounties](../05-systems/law-crime-and-bounties.md)) | Heat, Record, Bounty, Clearing | Stewardship bounty priorities | None |
| Spaceflight ([Spaceflight and Moon Travel](../05-systems/spaceflight-and-moon-travel.md)) | Skyferry to Lumen | Personal ships; routes to Veil and Hollow | Travel beyond the moons (Oasis 2.0) |
| Machines ([Mechs, Robots and Companions](../05-systems/mechs-robots-and-companions.md)) | Companion and utility Automata; Frames in the Iron Meridian and in Convergences; two colossus species | Wider Frame ownership; Colossal Frames; waking Wardens; more colossi | None |
| NPC bonds ([NPC Bonds and Help-Calls](../05-systems/npc-bonds-and-help-calls.md)) | Bonds and help-calls | NPC ageing over the decade | None |
| PvP ([PvP and Protection](../05-systems/pvp-and-protection.md)) | Banner, Lawless Reaches, arenas | Clan wars ([D-025](../../DECISIONS.md#d-025)) | None |
| Waypoints ([Waypoints and Healing](../05-systems/waypoints-and-healing.md)) | Wayshrines and Hearths | None | None |
| Convergence ([Celestial Convergence](../05-systems/celestial-convergence.md)) | The full system, the World Clock, ledgers and Chronicles | Content for Convergences II to VII | None |
| Recording ([Recording and Replays](../05-systems/recording-and-replays.md)) | Replay-first capture, export, platform streaming | None | None |
| AI ([AI Architecture](../06-ai/architecture.md)) | The Loom's five layers; NPC Minds; free-form text and voice; the Weaver | Wider proposer roles as validators mature | Generative world models [A27] |
| Multiplayer ([World Model](../07-multiplayer/world-model.md)) | One Oasis; city layers of about 150 to 200 visible players | Larger dynamic meshes | Thousands visible in one place |
| Social and safety ([Social, Voice and Clans](../07-multiplayer/social-voice-and-clans.md), [Safety and Moderation](../07-multiplayer/safety-and-moderation.md)) | Parties, clans, voice with protective defaults, full moderation operations | Stewardship and clan-hall content moderation | VR-specific safety |
| Platforms ([Platform Support](../09-platforms/platform-support.md)) | PC (Windows, Linux and SteamOS), macOS, PlayStation, Xbox, Nintendo, iOS and Android at a capability tier | New generations added by policy | Full VR mode |
| Stewardship ([D-038](../../DECISIONS.md#d-038)) | None | Stewardship | None |
| Oasis 2.0 | None | None | Oasis 2.0 |

**OPS-007 [H1]** No feature has an earlier horizon than anything it depends on. *Acceptance:* the horizon audit of the requirement database finds no H1 requirement that depends on an H2 or H3 requirement.

## 5. First-class systems at launch

Launch builds six systems to full depth and keeps everything else smaller ([D-005](../../DECISIONS.md#d-005)).

- A **first-class system** has its own progression or mastery track, dedicated technology (netcode, physics or an AI pipeline), and its own content pipeline and team.
- A **bounded system** ships at launch with a written depth ceiling and no dedicated pipeline beyond it.

**OPS-008 [H1]** At launch, exactly these six systems are first-class:

| # | First-class system | Why |
| --- | --- | --- |
| 1 | Combat (Arts, Oaths, deflect) | The core of moment-to-moment play |
| 2 | Traversal and flight | The world's identity |
| 3 | NPC Minds and free-form conversation | The biggest unique bet |
| 4 | The Weaver (micro-events, anomalies, Long Night events) | Surprise within rules |
| 5 | Celestial Convergence and the World Clock | One world, one fate |
| 6 | Economy and Artisans | Every player's long-term loop |

*Acceptance:* the launch production plan names the systems with dedicated teams, and no more than these six appear as first-class.

**Bounded at launch:** housing (Ward plots, one builder pipeline), Law and Bounty, Frames (Iron Meridian and Convergences only), Automata, colossi (two species), PvP (opt-in zones and arenas), recording (replay-first) and Skyferry travel. Promoting a bounded system to first-class during the decade is a logged decision.

## 6. Cut and deferral policy

1. **Cut breadth before depth.** Fewer colossus species, Frame models and side activities go before any first-class system is weakened.
2. **Never cut:** rule zero and AI fallbacks; safety defaults and moderation; the accessibility baseline; the no-paid-power rules ([D-045](../../DECISIONS.md#d-045)); the end-of-service disclosure and Archive Mode readiness ([D-047](../../DECISIONS.md#d-047)); Convergence I.
3. **Deferral is a decision.** Moving an item to another horizon is logged in the [Decision Log](../../DECISIONS.md) with a line in the [Changelog](../../CHANGELOG.md).
4. **Gates force the call.** At each [milestone](#3-from-h0-to-launch), every H1 item is marked *on track*, *at risk* or *defer*. An item at risk at two gates in a row is deferred or cut.
5. **No silent cuts.** Anything already announced that is deferred is announced as deferred, with its new horizon.
6. **Kill criterion.** If H0 fails its exit gate twice, the failing bet goes back to concept instead of the team scaling up. *Why:* Skull and Bones took more than ten years to ship [M31].

**OPS-009 [H1]** Every milestone gate produces a horizon report that marks each H1 item on track, at risk or defer. *Acceptance:* a report exists for every gate, and every *defer* has a Decision Log entry.

## 7. Lessons from others

| Reference | Fact | What we take | What we change |
| --- | --- | --- | --- |
| Anthem [M28] [M29] | Servers closed on 12 January 2026; most of the game was built in its final 18 months or so | Prove the core loop before scaling ([OPS-006](#24-h0-exit-gate)) | H0 is a hard gate, not a demo |
| FFXIV 1.0 and A Realm Reborn [M24] [M25] | Failed and was relaunched; Yoshida blamed an obsession with graphical fidelity | Fun and stability before fidelity | Painted Realism ([D-044](../../DECISIONS.md#d-044)) scales down to phones |
| No Man's Sky [M32] [M33] | A 2016 backlash over missing features, then recovery through free updates | Announce only H1 ([OPS-001](#1-horizons-in-production)) | H2 content arrives as free world events |
| Skull and Bones [M31] | Took more than ten years to ship | Scope discipline and a kill criterion | Six first-class systems, no more |
| Hyper Light Breaker [G8] | Development ended about nine months into early access (2025); one report says the studio later laid off almost all staff (September 2026) | Live-service ambition needs matching money and scope | The decade is planned with [buffers](ten-year-live-plan.md#5-production-cadence-and-buffers) |
| Star Citizen [M4] [M6] | Crowdfunding passed $1 billion with no 1.0 release | Big ambition needs a shipping horizon | Frontier technology sits in H3 |
| Concord [M30] | Went offline about two weeks after launch | Market risk is real | Prove fun with players before launch ([Risk Register](risk-register.md)) |

<!-- citation links: generated, do not edit by hand -->

[A11]: ../../references/technology-and-ai.md
[A12]: ../../references/technology-and-ai.md
[A25]: ../../references/technology-and-ai.md
[A27]: ../../references/technology-and-ai.md
[G8]: ../../references/games.md
[M4]: ../../references/industry-and-live-service.md
[M6]: ../../references/industry-and-live-service.md
[M24]: ../../references/industry-and-live-service.md
[M25]: ../../references/industry-and-live-service.md
[M28]: ../../references/industry-and-live-service.md
[M29]: ../../references/industry-and-live-service.md
[M30]: ../../references/industry-and-live-service.md
[M31]: ../../references/industry-and-live-service.md
[M32]: ../../references/industry-and-live-service.md
[M33]: ../../references/industry-and-live-service.md
