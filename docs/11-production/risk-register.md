# Risk Register

The risks to building *Ready Player Zero* and running it for ten years, with the evidence for each, how we reduce it, and who owns it.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Executive Producer (each risk has its own owner)
>
> **Horizons:** H0 to H3
>
> **Related:** [Scope and Horizons](scope-and-horizons.md) · [Ten-Year Live Plan](ten-year-live-plan.md) · [Legal and Compliance](../12-legal/compliance.md) · [Regulatory Watch](../12-legal/regulatory-watch.md) · [Tech Watch](../08-technology/tech-watch.md)

## 1. How the register works

| Field | Values |
| --- | --- |
| **Likelihood (L)** | Low, Med or High: a judgement by the risk owner, informed by the evidence |
| **Impact (I)** | Med, High or Critical |
| **Status** | **Open:** mitigation planned, work not started · **Mitigating:** mitigation in progress, not yet proven · **Watching:** mitigation proven; the risk is monitored · **Closed** |
| **Evidence** | Source IDs from the [reference library](../../references/README.md) |

- **OPS-060 [H0]** Production leads review the register every month, and review it with the project owner every quarter. Every High or Critical risk has a named owner and a mitigation linked to a requirement or document. *Acceptance:* minutes exist for every monthly review, and no High or Critical risk lacks an owner or a linked mitigation.
- **OPS-061 [H0]** A risk whose likelihood or impact rises by one step is escalated to the project owner within 7 days.

Risk IDs use the form RSK-NN so they can't be confused with the R-series of references.

## 2. The register

