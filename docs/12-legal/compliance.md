# Legal and Compliance

The legal issues the design must respect, what the design does about each, and the counsel reviews that must be complete before the game is shown or sold.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Legal lead
>
> **Horizons:** H0 IP and patent reviews before NPC memory design is final · H1 full compliance at launch · H2 end of service, Archive Mode and ongoing change
>
> **Related:** [Regulatory Watch](regulatory-watch.md) · [Risk Register](../11-production/risk-register.md) · [Safety and Moderation](../07-multiplayer/safety-and-moderation.md) · [AI Safety and Evaluation](../06-ai/safety-and-evaluation.md) · [References: Legal and Policy](../../references/legal-and-policy.md)

**This is not legal advice; counsel reviews before launch.** It is the design team's reading of public sources, checked on 10-10-2026 and 10-10-2026, written so the design avoids clear problems and counsel knows exactly what to review. Nothing here counts as cleared until its review in [required counsel reviews](#12-required-counsel-reviews) is signed off.

## 1. Intellectual property and permitted homages

The project owner accepted a short list of deliberate homages while the names are working names, and deferred the trademark search ([D-004](../../DECISIONS.md#d-004)). The search is therefore a required review before any public use, not a clearance.

| Element | Status | Evidence | Position |
| --- | --- | --- | --- |
| Title "Ready Player Zero" | Working name; permitted homage | Ernest Cline said in 2020 that a prequel would more likely be called "Ready Player Zero"; no such book had been announced by October 2026 [L1] [R8] | High risk of collision with the author's own floated title. Internal use only until LGL-C01 is signed off. |
| *Ready Player One* rights | Third party, actively licensed | Readyverse Studios holds the rights from Warner Bros. Discovery [L2] [R9] | The IP is commercially active, so the risk is real |
| "the Oasis" (world) | Working name; permitted homage | The virtual world in *Ready Player One* is the OASIS [R1] | Treated the same way as the title |
| Trademark landscape | Not yet searched ([D-004](../../DECISIONS.md#d-004)) | The one search done so far was incomplete; it found a Class 43 restaurant mark [L3] | Full search before any public use (LGL-C01) |
| "Celestials" | Permitted homage | Marvel's Celestials, since 1976 [L4] | Our Celestials are original people with original Oaths ([Celestials](../03-narrative/celestials.md)) and use no Marvel visual language |
| Eggs, the Chronicle Board, a world-scale quest | Permitted homage (ideas) | [D-004](../../DECISIONS.md#d-004); the Scoreboard and egg hunt in *Ready Player One* [R1] | Ideas are shared; all text and design are our own |
| *Pacific Rim* and *Gundam* | Lessons only; no terms or designs | The PACIFIC RIM mark is owned by Legend Pictures [L5]; design lessons from [J5] [J6] | Covered by [LGL-002](#1-intellectual-property-and-permitted-homages) |

- **LGL-001 [H0]** No working name (the title or "Oasis") appears in public material until LGL-C01 is signed off. *Acceptance:* the release checklist blocks marketing and store submissions until the sign-off is recorded.
- **LGL-002 [H1]** Content tools and generated text enforce a restricted-terms list that includes at least *Jaeger*, *Drift* (as a pilot link), *Kaiju* category labels, *Mobile Suit*, *Minovsky*, *OASIS* in Cline's styling, and Marvel character names. Our own terms are *Frame*, *Colossal Frame*, *Colossus* and *Warden* ([Glossary](../../GLOSSARY.md)). *Acceptance:* the content linter flags every seeded test string, and generated text is filtered the same way.

## 2. The Nemesis patent

Warner Bros.' Nemesis patent, US 10,926,179, runs until about 2036 [A18], which covers our whole decade. The design team has not analysed its claims; that is counsel's job (LGL-C04). These features go to counsel for a freedom-to-operate review before their design is final:

| Our feature | Why it needs review | Spec |
| --- | --- | --- |
| NPC Minds that remember a specific player and change how they behave over time | Persistent per-player NPC memory | [NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md) |
| NPC bounty hunters who pursue a wanted Returner across encounters | Recurring NPC antagonists tied to a player | [Law, Crime and Bounties](../05-systems/law-crime-and-bounties.md) · [D-034](../../DECISIONS.md#d-034) |
| Enemies or factions whose ranks or traits change after fights with players | Hierarchy changes driven by player outcomes | [Director and World Events](../06-ai/director-and-world-events.md) |
| NPC bonds and help-calls that deepen relationships | Relationship escalation | [NPC Bonds and Help-Calls](../05-systems/npc-bonds-and-help-calls.md) |

- **LGL-010 [H0]** No NPC memory, rivalry or hierarchy feature passes its design gate without a recorded counsel review against US 10,926,179. *Acceptance:* the design-gate checklist for each feature above links a counsel memo.

## 3. Children, age and online safety

The audience is 13+ ([D-006](../../DECISIONS.md#d-006)), and we follow the strictest common rules worldwide ([D-007](../../DECISIONS.md#d-007)).

| Rule | Fact | What the design does |
| --- | --- | --- |
| COPPA (US) | The amended Rule requires full compliance from 22 April 2026 [L7] | A neutral age screen at account creation. A declared age under 13 blocks the account; there is no under-13 path ([Safety and Moderation](../07-multiplayer/safety-and-moderation.md)). |
| FTC v. Epic (US) | A $275 million COPPA penalty; voice and text chat off by default for minors [L6] | Under-18 voice and open text chat are off by default, with opt-in and warnings ([D-008](../../DECISIONS.md#d-008)) |
| UK Children's Code | High privacy by default [L9] | Private-by-default profiles, location and recording settings for minors |
| UK Online Safety Act | Games with chat or stranger matchmaking are in scope [L8]; self-declaration is not "highly effective" age assurance [T42] | Risk assessments; the children's safety codes; age assurance with a buffer, because facial estimation has a mean error of about 2.5 years near ages 16 to 18 [T43] |
| EU DSA Article 28 | Duties to protect minors, and the Commission's 2025 guidelines [L10] [L11] | Safety by design for minors; no profiling-based advertising (the game has no ads) |
| GDPR Article 8 | The digital age of consent is 13 to 16, set by each member state [L26] | Parental consent where required, notably for voice processing |
| PEGI 2026 criteria | Reported: unrestricted communication raises the rating to 18, and spending off by default can lower it [L20] | Block and report tools everywhere; store spending off by default for under-18s |
| Industry direction | Roblox age checks for chat (January 2026); US state attorney-general lawsuits (2025) [L12] [L13] | Age-checked chat is planned as the norm |

- **LGL-020 [H1]** Every platform build passes a default-settings audit: under-18 accounts start with player voice off, high privacy, store spending off and recording of others off. *Acceptance:* an automated configuration audit on every build ([VIS-006](../01-vision/vision.md#4-experience-goals-observable-testable)).

## 4. AI law and disclosure

| Rule | Fact | What the design does |
| --- | --- | --- |
| EU AI Act Article 50 | People must be told they are interacting with an AI system unless it is obvious; applies from 2 August 2026 [A14] [A15] | Disclosure UX for AI-driven NPCs that does not break immersion, first built in H0 |
| Steam AI disclosure | Developers disclose pre-generated and live-generated AI content and describe their guardrails [A13] | The store disclosure lists both; the guardrails are rule zero, validators and filters ([D-042](../../DECISIONS.md#d-042)) |
| Accountability | Model output is not reproducible [A24] | Every AI decision is logged for replay ([D-042](../../DECISIONS.md#d-042)) |

- **LGL-030 [H1]** Every NPC conversation entry point carries AI disclosure that meets Article 50 and is signed off in LGL-C06. *Acceptance:* a UX review on every platform, and disclosure reachable in one interaction or fewer from any AI-driven conversation.
- **LGL-031 [H1]** Player voice sent to NPCs is processed under a separate permission from player-to-player voice ([D-008](../../DECISIONS.md#d-008), [D-041](../../DECISIONS.md#d-041)), and speech is recognised on the device wherever the hardware allows [T9]. *Acceptance:* a permission-matrix test.

## 5. Performers and AI voices

| Fact | What we do |
| --- | --- |
| SAG-AFTRA's 2025 Interactive Media Agreement requires consent, disclosure and pay for digital replicas, with higher minimums for real-time generation [A9] [A10] | Our voice policy ([D-043](../../DECISIONS.md#d-043)) follows these terms for every voice drawn from a performer |
| Fortnite's AI Darth Vader led to a SAG-AFTRA unfair labor practice charge [A8] | We engage the union before any AI voice is used, not after |
| Replica Studios signed a SAG-AFTRA AI voice agreement in January 2024 and shut down on 30 June 2025 [T11] [T12] | Voice vendors can disappear, so rights and models stay portable |
| Consent-based licensed voice marketplaces exist (ElevenLabs, November 2025) [T10] | A sourcing option, not an endorsement |

- **LGL-040 [H1]** A voice-rights register records, for every AI voice, the source performer (if any), consent scope, disclosure, pay terms, vendor, and portability and exit terms. *Acceptance:* no AI voice ships without a complete register entry.

## 6. Consumer law and the planned ten-year end

The live world ends exactly ten years after launch unless the community succeeds ([D-011](../../DECISIONS.md#d-011)). The schedule and operations are in the [Ten-Year Live Plan](../11-production/ten-year-live-plan.md); this section covers the law.

| Fact | Lesson |
| --- | --- |
| *The Crew* was shut down in 2024 with licences revoked and no offline mode, which started "Stop Killing Games" [R11] | Players resent losing access without warning or anything to keep |
| On 16 June 2026 the European Commission said it cannot propose an obligation to keep games playable, will convene a voluntary end-of-life code of conduct by the end of 2026, and the campaign is now targeting the Digital Fairness Act [R12] | Regulation is moving towards end-of-life duties; Archive Mode puts us ahead of it |
| California AB 2426 (from 1 January 2025): sellers of digital goods must disclose that the buyer gets a revocable licence, not ownership, with some exemptions [R14] | Cosmetic purchases carry licence disclosures |
| Story-timed endings were accepted when they were honest (*Dragalia Lost*, *NieR Re[in]carnation*), and offline or self-hosted editions have precedent [R17] [R18] [R19] [R20] | Honesty plus something to keep ([D-047](../../DECISIONS.md#d-047)) |

- **LGL-050 [H1]** From day one, the Terms of Service and every store page state: the planned end at launch plus ten years; that the outcome depends on the in-game saga; that Archive Mode is released within 7 days if the world ends, and what it keeps; and that the world continues if the community succeeds ([OPS-033](../11-production/ten-year-live-plan.md#8-preparing-both-endings)). *Acceptance:* wording signed off in LGL-C08 appears on every storefront at launch.
- **LGL-051 [H1]** The claim that "the community decides" is true: difficulty and scaling rules for every Convergence are published ([D-011](../../DECISIONS.md#d-011)), so no one can fairly say the developer engineered a failure. *Acceptance:* every Convergence has a public rules page before it unseals.
- **LGL-052 [H2]** From the ninth Long Night, the store follows [OPS-041](../11-production/ten-year-live-plan.md#9-end-of-service-honesty-and-people). *Acceptance:* store audit at LN9.
- **LGL-053 [H1]** Cosmetic purchases carry licence disclosures that meet AB 2426 and equivalent laws [R14]. *Acceptance:* checkout copy signed off in LGL-C10.

## 7. Monetization

The business model ([D-045](../../DECISIONS.md#d-045), [D-046](../../DECISIONS.md#d-046)) is free to enter, with cosmetic-only direct purchases, an optional Patron subscription, no random paid items ever, no paid Omnis and no real-money bridge.

| Rule | Fact | Our exposure |
| --- | --- | --- |
| Belgium | Paid loot boxes ruled illegal gambling (2018) [L16] | None: no random paid items |
| Netherlands | The Council of State overturned the FIFA loot-box penalty (2022) [L17] | None; it shows the law is unsettled elsewhere |
| Brazil | The Digital ECA (in force from 17 March 2026) bans loot boxes in games minors can access [L18] | None |
| PEGI 2026 | Spending and communication criteria affect ratings [L20] | Store spending off by default for under-18s |
| ESRB | "In-Game Purchases" and "Users Interact" labels [L19] | Both labels will apply |
| Apple and Google | Odds disclosure for randomised items; in-app purchase rules [L27] [L28] | Direct purchase only; standard in-app purchase |
| Epic v. Apple | Contempt finding upheld (2025); commission rate sent back for decision [L29] | Link-out payments may become possible; tracked in [Regulatory Watch](regulatory-watch.md) |
| Real-money trading | Demand for game currency never goes away; gold farming happens at scale [L21] [L22] | The Terms of Service ban it; enforcement is in [Economy and Crafting](../05-systems/economy-and-crafting.md) |

- **LGL-060 [H1]** An automated store audit finds no randomised paid items and no item that affects play ([VIS-005](../01-vision/vision.md#4-experience-goals-observable-testable)). *Acceptance:* the audit runs on every store content update.
- **LGL-061 [H1]** Patron auto-renewal, cancellation and refund terms meet the subscription rules of every launch market. *Acceptance:* LGL-C10 is signed off for every market on the launch list.

## 8. Accessibility law

The US CVAA requires accessible in-game communication (since 2019) [T34]. Free-form NPC conversation by text or voice ([D-041](../../DECISIONS.md#d-041)) already gives parity; player chat needs text-to-speech and speech-to-text options.

- **LGL-070 [H1]** Every communication feature (player text, player voice, NPC conversation) has an accessible alternative mode. *Acceptance:* LGL-C11 is signed off; the detail is in [Controls, Camera and Accessibility](../09-platforms/controls-camera-and-accessibility.md).

## 9. Cultural sensitivity

Consultation pays off and disrespect is costly. *Ghost of Tsushima*'s leads became tourism ambassadors [L23]; *Never Alone* was made with about 40 Iñupiat elders [L24]; Japan's prime minister criticised *Assassin's Creed Shadows* over the destruction of a shrine [L25]. The working rules (Culture Sheets, consultant sign-off, sacred elements never loot or destructible) are [WLD-050](../02-world/peoples-and-factions.md#1-cultural-care-rules) to [WLD-054](../02-world/peoples-and-factions.md#1-cultural-care-rules) in [Peoples and Factions](../02-world/peoples-and-factions.md).

## 10. Privacy in play

| Area | Rule |
| --- | --- |
| Recording | Other players' voices are never captured without consent ([D-037](../../DECISIONS.md#d-037)) |
| Voice reports | Privacy-preserving reporting: short clips held on the device, and audio checked only after a report [T37] [T38] |
| Telemetry | Collection for minors follows the Children's Code [L9] and GDPR Article 8 [L26] |
| AI logs | Logged AI inputs include player speech. Retention follows [AI-072](../06-ai/architecture.md#68-decision-records-and-replay) in [AI Architecture](../06-ai/architecture.md) and the retention table in [Safety and Moderation](../07-multiplayer/safety-and-moderation.md); LGL-C07 confirms the values for each jurisdiction. |

## 11. Markets with separate game licensing

Some markets require a separate game licence or impose their own content rules. One canonical world for every player ([D-028](../../DECISIONS.md#d-028)) comes first.

- **LGL-090 [H1]** Mainland China is not a launch datacenter region ([TEC-080](../08-technology/server-and-backend.md#8-multi-region-deployment) in [Server and Backend](../08-technology/server-and-backend.md)). Any later entry into mainland China or another market with separate licensing keeps the one canonical world; a separate, diverging realm is never an option. *Acceptance:* the launch region list matches [TEC-080](../08-technology/server-and-backend.md#8-multi-region-deployment), and any market-entry proposal shows how players in that market join the same world.

## 12. Required counsel reviews

Each review must be signed off by its deadline. The Legal lead is accountable for every review and works with the named co-owner. A missed deadline blocks the milestone it is tied to.

| ID | Review | Owner | Deadline | Sources |
| --- | --- | --- | --- | --- |
| LGL-C01 | Full trademark and title search for "Ready Player Zero", "Oasis" and our key terms | Legal lead with Marketing Lead | Before any public use of a working name | [L1] [L2] [L3] [R8] [R9] |
| LGL-C02 | Opinion on the scope of the permitted homages: title, "Oasis", "Celestials", Eggs, Chronicle Board | Legal lead with Design lead | Before any public use of a working name | [L4] [R1] |
| LGL-C03 | Review of the restricted-terms list (*Pacific Rim*, *Gundam*, Marvel) | Legal lead with Design lead | Vertical Slice | [L5] |
| LGL-C04 | Freedom-to-operate review of the Nemesis patent against NPC memory, bounty hunters and hierarchies | Legal lead with AI Director | Before H0 NPC memory design is final | [A18] |
| LGL-C05 | Age assurance and children's compliance for each market (COPPA, Online Safety Act, DSA, GDPR Article 8, Brazil) | Legal lead with Safety Lead | Closed Beta | [L6] [L7] [L8] [L9] [L10] [L11] [L18] [L26] [T42] |
| LGL-C06 | AI disclosure wording and UX (EU AI Act Article 50; Steam) | Legal lead with AI Director | First version before H0 testers play; final version at Closed Beta | [A13] [A14] [A15] |
| LGL-C07 | Privacy: voice sent to NPCs, AI logs, replays and telemetry retention | Legal lead with Safety Lead | Closed Beta | [L9] [L26] |
| LGL-C08 | End-of-service wording for the Terms of Service and store pages, success-path terms, and Archive Mode licence terms | Legal lead with Live Producer | Before any store page goes live | [R11] [R12] [R14] |
| LGL-C09 | Performer contracts, AI voice terms and union engagement | Legal lead with Audio Director | Before voice production starts | [A8] [A9] [A10] [T11] [T12] |
| LGL-C10 | Patron subscription terms and licence disclosures for each market | Legal lead with Economy Lead | Before any store page goes live | [R14] |
| LGL-C11 | Accessibility compliance (CVAA and equivalent laws) | Legal lead with Platform Lead | Closed Beta | [T34] |
| LGL-C12 | Ratings strategy (ESRB T, PEGI 12 to 16) against communication and spending features, checked against the published PEGI criteria | Legal lead with Executive Producer | Before the first rating submission | [L19] [L20] |
| LGL-C13 | Market-entry review for any market that needs a separate game licence or has its own content rules, confirming that entry keeps the one canonical world ([LGL-090](#11-markets-with-separate-game-licensing)) | Legal lead with Executive Producer | Before any such market is added to the region list | None yet ([Regulatory Watch](regulatory-watch.md#4-gaps-in-our-library)) |

<!-- citation links: generated, do not edit by hand -->

[A8]: ../../references/technology-and-ai.md
[A9]: ../../references/technology-and-ai.md
[A10]: ../../references/technology-and-ai.md
[A13]: ../../references/technology-and-ai.md
[A14]: ../../references/technology-and-ai.md
[A15]: ../../references/technology-and-ai.md
[A18]: ../../references/technology-and-ai.md
[A24]: ../../references/technology-and-ai.md
[J5]: ../../references/anime-and-manga.md
[J6]: ../../references/anime-and-manga.md
[L1]: ../../references/legal-and-policy.md
[L2]: ../../references/legal-and-policy.md
[L3]: ../../references/legal-and-policy.md
[L4]: ../../references/legal-and-policy.md
[L5]: ../../references/legal-and-policy.md
[L6]: ../../references/legal-and-policy.md
[L7]: ../../references/legal-and-policy.md
[L8]: ../../references/legal-and-policy.md
[L9]: ../../references/legal-and-policy.md
[L10]: ../../references/legal-and-policy.md
[L11]: ../../references/legal-and-policy.md
[L12]: ../../references/legal-and-policy.md
[L13]: ../../references/legal-and-policy.md
[L16]: ../../references/legal-and-policy.md
[L17]: ../../references/legal-and-policy.md
[L18]: ../../references/legal-and-policy.md
[L19]: ../../references/legal-and-policy.md
[L20]: ../../references/legal-and-policy.md
[L21]: ../../references/legal-and-policy.md
[L22]: ../../references/legal-and-policy.md
[L23]: ../../references/legal-and-policy.md
[L24]: ../../references/legal-and-policy.md
[L25]: ../../references/legal-and-policy.md
[L26]: ../../references/legal-and-policy.md
[L27]: ../../references/legal-and-policy.md
[L28]: ../../references/legal-and-policy.md
[L29]: ../../references/legal-and-policy.md
[R1]: ../../references/ready-player-and-lifecycle.md
[R8]: ../../references/ready-player-and-lifecycle.md
[R9]: ../../references/ready-player-and-lifecycle.md
[R11]: ../../references/ready-player-and-lifecycle.md
[R12]: ../../references/ready-player-and-lifecycle.md
[R14]: ../../references/ready-player-and-lifecycle.md
[R17]: ../../references/ready-player-and-lifecycle.md
[R18]: ../../references/ready-player-and-lifecycle.md
[R19]: ../../references/ready-player-and-lifecycle.md
[R20]: ../../references/ready-player-and-lifecycle.md
[T9]: ../../references/technology-and-ai.md
[T10]: ../../references/technology-and-ai.md
[T11]: ../../references/technology-and-ai.md
[T12]: ../../references/technology-and-ai.md
[T34]: ../../references/technology-and-ai.md
[T37]: ../../references/technology-and-ai.md
[T38]: ../../references/technology-and-ai.md
[T42]: ../../references/technology-and-ai.md
[T43]: ../../references/technology-and-ai.md
