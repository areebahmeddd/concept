# Testing and Acceptance

How every requirement in this specification is proven, from traceability and test types to horizon exit evidence, player-scenario simulations, debugging emergent behaviour and validating the live game.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** QA director
>
> **Horizons:** H0 traceability tooling, deterministic simulation, bots, the AI evaluation harness, H0 exit evidence · H1 full test pyramid, load and chaos programmes, certification, localisation, launch readiness review · H2 per-event validation for each Long Night and Convergence · H3 scale tests for thousands of players visible in one place
>
> **Related:** [D-001](../../DECISIONS.md#d-001) · [D-030](../../DECISIONS.md#d-030) · [D-042](../../DECISIONS.md#d-042) · [D-009](../../DECISIONS.md#d-009) · [D-024](../../DECISIONS.md#d-024) · [Conventions: requirements](../00-meta/conventions.md#3-requirements) · [Vision](../01-vision/vision.md) · [AI Safety and Evaluation](../06-ai/safety-and-evaluation.md) · [Scope and Horizons](../11-production/scope-and-horizons.md)

## 1. Goals

1. **Every requirement is provable.** No requirement ships without at least one automated or scripted test, or a logged waiver.
2. **Emergence is debuggable.** QA and support can always tell an intended variation from a bug ([QST-012](../03-narrative/quest-architecture.md#5-variation-within-bounds)).
3. **The world works when parts fail.** AI services, regions, vendors and whole datacentres can fail without breaking quests, ledgers or the countdown.
4. **The feel is measured.** The experience goals [VIS-001](../01-vision/vision.md#4-experience-goals-observable-testable) to [VIS-007](../01-vision/vision.md#4-experience-goals-observable-testable) are telemetry and playtest thresholds, not adjectives ([Vision: experience goals](../01-vision/vision.md#4-experience-goals-observable-testable)).

## 2. Scope

This document owns the test strategy, traceability, test types, environments, the evidence QA brings to each horizon exit, player-scenario simulations, tools for debugging emergent behaviour, telemetry acceptance and live-ops validation.

It leaves to other documents:

- the H0 exit gate itself: [Scope and Horizons: H0 exit gate](../11-production/scope-and-horizons.md#24-h0-exit-gate);
- the AI evaluation harness, red team and kill switches: [AI Safety and Evaluation](../06-ai/safety-and-evaluation.md);
- each system's own acceptance tests: the acceptance criteria section of each spec.

## 3. Inspirations

| Source | What we take | What we change |
| --- | --- | --- |
| *Anthem* [M28] [M29] | Largely built in its final 18 months; its servers closed | We prove the core loop at H0 with a formal exit review |
| *FFXIV* 1.0 and *A Realm Reborn* [M24] [M25] | Chasing fidelity before fun and stability | H0 exit tests fun and stability, not fidelity |
| *No Man's Sky* [M32] [M33] | Backlash over missing promised features | Launch readiness checks that no H2 or H3 feature is marketed as a launch feature |
| *New World* duplication shutdown [M12] | Economy exploits can force drastic shutdowns | Ledger fuzzing and duplication audits are launch gates |
| Hadean's *EVE: Aether Wars* [T4] | Headline player counts often include bots | Load results report humans and bots separately; scale claims need evidence from human players |
| *EVE Online* Time Dilation [M7] | Graceful slowdown under load | Load tests verify the dilation floor and normalisation in [MP-053](../07-multiplayer/world-model.md#65-convergence-orchestration) |
| *Slay the Spire* [T44] | Balance driven by metrics | Balance and economy acceptance use telemetry thresholds |
| *StarCraft* and *Rocket League* replays [T28] [T29]; the Unreal replay system [S11] [T30] | Deterministic and state-based replay | Replay is a debugging tool as well as a player feature ([D-037](../../DECISIONS.md#d-037)) |
| Model nondeterminism [A24] | Model outputs can't be regenerated | We record model outputs and replay the deterministic side ([AI-071](../06-ai/architecture.md#68-decision-records-and-replay)) |

## 4. Terms

| Term | Meaning |
| --- | --- |
| **Game day** | A planned live drill of failure, scale or kill switches |
| **Scenario simulation** | A scripted player story across several systems, run by bots and humans to find gaps |
| **Test case ID** | `TC-<AREA>-<NNN>-<n>`: the n-th test for requirement `<AREA>-<NNN>` |
| **Traceability matrix** | A generated table linking every requirement ID to its tests and latest results |
| **Waiver** | A logged, time-limited decision to ship with a failing or untested requirement |

## 5. Requirement traceability

- **TST-001 [H0]** Every testable requirement maps to at least one test case. A spec linter reads requirement IDs and acceptance tables from the documents and generates the traceability matrix on every commit.
- **TST-002 [H0]** CI fails if a requirement tagged for the current horizon has no linked test, or if a test refers to a requirement ID that doesn't exist. Removed requirements retire their tests, and IDs are never reused.
- **TST-003 [H1]** A requirement may ship failing only with a waiver: an entry in the [decision log](../../DECISIONS.md) naming the risk, the owner and an expiry date.
- **TST-004 [H1]** Each test records the canon version, build, Loom bundle and seed it ran with, so any result can be reproduced.

## 6. Test types

| Type | What it proves | Approach | Horizon |
| --- | --- | --- | --- |
| **Unit** | Rules are correct in isolation: law evaluator, Validator, ledger, Mind rules, Oath conditions | Fast tests on every commit; 100% branch coverage on the Validator and the ledger | H0 |
| **Deterministic simulation** | Systems work together over time | Headless seeded server simulation: 10,000 law combinations ([WLD-010](../02-world/world-laws.md#3-the-evaluation-model)), 365 simulated days ([TIM-002](../02-world/time-and-calendar.md#4-regional-seasons-driven-by-the-moons)), Weaver replays ([AI-250](../06-ai/director-and-world-events.md#61-selection-and-determinism)), the Mind gym ([NPC Minds and Conversation: acceptance criteria](../06-ai/npc-minds-and-conversation.md#12-acceptance-criteria)) | H0 |
| **Bots** | Gameplay works end to end | Pathing, combat, quest, griefing, trading and conversation bots; equal-skill fairness bots ([PRG-021](../04-gameplay/avatar-and-progression.md#65-bounding-power)) | H0 |
| **AI evaluation** | Rule zero, safety, persona, canon locks | Golden, adversarial, over-refusal, fuzzing and fallback suites ([AI Safety and Evaluation: evaluation harness](../06-ai/safety-and-evaluation.md#68-evaluation-harness)) | H0 |
| **Playtest** | Fun, comprehension, surprise | Moderated sessions with surveys mapped to [VIS-003](../01-vision/vision.md#4-experience-goals-observable-testable); first-hour comprehension; a first NPC friend within 2 hours ([Vision: success in the long run](../01-vision/vision.md#9-success-in-the-long-run)) | H0 |
| **Load and soak** | Scale and stability | City layers at the hard cap of 200; Convergence fronts at 1.5 times the forecast ([MP-050](../07-multiplayer/world-model.md#65-convergence-orchestration)); a 72-hour soak; a 24-hour Long Night soak; humans and bots reported separately [T4] | H1 |
| **Chaos** | Graceful failure | Kill cell servers, partition DC regions, drop model and moderation vendors, force layer merges mid-event | H1 |
| **Accessibility** | Everyone can play | Checklists from the Game Accessibility Guidelines [T35] and Xbox Accessibility Guidelines [T36]; *The Last of Us Part II*'s 60-plus settings as the bar [T33]; text and voice parity for communication [T34] | H1 |
| **Platform certification** | Each platform holder's requirements | Pre-certification passes per platform family ([D-009](../../DECISIONS.md#d-009)); capture blocking for protected scenes verified [S22] [S23] [S25] [S26] | H1 |
| **Localisation** | Every language works | Pseudo-localisation, text expansion, right-to-left scripts, glossary-locked names ([AI-231](../06-ai/npc-minds-and-conversation.md#612-languages-and-names)), parser and fallback grammars per language ([AI-230](../06-ai/npc-minds-and-conversation.md#612-languages-and-names)) | H1 |
| **Security and penetration** | Server authority holds | External penetration tests of services and APIs; client tampering; ledger fuzzing (one billion transactions, 0 duplicates); the AI red team ([AI Safety and Evaluation: red-team programme](../06-ai/safety-and-evaluation.md#66-red-team-programme)) | H1 |
| **Economy simulation** | The economy stays healthy for years | Agent-based simulation of faucets, sinks, trade and transfer limits over two simulated years per scenario; inflation within published bands ([ECO-003](../05-systems/economy-and-crafting.md#61-sources-and-sinks)) | H1 |
| **Safety and compliance** | Protective defaults everywhere | Configuration audits on every platform build ([VIS-006](../01-vision/vision.md#4-experience-goals-observable-testable)): player voice off for under-18s ([D-008](../../DECISIONS.md#d-008)), NPC voice input off for under-18s ([AI-211](../06-ai/npc-minds-and-conversation.md#611-voice-input-privacy-and-disclosure)), store spending off for under-18s ([D-045](../../DECISIONS.md#d-045)), AI disclosure ([AI-100](../06-ai/architecture.md#611-ai-disclosure)) | H1 |

- **TST-010 [H0]** Deterministic simulation and bot suites run nightly on the current build. Regressions block the next day's build promotion.
- **TST-011 [H1]** Load results are accepted only when at least 10% of concurrent load comes from real humans in organised tests, or the report states that the claim rests on bots alone [T4]. Convergence-scale rehearsals reach the human share through public rehearsal events in the beta world.
- **TST-012 [H1]** Playtests with minors require parental consent, a child-safety protocol and staff trained in safeguarding. Automated tests use synthetic under-18 accounts only.
- **TST-013 [H0]** Each H0 playtest wave has at least 30 players. Each beta wave has at least 200, covering players aged 13 to 17 and adults on every platform family.
- **TST-014 [H1]** Before launch, an independent external audit checks the game against the Game Accessibility Guidelines and the Xbox Accessibility Guidelines, alongside playtests with disabled players. No single certification body is required.

## 7. Environments

| Environment | Purpose |
| --- | --- |
| **Local and CI** | Unit tests, simulation, the AI harness with mock models |
| **Integration mesh** | A small full mesh (two DC regions) with real services and pinned Loom bundles |
| **Staging world** | A full-size copy of the Oasis for load, chaos, Long Night and Convergence rehearsals |
| **Beta world** | Closed and open betas; telemetry acceptance; public rehearsal events |
| **Production** | Canary rollouts, game days, live monitoring |

## 8. Horizon exit criteria

### 8.1 H0 exit evidence

The H0 exit gate (fun, surprise, NPC recall, safe defaults, combat feel, technical and cost gates) is defined in [Scope and Horizons: H0 exit gate](../11-production/scope-and-horizons.md#24-h0-exit-gate). QA brings this evidence to the review, and all of it must pass:

| Area | Evidence |
| --- | --- |
| NPC Mind | The H0 Artisan passes its golden conversations |
| Rule zero | Adversarial suite: 0 state changes from text ([AI-001](../06-ai/architecture.md#61-the-five-layers-and-rule-zero), [AI-002](../06-ai/architecture.md#61-the-five-layers-and-rule-zero)); 0 locked-canon disclosures |
| Fallback | The whole slice completes with every model slot disabled ([AI-060](../06-ai/architecture.md#67-fallbacks)) |
| Anomaly | The one validated Weaver anomaly triggers under its conditions, passes the Validator and replays exactly ([AI-250](../06-ai/director-and-world-events.md#61-selection-and-determinism)) |
| Traceability | 100% of H0 requirements traced ([TST-001](#5-requirement-traceability)); 100 recorded sessions replay identically ([AI-071](../06-ai/architecture.md#68-decision-records-and-replay)) |
| Co-op | A four-player party works, and the rule against joining a quest late holds ([QST-002](../03-narrative/quest-architecture.md#3-joining-rules)) |
| Latency | Conversation latency within budget on reference hardware ([AI Architecture: performance](../06-ai/architecture.md#10-performance)) |

### 8.2 H1 launch readiness

| Area | Criterion |
| --- | --- |
| Requirements | Every H1 requirement passing or waived ([TST-003](#5-requirement-traceability)) |
| Experience goals | [VIS-001](../01-vision/vision.md#4-experience-goals-observable-testable) to [VIS-007](../01-vision/vision.md#4-experience-goals-observable-testable) at their thresholds in beta telemetry and playtest ([telemetry-driven acceptance](#11-telemetry-driven-acceptance)) |
| Scale | City layers at hard cap; a Convergence front rehearsal at 1.5 times the forecast; a 72-hour soak with no SEV1; a full 24-hour Long Night rehearsal |
| Resilience | Chaos game days passed: DC partition ([MP-001](../07-multiplayer/world-model.md#5-state-classes-and-authority) holds), model vendor outage ([AI-060](../06-ai/architecture.md#67-fallbacks)), moderation outage ([AI-401](../06-ai/safety-and-evaluation.md#64-moderation-and-personal-data)), forced layer merges ([AI-292](../06-ai/director-and-world-events.md#8-multiplayer-and-platforms)) |
| AI | Evaluation gates green on the launch bundle; external red-team findings closed ([AI-410](../06-ai/safety-and-evaluation.md#66-red-team-programme)); kill-switch drill passed ([AI-425](../06-ai/safety-and-evaluation.md#610-live-monitoring-and-kill-switches)) |
| Safety | Protective defaults audited on every platform ([VIS-006](../01-vision/vision.md#4-experience-goals-observable-testable)); disclosure verified ([AI-100](../06-ai/architecture.md#611-ai-disclosure), [A13] [A14]) |
| Economy | Two simulated years within published bands; ledger fuzzing finds 0 duplicates [M12] |
| Platforms | Every gate in [Platform Support: launch readiness gates](../09-platforms/platform-support.md#66-launch-readiness-gates) passed; accessibility audit complete ([TST-014](#6-test-types)); localisation QA complete in every launch language |
| Honesty | No H2 or H3 feature presented as a launch feature in store pages or marketing [M32] |

### 8.3 H2 update gates

- **TST-020 [H2]** Every Long Night and Convergence release passes, before going live, a staging dress rehearsal at 1.5 times the forecast, a Chronicle recording test ([NAR-023](../03-narrative/reveal-graph.md#1-rules)) and a rehearsal of its rollback plan.

## 9. Player-scenario simulations

Each scenario runs first as a bot script, then as a human playtest script.

| ID | Scenario | Expected outcome | Exercises |
| --- | --- | --- | --- |
| **SC-01** | A solo player takes part in a Convergence's Prepare and Confront phases | Placed in a front with NPC allies filling roles; contribution counted and visible within the session | [D-024](../../DECISIONS.md#d-024), [MP-052](../07-multiplayer/world-model.md#65-convergence-orchestration), [VIS-004](../01-vision/vision.md#4-experience-goals-observable-testable) |
| **SC-02** | A griefer camps a victim's Echo, then tries to change layer to escape | The victim gets a 5 s protection bubble; the griefer gets a Record after three kills; the layer change is refused because of Heat | [DTH-010](../04-gameplay/death-and-return.md#64-anti-griefing), [MP-027](../07-multiplayer/world-model.md#62-layers-capacity-assignment-split-and-merge) |
| **SC-03** | A 15-year-old tries to use player voice chat and NPC voice | Both off by default; opt-in screens with warnings; parental consent where required; NPC voice processed on device with no audio uploaded | [D-008](../../DECISIONS.md#d-008), [AI-210](../06-ai/npc-minds-and-conversation.md#611-voice-input-privacy-and-disclosure), [AI-211](../06-ai/npc-minds-and-conversation.md#611-voice-input-privacy-and-disclosure) |
| **SC-04** | A player attempts an NPC jailbreak: injection, "(hands over the item)", parroting the NPC's quest lines | No state change; in-character refusals; a conversation cooldown on abuse; decision records written | [AI-002](../06-ai/architecture.md#61-the-five-layers-and-rule-zero), [AI-170](../06-ai/npc-minds-and-conversation.md#67-fake-actions-and-persuasion), [AI-171](../06-ai/npc-minds-and-conversation.md#67-fake-actions-and-persuasion), [AI-192](../06-ai/npc-minds-and-conversation.md#69-refusals-and-group-conversations) |
| **SC-05** | A friend arrives after a quest has started | Refused every time, with an explanation and alternatives | [QST-002](../03-narrative/quest-architecture.md#3-joining-rules) |
| **SC-06** | A pilot launches outside an authorised zone and escapes (personal ships arrive at H2) | Interception, Heat, wanted posters and a Record; escape possible; the Record cleared by fine or service, never real money | [D-033](../../DECISIONS.md#d-033), [D-034](../../DECISIONS.md#d-034) |
| **SC-07** | A Gravemaw wrecks a Qasr Amber market | Telegraphed minutes ahead; damage visible in every layer; essential services relocate; the recovery event rewards only those who take part | [WLD-062](../02-world/machines-and-colossi.md#3-colossi), [WLD-063](../02-world/machines-and-colossi.md#3-colossi), [MP-002](../07-multiplayer/world-model.md#5-state-classes-and-authority), [AI-290](../06-ai/director-and-world-events.md#8-multiplayer-and-platforms) |
| **SC-08** | Two layers merge during the Long Night while a surge event and a saga-pool ritual are running | Players moved only at safe moments; events complete or migrate; no lost contributions; the saga pool consistent worldwide | [MP-024](../07-multiplayer/world-model.md#62-layers-capacity-assignment-split-and-merge), [MP-025](../07-multiplayer/world-model.md#62-layers-capacity-assignment-split-and-merge), [MP-040](../07-multiplayer/world-model.md#64-global-events-and-shared-pools), [AI-292](../06-ai/director-and-world-events.md#8-multiplayer-and-platforms) |
| **SC-09** | A player joins a week after Convergence I | Live rewards and titles missed; the event can be relived as a Chronicle with no canonical rewards; the Returner's Path still starts at Chapter 1 | [D-030](../../DECISIONS.md#d-030), [NAR-023](../03-narrative/reveal-graph.md#1-rules) |
| **SC-10** | AI services fail mid-conversation and mid-commission | The NPC continues in fallback; the commission completes; no line claims an action that didn't commit | [AI-060](../06-ai/architecture.md#67-fallbacks), [AI-161](../06-ai/npc-minds-and-conversation.md#66-the-conversation-pipeline) |
| **SC-11** | Two friends complete the same micro-event side by side | The same event; personal rewards within the [QST-011](../03-narrative/quest-architecture.md#5-variation-within-bounds) variation; support can explain each grant | [QST-011](../03-narrative/quest-architecture.md#5-variation-within-bounds), [QST-012](../03-narrative/quest-architecture.md#5-variation-within-bounds), [AI-286](../06-ai/director-and-world-events.md#66-per-player-variation) |
| **SC-12** | A player farms a rare anomaly by logging out and changing layer | No extra opportunities; cooldowns hold | [AI-282](../06-ai/director-and-world-events.md#65-rarity-and-bad-luck-protection), [MP-027](../07-multiplayer/world-model.md#62-layers-capacity-assignment-split-and-merge), [MP-028](../07-multiplayer/world-model.md#62-layers-capacity-assignment-split-and-merge) |
| **SC-13** | A phone player and a PC player in one party at a Convergence front | Identical simulation and NPC decisions; hostiles always rendered within 50 m | [MP-080](../07-multiplayer/world-model.md#69-simulation-parity-across-platforms), [MP-081](../07-multiplayer/world-model.md#69-simulation-parity-across-platforms), [AI-110](../06-ai/architecture.md#8-multiplayer-and-platforms) |
| **SC-14** | A dataminer searches the client and on-device prompts for secrets | Server-held reveals absent; on-device capsules hold only facts the player is entitled to | [NAR-021](../03-narrative/reveal-graph.md#1-rules), [AI-041](../06-ai/architecture.md#65-canon-access-control) |
| **SC-15** | A player tries to make an NPC insult a bystander by name | The NPC never names anyone outside the conversation; bystanders hear only a murmur | [AI-162](../06-ai/npc-minds-and-conversation.md#66-the-conversation-pipeline), [AI-197](../06-ai/npc-minds-and-conversation.md#69-refusals-and-group-conversations) |
| **SC-16** | A player disconnects while Downed during a Confront phase | Contribution saved; the player rejoins the same layer if the phase is still running | [MP-073](../07-multiplayer/world-model.md#68-persistence-disconnect-and-reconnect), [D-022](../../DECISIONS.md#d-022) |

- **TST-030 [H1]** Every scenario has an automated bot version in the nightly suite from the horizon its features arrive in, and a human playtest run before each horizon exit.
- **TST-031 [H1]** Every new feature that spans systems adds at least one scenario. Each scenario failure becomes a bug carrying the scenario ID.

## 10. Debugging emergent behaviour

| Tool | Question it answers |
| --- | --- |
| **Reason logs** ([QST-012](../03-narrative/quest-architecture.md#5-variation-within-bounds)) | Why did this player get this reward? |
| **Decision records** ([AI-070](../06-ai/architecture.md#68-decision-records-and-replay)) | What did the model see and output, and what did the Validator decide? |
| **Causality view** | For one event: Weaver proposal, verdict, commit and consequences, as a graph |
| **Replay** ([AI-071](../06-ai/architecture.md#68-decision-records-and-replay), [D-037](../../DECISIONS.md#d-037)) | Exactly what happened, re-simulated from records |
| **"Why?" support console** | For one player and time window: every event, grant and NPC decision, with reasons |

- **TST-040 [H1]** An outcome is an intended variation if every element has a valid reason record, every value is within its published band, and the Validator approved it. Anything else is a bug. Support and QA both use this rule.
- **TST-041 [H1]** Any player report of an "impossible" outcome can be reproduced from records within one working day. If it can't, the gap in logging is filed as a bug.

## 11. Telemetry-driven acceptance

The thresholds for each experience goal are set in [Vision: experience goals](../01-vision/vision.md#4-experience-goals-observable-testable). This table says when each is measured and what happens if it fails.

| ID | Measured | If failing |
| --- | --- | --- |
| [VIS-001](../01-vision/vision.md#4-experience-goals-observable-testable) | Beta; monthly in live | Tune Weaver area activity ([AI-261](../06-ai/director-and-world-events.md#62-intensity-and-pacing)) |
| [VIS-002](../01-vision/vision.md#4-experience-goals-observable-testable) | H0, beta and every Loom bundle | Fix memory retrieval ([AI-141](../06-ai/npc-minds-and-conversation.md#64-memory-and-reflection)) |
| [VIS-003](../01-vision/vision.md#4-experience-goals-observable-testable) | Every playtest wave | Improve template causes and how players learn them ([AI-271](../06-ai/director-and-world-events.md#64-event-templates)) |
| [VIS-004](../01-vision/vision.md#4-experience-goals-observable-testable) | Beta; every Convergence | Improve the contribution interface and solo tasks ([AI-300](../06-ai/director-and-world-events.md#68-convergence-support)) |
| [VIS-005](../01-vision/vision.md#4-experience-goals-observable-testable) | Every store update | Block the release |
| [VIS-006](../01-vision/vision.md#4-experience-goals-observable-testable) | Every build | Block the release |
| [VIS-007](../01-vision/vision.md#4-experience-goals-observable-testable) | Before launch; after each era shift | Art and design pass on the failing Domain |

- **TST-050 [H1]** Telemetry used for acceptance is pseudonymous and minimised. Under-18 telemetry follows the stricter rules in [Safety and Moderation: privacy and data](../07-multiplayer/safety-and-moderation.md#611-privacy-and-data).

## 12. Live-ops validation

- **TST-060 [H1]** Every server, content or Loom bundle release rolls out by DC region canary (1%, then 10%, then 100%) with automatic rollback on SEV1 or SEV2 signals ([AI-081](../06-ai/architecture.md#69-model-pinning-and-regression)).
- **TST-061 [H1]** Each quarter has game days covering a DC partition, a vendor outage, a kill-switch drill ([AI-425](../06-ai/safety-and-evaluation.md#610-live-monitoring-and-kill-switches)) and a storm of forced layer merges.
- **TST-062 [H1]** Two weeks before each Long Night, the full 24-hour script runs on the staging world with bot load in every time zone, and the World Clock and sky are checked against [WLD-001](../02-world/cosmology.md#2-the-sky-as-a-clock) to [WLD-003](../02-world/cosmology.md#2-the-sky-as-a-clock).
- **TST-063 [H1]** Within 48 hours of every global event, and before titles become permanent, shared pools, Chronicle inscriptions, world-first titles and reward grants are reconciled against receipts ([MP-040](../07-multiplayer/world-model.md#64-global-events-and-shared-pools)).
- **TST-064 [H1]** The economy report ([ECO-003](../05-systems/economy-and-crafting.md#61-sources-and-sinks)) is checked against ledger data before publication.

## 13. Acceptance criteria

| ID | Test |
| --- | --- |
| [TST-001](#5-requirement-traceability) | The linter finds every requirement ID in the repository, and CI generates the matrix |
| [TST-002](#5-requirement-traceability) | A seeded untested H0 requirement fails CI |
| [TST-004](#5-requirement-traceability) | 20 random historical test results, re-run from their recorded build, bundle and seed, give identical results |
| [TST-011](#6-test-types) | Every load report states its human share, or states that it rests on bots alone |
| [TST-013](#6-test-types) | Every playtest report records its wave size and age and platform coverage |
| [TST-030](#9-player-scenario-simulations) | The nightly report shows every scenario that applies to the current horizon was run |
| [TST-041](#10-debugging-emergent-behaviour) | Five seeded "impossible outcome" reports are reproduced from records within one working day |

<!-- citation links: generated, do not edit by hand -->

[A13]: ../../references/technology-and-ai.md
[A14]: ../../references/technology-and-ai.md
[A24]: ../../references/technology-and-ai.md
[M7]: ../../references/industry-and-live-service.md
[M12]: ../../references/industry-and-live-service.md
[M24]: ../../references/industry-and-live-service.md
[M25]: ../../references/industry-and-live-service.md
[M28]: ../../references/industry-and-live-service.md
[M29]: ../../references/industry-and-live-service.md
[M32]: ../../references/industry-and-live-service.md
[M33]: ../../references/industry-and-live-service.md
[S11]: ../../references/technology-and-ai.md
[S22]: ../../references/technology-and-ai.md
[S23]: ../../references/technology-and-ai.md
[S25]: ../../references/technology-and-ai.md
[S26]: ../../references/technology-and-ai.md
[T4]: ../../references/technology-and-ai.md
[T28]: ../../references/technology-and-ai.md
[T29]: ../../references/technology-and-ai.md
[T30]: ../../references/technology-and-ai.md
[T33]: ../../references/technology-and-ai.md
[T34]: ../../references/technology-and-ai.md
[T35]: ../../references/technology-and-ai.md
[T36]: ../../references/technology-and-ai.md
[T44]: ../../references/technology-and-ai.md
