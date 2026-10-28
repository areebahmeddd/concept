# Tech Watch

A living tracker of the fast-moving technologies our specs depend on, so a mid-2030s launch is planned against verified, dated facts.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Technical Director (each row has its own owner)
>
> **Horizons:** H0 to H3 (each row names what it affects)
>
> **Related:** [D-002](../../DECISIONS.md#d-002) · [D-003](../../DECISIONS.md#d-003) · [D-009](../../DECISIONS.md#d-009) · [Engine and Stack](engine-and-stack.md) · [Server and Backend](server-and-backend.md) · [Platform Support](../09-platforms/platform-support.md) · [Regulatory Watch](../12-legal/regulatory-watch.md)

## 1. How the tracker works

1. **Scheduled checks.** Monthly rows are checked in the first week of every month. Quarterly rows are checked in the first week of January, April, July and October. Twice-yearly rows are checked in the first week of January and July. Each check updates the row's status and next-check date, and adds any new source to the [reference library](../../references/technology-and-ai.md).
2. **Primary sources decide.** A status changes on a primary source (grade P). A change reported only by the press is recorded with its grade, and does not fire a trigger on its own ([Reference Library](../../references/README.md)).
3. **Triggers.** When a row meets its trigger, the action in [Triggers](#3-triggers) runs and the owners of the affected specs are told. If the row owner and a spec owner disagree, the Technical Director decides, and the decision goes in the [decision log](../../DECISIONS.md).
4. **Stable IDs.** New facts get new reference IDs; existing IDs are never changed or reused ([Conventions: Sources and citations](../00-meta/conventions.md#5-sources-and-citations)).
5. **No promises.** Nothing on this page is a public commitment, a lesson No Man's Sky taught the industry [M32] [M33].
6. **Scope.** AI model deprecation is tracked under TW-05 and TW-06, with model pinning in [AI Architecture](../06-ai/architecture.md). Cloud and inference cost is tracked in [Server and Backend: Cost](server-and-backend.md#11-cost).

## 2. Tracker

All statuses were verified on 10-10-2026.

| ID | Area | Status | Affects | Next check | Owner |
| --- | --- | --- | --- | --- | --- |
| TW-01 | UE6 timeline | UE 5.8 was released on 17-06-2026 as the last planned UE5 major release [S2]. UE6 has no confirmed release date. | [Engine and Stack: UE6 migration](engine-and-stack.md#5-ue6-migration) | 02-11-2026 | Technical Director |
| TW-02 | Iris maturity | The UE 5.8 release notes call Iris "production-ready for licensees" [S1]. The Iris documentation is still marked Experimental [S7]. | [TEC-003](engine-and-stack.md#2-ue-58-baseline) | 04-01-2027 | Network lead |
| TW-03 | Unreal multi-server replication | The plugin is experimental (2025) [T6]. | [MP-012](../07-multiplayer/world-model.md#61-topology-world-regions-cells-and-the-mesh), [TEC-030](server-and-backend.md#2-meshing) | 04-01-2027 | Server lead |
| TW-04 | Industry server meshing | Star Citizen runs quasi-dynamic meshing in instances, with persistent territories still static (2026) [T1]. Morpheus demonstrated about 4,500 players against claims of 10,000 or more [T3]. EVE: Aether Wars had 10,412 combatants, of whom 3,852 were human [T4]. | [MP-012](../07-multiplayer/world-model.md#61-topology-world-regions-cells-and-the-mesh), [MP-013](../07-multiplayer/world-model.md#61-topology-world-regions-cells-and-the-mesh) | 04-01-2027 | Server lead |
| TW-05 | On-device small language models | NVIDIA ACE Minitron models of 2 to 8B parameters run through the In-Game Inferencing SDK [T22] [T23]. Apple Foundation Models run at about 3B parameters on the device [T24]. | On-device Loom tier | 04-01-2027 | AI lead |
| TW-06 | Structured model output | Schema-constrained output [T13], strict tool use with constrained decoding [T14] and GBNF grammars on the device [T15] are available. | Typed speech acts ([AI Architecture](../06-ai/architecture.md)) | 04-01-2027 | AI lead |
| TW-07 | Prompt-injection research | Defences include the dual-LLM pattern [T16], spotlighting (attack success fell from over 50% to under 2%) [T17] and CaMeL [T18]. OWASP states there is no fool-proof prevention [A25]. | AI red-team suite ([AI Safety and Evaluation](../06-ai/safety-and-evaluation.md)) | 02-11-2026 | AI safety lead |
| TW-08 | Speech technology | Whisper has open weights [T8]. Apple SpeechAnalyzer recognises speech on the device [T9]. | [SOC-070](../07-multiplayer/social-voice-and-clans.md#68-accessibility-parity), NPC voice input | 04-01-2027 | Audio tech lead |
| TW-09 | Text-to-speech vendor risk | A consent-based licensed voice marketplace exists [T10]. Replica Studios signed a SAG-AFTRA deal in 2024 and shut down on 30-06-2025 [T11] [T12]. Union terms require consent, disclosure and pay [A9] [A10]. | [TEC-020](engine-and-stack.md#7-middleware-and-services), [D-043](../../DECISIONS.md#d-043) | 04-01-2027 | Audio Director and Legal |
| TW-10 | VR hardware | Quest's UE5 support launched without Nanite or Lumen [S5]. Quest 3 (2023) uses the XR2 Gen 2 chip [S28]. Meta publishes comfort guidance [S27]. | Tier X, VR plan | 04-01-2027 | Platform lead |
| TW-11 | Platform generations | Switch 2 specifications are published [S21]. PS5 and Xbox Series are the current generations. No next PlayStation or Xbox generation has been announced. | [PLT-001](../09-platforms/platform-support.md#61-support-policy), [PLT-003](../09-platforms/platform-support.md#61-support-policy) | 04-01-2027 | Platform lead |
| TW-12 | Mobile GPU capability | Lumen on mobile covers Android Vulkan only and is experimental on high-end Android [S4]. A UE5 open world has shipped on iOS and Android [S16]. | Tier C lighting | 04-01-2027 | Rendering lead |
| TW-13 | Content streaming at launch | The MSFS 2024 launch overwhelmed its streaming cache [S29]. MSFS 2020 streams terrain from the cloud [S30]. | [PLT-030](../09-platforms/platform-support.md#65-mobile-thermals-storage-and-streaming-install) to [PLT-032](../09-platforms/platform-support.md#65-mobile-thermals-storage-and-streaming-install) | 04-01-2027 | Infrastructure lead |
| TW-14 | Anti-cheat and the Windows kernel | Microsoft's Windows Resiliency Initiative (2024) is moving security vendors out of the kernel [T46]. Vanguard [T25] and EAC through EOS [T26] are kernel-level today. | [SAF-083](../07-multiplayer/safety-and-moderation.md#69-anti-cheat-and-anti-bot) | 04-01-2027 | Security lead |
| TW-15 | Capture and recording APIs | PS5 blocks capture in some scenes [S22]. Xbox offers `XAppCaptureDisableRecord` [S23]. Steam has a timeline API [S24]. iOS ReplayKit needs system consent [S25]. Quest capture can be disabled [S26]. | [Recording and Replays](../05-systems/recording-and-replays.md) | 04-01-2027 | Platform lead |
| TW-16 | Engine licensing | Epic's "Launch Everywhere" programme cites a 3.5% royalty from 2025 (secondary source) [S12]. A 2025 court ruling may allow link-out payments on Apple's store [L29]. | [Engine and Stack: Licensing](engine-and-stack.md#8-licensing) | 04-01-2027 | Business and Legal |

## 3. Triggers

| Row | Trigger | Action |
| --- | --- | --- |
| TW-01 | The first public UE6 preview ships | Run the H0 slice on it (UE6 migration step 2) |
| TW-02 | The Iris documentation drops its Experimental label | Record the change against [TEC-003](engine-and-stack.md#2-ue-58-baseline) before its H0 gate |
| TW-03 | The plugin reaches production status with dynamic authority support | Test it against our handoff protocol for H2 dynamic cells |
| TW-04 | An audited result shows 1,000 or more humans together in action combat | Re-test the H2 and H3 population targets |
| TW-05 | A model fits the tier C memory budget at our quality bar | Move NPC expression on-device for tier C |
| TW-06 | Schema adherence regresses in a pinned model or runtime | Keep the previous pin and extend the Validator tests |
| TW-07 | A new attack bypasses our red-team suite | Patch it and add the attack to the suite |
| TW-08 | On-device speech recognition arrives on a platform family | Move transcripts and NPC voice input on-device for that family |
| TW-09 | A voice vendor shows financial distress | Run the exit plan ([TEC-020](engine-and-stack.md#7-middleware-and-services)) |
| TW-10 | Standalone VR gains Lumen-class lighting | Re-test tier X rendering |
| TW-11 | A new generation is announced, or support ends for a current one | Add it to the tier matrix, or apply the retirement rule ([PLT-003](../09-platforms/platform-support.md#61-support-policy)) |
| TW-12 | Lumen reaches production status on a mobile family | Test Lumen on the top band of tier C |
| TW-13 | A comparable launch fails on streaming | Re-run the CDN and install-streaming load tests |
| TW-14 | Windows restricts kernel access | Move PC ranked anti-cheat to user mode plus server detection ([SAF-083](../07-multiplayer/safety-and-moderation.md#69-anti-cheat-and-anti-bot)) |
| TW-15 | A platform changes its capture policy | Update the platform rules in Recording and Replays |
| TW-16 | Royalty or store-fee terms change | Update the business-plan royalty assumption |

## 4. Review log

| Date | Rows reviewed | Changes | Reviewer |
| --- | --- | --- | --- |
| 10-10-2026 | All | First baseline from the reference library | Technical Director |

## 5. Acceptance criteria

| ID | Test |
| --- | --- |
| TEC-100 [H0] | Automated doc lint: every row has an owner and a next-check date no more than 2 weeks overdue |
| TEC-101 [H0] | Every status cites at least one existing reference ID |
| TEC-102 [H1] | Every scheduled check adds a review-log entry, even when nothing changed |

<!-- citation links: generated, do not edit by hand -->

[A9]: ../../references/technology-and-ai.md
[A10]: ../../references/technology-and-ai.md
[A25]: ../../references/technology-and-ai.md
[L29]: ../../references/legal-and-policy.md
[M32]: ../../references/industry-and-live-service.md
[M33]: ../../references/industry-and-live-service.md
[S1]: ../../references/technology-and-ai.md
[S2]: ../../references/technology-and-ai.md
[S4]: ../../references/technology-and-ai.md
[S5]: ../../references/technology-and-ai.md
[S7]: ../../references/technology-and-ai.md
[S12]: ../../references/technology-and-ai.md
[S16]: ../../references/technology-and-ai.md
[S21]: ../../references/technology-and-ai.md
[S22]: ../../references/technology-and-ai.md
[S23]: ../../references/technology-and-ai.md
[S24]: ../../references/technology-and-ai.md
[S25]: ../../references/technology-and-ai.md
[S26]: ../../references/technology-and-ai.md
[S27]: ../../references/technology-and-ai.md
[S28]: ../../references/technology-and-ai.md
[S29]: ../../references/technology-and-ai.md
[S30]: ../../references/technology-and-ai.md
[T1]: ../../references/technology-and-ai.md
[T3]: ../../references/technology-and-ai.md
[T4]: ../../references/technology-and-ai.md
[T6]: ../../references/technology-and-ai.md
[T8]: ../../references/technology-and-ai.md
[T9]: ../../references/technology-and-ai.md
[T10]: ../../references/technology-and-ai.md
[T11]: ../../references/technology-and-ai.md
[T12]: ../../references/technology-and-ai.md
[T13]: ../../references/technology-and-ai.md
[T14]: ../../references/technology-and-ai.md
[T15]: ../../references/technology-and-ai.md
[T16]: ../../references/technology-and-ai.md
[T17]: ../../references/technology-and-ai.md
[T18]: ../../references/technology-and-ai.md
[T22]: ../../references/technology-and-ai.md
[T23]: ../../references/technology-and-ai.md
[T24]: ../../references/technology-and-ai.md
[T25]: ../../references/technology-and-ai.md
[T26]: ../../references/technology-and-ai.md
[T46]: ../../references/technology-and-ai.md
