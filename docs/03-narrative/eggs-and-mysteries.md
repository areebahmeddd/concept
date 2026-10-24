# Eggs and Mysteries

The hidden secrets of the Oasis, from small delights to world-first riddles, and how they stay secret, fair and accessible.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Quest design
>
> **Horizons:** H0 three Whisper Eggs · H1 every tier · H2 new Chronicle Eggs every Age · H3 optional real-world prize events, after legal review
>
> **Related:** [D-004](../../DECISIONS.md#d-004) · [D-030](../../DECISIONS.md#d-030) · [Reveal Graph](reveal-graph.md) · [Avatar and Progression](../04-gameplay/avatar-and-progression.md) · [Director and World Events](../06-ai/director-and-world-events.md)

## 1. Why Eggs

An Egg is a hidden mystery of the world, from a tiny joke to a world-shaking riddle. Eggs are how the Oasis holds more than any one player can take in, and they are the main source of Adventure Rank ([Avatar and Progression](../04-gameplay/avatar-and-progression.md)). "Eggs" is a permitted homage to *Ready Player One* ([D-004](../../DECISIONS.md#d-004)).

## 2. Tiers

| Tier | What it is | Scope | Example | Reward |
| --- | --- | --- | --- | --- |
| **Whisper** | A small delight: a joke, a view, a secret room | Personal | A Lowhaven cat that follows only Returners who hum the Returner motif | Adventure Rank, a lore page, a cosmetic |
| **Riddle** | A puzzle in several steps across several places | Personal | Learning Murmur's light-language to read a trench mural | Adventure Rank, a title, a lead to an Art |
| **Legacy** | A long chain tied to hidden canon | Personal, with reveal nodes | The sealed Lowhaven cottage (the crescent mark, letters, a broken net), which leads to RV-06 | Adventure Rank, a title, a Legacy Art |
| **Celestial** | Clues in a Convergence's Discover phase | Contribution to a global effort | Finding Orun's six resting stones | Contribution, a title |
| **Chronicle Egg** | A world-first riddle, held on the server and solved once, for everyone | Global, with the first solver honoured | "The Seventh Bell", a riddle across the customs of all seven weekdays | A unique title on the Chronicle Board forever |

## 3. Design rules

- **NAR-030 [H1] Datamining resistance.** Legacy, Celestial and Chronicle Eggs are held on the server. Clue content streams only when triggered, and solutions are checked on the server.
- **NAR-031 [H1] Spoiler-proof.** Even when a solution is public, the Egg still asks something of the player: a journey, timing, a skill or a Long Night. Knowing isn't the same as doing.
- **NAR-032 [H1] Clues for more than one sense.** Every clue can be perceived through at least two channels, such as visual plus audio or text, so Eggs stay accessible ([Controls, Camera and Accessibility](../09-platforms/controls-camera-and-accessibility.md)).
- **NAR-033 [H1] Authored, never invented.** Eggs are authored. The Weaver may place pointers (a rumour, a dream, an NPC hint) only to Eggs that exist ([Director and World Events](../06-ai/director-and-world-events.md)).
- **NAR-034 [H1] The community is welcome.** Sharing is encouraged. Chronicle Eggs are built for collaboration, with pieces held in different regions or layers.
- **NAR-035 [H1] No real-money prizes.** Real-world prize events are H3 only and need legal review first, because sweepstakes and lottery law differ by country ([Legal and Compliance](../12-legal/compliance.md)).

## 4. Named Eggs (H1 seed list)

| ID | Name | Tier | Where | Links |
| --- | --- | --- | --- | --- |
| EGG-001 | The Crescent Door | Legacy | Lowhaven | RV-05, RV-06 |
| EGG-002 | Blankday's Silence | Riddle | Every city | RV-05 |
| EGG-003 | Ghosts of Sennight | Riddle (Long Night only) | Sennight ruins | RV-02 |
| EGG-004 | The Hummed Motif | Whisper | Everywhere (the Returner motif) | RV-13 |
| EGG-005 | Light-Speech of Murmur | Riddle | Drowned Reach | Maris's Convergence |
| EGG-006 | The Star-Wheel Error | Riddle | Frostmarch | Ysolde, RV-07 |
| EGG-007 | Vantor's Last Free Blueprint | Legacy | The Iron Meridian's Undercity | Vantor's Convergence |
| EGG-008 | The Seventh Bell | Chronicle | World-wide | RV-05 |

## 5. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| The hidden credit room in *Adventure* (1980), which Atari chose to keep [G18] | The delight of finding something the makers hid | Eggs are part of the world and of progression, earning Adventure Rank |
| *Ready Player One* [R1] | A world's fate tied to a hunt for hidden Eggs | The hunt is shared: Chronicle Eggs are solved once, for everyone, and built for collaboration |
| Ernest Cline's real-world egg contest for readers [G18] | A real prize for solving a real puzzle | H3 only, and only after legal review ([NAR-035](#3-design-rules)) |
| *Outer Wilds* [N1] | Knowledge as progression | Our Eggs still ask for travel, timing or skill once the answer is known ([NAR-031](#3-design-rules)) |
| The Scarab Lord title from *World of Warcraft*'s Ahn'Qiraj opening [G17] | A unique title that marks the first to finish | Titles never grant power |
| The erased history in *One Piece* [J12] | A buried past players can chase for years | The records Zero erased from the Grand Library come back through Eggs and Chronicles |
| *Arrival* [W21] | A language that unlocks a mystery | Murmur's light-language, learnable by any player |
| *Uncharted* [G20] | Treasure hunts built on history | Eggs that follow in-world history across the Domains |

## 6. Acceptance criteria

| ID | Test |
| --- | --- |
| [NAR-030](#3-design-rules) | Client build audit finds no server-held Egg solution or clue text in client packages |
| [NAR-031](#3-design-rules) | For every Legacy and Chronicle Egg, a tester given the full solution still needs to travel, wait for a time window or pass a skill check to complete it |
| [NAR-032](#3-design-rules) | Accessibility review: every Egg clue has two or more channels |
| [NAR-033](#3-design-rules) | The Validator accepts Weaver pointer events only when they name an existing EGG ID |
| [NAR-035](#3-design-rules) | Store and event audit finds no real-money prize at H1 or H2 |

<!-- citation links: generated, do not edit by hand -->

[G17]: ../../references/games.md
[G18]: ../../references/games.md
[G20]: ../../references/games.md
[J12]: ../../references/anime-and-manga.md
[N1]: ../../references/film-literature-and-music.md#n-series-sources
[R1]: ../../references/ready-player-and-lifecycle.md
[W21]: ../../references/film-literature-and-music.md
