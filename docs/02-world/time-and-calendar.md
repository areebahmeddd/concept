# Time and Calendar

How time works in the Oasis: the day, the week, regional seasons, the Oasis season, the Long Year and the ten-year count, and what time changes in the world.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Systems design
>
> **Horizons:** H0 day and night, one season wheel · H1 the full calendar · H2 festivals grow each year
>
> **Related:** [D-013](../../DECISIONS.md#d-013) · [D-011](../../DECISIONS.md#d-011) · [Cosmology](cosmology.md) · [NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md) · [Director and World Events](../06-ai/director-and-world-events.md) · [Ten-Year Live Plan](../11-production/ten-year-live-plan.md)

## 1. Design goals

1. **Fair across time zones.** No player always logs in at the same time of day. Tying the world to local time leaves some regions out [R29].
2. **Seasons that matter but never punish.** Every season comes round again within weeks, not months.
3. **One real anchor.** The Long Year and the Conjunction follow real time, so the countdown is honest ([D-011](../../DECISIONS.md#d-011)).
4. **Readable.** Players always know the time, the season and how long remains.

## 2. Units

| Unit | Length (rt) | Made of | Why |
| --- | --- | --- | --- |
| **Oasis hour (bell)** | About 4 min 10 s | 1/24 of an Oasis day | A familiar 24-hour clock for NPC schedules |
| **Oasis day** | 100 min | Dawn 5, day 55, dusk 5, night 35 (rt minutes) | 14.4 Oasis days pass per real day, so the hour drifts through every time zone. Longer than FFXIV's 70-minute day [M27] so that schedules matter. |
| **Oasis week** | 7 Oasis days, about 11 h 40 min | Seven named days ([The Oasis week](#3-the-oasis-week)) | Weekly NPC routines such as market day and rest day |
| **Moon cycle** | Lumen 28 days, Veil 36, Hollow 52 | Four phases each, one per season | Drives regional seasons ([Regional seasons](#4-regional-seasons-driven-by-the-moons)) |
| **Oasis season** | 7 days | One phase of Lumen, the same everywhere | The global cycle for commissions, Grandmaster limits, Singular Relic tenure and rotations. Separate from regional seasons. |
| **Long Year** | 1 real year (365 days) | Starts at launch and ends with a Long Night | The heartbeat of the countdown |
| **The Count** | 10 Long Years | None | Ends at the Great Conjunction |

**Numbering.** Long Year 0 runs from launch to the first Long Night (LN1), Long Year 1 from LN1 to LN2, and so on. "Long Year *k*" means the same as "Year *k*" in the [Ten-Year Saga](../03-narrative/ten-year-saga.md) and the [Ten-Year Live Plan](../11-production/ten-year-live-plan.md). The World Clock reaches zero as the tenth Long Night begins. The saga's outcome is settled when that 24-hour window ends ([The endings](../03-narrative/ten-year-saga.md#6-the-endings)).

**Time stamp** (as shown in the interface): `Long Year 3 · Hearthlands autumn · Ysolday, 14th bell`.

- **TIM-001 [H1]** Oasis time is global and set by the server. Every player in every layer sees the same Oasis time.

## 3. The Oasis week

The days are named for the Celestials. The seventh has no name.

| # | Day | Custom |
| --- | --- | --- |
| 1 | Orunday | Labour, travel and roads |
| 2 | Marisday | Remembrance, letters and coastal markets |
| 3 | Kestraday | Couriers, messengers and duels |
| 4 | Sahrday | Fasting at noon, feasting at night |
| 5 | Vantorday | Workshops open late and Artisans take new commissions |
| 6 | Ysolday | The Library opens its reading halls to everyone |
| 7 | **Blankday** | Nobody works, and nobody knows why. Naming it is "bad luck". |

Blankday was once named for the seventh Celestial, and the Library holds the erased records. This is an Egg and a reveal node (RV-05 in the [Reveal Graph](../03-narrative/reveal-graph.md)).

## 4. Regional seasons, driven by the moons

Each region takes its seasons from one moon's cycle. Because the cycles differ (28, 36 and 52 days), regions rarely change season together, and the rare **season alignments** become events.

| Region | Governing moon | Season length (rt) | Seasons |
| --- | --- | --- | --- |
| Hearthlands | Lumen | 7 days | Spring, summer, autumn, winter |
| Drowned Reach | Lumen | 7 days | High Tide, Bloom, Low Tide, Drift |
| Verdant Spine | Veil | 9 days | Thaw, Canopy, Fall, Hush |
| Frostmarch | Veil | 9 days | Aurora, Melt, Starfall, Deepfrost |
| Ember Wastes | Hollow | 13 days | Ember, Glass, Ash, Cool Wind |
| Stormcrown | Hollow | 13 days | Gale, Eye, Thunder, Stillsky |
| Iron Meridian | None | Set by decree | An engineered climate. The city declares "civic seasons" by festival decree, a Stewardship choice at H2 ([D-038](../../DECISIONS.md#d-038)). |

- **TIM-002 [H1]** No seasonal content can be missed for good. Every regional season comes round again within 52 real days.
- **TIM-003 [H1]** Each season changes at least three of: weather, wildlife, resources, traversal (for example, frozen rivers become paths), NPC routines, shop stock, special quests and temporary abilities.
- **TIM-004 [H1]** A season-limited reward is either cosmetic or returns next cycle. Seasonal power is never exclusive.

## 5. What time changes

| System | Effect of time |
| --- | --- |
| **NPCs** | Daily schedules by Oasis hour (work, meals, sleep, worship), weekly customs and seasonal migrations |
| **Shops and services** | Opening hours, with an essential service of each kind always open in capitals ([TIM-005](#5-what-time-changes)) |
| **Wildlife and monsters** | Day and night spawn tables, seasonal migration, and the Long Night surge ([Cosmology](cosmology.md#3-the-long-night)) |
| **Weather** | Seasonal weather tables per region. Storms affect flight ([Traversal and Flight](../04-gameplay/traversal-and-flight.md)). |
| **Quests** | Weaver templates can require a time of day or a season ([Director and World Events](../06-ai/director-and-world-events.md)) |
| **Travel** | The Skyferry leaves every 2 Oasis hours, about every 8 rt minutes |
| **Artisans and housing** | Commission and build times are set in real time, so players can plan, and shown as Oasis time in the world |
| **Ageing [H2]** | NPCs age one year per Long Year, so children grow up over the decade ([NPC Bonds and Help-Calls](../05-systems/npc-bonds-and-help-calls.md)) |

- **TIM-005 [H1]** Every capital keeps at least one repair, healing and Exchange service open at every hour.
- **TIM-006 [H1]** No player can skip or speed up time, because the world is shared. Sleeping at an inn gives a Rested bonus instead.

## 6. The Long Year and its festivals

The festivals in order through each Long Year:

| When (rt) | Festival | What happens |
| --- | --- | --- |
| Launch anniversary | **The Long Night** (24 hours) | The three moons align ([Cosmology](cosmology.md#3-the-long-night)) |
| The day after | **First Light** | Celebration, Chronicle unveilings and the Clock's yearly toll |
| Mid-year | **Library Day** | Ysolde's founding of the Library: lore reveals and reading quests |
| The week before the next Long Night | **Festival of Lanterns** | Preparation, lantern crafting and stories of the Seven |
| Once per regional cycle | Season festivals, such as the Drowned Reach's *Song of Bloom* | One per region per cycle |

## 7. Acceptance criteria

| ID | Test |
| --- | --- |
| [TIM-001](#2-units) | Three clients in three layers and two regions report the same Oasis time (within 1 s) over 24 rt hours |
| [TIM-002](#4-regional-seasons-driven-by-the-moons) | Simulating 365 rt days, every season of every region occurs at least 7 times |
| [TIM-005](#5-what-time-changes) | At every Oasis hour, a pathing bot in each capital reaches an open repair, healing and Exchange service |
| [TIM-006](#5-what-time-changes) | No client action or server command available to players changes Oasis time; inn rest applies the Rested bonus |
| Drift | Over 7 rt days, a player logging in at the same real time sees at least 5 different Oasis hours |

<!-- citation links: generated, do not edit by hand -->

[M27]: ../../references/industry-and-live-service.md
[R29]: ../../references/ready-player-and-lifecycle.md
