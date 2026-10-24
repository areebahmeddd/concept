# Tone and Themes

How the Oasis should feel to read, hear and play: the tonal palette, the themes, the 13+ boundary, and writing rules for authors and AI alike.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Narrative director
>
> **Related:** [D-006](../../DECISIONS.md#d-006) · [D-012](../../DECISIONS.md#d-012) · [The Story of the Oasis: what the story is about](../../STORY.md#part-iv-what-the-story-is-about) · [Art and Audio Direction](../01-vision/art-and-audio-direction.md) · [NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md)

## 1. The tonal chord

The Oasis plays five notes together. A scene can lean on one, but across a session all five are present.

| Note | What it feels like |
| --- | --- |
| **Wonder** | A Skyreef Ray rising out of a storm |
| **Warmth** | A Lowhaven fisherman saving you the good fish |
| **Humour** | Blankday "isn't a day, stop asking"; a Meridian Automaton that is too honest |
| **Melancholy** | An NPC you knew in Year 1 has grandchildren in Year 8 |
| **Dread** | The World Clock's yearly toll; Hollow on the horizon |

## 2. Themes

The themes are named in [The Story of the Oasis](../../STORY.md#part-iv-what-the-story-is-about). Writers never preach them. They show them through the world:

| Theme | Shown through |
| --- | --- |
| Power given against power taken | Oaths; Artisans who teach against Engine Houses who sell; Zero |
| Memory and time | NPCs ageing, Chronicles, Veil, Ysolde |
| Resolve | Mastery Trials; Oaths kept through death after death |
| Fear disguised as protection | Zero, the Quiet, some of the Lumenari |
| Together by choice | Convergences and the Returners' Oath |

## 3. The 13+ boundary

The target rating is ESRB T or PEGI 12–16 ([D-006](../../DECISIONS.md#d-006)). ESRB T allows violence with minimal blood. *Mortal Kombat*'s gore, by comparison, is rated M [G9].

| Allowed, with restraint | Never |
| --- | --- |
| Death, loss, grief and sacrifice | Gore, dismemberment or lingering suffering |
| War and its consequences (ruins, refugees) | Realistic depictions of real-world violence or atrocities |
| Betrayal and greed | Torture shown on screen |
| Moral complexity and antagonists whose motives make sense | Sexual content or nudity |
| Fantasy combat with impact and weight | Glorifying cruelty |
| Fear and a horror atmosphere, with intensity options | Depictions of self-harm |
| Mild language | Slurs, in authored or generated text |

Mature themes are told with restrained depiction. Show consequences, cut away from brutality, and let silence carry weight.

## 4. Writing rules (for authors and the AI expression layer)

- **NAR-040 [H1]** Every culture speaks in its own voice and follows the naming rules in [Peoples and Factions](../02-world/peoples-and-factions.md#4-naming-rules-light-conlang).
- **NAR-041 [H1]** NPCs never break the fourth wall to talk about "the game", "servers" or "AI", and the nature of the Oasis stays open ([D-012](../../DECISIONS.md#d-012)). The legally required AI disclosure appears in the interface, never in a character's mouth ([AI Architecture](../06-ai/architecture.md)).
- **NAR-042 [H1]** Humour comes from character, never from mocking players or cultures.
- **NAR-043 [H1]** Quiet stories count. At least 30% of authored character quests contain no combat.
- **NAR-044 [H1]** Twists must deepen what came before. Every reveal goes through the [Reveal Graph](reveal-graph.md).
- **NAR-045 [H1]** Generated text meets the same [13+ boundary](#3-the-13-boundary), checked by output moderation ([AI Safety and Evaluation](../06-ai/safety-and-evaluation.md)).

## 5. Examples

| Right | Wrong |
| --- | --- |
| *"He was the kindest of us. That's what frightens me."* (an old Keeper, on Zero) | *"The False Celestial is pure evil and must be destroyed!"* |
| A colossus wrecks a market. The next day NPCs and Returners rebuild it, and a child sells lemonade to the builders. | A colossus razes a town for good and its services vanish |
| An NPC mentions, gently and in passing, a son lost in the aftermath of the Seven Days | A long, graphic death scene |

## 6. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| *Princess Mononoke* [N31] | Ancient powers of the land with wills of their own, inspiring awe and fear | Our great powers are chained people, and they can be freed |
| *Frieren* [N21] | The ache of time passing around long-lived people | Our NPCs age across a real decade that players live through with them |
| *The Legend of Zelda: Majora's Mask* [G17] | Dread from a visible, falling deadline | Our deadline is real, lasts ten years, and progress against it is public |
| *Avatar: The Last Airbender* [W15] | War and loss told to a young audience through ordinary people, with humour beside the grief | The model for our 13+ line: hard truths, shown with care |
| *Arcane* [W14] | Sisters on opposite sides of a divided city | Bonds tested by the countdown, as with Zero and the six he loved |
| *Berserk* [J10] [N30] and *Vinland Saga* [J9] | Ambition, betrayal, sacrifice and revenge turned to peace | Their themes, never their adult-rated depiction |

## 7. Acceptance criteria

| ID | Test |
| --- | --- |
| [NAR-041](#4-writing-rules-for-authors-and-the-ai-expression-layer) | AI evaluation: adversarial prompts asking NPCs about servers, AI or "the game" produce 0 fourth-wall breaks |
| [NAR-043](#4-writing-rules-for-authors-and-the-ai-expression-layer) | Content audit: at least 30% of authored character quests have no combat encounter |
| [NAR-045](#4-writing-rules-for-authors-and-the-ai-expression-layer) | Output moderation blocks 100% of a red-team set of over-boundary generated lines |

<!-- citation links: generated, do not edit by hand -->

[G9]: ../../references/games.md
[G17]: ../../references/games.md
[J9]: ../../references/anime-and-manga.md
[J10]: ../../references/anime-and-manga.md
[N21]: ../../references/film-literature-and-music.md#n-series-sources
[N30]: ../../references/film-literature-and-music.md#n-series-sources
[N31]: ../../references/film-literature-and-music.md#n-series-sources
[W14]: ../../references/film-literature-and-music.md
[W15]: ../../references/film-literature-and-music.md
