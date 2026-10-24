# Vision

Why *Ready Player Zero* exists, who it is for, what it should feel like, and the pillars every decision is tested against.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Creative director
>
> **Related:** [The Story of the Oasis](../../STORY.md) · [Art and Audio Direction](art-and-audio-direction.md) · [Core Loops](../04-gameplay/core-loops.md) · [D-001](../../DECISIONS.md#d-001) · [D-006](../../DECISIONS.md#d-006) · [D-011](../../DECISIONS.md#d-011) · [D-045](../../DECISIONS.md#d-045)

## 1. The game in one breath

> **One world. Ten years. Seven Celestials. Everyone shares one fate.**
>
> *Ready Player Zero* is an open world shared by every player on every platform. It is always online: every Returner you meet is a real person playing live, beside you or against you, and NPCs with their own lives fill the world between them. Each player is a Returner: someone who comes back from death. You explore very different lands, learn weighty anime-inspired combat, fly, pilot machines, build a home and make friends with NPCs who remember you. From launch day a real clock counts down ten years to the day the sun burns the world. The players can save the Oasis only by working together to free six chained Celestials and defeat the False Celestial who betrayed them. If they fail, the world really ends.

## 2. Why it should exist

- **A shared fate with a real ending.** Online worlds share a place. Few share a destiny that can end. The countdown makes every contribution count and turns the decade into something people remember living through.
- **NPCs you can really talk to.** Players speak freely to NPCs who remember them, and the rules underneath can't be talked into breaking the game ([D-041](../../DECISIONS.md#d-041), [D-042](../../DECISIONS.md#d-042)).
- **Skill, never money.** Power can't be bought ([D-045](../../DECISIONS.md#d-045)).
- **A story people already love, made collective.** *Ready Player One* promised a world worth fighting for [R1]. Here the whole player base fights for it together.

## 3. Audience

| Dimension | Decision |
| --- | --- |
| **Age** | 13+ (ESRB T, PEGI 12–16), with depth that adults enjoy ([D-006](../../DECISIONS.md#d-006)) |
| **Markets** | Global ([D-007](../../DECISIONS.md#d-007)) |
| **Platforms** | PC, consoles, mobile and handhelds in one world; full VR is H3 ([D-009](../../DECISIONS.md#d-009)) |
| **Motivations** | Every major player motivation has a home, mapped in [Core Loops](../04-gameplay/core-loops.md) using Bartle's types [R25] and the Quantic Foundry model [R27] |
| **Play styles** | Solo, with friends or in clans; all viable, none required ([D-024](../../DECISIONS.md#d-024)) |

## 4. Experience goals (observable, testable)

Each aspiration becomes a behaviour we can measure. The thresholds are design targets, tuned in playtest.

| ID | Aspiration | Observable behaviour | Acceptance |
| --- | --- | --- | --- |
| **VIS-001 [H1]** | "Something is always happening" | From any open-world position, a joinable activity (micro-event, NPC request, world event or Egg lead) is reachable within 3 minutes of normal travel | At least 95% of sampled positions and times, in telemetry |
| **VIS-002 [H1]** | "NPCs feel like people" | NPCs keep schedules, remember what the player did and mention it later | In a scripted 10-session test, at least 90% of named NPCs recall at least one earlier interaction correctly |
| **VIS-003 [H1]** | "Surprise within rules" | Players meet events they didn't predict and can explain them afterwards from world logic | Playtest survey: at least 70% report surprise, and at least 80% of those can name the cause |
| **VIS-004 [H1]** | "My contribution matters" | Every player can see their own contribution to the active Convergence | 100% of players have a visible contribution record within their first 10 hours |
| **VIS-005 [H1]** | "Skill, not money" | No item for sale changes any gameplay stat or outcome | Automated store audit finds 0 gameplay-affecting items |
| **VIS-006 [H1]** | "Safe by default" | New and under-18 accounts start with protective defaults | Configuration audit on every platform build |
| **VIS-007 [H1]** | "Every region feels different" | Each Domain differs in Natural Law, palette, music, traversal and culture | Each Domain passes the five-axis review in [Geography and Domains](../02-world/geography-and-domains.md#2-distinctness-standard-vis-007) |

## 5. Pillars

Every feature strengthens at least one pillar and weakens none. Where two pillars pull against each other, the spec records the trade-off.

| # | Pillar | Means | Never means |
| --- | --- | --- | --- |
| **P1** | **One World, One Fate** | One global world on every platform. The countdown and every Celestial freed belong to everyone. | Forced grouping, or punishing players for not being there |
| **P2** | **Surprise Within Rules** | Unpredictable encounters that follow stated laws. Anything that solves a problem can be understood first (Sanderson's First Law [W8]). | Random, unexplained or AI-invented outcomes |
| **P3** | **Mastery Over Money** | Power comes from skill, knowledge, practice and resolve. Low caps, deep mastery. | Paid power, grind walls or gacha |
| **P4** | **Freedom With Reasons** | Every restriction has an in-world cause and usually a way around it that players can discover ([World Laws](../02-world/world-laws.md)) | Arbitrary walls |
| **P5** | **Myth and the Ordinary** | World-ending stakes next to small human stories: a fisherman, a lost letter, a friend who remembers you | All spectacle and no heart |
| **P6** | **Safe by Default, Social by Choice** | Protective defaults, opt-in voice, solo always viable, community easy to find | Isolation, or exposure without consent |
| **P7** | **Readable Spectacle** | Flight, Frames, colossi and Arts stay clear and fair at any scale and on any device | Effects that hide the game |

Self-Determination Theory finds that autonomy, competence and relatedness predict enjoyment and continued play [R26]. P4 serves autonomy, P3 serves competence, and P1 and P6 serve relatedness.

## 6. Design principles

1. **Ambitious and buildable in one spec.** Design the full idea, then tag each part with its horizon ([D-001](../../DECISIONS.md#d-001)).
2. **Rules before exceptions.** Define a law before the artifacts that bend it, and progression before rare rewards.
3. **Canon is fixed; variation is free.** AI and procedural systems vary the present. They never rewrite the past ([Conventions](../00-meta/conventions.md#4-canon)).
4. **The world explains itself.** Every system has an in-world reason: a Natural Law, a Civic Law, a person or a history.
5. **Weight over flash.** Combat, flight and machines feel physical. Spectacle serves readability.
6. **Honesty with players.** The countdown is real. The end of service is announced on day one. AI is disclosed. Odds and scaling are published.
7. **Respect for cultures.** Traditions that inspire us are researched, reviewed by consultants and shown from the inside ([Peoples and Factions](../02-world/peoples-and-factions.md)).

## 7. Firm constraints

- Nothing sold affects gameplay. No loot boxes and no paid power ([D-045](../../DECISIONS.md#d-045)).
- No nudity, no sexual content and no realistic real-world violence ([D-006](../../DECISIONS.md#d-006)).
- Avatar, skills and items cap at level 10. Player Rank and Adventure Rank cap at 100. Nothing goes above 100 ([D-021](../../DECISIONS.md#d-021)).
- Voice is never required ([D-008](../../DECISIONS.md#d-008)).
- Clans are optional and give no automatic gameplay advantage.
- AI never invents powers, breaks lore, breaks progression or grants impossible rewards ([D-042](../../DECISIONS.md#d-042)).

## 8. What this game is not

- **A gacha.** Nothing paid is random.
- **Host-world co-op.** The world is always shared ([D-029](../../DECISIONS.md#d-029)).
- **An AI sandbox where anything goes.** The world has laws, and the AI works inside them.
- **Endless.** It has a real ending, and a future only if the players earn it ([D-011](../../DECISIONS.md#d-011)).
- **A copy.** Every borrowed lesson is changed to fit this world ([Inspirations](#10-inspirations)).

## 9. Success in the long run

| Horizon | We succeed if… |
| --- | --- |
| H0 | A small team playing the first slice tells surprising, explainable stories they want to retell |
| H1 | New players see the World Clock and understand the stakes within 15 minutes ([D-027](../../DECISIONS.md#d-027)), and make their first NPC friend within 2 hours |
| H2 | Each Convergence becomes a community event people talk about outside the game |
| End of the decade | Whatever the outcome, players say *"I was there."* |

## 10. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| *Ready Player One* [R1] | A world-scale quest with world-scale stakes and a public record of firsts | One winner inheriting everything becomes everyone surviving together, or no one |
| *Ready Player Two* [R4] | A warning: a hunt for scattered pieces turns hollow without people at its centre | Each of our seven pieces is a person's Oath, and small human stories sit beside the myth (P5) |
| *World of Warcraft*'s Ahn'Qiraj war effort [G17] | A server-wide effort whose titles mark who was there | Latecomers can relive every global moment as a Chronicle, without its rewards ([D-030](../../DECISIONS.md#d-030)) |
| *Fortnite*'s "The End" [R24] | A live event that ends a world, watched by millions at once | Our ending is announced on launch day, runs for 24 hours across every time zone and can be averted |
| *EVE Online*'s Triglavian Invasion [R22] | Player actions decide a world event's outcome | The rules that decide our outcome are published from the start |

<!-- citation links: generated, do not edit by hand -->

[G17]: ../../references/games.md
[R1]: ../../references/ready-player-and-lifecycle.md
[R4]: ../../references/ready-player-and-lifecycle.md
[R22]: ../../references/ready-player-and-lifecycle.md
[R24]: ../../references/ready-player-and-lifecycle.md
[R25]: ../../references/ready-player-and-lifecycle.md
[R26]: ../../references/ready-player-and-lifecycle.md
[R27]: ../../references/ready-player-and-lifecycle.md
[W8]: ../../references/film-literature-and-music.md
