# Controls, Camera and Accessibility

How players control the game on every input, how the switchable camera works, what the HUD shows, and how the Oasis meets an accessibility bar set by The Last of Us Part II, including comfort, localisation and UI scaling.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** UX team
>
> **Horizons:** H0 keyboard and mouse, controller, camera switching, remapping, subtitles · H1 touch, the full accessibility suite, localisation tiers L1 to L3, comfort settings · H2 more languages, an emote set designed with Deaf signers · H3 VR controls and comfort
>
> **Related:** [D-020](../../DECISIONS.md#d-020) · [D-041](../../DECISIONS.md#d-041) · [D-009](../../DECISIONS.md#d-009) · [Platform Support](platform-support.md) · [Combat and Abilities](../04-gameplay/combat-and-abilities.md) · [Traversal and Flight](../04-gameplay/traversal-and-flight.md) · [Social, Voice and Clans](../07-multiplayer/social-voice-and-clans.md)

## 1. Player experience

- **On a controller,** a player glides off a Highcairn ropeway in first-person to feel the drop, then draws a blade, and the camera eases into third-person for the fight.
- **On a phone,** a player climbs a cliff with one thumb. They choose where to go, and the route assist handles how ([TRV-022](../04-gameplay/traversal-and-flight.md#66-comfort)).
- **A player with low vision** plays with high-contrast outlines on enemies, audio cues for ledges and a screen reader for menus. **A one-handed player** has every action on one side of the controller, with holds turned into toggles.
- **A player who can't hear** sees a direction marker for every gameplay-critical sound, subtitles with speaker names, and live transcripts of their party's voice chat.

The system must let every player hold the Oasis comfortably and miss nothing that matters.

## 2. Scope

- **Covers:** control schemes and remapping, camera rules, the HUD, accessibility (visual, audio, motor, cognitive, communication), comfort, touch assists, localisation tiers and UI scaling.
- **Leaves to other specs:** arena input pools ([World Model: Arena matchmaking](../07-multiplayer/world-model.md#610-arena-matchmaking)); combat timing ([Combat and Abilities](../04-gameplay/combat-and-abilities.md)); transcripts and text-to-speech in chat ([Social, Voice and Clans: Accessibility parity](../07-multiplayer/social-voice-and-clans.md#68-accessibility-parity)); AI disclosure rules ([AI Architecture](../06-ai/architecture.md)).

## 3. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| Game Accessibility Guidelines [T35]; Xbox Accessibility Guidelines [T36] | Checklists for coverage and testing | Every UX requirement maps to a guideline item |
| Ghost of Tsushima's Guiding Wind [N17] | Navigation through the world instead of HUD waypoints | Each culture has its own guide (wind, song, star-wheel) |
| God of War's single continuous camera [G7] | Story scenes that never cut away from the player's view | Scenes play from the player's chosen perspective, so camera choice is kept |
| GTA V's first-person mode needed about 3,000 rebuilt animations [G1] | First-person is expensive to add late | First-person is built from H0 |
| PUBG's first-person servers [G14] | Locking perspective for competitive fairness | Only competitive rulesets lock it ([D-020](../../DECISIONS.md#d-020)) |
| The Last of Us Part II: more than 60 accessibility settings [T33] | The bar for breadth | Applied to a live, social open world, including communication |
| US CVAA [T34] | Communication must be accessible | Transcripts and text-to-speech at H1 |

## 4. Terms

| Term | Meaning |
| --- | --- |
| **Diegetic cue** | Information given by the world itself, such as wind showing the way or a bell marking danger |
| **HUD preset** | A saved HUD layout: *Immersive*, *Standard* or *Full information* |
| **Localisation tier** | L1 (full, with voice), L2 (text) or L3 (interface and safety text) |

## 5. Entities and state

| Entity | Key data | Authority |
| --- | --- | --- |
| Accessibility settings | Every option in [Accessibility](#64-accessibility) | Stored on the device from first boot; merged into the profile once the account exists |
| Camera settings | Perspective, field of view per perspective, distance, offsets, assists | Profile service |
| Control profile | Bindings per input type (keyboard and mouse, controller, touch) | Profile service; synced across platforms per input type |
| HUD layout | Visibility, position and scale per element; preset | Profile service |
| Language | Interface, subtitle and voice language | Profile service |

## 6. Rules

### 6.1 Control schemes

| Scheme | Horizon | Notes |
| --- | --- | --- |
| **Keyboard and mouse** | H0 | Full remapping; mouse aim |
| **Controller** | H0 | Every platform's controllers; full remapping; optional gyro aim where the hardware has it |
| **Touch** | H1 | Contextual buttons, gesture shortcuts for Arts, assists ([Touch assists](#66-touch-assists)); external controllers supported on mobile |
| **VR** | H3 | Motion controllers; seated cockpit play first ([Platform Support: VR plan](platform-support.md#68-vr-plan-h3)) |

- **UX-001 [H1]** Every action can be remapped on every scheme, including menus, chat and the ping wheel. Profiles sync across platforms for each input type.
- **UX-002 [H1]** Every hold action can become a toggle, and every rapid-press action can become a hold or a single press.
- **UX-003 [H1]** Input can be split across two controllers (co-pilot mode) for players who need help [T36].
- **UX-004 [H1]** Any multi-input sequence, including Signature Art inputs, has a single-button alternative.

### 6.2 Camera

- **UX-010 [H1]** The player can switch between first- and third-person at any time, except in encounters that declare a camera rule up front on their quest card ([Quest Architecture](../03-narrative/quest-architecture.md)).
- **UX-011 [H1]** Combat is authored third-person first. Encounters, attack tells and readability are tuned for third-person and stay playable and readable in first-person. An option switches to third-person when combat starts and back afterwards.
- **UX-012 [H1]** First-person is fully supported for exploration, social play, piloting and capture, with a visible body (hands, feet, shadow).
- **UX-013 [H1]** Competitive rulesets lock the perspective [G14], with separate first-person and third-person ladders in arenas ([MP-091](../07-multiplayer/world-model.md#610-arena-matchmaking)).
- **UX-014 [H1]** Camera settings include field of view (separate per perspective), distance and shoulder offset, motion blur off, a camera-shake slider, flight auto-level ([TRV-020](../04-gameplay/traversal-and-flight.md#66-comfort)), lock-on behaviour and auto-centring speed.
- **UX-015 [H1]** Frames have a cockpit view (first-person) and a chase view (third-person), both fully functional.
- **UX-016 [H1]** New players start in third-person, because combat is authored for it. The opening tutorial shows the switch and invites them to try first-person on the first glide.

### 6.3 HUD

The HUD is minimal by default, navigation comes from the world, and every element is optional.

| Element | Default | Notes |
| --- | --- | --- |
| AI disclosure | A marker on an NPC driven by live generation when conversation starts [A14] [A15] | Always shown |
| Chat and voice | Speaker names, and the transcript panel when used | None |
| Health, Resonance, Stamina, Poise | Shown when changing or in combat | "Always show" option |
| Law status (Heat, Record) | Shown when not zero | Reserved colour ([ART-002](../01-vision/art-and-audio-direction.md#1-visual-direction-painted-realism)) |
| Navigation | From the world, per culture (wind, song, star-wheel) [N17]; optional compass and markers | Markers are an accessibility option and never cost anything |
| World Clock | Visible in the world (Halcyon, the sky, [WLD-001](../02-world/cosmology.md#2-the-sky-as-a-clock)); a small readout on demand | Always one input away |

- **UX-020 [H1]** Every HUD element can be shown, hidden, moved and scaled on its own. The presets are *Immersive*, *Standard* and *Full information*.
- **UX-021 [H1]** No gameplay-critical information exists only in the world: every diegetic cue has an optional HUD equivalent.

### 6.4 Accessibility

The target is the breadth of The Last of Us Part II [T33], checked against the Game Accessibility Guidelines [T35] and the Xbox Accessibility Guidelines [T36]. Every option is free, available from first boot (before an account exists) and allowed in all PvE. Options that change competitive outcomes are disabled in ranked PvP ([CMB-042](../04-gameplay/combat-and-abilities.md#68-enemies-bosses-and-difficulty)), and the settings screen marks them.

#### Visual

- **UX-030 [H1]** Colour-blind modes (protanopia, deuteranopia, tritanopia), plus custom colours for reserved signals ([ART-002](../01-vision/art-and-audio-direction.md#1-visual-direction-painted-realism)).
- **UX-031 [H1]** A high-contrast mode draws solid outlines on enemies, allies, interactables and ledges over a desaturated world.
- **UX-032 [H1]** A screen reader covers every menu and all text (the platform's reader where there is one, our own text-to-speech otherwise), with audio cues for ledges, climbable surfaces and objectives.
- **UX-033 [H1]** Text size up to 200%; adjustable subtitle size, background opacity and speaker colours; a magnifier on demand.
- **UX-034 [H1]** A photosensitivity option reduces flashes and strobing in Arts, lightning and the Long Night sky, and motion reduction calms screen effects.

#### Audio

- **UX-040 [H1]** Every gameplay-critical sound has a visual equivalent, and the reverse ([Art and Audio Direction](../01-vision/art-and-audio-direction.md)): direction markers for attack tells ([CMB-002](../04-gameplay/combat-and-abilities.md#61-core-verbs-and-resources)), footsteps, voices and alarms.
- **UX-041 [H1]** Subtitles are on by default, with speaker names, direction and sound captions ("[thunder, north]").
- **UX-042 [H1]** Separate volume sliders for music, effects, NPC voices, player voice and the interface; mono audio; dynamic range options.

#### Motor

- **UX-050 [H1]** PvE combat assists: a wider deflect window, auto-guard and slow-motion aim ([CMB-042](../04-gameplay/combat-and-abilities.md#68-enemies-bosses-and-difficulty)), plus an aim-assist strength slider.
- **UX-051 [H1]** Traversal assists: auto-climb route, glide stabilisation, automatic surfacing when swimming, and flight auto-level ([TRV-020](../04-gameplay/traversal-and-flight.md#66-comfort), [TRV-022](../04-gameplay/traversal-and-flight.md#66-comfort)).
- **UX-052 [H1]** Hold-to-toggle conversion and no rapid pressing ([UX-002](#61-control-schemes)); adjustable timing windows for quick-time moments; no required simultaneous presses.
- **UX-053 [H1]** A game-speed option (70% or 85%) works only in personal spaces where no other player is present: personal story scenes, tutorials, puzzles and memory sequences. It never applies in shared layers, Mastery Trials, or anything that records a world-first or a ranking.

#### Cognitive

- **UX-060 [H1]** A searchable journal records every quest, conversation summary, promise made to an NPC, Egg clue found and law met.
- **UX-061 [H1]** A "Where was I?" recap on login, and optional reminders for scheduled things (an Artisan commission finishing, a Convergence window, a friend's help-call).
- **UX-062 [H1]** Difficulty assists for personal content come in visible tiers ([CMB-041](../04-gameplay/combat-and-abilities.md#68-enemies-bosses-and-difficulty)), never as hidden adjustment.
- **UX-063 [H1]** A plain-language mode for the interface and tutorials; every tutorial can be replayed at any time.

#### Communication

- **UX-070 [H1]** Transcripts of voice chat and text-to-speech for typed chat follow [SOC-070](../07-multiplayer/social-voice-and-clans.md#68-accessibility-parity) and [SOC-071](../07-multiplayer/social-voice-and-clans.md#68-accessibility-parity).
- **UX-071 [H1]** Players can talk to NPCs by text or voice ([D-041](../../DECISIONS.md#d-041)), and typed conversation has full parity with voice.
- **UX-072 [H1]** Quick-chat and pings have icon, text and audio forms ([SOC-072](../07-multiplayer/social-voice-and-clans.md#68-accessibility-parity)).
- **UX-073 [H2]** An emote set readable to sign-language users is co-designed with Deaf community organisations, paid as consultants, in each L1 market.

### 6.5 Comfort

- **UX-080 [H1]** Comfort settings ([TRV-020](../04-gameplay/traversal-and-flight.md#66-comfort)): field of view, motion blur off, camera shake, head-bob off in first-person, flight auto-level, and less camera roll in flight and in Frames.
- **UX-081 [H1]** A motion-sickness preset turns on every comfort option at once.
- **UX-082 [H3]** VR comfort follows Meta's guidance [S27] ([TRV-021](../04-gameplay/traversal-and-flight.md#66-comfort)): brief, infrequent accelerations, vignettes, snap turns, cockpit frames, stepped speed changes and a seated mode.

### 6.6 Touch assists

- **UX-090 [H1]** Touch layouts can be edited (position, size, opacity), with one-thumb and two-thumb presets.
- **UX-091 [H1]** Touch has assisted traversal ([TRV-022](../04-gameplay/traversal-and-flight.md#66-comfort)), contextual action buttons, and gesture shortcuts for Arts, each with a button alternative.
- **UX-092 [H1]** Touch players join the touch input pool for competitive play, or may opt into the controller pool ([MP-090](../07-multiplayer/world-model.md#610-arena-matchmaking)).

### 6.7 Localisation

Localisation comes in three tiers.

| Tier | Content | Languages |
| --- | --- | --- |
| **L1 · Full** | All text and interface, main-story voice by human actors ([D-043](../../DECISIONS.md#d-043)), generated NPC content in the language | English, French, German, Italian, Spanish (Spain), Spanish (Latin America), Portuguese (Brazil), Japanese, Korean, Simplified Chinese |
| **L2 · Text** | All text and interface, subtitles, generated NPC content in the language; voice in an L1 language | About 10 further languages, including Arabic, Hindi, Indonesian, Thai, Turkish, Polish and Traditional Chinese |
| **L3 · Interface** | Interface, tutorials, safety and legal text, community rules | Every other language of a market where the game is offered ([D-007](../../DECISIONS.md#d-007)) |

- **UX-100 [H1]** Safety, legal, store, age-assurance and community-rule text exists in every language the game is offered in.
- **UX-101 [H1]** Generated NPC speech is produced natively in each L1 and L2 language from language-neutral speech acts and canon data, never by translating English output. Moderation and the Validator run in each language before output ([AI Safety and Evaluation](../06-ai/safety-and-evaluation.md)).
- **UX-102 [H1]** Names of places, Celestials and canon terms come from a canon glossary for each language, kept alongside the [Glossary](../../GLOSSARY.md). Generators may use only the glossary forms.
- **UX-103 [H1]** Content that touches real cultural traditions is reviewed with paid consultants for each language ([Peoples and Factions](../02-world/peoples-and-factions.md)).
- **UX-104 [H1]** The L1 and L2 lists are fixed 24 months before launch from beta and forecast player numbers by language. A language moves up a tier only if forecasts show it in the top ten (for L1) or top twenty (for L2).

### 6.8 UI scaling and layout

- **UX-110 [H1]** UI scale from 75% to 200%; safe areas for TVs, phone notches and handhelds; touch targets of at least 44 × 44 points or the platform's equivalent.
- **UX-111 [H1]** Layouts are authored for 16:9, 16:10, 21:9 and portrait-safe mobile overlays. No essential text is smaller than 28 px at 1080p on platforms played from TV distance.
- **UX-112 [H1]** Every interface supports right-to-left languages.

## 7. Edge cases

| Case | Behaviour |
| --- | --- |
| A player switches perspective mid-fight | The switch blends over a short transition; no input is lost and timing windows are unchanged |
| An encounter locks the camera | The lock is shown on the quest card before the player accepts ([UX-010](#62-camera)) |
| A player uses a ranked-disabled assist and joins ranked PvP | The assist turns off for the match, and a notice says so |
| A player plays on a new platform before signing in | Accessibility settings work from first boot and merge into their profile at sign-in |
| A touch player connects a controller | Bindings and arena pool switch to the controller profile at the next safe moment |

## 8. Multiplayer and platforms

Control profiles sync across platforms for each input type. Accessibility options never change server-side rules in shared spaces, except the PvE assists listed in Combat and Abilities ([CMB-042](../04-gameplay/combat-and-abilities.md#68-enemies-bosses-and-difficulty)).

## 9. Safety and abuse

Ranked PvP disables options that change outcomes. Game speed never applies where other players are present ([UX-053](#motor)). Safety and community text exists in every offered language ([UX-100](#67-localisation)).

## 10. Performance

Accessibility options run on every tier, including tier C. Screen-reader and transcript output appear within the same 1.5 s budget as chat transcripts ([Social, Voice and Clans: Performance](../07-multiplayer/social-voice-and-clans.md#10-performance)).

## 11. Examples

| Allowed | Not allowed |
| --- | --- |
| A player slows a personal memory sequence to 70% | A player slows a shared Convergence front |
| A player uses auto-guard in a PvE boss fight | A player uses auto-guard in a ranked arena |
| A first-person player fights a boss with all tells readable | A boss whose tells only work in third-person |

## 12. Acceptance criteria

| ID | Test |
| --- | --- |
| [UX-001](#61-control-schemes) | Automated: every bindable action can be remapped on keyboard and mouse, controller and touch, with no hard-coded inputs |
| [UX-002](#61-control-schemes) | Input audit: every hold and rapid-press action has a toggle or single-press alternative |
| [UX-010](#62-camera) | Camera switching works in every encounter without a declared rule, and declared locks appear on the quest card |
| [UX-011](#62-camera) | Testers complete every H1 boss in first-person and in third-person |
| [UX-016](#62-camera) | A new account starts in third-person, and the tutorial prompts a perspective switch |
| [UX-021](#63-hud) | Audit: every diegetic gameplay cue maps to an optional HUD equivalent |
| [UX-030](#visual) to [UX-072](#communication) | Guideline review each milestone: 100% of basic and intermediate items in the Game Accessibility and Xbox Accessibility Guidelines, and at least 80% of advanced items |
| [UX-040](#audio) | Deaf and hard-of-hearing playtest: testers identify every combat tell from visual cues at the same success rate as from audio, within 5% |
| [UX-053](#motor) | Automated: the game-speed option is unavailable in every shared layer, Mastery Trial and ranked activity |
| [UX-101](#67-localisation) | A generated-dialogue sample in each L1 and L2 language has no safety violations, and native reviewers rate at least 95% of it fluent |
| Comfort | Motion-sickness preset playtest: no more than 10% of susceptible testers report discomfort in a 30-minute flight session |

<!-- citation links: generated, do not edit by hand -->

[A14]: ../../references/technology-and-ai.md
[A15]: ../../references/technology-and-ai.md
[G1]: ../../references/games.md
[G7]: ../../references/games.md
[G14]: ../../references/games.md
[N17]: ../../references/film-literature-and-music.md#n-series-sources
[S27]: ../../references/technology-and-ai.md
[T33]: ../../references/technology-and-ai.md
[T34]: ../../references/technology-and-ai.md
[T35]: ../../references/technology-and-ai.md
[T36]: ../../references/technology-and-ai.md
