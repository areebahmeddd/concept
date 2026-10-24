# Traversal and Flight

How moving through the Oasis becomes play in its own right: running, climbing, swimming, diving, gliding, flying, riding, extreme sports and getting home again.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Systems Design
>
> **Horizons:** H0 run, climb, glide, swim · H1 dive, hover, licensed sustained flight, mounts, boats, aircraft · H2 personal spaceships, Colossal Frame transport · H3 a VR traversal mode
>
> **Related:** [D-023](../../DECISIONS.md#d-023) · [World Laws](../02-world/world-laws.md) · [Waypoints and Healing](../05-systems/waypoints-and-healing.md) · [Spaceflight and Moon Travel](../05-systems/spaceflight-and-moon-travel.md)

## 1. Player experience

> *Lin runs off the edge of a Stormcrown isle, opens her cloth wings and rides the storm's pull toward a reef of cloud. She has wanted a flight licence for weeks, but gliding has already shown her two sky-shrines that flyers rush past. Below her, a friend who never flies takes the root paths through the Verdant Spine and reaches a cave Lin has flown over a hundred times without seeing.*

The system must create these feelings:

1. **Movement is mastery.** Fast, expressive movement is a skill, not a speed stat.
2. **Every medium matters.** Ground, cliffs, air and water each hold discoveries the others can't reach.
3. **Flight is identity, not a shortcut.** It is licensed, costs energy and obeys the law. It never makes ground content irrelevant.
4. **Every barrier has a reason** ([World Laws](../02-world/world-laws.md)).

## 2. Scope

**Covers:** the movement set, sources and tiers of flight, flight rules, extreme traversal, how fast travel fits into movement, and comfort settings.

**Leaves to other specs:** Wayshrine travel and fees ([Waypoints and Healing](../05-systems/waypoints-and-healing.md)); the Skyferry and spaceships ([Spaceflight and Moon Travel](../05-systems/spaceflight-and-moon-travel.md)); penalties for airspace crimes ([Law, Crime and Bounties](../05-systems/law-crime-and-bounties.md)); Frames ([Mechs, Robots and Companions](../05-systems/mechs-robots-and-companions.md)); how each Domain changes movement ([World Laws](../02-world/world-laws.md#4-natural-law-by-domain)); help-calls ([NPC Bonds and Help-Calls](../05-systems/npc-bonds-and-help-calls.md)).

## 3. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| *World of Warcraft*'s flying debate [M17] | Free flight can hollow out the ground game | Flight is licensed late, costs energy, obeys airspace law, and every region keeps discoveries that only ground, water or a single altitude band can reach |
| *Microsoft Flight Simulator 2024* [S29] | Fast flight over a huge world can overwhelm streaming | One top flight speed for every platform, set by what the lowest supported tier can stream cleanly |
| The Na'vi bond in *Avatar* [W16] | A neural bond with a flying creature | Sky-nomad Bond flight: a partnership with stamina, rest and care, not a summoned mount |
| Meta's VR comfort guidance [S27] | Brief, rare accelerations; vignettes; snap turns | Applied to the H3 VR mode, with a cockpit or reference frame for flight |

## 4. Terms

| Term | Meaning |
| --- | --- |
| **Altitude band** | Low (canopy and rooftop), mid, high, and ceiling (thin air) |
| **Flight licence** | Permission for sustained personal flight, earned through a quest chain and a test |
| **Emergency glide** | A once-per-fall glide that opens even with no Stamina left |
| **Pressure tier** | How deep a diver's gear lets them go |

## 5. Entities and state

| Entity | Data | Authority |
| --- | --- | --- |
| Movement state | Mode, Stamina, flight energy, oxygen, pressure tier, altitude band, emergency glide cooldown | Server, with client prediction |
| Licences | Flight and vehicle licences held, suspensions by jurisdiction | Server |
| Mount | Species, stamina, rest need, passenger seat | Server |

## 6. Rules

### 6.1 Movement set

| Mode | Resource | Notes | Horizon |
| --- | --- | --- | --- |
| Run, sprint, slide | Stamina (sprint) | Slides keep momentum; vaults | H0 |
| **Climb** | Stamina | Almost any rough surface; Domain modifiers apply | H0 |
| **Swim** | Stamina | Surface swimming | H0 |
| **Glide** | Stamina | Cloth wings; everyone gets them in the first hour | H0 |
| Mantle and wall-run | Stamina | Short wall-runs for skilled chaining | H1 |
| Grapple line | Tool durability | Swing, pull, zip | H1 |
| **Dive** | Oxygen and pressure tier | Gear path: breath training, rebreather, Saltglass suit, pressure shell | H1 |
| Current-riding | None | Ride ocean currents in the Drowned Reach | H1 |
| **Hover** | Stamina and Resonance | Storm Arts, wing-packs | H1 |
| **Sustained flight** | Flight energy (Resonance or Spark-cells) and a licence | Late, lawful ([D-023](../../DECISIONS.md#d-023)) | H1 |
| Mounts | Mount stamina | Land, sea and sky mounts by Domain | H1 |
| Vehicles | Fuel or Spark-cells | Boats, rail-cars, land crawlers, aircraft (Iron Meridian) | H1 |
| Frames | Spark-cells | Walking and boosting, within city limits | H1 |
| Spaceflight | Ship systems | [Spaceflight and Moon Travel](../05-systems/spaceflight-and-moon-travel.md) | H1 public, H2 personal |

### 6.2 Sources of flight

Flight comes from four sources, each with its own feel.

| Source | Feel | Strengths | Limits |
| --- | --- | --- | --- |
| **Arts** (Storm Attunement) | Graceful, expressive | No gear; works in combat | Hungry for Resonance; weak in the Iron Meridian |
| **Wearables** (Meridian wing-packs) | Powerful, mechanical | Reliable and upgradable | Fail more than 20 m above the Verdant Spine canopy; overheat at Ember Wastes noon |
| **Bond** (sky-nomad riding) | A partnership | Endurance and a companion | Rest needs and mount care |
| **Machine** (aircraft, Frames with thrusters) | A vehicle | Speed, cargo, passengers | Airspace law, fuel, landing zones |

### 6.3 Flight tiers and rules

| Tier | Gained | Rules |
| --- | --- | --- |
| Glide | Avatar Level 1, in the first hour | Descends only; uses Stamina |
| Hover | Avatar Level 5 plus training | Short hops of about 8 s; usable in combat |
| Sustained | Avatar Level 9 plus a flight licence (quest chain and test) | Limited by energy; affected by weather; airspace law applies |
| Machine | A licence for each vehicle class | Fuel, maintenance, traffic control |

- **TRV-001 [H1]** Takeoff needs height, a running start or a Resonance burst. A vertical takeoff costs at least twice the energy. Landing has a short recovery, and hard landings cost Stamina or Health.
- **TRV-002 [H1]** **Altitude bands:** low, mid, high and ceiling. The ceiling's thin air doubles energy drain. Each band holds discoveries found only there, such as sky-shrines, cloud-reefs and high nests.
- **TRV-003 [H1]** **Weather:** storms push and pull; lightning seeks metal at high altitude in the Stormcrown; fog cuts visibility; rain shortens glides.
- **TRV-004 [H1]** **Airspace law:** cities define corridors and ceilings. Entering restricted airspace brings a warning, then Heat ([Law, Crime and Bounties](../05-systems/law-crime-and-bounties.md#64-heat-15)).
- **TRV-005 [H1]** **Collision:** players pass through each other in lawful airspace, so nobody can ram or body-block. Collision is on in the Lawless Reaches and in arenas.
- **TRV-006 [H1]** **Ground still matters:** anti-air tools can pull flyers down ([Aerial and scale combat](combat-and-abilities.md#67-aerial-and-scale-combat)), and ground-only routes (root paths, caves, underwater tunnels) stay essential.
- **TRV-007 [H1]** **Rescue:** a falling player with no Stamina can open an emergency glide once per fall, on a cooldown. A drowning player gets one auto-surface prompt. Settlements have rescue NPCs.
- **TRV-008 [H1]** **Top speed:** sustained flight has one top speed on every platform, so no device flies faster than another. The design target is 60 m/s. The real cap is the fastest speed at which the lowest supported tier streams without pop-in (see the streaming test in [Acceptance criteria](#12-acceptance-criteria)).
- **TRV-009 [H1]** **Passengers:** a bonded sky-mount can carry one passenger who accepts the ride. The passenger can't steer. The mount's stamina drains 1.5 times faster. Airspace Heat goes to the rider only.

### 6.4 Extreme traversal

| Activity | Where | Why it matters |
| --- | --- | --- |
| Climbing routes | Verdant Spine | Mastery Trials, hidden shrines, the respect of NPC guides |
| Cliff diving | Coasts, Pelagia | The way into sea caves |
| Current-riding | Drowned Reach | Ocean highways |
| Glass-sliding | Ember Wastes dunes | Fast travel at night |
| Ice-skating and sledging | Frostmarch | River-roads in the Deepfrost season |
| Skydiving and wingsuits | Stormcrown edges | The fastest descent, aerial Eggs, courier races |

- **TRV-010 [H1]** Every extreme activity unlocks something outside itself: a route, a discovery, a trial, a title or NPC respect.

### 6.5 Fast travel

Fast travel sits beside movement, never in place of discovery:

- **Wayshrines** link the shrines a player has reached in person. Rules and fees are in [Waypoints and Healing](../05-systems/waypoints-and-healing.md#61-wayshrines-discovery-and-travel).
- **The Skyferry** runs between Halcyon Ascent and Lumen ([Spaceflight and Moon Travel](../05-systems/spaceflight-and-moon-travel.md#61-the-skyferry-h1)). Travel between capitals uses Wayshrines, mounts, roads and vehicles.
- **Help-calls** bring a friend to their nearest discovered Wayshrine, never on top of the caller ([NPC Bonds and Help-Calls](../05-systems/npc-bonds-and-help-calls.md#67-friend-help-calls)).

### 6.6 Comfort

- **TRV-020 [H1]** Camera options include field of view, motion blur off, a camera-shake slider and an auto-level assist for flight.
- **TRV-021 [H3]** VR traversal follows Meta's comfort guidance: brief, infrequent accelerations, vignettes and snap turns [S27]. VR flight uses a cockpit or reference frame, auto-levelling and stepped speed changes.
- **TRV-022 [H1]** Touch controls have assisted climbing and flight that follow climbable surfaces automatically ([Controls, Camera and Accessibility](../09-platforms/controls-camera-and-accessibility.md)).

## 7. Edge cases

| Case | Rule |
| --- | --- |
| Stamina runs out mid-climb | The player falls; the emergency glide opens if it is off cooldown ([TRV-007](#63-flight-tiers-and-rules)) |
| A flyer crosses into a zone where their flight is Impossible | Flight drops to a controlled glide with an in-world reason ([WLD-011](../02-world/world-laws.md#3-the-evaluation-model)). It never cuts out into a sudden fall. |
| A licence is suspended mid-flight | The flyer must land; flying on is an airspace crime |
| Disconnect mid-flight | The avatar glides safely to the ground during the logout window |
| A passenger's rider dismounts in the air | The passenger's glide opens automatically |

## 8. Multiplayer and platforms

Movement speeds, flight energy and top speed are identical on every platform ([TRV-008](#63-flight-tiers-and-rules)). Lawful airspace has no player collision ([TRV-005](#63-flight-tiers-and-rules)), so crowded skies over cities stay safe. Touch players get assisted climbing and flight ([TRV-022](#66-comfort)).

## 9. Safety and abuse

- Movement is validated on the server. Speed, teleport and fly hacks are rejected and flagged.
- Pass-through collision in lawful airspace removes ramming and body-blocking as griefing tools.
- Flight can't be used to escape the law for free: Heat follows its own escape rules ([Law, Crime and Bounties](../05-systems/law-crime-and-bounties.md)).

## 10. Performance

At top flight speed, gameplay-relevant objects within 300 m never pop in on the lowest supported tier ([Platform Support](../09-platforms/platform-support.md)). Areas ahead of a flyer are pre-streamed along their heading.

## 11. Examples

| Allowed | Not allowed |
| --- | --- |
| A licensed flyer crosses the Stormcrown at high altitude | An unlicensed flyer cruises over Halcyon's market without Heat |
| A friend rides pillion on a sky-mount | A passenger steering someone else's mount |
| A cave reachable only on foot through root paths | Every point of interest reachable by air |
| A flyer drops to a glide on rising more than 20 m above the Verdant Spine canopy | A flyer's wing-pack cuts out and they fall to their death |

## 12. Acceptance criteria

| ID | Test |
| --- | --- |
| [TRV-002](#63-flight-tiers-and-rules) | Each region has at least 3 discoveries per altitude band that can be reached only in that band |
| [TRV-005](#63-flight-tiers-and-rules) | In lawful airspace, 1,000 forced mid-air player collisions cause 0 damage or displacement |
| [TRV-006](#63-flight-tiers-and-rules) | Each region has at least 5 points of interest reachable only on foot or under water |
| [TRV-008](#63-flight-tiers-and-rules) | Streaming test: at the top speed, the lowest supported tier shows no pop-in of gameplay-relevant objects within 300 m. The cap is set to the highest speed that passes. |
| [TRV-009](#63-flight-tiers-and-rules) | 500 passenger rides: the passenger never gains control, and Heat events go only to the rider |

<!-- citation links: generated, do not edit by hand -->

[M17]: ../../references/industry-and-live-service.md
[S27]: ../../references/technology-and-ai.md
[S29]: ../../references/technology-and-ai.md
[W16]: ../../references/film-literature-and-music.md
