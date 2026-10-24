# Conventions

The rules every document in this repository follows, so anyone can pick up any spec and read it the same way.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Design lead
>
> **Related:** [Spec Template](spec-template.md) · [Contributing](../../CONTRIBUTING.md) · [Decisions](../../DECISIONS.md) · [Glossary](../../GLOSSARY.md)

## 1. One spec, four horizons

There is one specification. Every feature, rule and content item carries a horizon tag that says *when* it exists. A tag never signals importance.

| Tag | Name | Meaning |
| --- | --- | --- |
| **H0** | First Playable | The internal slice that proves the game's unique bets |
| **H1** | Launch | What exists on launch day (target mid-2030s) |
| **H2** | The Decade | What arrives during the ten-year saga |
| **H3** | Horizon | What needs technology or scale we can't promise yet; designed now so nothing blocks it |

Three rules apply:

- A feature can't arrive earlier than anything it depends on.
- H3 items still have to agree with canon.
- Moving an item to another horizon is a decision, so it goes in the [decision log](../../DECISIONS.md).

## 2. Decisions

Specs state decisions. They don't recommend, propose or leave questions open. Every decision that shapes more than one document is logged in [DECISIONS.md](../../DECISIONS.md). A logged decision stays in force until a later one replaces it; the old entry is then marked **Superseded** and links to its replacement. Ideas that were considered and declined are recorded in the log's **Declined** section with the reason.

Rules that only matter inside one system live in that system's spec. Changes from players, contributors or the team go through the process in [Contributing](../../CONTRIBUTING.md).

## 3. Requirements

A requirement is one testable rule, written as a plain statement in the present tense.

> [CMB-001](../04-gameplay/combat-and-abilities.md#61-core-verbs-and-resources) [H1]: Deflecting a heavy attack inside the window takes at least 35% of the attacker's Poise and costs the defender no Stamina.

- **Format:** the ID and horizon in bold (`**AREA-NNN [Horizon]**`), then the rule. IDs are never renumbered or reused.
- **One rule per requirement.** If a sentence needs "and also", it is two requirements.
- **Numbers are design targets.** Durations, caps and percentages are tuned in playtest without a new decision, as long as the rule's behaviour stays the same.
- **Every spec ends with acceptance criteria** that say how each key requirement is tested.

| Code | Area | Code | Area |
| --- | --- | --- | --- |
| VIS | Vision | ECO | Economy and crafting |
| WLD | World and laws | HSG | Housing |
| TIM | Time and calendar | LAW | Law and bounties |
| NAR | Narrative | SPC | Spaceflight |
| CEL | Celestials and Convergence | MCH | Machines and companions |
| QST | Quests and events | NPC | NPC relationships and help-calls |
| PRG | Progression | PVP | PvP and protection |
| CMB | Combat and abilities | WAY | Waypoints and healing |
| TRV | Traversal and flight | REC | Recording and replays |
| DTH | Death and return | AI | AI systems |
| MP | Multiplayer | SOC | Social and voice |
| SAF | Safety and moderation | TEC | Technology |
| PLT | Platforms | UX | Controls and accessibility |
| ART | Art and audio | TST | Testing |
| OPS | Production and live operations | LGL | Legal and compliance |
| LOOP | Core loops | | |

## 4. Canon

Every piece of lore belongs to exactly one layer.

| Layer | Who knows it | Where it lives |
| --- | --- | --- |
| **Public canon** | Players can learn it in the game | [STORY.md](../../STORY.md) Parts I and II, the world bible |
| **Hidden canon** | Designers only, until the [reveal graph](../03-narrative/reveal-graph.md) releases it | Sections marked **Hidden canon** |
| **Generated** | Varies per player and per run | Produced by the [Loom](../06-ai/architecture.md). It may never contradict the two layers above. |

AI systems read public canon and the parts of hidden canon a character is allowed to know. They never write canon.

## 5. Sources and citations

- Facts about the real world cite a source ID, such as [G2] or [M12]. Each ID links to the [reference library](../../references/README.md), where the source is graded and its lesson for this game is explained.
- IDs are permanent. The prefixes are: S, T and A for technology and AI; M for industry; G for games; J for anime and manga; W and N for film, literature and music; R for *Ready Player* and game lifecycles; L for law and policy.
- Anything without a citation is a design decision of this project.
- Inspiration is never copying. Every spec that borrows a lesson says what it takes and what it changes.

## 6. Links

- **Link every reference where it appears.** Don't write "see section 4" or use the section sign. Link the section itself, such as [canon](#4-canon).
- **Link text is the title** of the document or section, not its file name.
- **Requirement IDs link to the document that defines them**, such as [DTH-003](../04-gameplay/death-and-return.md#61-the-return-sequence).
- Every folder has a `README.md` that indexes its documents and links to the previous and next folders.

## 7. Writing

The house style follows plain-language practice (ISO 24495-1): write for the reader, put the point first, use everyday words.

- **Be direct.** Say what happens. Skip filler, hype and throat-clearing.
- **British English** spelling (colour, behaviour, centre, licence as a noun, defence).
- **No em dashes.** Use a full stop, colon, comma or brackets.
- **They/them** for players and for any person whose pronouns aren't stated.
- **Dates** are written day-month-year with hyphens (10-10-2026). Time is real time (rt) or Oasis time (ot). Unmarked durations in system specs are real time.
- **Tables** have a header row, columns in a logical order, and rows sorted by sequence, importance or name. Use empty-value text such as "None", never a dash.
- **Story and specs sound different.** Poetic language belongs in [STORY.md](../../STORY.md) and player-facing examples. Specs are precise.

## 8. Diagrams

- Use Mermaid, so diagrams live in the text and can be reviewed like code.
- Introduce every diagram with one sentence that says what it shows.
- A diagram must match the rules written next to it. If they disagree, fix both in the same change.

## 9. Documents and files

- **Names:** folders are `NN-topic`, numbered in reading order. Files are lowercase kebab-case and match the document title.
- **Header:** every document starts with its title, a one-sentence purpose, then a short block with version, date, owner, horizons (for system specs) and related links. Each item in that block sits on its own line.
- **Structure:** system specs follow the [spec template](spec-template.md). Section numbers keep long documents easy to cite.
- **History:** change history lives in [CHANGELOG.md](../../CHANGELOG.md), not inside documents.

<!-- citation links: generated, do not edit by hand -->

[G2]: ../../references/games.md
[M12]: ../../references/industry-and-live-service.md