| ID | Risk | L | I | Evidence | Mitigation | Owner | Status | Linked docs |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **RSK-01** | **Scope collapse:** too many first-class systems | High | Critical | Anthem built in its final 18 months or so [M29]; Skull and Bones took more than ten years [M31]; FFXIV 1.0 [M24] [M25]; Hyper Light Breaker [G8] | H0 hard gate ([OPS-006](scope-and-horizons.md#24-h0-exit-gate)); six first-class systems at launch ([D-005](../../DECISIONS.md#d-005)); cut and deferral policy | Executive Producer | Mitigating | [Scope and Horizons](scope-and-horizons.md) |
| **RSK-02** | **The real ten-year end:** consumer and legal exposure (misleading-practice claims, licence disclosure, refunds, new end-of-life duties) | Med | High | *The Crew* shutdown [R11]; the EU reply and code of conduct due by end-2026 [R12]; California AB 2426 [R14]; story-timed endings accepted when honest [R17] [R18] | End announced from day one in the Terms of Service and on store pages ([OPS-040](ten-year-live-plan.md#9-end-of-service-honesty-and-people)); Archive Mode ([D-047](../../DECISIONS.md#d-047)); no subscription or prepaid item past LN10 ([OPS-041](ten-year-live-plan.md#9-end-of-service-honesty-and-people)); counsel review LGL-C08 | Legal lead | Mitigating | [Legal and Compliance](../12-legal/compliance.md#6-consumer-law-and-the-planned-ten-year-end) · [Ten-Year Live Plan](ten-year-live-plan.md#9-end-of-service-honesty-and-people) |
| **RSK-03** | **NPC conversation is manipulated or says something unsafe** | High | High | *Where Winds Meet* exploits [A11] [A12]; Fortnite's AI Darth Vader [A7]; AI Dungeon [A16]; OWASP LLM01 [A25] | Rule zero ([D-042](../../DECISIONS.md#d-042)); typed speech acts; validators; a dual-model split [T16]; spotlighting [T17]; control and data separation as in CaMeL [T18]; guard models [T19] [T20]; H0 red-team gate ([OPS-004](scope-and-horizons.md#23-h0-requirements)) | AI Director | Mitigating | [NPC Minds and Conversation](../06-ai/npc-minds-and-conversation.md) · [AI Safety and Evaluation](../06-ai/safety-and-evaluation.md) |
| **RSK-04** | **AI cost and latency at scale** | High | High | *Generative Agents* cost [A1]; the *Death by AI* vendor case study [A26] (vendor source only); an on-device 2B model in PUBG Ally [A3] | Small on-device models where possible [T22] [T24]; pre-generation; caching; per-player budgets; H0 cost gate | Technical Director | Open | [AI Architecture](../06-ai/architecture.md) |
| **RSK-05** | **AI behaviour can't be reproduced, which breaks QA** | High | Med | Model output differs even at temperature 0 [A24] | Record and replay model outputs; test against validators, not text ([OPS-005](scope-and-horizons.md#23-h0-requirements)) | QA Director | Mitigating | [Testing and Acceptance](../10-testing/testing-and-acceptance.md) |
| **RSK-06** | **One canonical world at scale** is beyond proven technology | High | Critical | SpatialOS and *Worlds Adrift* [M1] [M3]; Star Citizen meshing [M5] [T1]; EVE time dilation [M7]; bot-padded scale claims [T3] [T4]; *Dual Universe*'s single shard closed [T41] | Layers and phases at H1 ([D-028](../../DECISIONS.md#d-028)); own the core simulation layer [M1]; time-dilation fallback in Confronts; thousands visible in one place is H3 | Technical Director | Mitigating | [Server and Backend](../08-technology/server-and-backend.md) · [World Model](../07-multiplayer/world-model.md) |
| **RSK-07** | **Cross-platform parity** from phones to high-end PCs in one world | High | High | Lumen platform limits [S3] [S4]; Cyberpunk 2077 on last-gen consoles [S19] [S20]; input fairness [M39] | Capability tiers ([D-009](../../DECISIONS.md#d-009)); Painted Realism scales ([D-044](../../DECISIONS.md#d-044)); input-based pools for competitive play | Technical Director | Mitigating | [Platform Support](../09-platforms/platform-support.md) |
| **RSK-08** | **Netcode for melee, aerial and Frame combat** | High | High | For Honor's move to servers [M38]; physics networking [M35] [M37]; Chaos Destruction has no networking guidance [S10] | Prototype the netcode in H0; cap large actors; split cosmetic from deterministic destruction | Technical Director | Open | [Engine and Stack](../08-technology/engine-and-stack.md) |
| **RSK-09** | **The community fails the saga:** players feel it was rigged, leave after a failed Convergence, or lose heart in the final years | Med | Critical | Collective goals work when anyone can contribute [R21] [R23]; outcomes players decide are remembered [R22] | The safeguards in [D-011](../../DECISIONS.md#d-011): visible progress, no group can make the world fail, retries until the Conjunction, published scaling; a public Mercy tally ([D-017](../../DECISIONS.md#d-017)); both endings fully built ([OPS-030](ten-year-live-plan.md#8-preparing-both-endings)); Archive Mode; Chronicles keep the story readable | Live Producer and Narrative Director | Mitigating | [Ten-Year Live Plan](ten-year-live-plan.md#8-preparing-both-endings) · [Celestial Convergence](../05-systems/celestial-convergence.md) |
| **RSK-10** | **Sustaining ten years of content:** pipeline exhaustion, the cost of keeping two Convergences ready, budget pressure late in the decade | High | High | Destiny's ten-year plan [R15]; FFXIV's saga cadence [R16]; New World's closure [M13] | Pipeline three Ages deep; ready pair certified 120 days ahead ([OPS-020](ten-year-live-plan.md#52-pipeline-depth)); 20% buffer ([OPS-022](ten-year-live-plan.md#52-pipeline-depth)); Weaver templates extend content systemically | Live Producer | Open | [Ten-Year Live Plan](ten-year-live-plan.md#5-production-cadence-and-buffers) |
| **RSK-11** | **Burnout and crunch** over a decade of fixed Long Night dates | Med | High | Reported crunch on *Red Dead Redemption 2* [N7] | No-crunch policy with an overtime limit ([OPS-042](ten-year-live-plan.md#9-end-of-service-honesty-and-people)); 60-day content lock ([OPS-021](ten-year-live-plan.md#52-pipeline-depth)); Long Night rota; wellbeing in every post-mortem ([OPS-043](ten-year-live-plan.md#9-end-of-service-honesty-and-people)) | Studio Head | Mitigating | [Ten-Year Live Plan](ten-year-live-plan.md#9-end-of-service-honesty-and-people) |
| **RSK-12** | **Homage and IP risk:** the title, "Oasis", "Celestials", and the Nemesis patent | Med | High | Cline's own floated title [L1] [R8]; active Ready Player One licensing [L2] [R9]; an incomplete trademark search [L3]; Marvel's Celestials [L4]; Nemesis patent US 10,926,179 [A18] | Homages limited to [D-004](../../DECISIONS.md#d-004)'s list; working names only; trademark search before any public use (LGL-C01); Nemesis freedom-to-operate review (LGL-C04) | Legal lead | Open | [Legal and Compliance](../12-legal/compliance.md#1-intellectual-property-and-permitted-homages) |
| **RSK-13** | **Voice actors, unions and AI voices** | Med | Med | Fortnite Vader unfair labor practice charge [A8]; SAG-AFTRA 2025 agreement [A9] [A10]; Replica's agreement and shutdown [T11] [T12] | Actors for the main story ([D-043](../../DECISIONS.md#d-043)); consent, disclosure and pay; portable voice rights; vendor exit clauses | Audio Director and Legal lead | Mitigating | [Legal and Compliance](../12-legal/compliance.md#5-performers-and-ai-voices) |
| **RSK-14** | **Safety for a 13+ audience and child-safety law:** under-13s getting through, voice, age assurance, the DSA and the Online Safety Act | High | Critical | FTC v. Epic [L6]; amended COPPA [L7]; Online Safety Act [L8]; Children's Code [L9]; DSA Article 28 [L10] [L11]; age assurance [T42] [T43]; Roblox [L12] [L13] | Protective defaults ([D-008](../../DECISIONS.md#d-008)); age assurance with a buffer; strictest common rules ([D-007](../../DECISIONS.md#d-007)); moderation staffing [G12] | Safety Lead | Mitigating | [Safety and Moderation](../07-multiplayer/safety-and-moderation.md) · [Regulatory Watch](../12-legal/regulatory-watch.md) |
| **RSK-15** | **Economy exploits and real-money trading** | High | High | New World duplication [M12]; the scale of gold farming [L22]; "the demand for ISK will not go away" [L21] | Earn-only Omnis, regulated Exchanges, transfer limits, bound top-tier gear ([D-046](../../DECISIONS.md#d-046)); duplication audits; public economy reports [M10] | Economy Lead | Mitigating | [Economy and Crafting](../05-systems/economy-and-crafting.md) |
| **RSK-16** | **Moving to UE6** mid-project | Med | Med | UE 5.8 is the last planned major UE5 release [S2]; Iris documentation still says Experimental [S1] [S7] | Track UE6; keep gameplay apart from engine-specific networking; migration decision gate before the Vertical Slice | Technical Director | Watching | [Engine and Stack](../08-technology/engine-and-stack.md) · [Tech Watch](../08-technology/tech-watch.md) |
| **RSK-17** | **AI vendor dependency and model drift:** deprecations, behaviour changes, price changes, a vendor closing | High | High | Unity's terms change that blocked SpatialOS [M2]; Replica's shutdown [T12]; non-reproducible output [A24] | Pin model versions per release; regression-test against validators; at least two interchangeable providers or an open-weights fallback [T20] [T22]; authored fallbacks ([OPS-003](scope-and-horizons.md#23-h0-requirements)) | AI Director | Open | [AI Architecture](../06-ai/architecture.md) · [Tech Watch](../08-technology/tech-watch.md) |
| **RSK-18** | **Cultural misrepresentation** | Med | Med | Criticism of *Assassin's Creed Shadows* over a shrine [L25]; *Never Alone*'s co-creation [L24]; *Ghost of Tsushima* [L23] | Culture Sheets and consultant sign-off ([WLD-050](../02-world/peoples-and-factions.md#1-cultural-care-rules) to [WLD-054](../02-world/peoples-and-factions.md#1-cultural-care-rules)) | World Lead | Mitigating | [Peoples and Factions](../02-world/peoples-and-factions.md) |
| **RSK-19** | **Live-service market risk** | Med | Critical | Concord [M30]; the closures of Anthem and New World [M13] [M28] | Prove fun in H0 and in closed beta; an honest end-of-service plan | Executive Producer | Open | [Scope and Horizons](scope-and-horizons.md) |
| **RSK-20** | **Overpromising** H2 and H3 features | Med | High | No Man's Sky [M32] [M33] | Only H1 is announced as launch content ([OPS-001](scope-and-horizons.md#1-horizons-in-production)) | Marketing Lead | Mitigating | [Scope and Horizons](scope-and-horizons.md#1-horizons-in-production) |
| **RSK-21** | **AI disclosure rules change faster than the game** | Med | Med | EU AI Act Article 50 [A14] [A15]; Steam disclosure [A13] | Disclosure UX from H0; quarterly regulatory watch | Legal lead | Watching | [Regulatory Watch](../12-legal/regulatory-watch.md) |
| **RSK-22** | **Loot-box and spending law tightens**, even for cosmetic stores | Low | Med | Belgium [L16]; Brazil [L18]; PEGI 2026 [L20]; store rules [L27] [L28] | No random paid items ([D-045](../../DECISIONS.md#d-045)); store spending off by default for under-18s | Legal lead | Watching | [Legal and Compliance](../12-legal/compliance.md#7-monetization) |

## 3. Heat map

| Impact / Likelihood | Low | Med | High |
| --- | --- | --- | --- |
| **Critical** | None | RSK-09, RSK-19 | RSK-01, RSK-06, RSK-14 |
| **High** | None | RSK-02, RSK-11, RSK-12, RSK-20 | RSK-03, RSK-04, RSK-07, RSK-08, RSK-10, RSK-15, RSK-17 |
| **Med** | RSK-22 | RSK-13, RSK-16, RSK-18, RSK-21 | RSK-05 |

## 4. When each risk peaks

| Phase | Risks that peak |
| --- | --- |
| Pre-production to H0 | RSK-01, RSK-03, RSK-04, RSK-08, RSK-12 (the Nemesis review comes before NPC memory design is final) |
| Launch | RSK-06, RSK-07, RSK-14, RSK-19 |
| Years 1 to 5 | RSK-10, RSK-15, RSK-17 |
| Years 6 to 10 | RSK-02 (end of service), RSK-09, RSK-10 (late-decade budget), RSK-11 |

<!-- citation links: generated, do not edit by hand -->

[A1]: ../../references/technology-and-ai.md
[A3]: ../../references/technology-and-ai.md
[A7]: ../../references/technology-and-ai.md
[A8]: ../../references/technology-and-ai.md
[A9]: ../../references/technology-and-ai.md
[A10]: ../../references/technology-and-ai.md
[A11]: ../../references/technology-and-ai.md
[A12]: ../../references/technology-and-ai.md
[A13]: ../../references/technology-and-ai.md
[A14]: ../../references/technology-and-ai.md
[A15]: ../../references/technology-and-ai.md
[A16]: ../../references/technology-and-ai.md
[A18]: ../../references/technology-and-ai.md
[A24]: ../../references/technology-and-ai.md
[A25]: ../../references/technology-and-ai.md
[A26]: ../../references/technology-and-ai.md
[G8]: ../../references/games.md
[G12]: ../../references/games.md
[L1]: ../../references/legal-and-policy.md
[L2]: ../../references/legal-and-policy.md
[L3]: ../../references/legal-and-policy.md
[L4]: ../../references/legal-and-policy.md
[L6]: ../../references/legal-and-policy.md
[L7]: ../../references/legal-and-policy.md
[L8]: ../../references/legal-and-policy.md
[L9]: ../../references/legal-and-policy.md
[L10]: ../../references/legal-and-policy.md
[L11]: ../../references/legal-and-policy.md
[L12]: ../../references/legal-and-policy.md
[L13]: ../../references/legal-and-policy.md
[L16]: ../../references/legal-and-policy.md
[L18]: ../../references/legal-and-policy.md
[L20]: ../../references/legal-and-policy.md
[L21]: ../../references/legal-and-policy.md
[L22]: ../../references/legal-and-policy.md
[L23]: ../../references/legal-and-policy.md
[L24]: ../../references/legal-and-policy.md
[L25]: ../../references/legal-and-policy.md
[L27]: ../../references/legal-and-policy.md
[L28]: ../../references/legal-and-policy.md
[M1]: ../../references/industry-and-live-service.md
[M2]: ../../references/industry-and-live-service.md
[M3]: ../../references/industry-and-live-service.md
[M5]: ../../references/industry-and-live-service.md
[M7]: ../../references/industry-and-live-service.md
[M10]: ../../references/industry-and-live-service.md
[M12]: ../../references/industry-and-live-service.md
[M13]: ../../references/industry-and-live-service.md
[M24]: ../../references/industry-and-live-service.md
[M25]: ../../references/industry-and-live-service.md
[M28]: ../../references/industry-and-live-service.md
[M29]: ../../references/industry-and-live-service.md
[M30]: ../../references/industry-and-live-service.md
[M31]: ../../references/industry-and-live-service.md
[M32]: ../../references/industry-and-live-service.md
[M33]: ../../references/industry-and-live-service.md
[M35]: ../../references/industry-and-live-service.md
[M37]: ../../references/industry-and-live-service.md
[M38]: ../../references/industry-and-live-service.md
[M39]: ../../references/industry-and-live-service.md
[N7]: ../../references/film-literature-and-music.md#n-series-sources
[R8]: ../../references/ready-player-and-lifecycle.md
[R9]: ../../references/ready-player-and-lifecycle.md
[R11]: ../../references/ready-player-and-lifecycle.md
[R12]: ../../references/ready-player-and-lifecycle.md
[R14]: ../../references/ready-player-and-lifecycle.md
[R15]: ../../references/ready-player-and-lifecycle.md
[R16]: ../../references/ready-player-and-lifecycle.md
[R17]: ../../references/ready-player-and-lifecycle.md
[R18]: ../../references/ready-player-and-lifecycle.md
[R21]: ../../references/ready-player-and-lifecycle.md
[R22]: ../../references/ready-player-and-lifecycle.md
[R23]: ../../references/ready-player-and-lifecycle.md
[S1]: ../../references/technology-and-ai.md
[S2]: ../../references/technology-and-ai.md
[S3]: ../../references/technology-and-ai.md
[S4]: ../../references/technology-and-ai.md
[S7]: ../../references/technology-and-ai.md
[S10]: ../../references/technology-and-ai.md
[S19]: ../../references/technology-and-ai.md
[S20]: ../../references/technology-and-ai.md
[T1]: ../../references/technology-and-ai.md
[T3]: ../../references/technology-and-ai.md
[T4]: ../../references/technology-and-ai.md
[T11]: ../../references/technology-and-ai.md
[T12]: ../../references/technology-and-ai.md
[T16]: ../../references/technology-and-ai.md
[T17]: ../../references/technology-and-ai.md
[T18]: ../../references/technology-and-ai.md
[T19]: ../../references/technology-and-ai.md
[T20]: ../../references/technology-and-ai.md
[T22]: ../../references/technology-and-ai.md
[T24]: ../../references/technology-and-ai.md
[T41]: ../../references/technology-and-ai.md
[T42]: ../../references/technology-and-ai.md
[T43]: ../../references/technology-and-ai.md
