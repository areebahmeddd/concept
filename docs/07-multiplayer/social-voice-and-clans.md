# Social, Voice and Clans

How Returners talk, find each other, group up and belong, with safe defaults for younger players and full parity for players who can't use voice.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Social team
>
> **Horizons:** H0 party text and voice, friends, block and mute · H1 every channel, clans, alliances, transcripts and text-to-speech, cross-platform friends · H2 clan halls in Wards, Steward notices on city boards · H3 spatial voice in VR
>
> **Related:** [D-008](../../DECISIONS.md#d-008) · [D-019](../../DECISIONS.md#d-019) · [D-028](../../DECISIONS.md#d-028) · [D-025](../../DECISIONS.md#d-025) · [World Model](world-model.md) · [Safety and Moderation](safety-and-moderation.md) · [PvP and Protection](../05-systems/pvp-and-protection.md)

## 1. Player experience

- **A 14-year-old's first evening.** They join a party with two school friends using a friend code. Text with their friends works at once, and so do quick-chat and pings. Voice is off, and the settings explain why and how to turn it on, with a parent's approval where their country requires it. Nobody they don't know can message them. They still play freely with strangers at the Convergence front, using pings, emotes and quick-chat.
- **An adult in Halcyon.** Party voice is on and proximity voice is off. They switch proximity on for a festival, hear the crowd around the Chronicle Board as positional voices, and mute one loud stranger with a single action.
- **A Deaf player in a clan raid.** The clan talks by voice. Live transcripts of the channel appear in a chat panel. They type replies, which are read aloud to the party in a voice they chose.
- **A clan of thirty.** They plan Confront night on the clan calendar, form an alliance with two other clans to cover three fronts, and show nothing more than their colours. Being in a clan gives them better coordination, never more power.

The system must make every player feel reachable by the people they choose and unreachable by everyone else.

## 2. Scope

- **Covers:** voice and text channels, defaults by age, direct messages, friends, presence, parties and raid groups, clans and alliances, the Returners' Concord, cross-platform communication, accessibility parity, identity, and the block, mute and report actions.
- **Leaves to other specs:** age assurance, moderation and data retention ([Safety and Moderation](safety-and-moderation.md)); talking to NPCs, which is a separate permission ([NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md)); clan war rules ([PvP and Protection](../05-systems/pvp-and-protection.md)); layer placement of parties and clans ([World Model: Layers](world-model.md#62-layers-capacity-assignment-split-and-merge)); help-call rules ([NPC Bonds and Help-Calls](../05-systems/npc-bonds-and-help-calls.md)).

## 3. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| Club Penguin Safe Chat and sender-only blocking [G12] | Preset-phrase chat as a safe floor | Quick-chat is a floor, not the whole experience, for a 13+ audience |
| Epic Online Services: cross-platform accounts, lobbies and voice [T31] [T26] | One friends list and voice across every platform family | Our own account stays the identity root, so a vendor change can't erase anyone's identity [M2] |
| FTC v. Epic: voice and text chat off by default for minors [L6] | Protective defaults for under-18s | Quick-chat and pings mean minors are never socially mute |
| Roblox age checks for chat [L12] | Age-banded chat as the industry direction | Age bands gate communication features, never basic play |
| US CVAA [T34] | Communication features must be accessible | Transcripts and text-to-speech ship at H1 |

## 4. Terms

| Term | Meaning |
| --- | --- |
| **Alliance** | Up to 5 clans linked for scheduling and shared channels. No shared assets. |
| **Clan** | A persistent, optional player organisation of up to 300 members. |
| **Party** | Up to 6 Returners who share a layer, quest join state and party channels. |
| **Quick-chat** | Preset, localised phrases and contextual pings. Always available to everyone. |
| **Raid group** | Up to 8 parties (48 Returners) linked for a Convergence front, a Long Night event or a clan war. |
| **Returners' Concord** | The loose fellowship of all Returners ([Peoples and Factions](../02-world/peoples-and-factions.md)). A shared identity for global contribution, not a clan. |

## 5. Entities and state

| Entity | Key data | Authority |
| --- | --- | --- |
| Account | Age band, assurance status, parental settings, platform links | Identity service |
| Avatar | One per account ([D-019](../../DECISIONS.md#d-019)); name and its change history ([PRG-001](../04-gameplay/avatar-and-progression.md#61-the-avatar)) | Profile service |
| Block list | Per account; enforced everywhere | Social graph service |
| Clan | Name, crest, roles, members, calendar, board, alliance links | Clan service (G-class, [World Model: State classes](world-model.md#5-state-classes-and-authority)) |
| Comms settings | On or off per channel, who can make contact, transcript and text-to-speech preferences | Profile service; the strictest of game, platform and parental settings applies |
| Friend link | Two accounts, mutual consent, how it was made (code, party, platform import) | Social graph service |

## 6. Rules

### 6.1 Defaults by age band

The table applies [D-008](../../DECISIONS.md#d-008) and the strictest-rule principle of [D-007](../../DECISIONS.md#d-007) to every channel. "Opt-in" always means an affirmative choice on a plain-language warning screen, plus verified parental consent where law requires it [L26].

| Feature | Under 18: default | Under 18: can change? | Adult: default |
| --- | --- | --- | --- |
| **Party voice** | Off | Yes, by opt-in | On |
| **Clan voice** | Off | Yes, by opt-in | Off (one action to join) |
| **Proximity voice** | Off | Yes, by opt-in, but heard by and hearing friends only | Off |
| **Text with friends** (direct messages, and party and clan text from friends) | On, filtered | Not applicable | On, filtered |
| **Party and clan text from non-friends** | Quick-chat only | Yes, by opt-in, at the strictest filter | On, filtered |
| **Open text** (proximity, city, world region) | Off; quick-chat only | Yes, by opt-in, at the strictest filter | On, filtered |
| **Direct messages** | Friends only | No | Friends only (can widen to party and clan) |
| **Friend requests** | Only from players they have partied with, or by friend code | No | From anyone (can be restricted) |
| **Presence and location** | Friends only; "appear offline" available | Not applicable | Friends only |
| **Voice to NPCs** | Off; typed conversation always available ([NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md#611-voice-input-privacy-and-disclosure)) | Yes, by opt-in | On, processed on the device; cloud processing only with explicit consent |

- **SOC-001 [H1]** Player-to-player voice is off by default for every under-18 account. Turning it on needs the opt-in described above.
- **SOC-002 [H1]** Adults start with proximity voice off and party voice on.
- **SOC-003 [H1]** An account without the age assurance its jurisdiction requires gets under-18 defaults for every feature in the table ([Safety and Moderation: Age assurance](safety-and-moderation.md#61-age-assurance)).
- **SOC-004 [H1]** No content ever requires voice, including Convergences, clan wars and arenas. Quick-chat and pings cover every coordination need of every front.
- **SOC-005 [H1]** Settings are per channel and can be changed at any time outside combat, in two steps or fewer from the pause menu.
- **SOC-006 [H1]** An under-18 account that opts into proximity voice hears, and is heard by, only its friends. Other players nearby hear nothing from it and see its quick-chat instead.

### 6.2 Channels

| Channel | Voice | Text | Who | Kept for |
| --- | --- | --- | --- | --- |
| **Party** | Yes | Yes | Party members, in any layer or DC region | The session |
| **Raid group** | Leaders' channel plus party channels | Yes | The raid group | The session |
| **Clan** | Yes, in rooms | Yes | Online clan members | Text: 30 days |
| **Alliance** | Officers' room | Yes | Alliance officers and members | Text: 30 days |
| **Proximity** | Positional, fading over 30 m | Speech bubbles and a log | Nearby players in the same layer | Not kept |
| **City board** | No | Posts (notices, recruitment, trade wants) | One per city, shared by every layer (S-class) | 7 days; moderated as user content |
| **World region** | No | Yes | One per world region and per moon, in each DC region | Not kept |
| **Front** | No; pings only | Quick-chat and filtered text | One Convergence front layer | The session |

- **SOC-010 [H1]** Proximity voice is positional and muffled by walls and water. Underwater it stays muffled unless both players are inside a Drowned Reach air-dome city or using song-lanterns.
- **SOC-011 [H1]** Every voice channel shows who is speaking, and each speaker can be muted with one action.
- **SOC-012 [H1]** A contextual ping wheel (danger, go here, need help, gather, thanks) works on every input and is localised automatically.
- **SOC-013 [H2]** A Steward may pin official notices to their city's board within published limits ([D-038](../../DECISIONS.md#d-038)).

### 6.3 Friends and presence

- **SOC-020 [H1]** Each account has one friends list across every platform. Platform friends can be imported where the platform allows, and appear only after both players accept in the game.
- **SOC-021 [H1]** Presence (online, world region, activity) is visible to friends only, for everyone. Exact location is never shown to non-friends.
- **SOC-022 [H1]** Help-calls go only between friends. The helper arrives at their own nearest discovered Wayshrine, not on top of the caller ([NPC Bonds and Help-Calls](../05-systems/npc-bonds-and-help-calls.md)).
- **SOC-023 [H1]** Profiles follow the visibility defaults in [PRG-003](../04-gameplay/avatar-and-progression.md#61-the-avatar) ([Avatar and Progression](../04-gameplay/avatar-and-progression.md)): public name, Player Rank, Adventure Rank and chosen titles are public; everything else is private until shared.

### 6.4 Parties and raid groups

- **SOC-030 [H1]** A party holds up to 6 Returners and always shares a layer ([MP-020](world-model.md#62-layers-capacity-assignment-split-and-merge)). The leader can hand over leadership, and a party survives a disconnect for 5 minutes.
- **SOC-031 [H1]** Party members follow quest joining rules: someone who joins after a quest starts can help outside it but can't join it ([QST-002](../03-narrative/quest-architecture.md#3-joining-rules), [Quest Architecture](../03-narrative/quest-architecture.md)).
- **SOC-032 [H1]** Raid groups exist only for activities that need them and dissolve afterwards. A raid group never puts strangers into voice together.

### 6.5 Clans and alliances

Clans are light and optional, and give no gameplay advantage.

| Feature | Rule |
| --- | --- |
| Size | 2 to 300 members. Larger communities link through alliances. |
| Joining | One clan per avatar. Leaving has no penalty. Joining a different clan has a 24-hour cooldown, to stop spy churn. |
| Roles | Founder, Officer, Member, plus up to 5 custom roles with chosen permissions: invite, remove, edit board, schedule, manage alliance, declare clan war |
| Tools | Roster, calendar showing Oasis time and local time, clan board, voice rooms, crest and colours (cosmetic), and a shared Chronicle of the clan's deeds |
| Shared storage | A clan chest for materials and crafted goods, inside the daily transfer limits of [D-046](../../DECISIONS.md#d-046), with a full audit log |
| Housing [H2] | A clan may commission a clan hall in a Ward from an NPC builder ([Housing](../05-systems/housing.md)) |
| Alliances | Up to 5 clans, with a shared channel and calendar; no shared storage or assets |

- **SOC-040 [H1]** Clan membership never changes damage, defence, drop rates, progression speed, Omnis income or access to content. No stat or reward table refers to clan membership, apart from cosmetic clan rewards.
- **SOC-041 [H1]** No content is clan-only ([QST-004](../03-narrative/quest-architecture.md#3-joining-rules)). Every clan activity has a route outside clans with equal reward.
- **SOC-042 [H1]** Clan wars are opt-in for the clan and for each member, under the rules in [PvP and Protection](../05-systems/pvp-and-protection.md) ([D-025](../../DECISIONS.md#d-025)). Their rewards are cosmetic or reputational and never harm players who didn't take part.
- **SOC-043 [H1]** Clan names, crests and boards are user content and pass moderation before anyone else can see them ([Safety and Moderation: User-generated content](safety-and-moderation.md#67-user-generated-content)).
- **SOC-044 [H1]** If a clan's founder is inactive for 60 days, foundership passes to the longest-serving active Officer.

### 6.6 The Returners' Concord

- **SOC-050 [H1]** Every Returner belongs to the Concord automatically. It has no leaders, no chat channel, no roster and no ranks.
- **SOC-051 [H1]** The Concord is the player-facing name for global contribution: each player's contribution record ([VIS-004](../01-vision/vision.md#4-experience-goals-observable-testable)), the World Clock's global progress and the Chronicle inscriptions all appear under it.
- **SOC-052 [H1]** The Concord is never presented or treated as a clan. Clan screens never list it, and nobody needs a clan to contribute.

### 6.7 Cross-platform communication

- **SOC-060 [H1]** Text, voice, friends, parties and clans work across every platform family ([Platform Support](../09-platforms/platform-support.md)), through a cross-platform service behind our own identity layer ([Engine and Stack: Middleware](../08-technology/engine-and-stack.md#7-middleware-and-services)).
- **SOC-061 [H1]** Where a platform's own communication or parental setting is stricter than the game's, the platform setting wins, and the UI says which setting is in force.
- **SOC-062 [H1]** On touch devices voice defaults to push-to-talk. On consoles and PC, players choose open mic or push-to-talk.

### 6.8 Accessibility parity

- **SOC-070 [H1]** Any listener can turn on live transcripts of the voice channels they are in. Transcription runs on the device where the platform supports it [T9], and otherwise in our own speech service [T8]. Transcripts are shown and discarded, and are kept only inside a report the listener submits.
- **SOC-071 [H1]** Any player can have their typed messages spoken into voice channels, and have incoming text read to them, with a choice of synthetic voices and speeds [T34].
- **SOC-072 [H1]** Quick-chat and pings have text, icon and audio forms, so they work for blind, Deaf and non-verbal players alike.

### 6.9 Identity

- **SOC-080 [H1]** The one persistent avatar is the player's public identity ([D-019](../../DECISIONS.md#d-019)). Platform IDs and real names are never shown to other players by default.
- **SOC-081 [H1]** Avatar, clan and house names are filtered. Name changes are rare, and their history is visible to safety staff ([PRG-001](../04-gameplay/avatar-and-progression.md#61-the-avatar)).
- **SOC-082 [H1]** Recordings never capture other players' voices without their consent ([D-037](../../DECISIONS.md#d-037), [Recording and Replays](../05-systems/recording-and-replays.md)).

### 6.10 Block, mute and report

| Action | Effect | Scope |
| --- | --- | --- |
| **Mute** | You stop hearing or seeing their voice and text | You only; reversible |
| **Block** | Works both ways: no voice, text, messages, invites, trades, friend requests or help-calls between you; their user content (signs, house name, board posts) is hidden from you; layering keeps you apart ([MP-026](world-model.md#62-layers-capacity-assignment-split-and-merge)) | Enforced by the server everywhere |
| **Report** | Opens a report from any surface (name, chat line, voice speaker, clip, house, board post) in two interactions or fewer ([Safety and Moderation: Reporting](safety-and-moderation.md#66-reporting-sanctions-appeals-and-escalation)) | Sent to moderation |

- **SOC-090 [H1]** Mute and block are available everywhere a player can be seen or heard, including the voice speaker list and the replay viewer.
- **SOC-091 [H1]** A blocked player is not told they were blocked.

## 7. Edge cases

| Case | Behaviour |
| --- | --- |
| An under-18 turns voice on, then a parent withdraws consent | Voice turns off at once on every device, and the player is told why |
| A party has an adult and a minor whose voice is off | The adult hears nothing from the minor and gets no transcript of them; quick-chat works for everyone |
| A clan's founder is banned | Foundership passes under [SOC-044](#65-clans-and-alliances); the clan is unaffected unless it is sanctioned itself |
| The voice service goes down | Text, quick-chat and pings continue, and a banner explains the outage |
| A player in a clan war is at the protected Avatar Level 1 to 3 | They can't be targeted outside arenas ([D-025](../../DECISIONS.md#d-025)), and the war screen leaves them out |

## 8. Multiplayer and platforms

Party channels span layers and DC regions. Proximity voice is per layer, so you only hear players you can see. Cross-platform voice routes through the voice relay nearest each speaker.

## 9. Safety and abuse

The defaults, block and report actions are specified here and operated by [Safety and Moderation](safety-and-moderation.md). Clan chest logs and transfer limits make the chest useless for laundering real-money trades ([D-046](../../DECISIONS.md#d-046)). Friend-code links expire after 24 hours.

## 10. Performance

Party voice reaches listeners in the same DC region within 200 ms. Proximity voice mixes at most the 8 loudest nearby speakers for each listener. Transcripts appear within 1.5 s of speech.

## 11. Examples

| Allowed | Not allowed |
| --- | --- |
| A clan's crest glows on the Chronicle Board after a Convergence | A clan buff of 5% more damage |
| A 15-year-old with parental consent uses party voice with friends | A 15-year-old's proximity voice heard by strangers |
| A Convergence front coordinated entirely with pings | A front that only succeeds with voice |

## 12. Acceptance criteria

| ID | Test |
| --- | --- |
| [SOC-001](#61-defaults-by-age-band) | Settings audit on every platform build: new under-18 accounts have every voice channel off, and turning one on always needs the opt-in flow (with parental consent in flagged jurisdictions) |
| [SOC-002](#61-defaults-by-age-band) | New adult accounts on every platform: party voice on, proximity voice off |
| [SOC-003](#61-defaults-by-age-band) | An unassured account in a jurisdiction that requires assurance gets under-18 defaults, verified by an automated matrix test |
| [SOC-004](#61-defaults-by-age-band) | Bot parties with voice disabled complete every Convergence front and arena mode |
| [SOC-006](#61-defaults-by-age-band) | An opted-in under-18 in a 200-player layer is heard by friends only, across 1,000 trials |
| [SOC-040](#65-clans-and-alliances) | Static analysis of stat and reward tables finds no reference to clan membership outside cosmetic tables |
| [SOC-070](#68-accessibility-parity) | Transcripts reach at least 90% word accuracy on the internal test set in each launch language, and none remain in storage after the session |
| [SOC-090](#610-block-mute-and-report) | UI audit: mute and block are reachable in two interactions or fewer from every listed surface |
| Block | 10,000 blocked pairs under bot load: no message, invite, trade or help-call is delivered between them |

<!-- citation links: generated, do not edit by hand -->

[G12]: ../../references/games.md
[L6]: ../../references/legal-and-policy.md
[L12]: ../../references/legal-and-policy.md
[L26]: ../../references/legal-and-policy.md
[M2]: ../../references/industry-and-live-service.md
[T8]: ../../references/technology-and-ai.md
[T9]: ../../references/technology-and-ai.md
[T26]: ../../references/technology-and-ai.md
[T31]: ../../references/technology-and-ai.md
[T34]: ../../references/technology-and-ai.md
