# Art and Audio Direction

How the Oasis looks and sounds, and why.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Art director and audio director
>
> **Horizons:** H0 one Domain palette, the combat audio kit and the painterly lighting proof on a tier C device · H1 all seven regions and Lumen · H2 Veil and Hollow · H3 presentation for full VR
>
> **Related:** [D-044](../../DECISIONS.md#d-044) · [D-006](../../DECISIONS.md#d-006) · [D-043](../../DECISIONS.md#d-043) · [Vision](vision.md) · [Platform Support](../09-platforms/platform-support.md) · [Controls, Camera and Accessibility](../09-platforms/controls-camera-and-accessibility.md)

## 1. Visual direction: Painted Realism

Painted Realism means believable forms, proportions, materials and light, finished by a painter's hand: brush-textured surfaces, designed palettes, simpler detail at distance, and expressive hand-made effects for Arts ([D-044](../../DECISIONS.md#d-044)).

It suits this game for four reasons:

| Need | How Painted Realism meets it |
| --- | --- |
| A ten-year service | A stylised look ages better than chasing photorealism. This is critical consensus, not a study [G19]. |
| Phones and high-end PCs in one world | A painterly finish hides lower-tier simplification, and clear silhouettes survive low resolution. A UE5 open world already spans mobile and console [S16]. |
| Seven regions that must feel different | Each region gets its own palette and brush language ([Domain palettes](#2-domain-palettes)). |
| Anime-inspired abilities that still feel heavy | Painted, hand-timed effects sit on grounded bodies with real weight. |

- **ART-001 [H1]** Silhouette first. Every enemy class, Frame and colossus is identifiable from its silhouette alone at 50 m on the lowest supported screen.
- **ART-002 [H1]** Readability over richness. Gameplay-critical signals (attack tells, Oath glow, Heat status) use reserved colours that no environment palette may use.
- **ART-003 [H1]** No realistic gore ([D-006](../../DECISIONS.md#d-006)). Impact is shown with stylised flashes, Resonance sparks and dust.
- **ART-004 [H1]** Scale is staged. Camera, ground shake, sound and atmosphere make colossi and Colossal Frames feel huge.

During H0, a painterly lighting research track proves the look on a tier C device, using the lower-tier lighting path. The rule and its test are [TEC-010](../08-technology/engine-and-stack.md#4-rendering-painted-realism-across-tiers) in [Engine and Stack](../08-technology/engine-and-stack.md).

## 2. Domain palettes

| Region | Palette | Brush language | Light motif | Horizon |
| --- | --- | --- | --- | --- |
| Hearthlands | Warm ochres, sea-greys | Soft, inviting | Golden hour | H0 |
| Verdant Spine | Deep greens, moss, granite | Layered foliage strokes | Shafts through the canopy | H1 |
| Drowned Reach | Teal, coral, bioluminescent violet | Flowing, rippled | Caustics and glow-song | H1 |
| Stormcrown | Slate, electric white, sky-blue | Sharp, windswept | Lightning silhouettes | H1 |
| Ember Wastes | Glass-amber, bone, scorched red | Dry brush with heat shimmer | Hard noon, cool night | H1 |
| Iron Meridian | Steel, brass, neon cyan and magenta | Graphic, hard-edged | Neon rain | H1 |
| Frostmarch | Ice-blue, aurora green, ink-black | Fine, crystalline | Aurora and starlight | H1 |
| Lumen | Silver, pearl | Luminous, minimal | The Oasis shining in its sky | H1 |
| Veil | Pearl mist, faded sepia that sharpens into full colour as a memory comes clear | Soft-edged, dissolving | Light with no source | H2 |
| Hollow | Ink-black, dull red rim | Heavy, still | A thin red horizon | H2 |

## 3. Characters, machines and creatures

- **Returners.** One avatar with deep customisation ([D-019](../../DECISIONS.md#d-019)). Cosmetics never hide gameplay signals ([ART-002](#1-visual-direction-painted-realism)).
- **Machines and colossi.** Designed ecology first, with readable anatomy. Traits are combined from several animals, never copied from one. No designs or terms from *Pacific Rim*, *Gundam* or other protected works ([Legal and Compliance](../12-legal/compliance.md)).
- **Celestials.** Each Bound form turns its virtue inside out, and the design shows it: Orun's patient climb becomes an endless walk, and Maris's song becomes a flood ([Celestials](../03-narrative/celestials.md)).

## 4. Camera and presentation

- Players switch between first- and third-person ([D-020](../../DECISIONS.md#d-020)).
- Main-story scenes keep the player's continuous view where possible instead of cutting away.
- Navigation is in the world where possible. Each culture has its own guide (wind, song or star-wheel) instead of HUD waypoints.

## 5. Audio direction

| Area | Direction |
| --- | --- |
| **Score** | A few deep motifs instead of a theme per character. The **World Clock motif** is a ticking pulse that slows across the decade. The **Celestial motif** has six variations and one inverted form for Zero. The **Returner motif** is a hummed melody players can learn and sing. |
| **Adaptive music** | Layers respond to danger, time of day, the Long Night and the current Convergence phase. |
| **Combat sound** | Weight first. Heavy hits have a low thump and a moment of silence on impact. Deflects ring. Every attack has an audible tell. |
| **Voices** | Main-story characters are performed by actors. Other NPCs use licensed, consented AI voices or recorded lines ([D-043](../../DECISIONS.md#d-043)) [A10] [T10]. |
| **Domain instruments** | Each region has its own instrument palette, chosen with that culture's consultants ([Peoples and Factions](../02-world/peoples-and-factions.md#1-cultural-care-rules)). |

- **ART-006 [H1]** Every region's instrument palette is signed off by the consultants for the culture it draws on before its score is recorded.
- **ART-007 [H1]** Every gameplay-critical sound has a visual equivalent, and every gameplay-critical visual has a sound or haptic equivalent [T35] [T36].

## 6. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| *Arcane* and *Into the Spider-Verse* [G19] | Painted textures and hand-drawn effects layered over 3D | Built for a real-time open world, with every effect tuned for gameplay readability ([ART-002](#1-visual-direction-painted-realism)) |
| *Clair Obscur: Expedition 33* [N8] [N9] | Proof that a distinctive painterly look works in UE5, even for a small team | Scaled from phones to high-end PCs and kept fresh for ten years |
| *Pacific Rim* [J6] | Staging scale through camera, sound and atmosphere | Every creature and machine is original |
| *Horizon* [G6] and *Monster Hunter* [M46] | Creatures designed around ecology and readable weak points | Our colossi change ecosystems and settlements, not just fights |
| *Ghost of Tsushima*'s Guiding Wind [N17] | Navigation that lives in the world | Each culture gets its own guide |
| *God of War* (2018) [G7] | One continuous camera for story scenes | Used for main-story scenes, with cuts allowed elsewhere |
| Hans Zimmer's scores for *Interstellar* and *Dune* [N27] [N28] | A few motifs, each starting from an emotional brief | Our motifs track the decade itself, such as the clock pulse slowing as the end nears |
| *Journey* [N29] | A score that follows the player's emotion | Layers also follow world state: the Long Night and Convergence phases |
| *Sekiro* [G10] | Deflects that ring clearly | Every attack in the game has its own audible tell |

## 7. Acceptance criteria

| ID | Test |
| --- | --- |
| [ART-001](#1-visual-direction-painted-realism) | Testers shown black silhouettes at 50 m on the lowest supported screen name the enemy class, Frame or colossus correctly at least 90% of the time |
| [ART-002](#1-visual-direction-painted-realism) | An automated palette check finds no environment material using a reserved signal colour |
| [ART-003](#1-visual-direction-painted-realism) | Content review finds no gore assets in any build |
| [ART-006](#5-audio-direction) | Every region's score has a signed consultant review on file before recording |
| [ART-007](#5-audio-direction) | An accessibility audit pairs every gameplay-critical sound and visual with an equivalent in another channel |

<!-- citation links: generated, do not edit by hand -->

[A10]: ../../references/technology-and-ai.md
[G6]: ../../references/games.md
[G7]: ../../references/games.md
[G10]: ../../references/games.md
[G19]: ../../references/games.md
[J6]: ../../references/anime-and-manga.md
[M46]: ../../references/industry-and-live-service.md
[N8]: ../../references/film-literature-and-music.md#n-series-sources
[N9]: ../../references/film-literature-and-music.md#n-series-sources
[N17]: ../../references/film-literature-and-music.md#n-series-sources
[N27]: ../../references/film-literature-and-music.md#n-series-sources
[N28]: ../../references/film-literature-and-music.md#n-series-sources
[N29]: ../../references/film-literature-and-music.md#n-series-sources
[S16]: ../../references/technology-and-ai.md
[T10]: ../../references/technology-and-ai.md
[T35]: ../../references/technology-and-ai.md
[T36]: ../../references/technology-and-ai.md
