# Decision Log

Every decision that shapes more than one document: what was decided, why, and where the detail lives. If a spec disagrees with this log, the log wins until the spec is fixed.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Design lead
>
> Every decision is in force unless it is marked **Superseded**, with a link to the decision that replaces it. Ideas that were considered and declined go in a **Declined** section, with the reason. How changes are proposed: [Contributing](CONTRIBUTING.md).

## Index

| Theme | Decisions |
| --- | --- |
| [Project](#project) | [D-001](#d-001) one spec, four horizons · [D-002](#d-002) mid-2030s launch · [D-003](#d-003) Unreal Engine 5.8 · [D-004](#d-004) working names · [D-005](#d-005) launch scope |
| [Audience and platforms](#audience-and-platforms) | [D-006](#d-006) 13+ · [D-007](#d-007) global release · [D-008](#d-008) minors' chat defaults · [D-009](#d-009) platform policy |
| [World and story](#world-and-story) | [D-010](#d-010) the Seven Celestials · [D-011](#d-011) the Ten-Year Saga · [D-012](#d-012) nature of the Oasis · [D-013](#d-013) time · [D-014](#d-014) canon names · [D-015](#d-015) Avatar references · [D-016](#d-016) Convergence order · [D-017](#d-017) Zero's fate · [D-018](#d-018) what is published |
| [Players and play](#players-and-play) | [D-019](#d-019) one avatar · [D-020](#d-020) camera · [D-021](#d-021) levels and ranks · [D-022](#d-022) death · [D-023](#d-023) flight · [D-024](#d-024) solo play · [D-025](#d-025) PvP · [D-026](#d-026) Arts and Oaths · [D-027](#d-027) the first hour |
| [The shared world](#the-shared-world) | [D-028](#d-028) One Oasis · [D-029](#d-029) no host-world co-op · [D-030](#d-030) global events · [D-031](#d-031) NPC scarcity · [D-032](#d-032) NPC mortality |
| [Systems](#systems) | [D-033](#d-033) moons and spaceflight · [D-034](#d-034) law and wanted posters · [D-035](#d-035) housing · [D-036](#d-036) machines and colossi · [D-037](#d-037) recording · [D-038](#d-038) Stewardship · [D-039](#d-039) nothing owned is lost forever · [D-040](#d-040) one Convergence at a time |
| [AI](#ai) | [D-041](#d-041) free-form conversation · [D-042](#d-042) rule zero · [D-043](#d-043) NPC voices |
| [Look, business and lifecycle](#look-business-and-lifecycle) | [D-044](#d-044) Painted Realism · [D-045](#d-045) business model · [D-046](#d-046) economy · [D-047](#d-047) Archive Mode · [D-048](#d-048) after success · [D-049](#d-049) launch regions |
| [Declined](#declined) | None yet |

---

## Project

<a id="d-001"></a>

### D-001 · One spec, four horizons

One specification that is ambitious and grounded at the same time, rather than separate "dream" and "buildable" versions. Every feature carries a horizon tag: H0 First Playable, H1 Launch, H2 The Decade, H3 Horizon.

*Why:* two parallel documents drift apart. Tags keep the ambition and its timing visible in one place.

*Detail:* [Conventions](docs/00-meta/conventions.md#1-one-spec-four-horizons).

<a id="d-002"></a>

### D-002 · Launch in the mid-2030s

Platform and engine choices are written as policies ("generations still supported at launch") rather than device lists.

*Detail:* [Tech Watch](docs/08-technology/tech-watch.md).

<a id="d-003"></a>

### D-003 · Unreal Engine 5.8 baseline

Specs assume UE 5.8 features and terms. Design is never limited by the engine: where UE lacks something, such as server meshing at our scale, we build it. UE6 is a planned migration once it passes defined checks.

*Why:* UE 5.8 is the last planned major UE5 release [S2]. Its release notes call Iris production-ready [S1], although the Iris documentation still says Experimental [S7]. UE6 has no confirmed date.

*Detail:* [Engine and Stack](docs/08-technology/engine-and-stack.md).

<a id="d-004"></a>

### D-004 · Working names and permitted homages

"Ready Player Zero" and "the Oasis" are working names. A few deliberate homages to *Ready Player One* and to Marvel's Celestials are accepted while the names are provisional: the title, "Oasis", "Celestials", "Eggs" (hidden mysteries), the Chronicle Board (a public record of world-firsts) and the idea of a world-scale quest. Everything else is original. A trademark search is deferred.

*Detail:* [Legal and Compliance](docs/12-legal/compliance.md).

<a id="d-005"></a>

### D-005 · Six first-class systems at launch

Launch focuses on six systems built to full depth: combat, traversal and flight, NPC Minds, the Weaver, Convergence, and the economy with its Artisans. Everything else ships smaller at launch and grows through the decade.

*Why:* too many first-class systems at once is how large online games fail [M28] [M29].

*Detail:* [Scope and Horizons](docs/11-production/scope-and-horizons.md).

## Audience and platforms

<a id="d-006"></a>

### D-006 · Audience 13+, with depth adults enjoy

Target rating ESRB T / PEGI 12–16. Mature themes (loss, ambition, sacrifice, greed, war) are told with restraint, never shown explicitly. There is no nudity, no sexual content and no realistic real-world violence.

*Detail:* [Tone and Themes](docs/03-narrative/tone-and-themes.md).

<a id="d-007"></a>

### D-007 · Global release

The game is designed for release everywhere. Compliance follows the strictest common rules, and regional differences are configuration, never separate builds.

*Detail:* [Legal and Compliance](docs/12-legal/compliance.md), [Regulatory Watch](docs/12-legal/regulatory-watch.md).

<a id="d-008"></a>

### D-008 · Chat defaults for under-18s

For under-18 accounts, player voice chat and open text chat with non-friends are off by default. They can be switched on by affirmative opt-in with clear warnings, plus parental consent where the law requires it. Text with friends is on. Talking to NPCs by voice is also off by default for under-18s, and their audio never leaves the device. Typed conversation is always available.

*Why:* the FTC–Epic order covers both voice and text [L6].

*Detail:* [Social, Voice and Clans](docs/07-multiplayer/social-voice-and-clans.md), [Safety and Moderation](docs/07-multiplayer/safety-and-moderation.md).

<a id="d-009"></a>

### D-009 · Platform policy

One world on every platform, with cross-play and cross-progression. Support is defined by platform family: PC (Windows, Linux and SteamOS, including Steam Deck-class handhelds), macOS on Apple silicon, PlayStation 5 and later, Xbox Series X|S and later, Nintendo Switch 2 and later, iOS/iPadOS and Android at a published capability tier. At launch we support the generations their makers still support, and OS versions inside the vendor's security window. PS4 and Xbox One are out: Lumen doesn't run on them [S3], and launching on an old generation has gone badly before [S19]. A full VR mode is H3.

*Detail:* [Platform Support](docs/09-platforms/platform-support.md).

## World and story

<a id="d-010"></a>

### D-010 · The Seven Celestials

Six Celestials were once players ("Returners") who kept an Oath in service of others so faithfully that they ascended. Each is bound to one region, and one lives in the underwater region of three cities. The seventh, the **False Celestial**, was also a player. He defeated the six in a seven-day battle at a city now in ruins, took their power, and has controlled the Oasis unseen ever since. He once lived in an ordinary town. The six are chained, not evil: defeating one frees it, and a freed Celestial gives its Oath to everyone. The **Dawnkey**, the only thing that can stop the end of the world, is forged from the six freed Oaths and a seventh Oath sworn by the players themselves.

*Detail:* [Celestials](docs/03-narrative/celestials.md), [STORY.md](STORY.md).

<a id="d-011"></a>

### D-011 · The Ten-Year Saga

From launch, every player is told the Oasis will burn in ten years, when the Wanderer planets align and the sun breathes fire. Freeing all the Celestials together is everyone's endgame. The live servers really do close ten years after launch unless the players succeed. Success opens Oasis 2.0. Failure ends the world, with a time-travel coda.

Safeguards: progress is always visible on the World Clock; no single player or group can make the world fail; Convergences can be retried until the end; scaling rules are published.

*Detail:* [Ten-Year Saga](docs/03-narrative/ten-year-saga.md), [Ten-Year Live Plan](docs/11-production/ten-year-live-plan.md).

<a id="d-012"></a>

### D-012 · The nature of the Oasis stays ambiguous

What the Oasis really is (real, made, dreamed or remembered) is revealed in layers and never fully settled. Players are called **Returners** because they come back from death. Two readings of who they are always coexist: travellers from beyond the Oasis, or the world dreaming its own heroes. No reveal is allowed to say "it was all a simulation".

*Detail:* [Cosmology](docs/02-world/cosmology.md), [Reveal Graph](docs/03-narrative/reveal-graph.md).

<a id="d-013"></a>

### D-013 · Time

One Oasis day lasts 100 real minutes, so the in-game hour drifts through every time zone. The Long Year is one real year, starting at launch. The Long Night, when the three moons align, lasts 24 real hours on each launch anniversary. Regional seasons follow the moons and come round within weeks.

*Why:* a longer day than FFXIV's 70 minutes [M27], so NPC schedules matter, without tying anyone to one time of day.

*Detail:* [Time and Calendar](docs/02-world/time-and-calendar.md).

<a id="d-014"></a>

### D-014 · Canon names

The title and "Oasis" stay working names ([D-004](#d-004)).

| Thing | Name |
| --- | --- |
| Sun | Solace |
| Outer planets | the Wanderers |
| The ten-year event | the Great Conjunction |
| The yearly alignment | the Long Night |
| Moons | Lumen (known), Veil (mist-shrouded), Hollow (dark) |
| People of Lumen | the Lumenari |
| Players, in the world | Returners |
| Central region and capital | the Hearthlands; Halcyon, home of the Grand Library |
| Ruined battle city | Sennight (once Everbright) |
| The False Celestial's home town | Lowhaven |
| The key that saves the world | the Dawnkey |
| The global effort to free a Celestial | a Convergence |
| The AI system and its director | the Loom; the Weaver |

| # | Domain | Character | Celestial | Oath |
| --- | --- | --- | --- | --- |
| I | The Verdant Spine | Mountains and ancient forests | Orun, the Mountain That Walks | Perseverance |
| II | The Drowned Reach | Undersea, with the cities of Pelagia, Murmur and Saltglass | Maris, the Tide That Remembers | Compassion |
| III | The Stormcrown | Floating isles in an endless storm | Kestra, the Unbound Wind | Courage |
| IV | The Ember Wastes | Deserts of sun-glass | Sahr, the Lantern in the Dust | Sacrifice |
| V | The Iron Meridian | A machine megacity | Vantor, the First Engineer | Ingenuity |
| VI | The Frostmarch | Ice, aurora and old kingdoms | Ysolde, the Keeper of Hours | Memory |
| VII | Hollow, the dark moon | His refuge | The False Celestial (Zero) | Greed: a broken Oath |

<a id="d-015"></a>

### D-015 · "Avatar" means both works

We learn from James Cameron's *Avatar* for science-grounded ecology and bonded creatures [W16], and from *Avatar: The Last Airbender* for elements that shape a culture and a fighting style rooted in real martial arts [W15].

<a id="d-016"></a>

### D-016 · The order of the Convergences

Orun is always first, unsealed at the first Long Night. The community influences the order of Maris, Kestra, Sahr and Vantor, with two regions "ready" at a time. Ysolde is always last of the six, because freeing her reveals Zero's name. The False Celestial comes last of all, no earlier than eight and a half years after launch. Only Orun's Unseal is tied to a Long Night, so a missed window never costs a year.

*Detail:* [Celestial Convergence](docs/05-systems/celestial-convergence.md), [Ten-Year Live Plan](docs/11-production/ten-year-live-plan.md).

<a id="d-017"></a>

### D-017 · Zero's fate is decided by the players

In the final Convergence, the community decides whether Zero gives back what he stole or is destroyed. If at least 4 of its 6 phases are resolved through understanding rather than force, he returns the stolen Oaths and fades into Veil, remembered. Otherwise he is unmade. Either way the Dawnkey can be forged. The "understanding vs force" record is public throughout the decade, and what it means is revealed when the final Convergence opens.

*Detail:* [Celestials](docs/03-narrative/celestials.md).

<a id="d-018"></a>

### D-018 · What is published, and what stays secret

The earliest unseal dates are published one Age ahead. They can only ever move later, with at least 90 days' notice. Hidden canon is never scheduled publicly: the reveal graph releases it.

*Detail:* [Ten-Year Live Plan](docs/11-production/ten-year-live-plan.md), [Reveal Graph](docs/03-narrative/reveal-graph.md).

## Players and play

<a id="d-019"></a>

### D-019 · One persistent avatar

Each account has one avatar, with one identity and one history. Gear and cosmetics change how it looks and plays, never who it is. Some quests transform the avatar for a while, and everything is restored afterwards.

*Detail:* [Avatar and Progression](docs/04-gameplay/avatar-and-progression.md).

<a id="d-020"></a>

### D-020 · Switchable camera

Players can switch between first and third person outside specific encounters. Combat is designed for third person first. Competitive rulesets lock the perspective, because a third-person camera lets players see around cover [G14].

*Detail:* [Controls, Camera and Accessibility](docs/09-platforms/controls-camera-and-accessibility.md).

<a id="d-021"></a>

### D-021 · Levels and ranks

Avatar Level runs from 1 to 10, as does every Art, weapon and piece of gear. Each level is harder than the last, and levels 8 to 10 are gruelling by design: they need Mastery Trials (feats of skill, rare commissions, dangerous journeys), never repetitive grinding. Player Rank (general progress) and Adventure Rank (exploration and discovery) each run from 1 to 100. Nothing anywhere goes above 100, and ranks never grant combat power.

*Detail:* [Avatar and Progression](docs/04-gameplay/avatar-and-progression.md).

<a id="d-022"></a>

### D-022 · Death and Return

A fallen player is first Downed, with a short window for rescue. After that they Return to a Wayshrine of their choice. An Echo holding their unbanked goods stays where they fell, and only they can recover it. Gear wears a little. Equipped gear is never lost. Convergences carry no death penalty.

*Detail:* [Death and Return](docs/04-gameplay/death-and-return.md).

<a id="d-023"></a>

### D-023 · Flight is a skill and a licence

Gliding comes early. Hovering comes at Avatar Level 5. Sustained flight is licensed late, costs energy and obeys weather and airspace law. Aircraft and Frames have their own licences. Each region's Natural Law and each city's laws can limit altitude, type or speed.

*Why:* unrestricted flight hollows out ground play, as World of Warcraft found [M17].

*Detail:* [Traversal and Flight](docs/04-gameplay/traversal-and-flight.md).

<a id="d-024"></a>

### D-024 · Everything personal can be done solo

All personal content can be completed alone, with NPC allies filling any team roles [M26]. Every phase of a Convergence accepts solo contributions. "Finishing the game" means finishing your personal saga, the Returner's Path, and contributing to the world's.

*Detail:* [Quest Architecture](docs/03-narrative/quest-architecture.md).

<a id="d-025"></a>

### D-025 · PvP is opt-in

Players fight each other only by choice: in the Lawless Reaches, in arenas, in declared clan wars (H2) and when both raise their Banner. Hostile acts in lawful places go through the law system. Equipped gear is never lost. New players (Avatar Level 1 to 3) can't be attacked outside arenas; at Level 3 the Banner allows consensual duels only. Under-18 accounts can't be hunted by player bounty hunters, and their Echo can never be looted.

*Why:* most players choose protection when given the choice [M14] [M15] [M11].

*Detail:* [PvP and Protection](docs/05-systems/pvp-and-protection.md).

<a id="d-026"></a>

### D-026 · Resonance, Arts and Oaths

Resonance is the energy that powers abilities. Arts are techniques learned from mentors across the six regions, with no class lock. Oaths are constraints a player chooses in exchange for power (fight unarmed, never strike first, fight only at night). Breaking one has a cost. Oaths are also how the Celestials ascended, so the ability system and the central story share one idea. From launch, every Returner who keeps a declared Oath through a Convergence's Confront adds to the world's Resolve.

*Why:* drawn from Hunter x Hunter's vows and limitations [J3] and Jujutsu Kaisen's binding vows [J2].

*Detail:* [Combat and Abilities](docs/04-gameplay/combat-and-abilities.md).

<a id="d-027"></a>

### D-027 · The first hour

A new player wakes at a Wayshrine above Halcyon. Launch-day players see the Herald's Warning live. Later players relive it as a Chronicle. The World Clock appears within the first 15 minutes. The opening leads with warmth and wonder, then reveals the stakes.

*Detail:* [Core Loops](docs/04-gameplay/core-loops.md).

## The shared world

<a id="d-028"></a>

### D-028 · One Oasis

There is one world, and its canonical state (the countdown, the Celestials, the eras, the economy, the laws) is shared by every player on every platform. A mesh of servers simulates it. A crowded place runs as parallel layers. Friends and parties always share a layer, and so do clans, up to a layer's capacity, with one linked overflow layer. Global moments merge into one shared result. Personal story outcomes are phased for each player.

Targets: about 150 to 200 visible players in a city layer at H1, larger meshes at H2, thousands in one place at H3.

*Why:* proven by WoW's layering and phasing [M18] [M19] and Destiny's shared world [M42]. Single-shard middleware has failed before [M1] [M3].

*Detail:* [World Model](docs/07-multiplayer/world-model.md), [Server and Backend](docs/08-technology/server-and-backend.md).

<a id="d-029"></a>

### D-029 · No host-world co-op

There is no "visit my world" co-op. The world is always shared, and parties form inside it.

<a id="d-030"></a>

### D-030 · World events are global; side stories are personal

Freeing a Celestial happens once, for everyone. A player who arrives later has missed that moment, its live rewards and its world-first titles. Side stories and small events are personal and vary between players. NPC historians record every global event as a Chronicle. Anyone can relive a Chronicle with the real participants' names inscribed, for understanding and a keepsake, never for the original rewards.

*Detail:* [Quest Architecture](docs/03-narrative/quest-architecture.md), [Celestial Convergence](docs/05-systems/celestial-convergence.md).

<a id="d-031"></a>

### D-031 · NPCs are scarce in the world's own terms

NPCs feel limited through their schedules, journeys, trust and the time their work takes, never through queues behind other players. Each Grandmaster takes one commission per Returner per Oasis season (seven real days).

*Detail:* [Economy and Crafting](docs/05-systems/economy-and-crafting.md).

<a id="d-032"></a>

### D-032 · Who can die

No player can kill an NPC that other players share. Players can knock NPCs down, not kill them. Authored world deaths are rare (no more than three per Long Year) and always recorded as Chronicles. When an ordinary NPC's role passes on, an heir or apprentice takes over at half the trust. Essential services never disappear.

*Detail:* [NPC Bonds and Help-Calls](docs/05-systems/npc-bonds-and-help-calls.md).

## Systems

<a id="d-033"></a>

### D-033 · Moons and spaceflight

The moons are the only off-world destinations. Players reach them by public Skyferry or by their own very expensive spaceship. Ships launch only from authorised launch zones and land only in authorised landing zones. Flight is piloted, distances are compressed, and pilots must mind other traffic. Lumen is reachable by Skyferry from launch day. Personal ships arrive at the third Long Night. Veil opens at the fifth Long Night and Hollow at the eighth.

*Detail:* [Spaceflight and Moon Travel](docs/05-systems/spaceflight-and-moon-travel.md).

<a id="d-034"></a>

### D-034 · Law and wanted posters

Breaking the law brings Heat (immediate pursuit), then a Record and wanted posters, then a Bounty. Players can escape. They clear a Record by paying a fine at a Watch post, by surrendering, or by doing community service, so it is never only a matter of money. Real money is never involved.

*Why:* modelled on Red Dead Redemption 2's bounties [G2], GTA's pursuit [G1] and Elite Dangerous docking law [G15].

*Detail:* [Law, Crime and Bounties](docs/05-systems/law-crime-and-bounties.md).

<a id="d-035"></a>

### D-035 · Housing

Players design their house, NPC builders construct it over a few real hours, and the builder writes to them when it's done. Every Returner is guaranteed a plot in a Ward, a housing district attached to a town, so there is no plot lottery. Rare open-world Holdings are earned, never bought.

*Why:* FFXIV's plot scarcity forced a lottery [G16].

*Detail:* [Housing](docs/05-systems/housing.md).

<a id="d-036"></a>

### D-036 · Machines and colossi

At launch: companion and utility Automata, piloted Frames in the Iron Meridian and inside Convergences, and two colossus species as world events. Through the decade: wider Frame ownership, multi-crew Colossal Frames, more colossi and the waking Wardens.

*Detail:* [Machines and Colossi](docs/02-world/machines-and-colossi.md), [Mechs, Robots and Companions](docs/05-systems/mechs-robots-and-companions.md).

<a id="d-037"></a>

### D-037 · Recording replays first

The server keeps compact replays of each player's recent play. Players re-render any moment from any camera, including their character's eyes, and export it. Live streaming goes through platform services. Other players' voices are never captured without consent.

*Detail:* [Recording and Replays](docs/05-systems/recording-and-replays.md).

<a id="d-038"></a>

### D-038 · Stewardship

"Ruling a kingdom" is a Stewardship, opening at the second Long Night: a time-limited civic office over a town, earned through contribution and reputation. A Steward chooses festivals, bounty priorities and public works within published limits, and keeps a permanent title. Stewards can't set or raise taxes; they direct a share of the tax already collected to public works. A Steward can never harm other players or lock them out of services.

*Detail:* [Avatar and Progression](docs/04-gameplay/avatar-and-progression.md).

<a id="d-039"></a>

### D-039 · Nothing you own is lost forever

Equipped gear, ships, Frames and companions can be damaged, wrecked or withdrawn, but never permanently lost. Insurance, salvage and recovery always bring them back.

*Detail:* [Spaceflight and Moon Travel](docs/05-systems/spaceflight-and-moon-travel.md), [Mechs, Robots and Companions](docs/05-systems/mechs-robots-and-companions.md).

<a id="d-040"></a>

### D-040 · One Convergence at a time

Only one Convergence is in its Unseal or Confront phase at any moment, so the whole world fights together. Discover and Prepare can run for the ready pair in parallel. A world that is behind can unseal the next Convergence straight after a Release, with no minimum gap.

*Detail:* [Celestial Convergence](docs/05-systems/celestial-convergence.md), [Ten-Year Live Plan](docs/11-production/ten-year-live-plan.md).

## AI

<a id="d-041"></a>

### D-041 · Free-form conversation with NPCs

Players talk to NPCs in their own words, by text or voice, with no menu of generated options.

*Detail:* [NPC Minds and Conversation](docs/06-ai/npc-minds-and-conversation.md).

<a id="d-042"></a>

### D-042 · Rule zero: model output never changes the game

The Loom has five layers: canon, simulation, the Weaver (director), generative proposals and generative expression. Model output never changes game state directly. Player speech is turned into typed "speech acts", the NPC decides with deterministic rules, and only validated server actions change the world. Every AI-driven slot has an authored fallback, and every AI decision is logged.

*Why:* players in *Where Winds Meet* talked AI characters into handing over rewards [A11] [A12]; prompt injection has no complete defence [A25]; model output isn't reproducible [A24].

*Detail:* [AI Architecture](docs/06-ai/architecture.md).

<a id="d-043"></a>

### D-043 · NPC voices

Main-story characters are performed by actors. When players talk to them freely, they answer from a performer-recorded line bank, or with a digital replica only where the actor agrees. Other NPCs use licensed, consented AI voices or recorded lines. Every voice drawn from a performer requires informed consent, disclosure and payment [A9] [A10].

*Detail:* [NPC Minds and Conversation](docs/06-ai/npc-minds-and-conversation.md).

## Look, business and lifecycle

<a id="d-044"></a>

### D-044 · Painted Realism

Believable forms, materials and light, finished with a painterly hand. This look ages better over a decade than chasing photorealism, scales from phones to high-end PCs, gives every region its own palette, and suits expressive abilities on weighty bodies.

*Why:* see Arcane and Spider-Verse [G19], and *Clair Obscur* in UE5 [N8].

*Detail:* [Art and Audio Direction](docs/01-vision/art-and-audio-direction.md).

<a id="d-045"></a>

### D-045 · Business model

The game is free to enter. A cosmetic-only store sells items directly, with no random paid items ever. An optional Patron subscription gives cosmetics and a monthly décor allowance, with no gameplay, storage, speed or progression benefit. Omnis can't be bought, and there is no way to turn real money into Omnis, directly or through trading, unlike EVE's PLEX [M9]. Store spending is off by default for under-18s. AI running costs are a business cost, never a player-facing meter.

*Why:* it meets the "no paid power" rule and stays clear of loot-box law [L16] [L18] [L20].

*Detail:* [Economy and Crafting](docs/05-systems/economy-and-crafting.md).

<a id="d-046"></a>

### D-046 · Economy

Omnis can only be earned. Players trade materials and most crafted goods through regulated Exchanges and direct trade, with daily limits. Gear at levels 9 and 10, artifacts and Celestial rewards are bound to the avatar. The server owns every item, duplication is audited, and an economy team publishes regular reports.

*Why:* see New World's duplication crisis [M12], the scale of real-money trading [L22] and EVE's public reports [M10].

*Detail:* [Economy and Crafting](docs/05-systems/economy-and-crafting.md).

<a id="d-047"></a>

### D-047 · Archive Mode

If the Oasis falls, the final event runs, the live servers close as promised, and within seven days an Archive Mode is released. It is an offline way to keep your avatar, house, Chronicles and the Grand Library.

*Why:* honest endings with an offline legacy have precedent [R19] [R20], and regulators are moving that way [R12].

*Detail:* [Ten-Year Live Plan](docs/11-production/ten-year-live-plan.md).

<a id="d-048"></a>

### D-048 · If the world survives

If the Dawn Rite succeeds, the service carries on with no new end date, and Oasis 2.0 grows from it. Any future end gets at least 12 months' notice and an Archive Mode.

*Detail:* [Ten-Year Live Plan](docs/11-production/ten-year-live-plan.md), [Legal and Compliance](docs/12-legal/compliance.md).

<a id="d-049"></a>

### D-049 · Launch regions

At launch the world runs from datacenter regions in North America, South America, Europe, the Middle East, India, South-East Asia, East Asia and Oceania. Mainland China is not a launch region. Any later entry must keep the single canonical world ([D-028](#d-028)).

*Detail:* [Server and Backend](docs/08-technology/server-and-backend.md), [Legal and Compliance](docs/12-legal/compliance.md).

## Declined

Ideas considered and turned down, with the reason, so they are not reopened without new information. None yet.

<!-- citation links: generated, do not edit by hand -->

[A9]: references/technology-and-ai.md
[A10]: references/technology-and-ai.md
[A11]: references/technology-and-ai.md
[A12]: references/technology-and-ai.md
[A24]: references/technology-and-ai.md
[A25]: references/technology-and-ai.md
[G1]: references/games.md
[G2]: references/games.md
[G14]: references/games.md
[G15]: references/games.md
[G16]: references/games.md
[G19]: references/games.md
[J2]: references/anime-and-manga.md
[J3]: references/anime-and-manga.md
[L6]: references/legal-and-policy.md
[L16]: references/legal-and-policy.md
[L18]: references/legal-and-policy.md
[L20]: references/legal-and-policy.md
[L22]: references/legal-and-policy.md
[M1]: references/industry-and-live-service.md
[M3]: references/industry-and-live-service.md
[M9]: references/industry-and-live-service.md
[M10]: references/industry-and-live-service.md
[M11]: references/industry-and-live-service.md
[M12]: references/industry-and-live-service.md
[M14]: references/industry-and-live-service.md
[M15]: references/industry-and-live-service.md
[M17]: references/industry-and-live-service.md
[M18]: references/industry-and-live-service.md
[M19]: references/industry-and-live-service.md
[M26]: references/industry-and-live-service.md
[M27]: references/industry-and-live-service.md
[M28]: references/industry-and-live-service.md
[M29]: references/industry-and-live-service.md
[M42]: references/industry-and-live-service.md
[N8]: references/film-literature-and-music.md#n-series-sources
[R12]: references/ready-player-and-lifecycle.md
[R19]: references/ready-player-and-lifecycle.md
[R20]: references/ready-player-and-lifecycle.md
[S1]: references/technology-and-ai.md
[S2]: references/technology-and-ai.md
[S3]: references/technology-and-ai.md
[S7]: references/technology-and-ai.md
[S19]: references/technology-and-ai.md
[W15]: references/film-literature-and-music.md
[W16]: references/film-literature-and-music.md
