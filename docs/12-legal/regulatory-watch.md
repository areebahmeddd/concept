# Regulatory Watch

A dated tracker of the laws, policies and rulings that affect *Ready Player Zero*, what each one means for the design, and when it is next checked.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Legal lead
>
> **Horizons:** H0 to H2 (continuous)
>
> **Related:** [Legal and Compliance](compliance.md) · [Risk Register](../11-production/risk-register.md) · [Tech Watch](../08-technology/tech-watch.md) · [References: Legal and Policy](../../references/legal-and-policy.md)

Launch is in the mid-2030s ([D-002](../../DECISIONS.md#d-002)), so almost everything here will change before then. The legal analysis behind each row is in [Legal and Compliance](compliance.md); this page only tracks status and dates.

## 1. How the watch works

- **LGL-080 [H0]** The tracker is re-verified every quarter (next full pass: 18-01-2027), and straight away when a tracked item reaches a known milestone. Each pass updates the *Verified* date, adds new sources to the [reference library](../../references/README.md) under new IDs, and records changes in the [Changelog](../../CHANGELOG.md). *Acceptance:* no row has a *Verified* date more than 100 days old.
- **LGL-081 [H0]** Any change rated High opens or updates a risk in the [Risk Register](../11-production/risk-register.md) within 7 days and, if it changes a decision, a [Decision Log](../../DECISIONS.md) entry. *Acceptance:* every High change links its risk ID.

**Impact levels:** **High** may change a decision or a system. **Med** changes UX, copy or process. **Low** is monitored only.

## 2. Tracker

Rows marked "not yet sourced" have no source in the library yet. No decision relies on them until the next pass adds one.

| # | Law or policy | Jurisdiction | Status on the verified date | Verified | Impact | Next check | Source |
| --- | --- | --- | --- | --- | --- | --- | --- |
| W-01 | EU AI Act, Article 50 (tell people they are interacting with AI) | EU | Applies from 2 August 2026 | 10-10-2026 | **High.** AI disclosure UX for NPC Minds ([AI law and disclosure](compliance.md#4-ai-law-and-disclosure)) | 18-01-2027 | [A14] [A15] |
| W-02 | EU AI Act: other provisions and the "omnibus" simplification changes | EU | Press reports say some provisions did not take effect in August 2026; the omnibus amendments are not yet sourced | 10-10-2026 | Med. May move the timing of other duties | 18-01-2027 | [A15] (partial) |
| W-03 | EU Digital Services Act, Article 28, and the 2025 guidelines on minors | EU | In force; guidelines published in 2025 | 10-10-2026 | **High.** Protection of minors by design | 18-01-2027 | [L10] [L11] |
| W-04 | EU Digital Fairness Act | EU | Pending; the "Stop Destroying Videogames" campaign is targeting it | 10-10-2026 | **High.** Could add end-of-life or digital-goods duties that touch the ten-year end | 18-01-2027 | [R12] |
| W-05 | EU end-of-life code of conduct for games (voluntary) | EU | The Commission will convene it by the end of 2026 (reply of 16 June 2026) | 10-10-2026 | **High.** Check Archive Mode ([D-047](../../DECISIONS.md#d-047)) against the code | 05-01-2027 | [R12] |
| W-06 | GDPR Article 8 (digital age of consent 13 to 16, by member state) | EU | In force | 10-10-2026 | Med. Parental consent for voice and data in some states | 18-04-2027 | [L26] |
| W-07 | COPPA amended Rule | US | Full compliance from 22 April 2026 | 10-10-2026 | **High.** Age screening and under-13 handling | 18-01-2027 | [L7] |
| W-08 | FTC v. Epic consent order (chat off by default for minors) | US | In effect since 2022 | 10-10-2026 | **High.** The basis of [D-008](../../DECISIONS.md#d-008) | 18-04-2027 | [L6] |
| W-09 | UK Online Safety Act: codes and age assurance | UK | Games with chat are in scope; Ofcom's January 2025 guidance says self-declaration doesn't count as age assurance | 10-10-2026 | **High.** Risk assessments; highly effective age assurance for voice | 18-01-2027 | [L8] [T42] [T43] |
| W-10 | UK Children's Code | UK | In force; high privacy by default | 10-10-2026 | Med. Defaults for minors | 18-04-2027 | [L9] |
| W-11 | PEGI 2026 criteria (communication, spending, loot boxes) | Europe | Launched, according to a law-firm summary; PEGI's own text is not yet sourced | 10-10-2026 | Med. The rating depends on block and report tools and spending defaults | 18-01-2027 | [L20] |
| W-12 | ESRB interactive elements | US and Canada | Current labels | 10-10-2026 | Low. The labels apply | 18-04-2027 | [L19] |
| W-13 | Brazil's Digital ECA | Brazil | In force from 17 March 2026; loot boxes banned in games minors can access | 10-10-2026 | Med. We already have no loot boxes; check its other child-safety duties | 18-01-2027 | [L18] |
| W-14 | California AB 2426 (digital goods licence disclosure) | US (California) | In force from 1 January 2025 | 10-10-2026 | Med. Checkout copy; Archive Mode terms | 18-04-2027 | [R14] |
| W-15 | Epic v. Apple (anti-steering; commission rate sent back for decision) | US | Contempt finding upheld in 2025 | 10-10-2026 | Med. Link-out payments may become possible on iOS | 18-01-2027 | [L29] |
| W-16 | Apple guideline 3.1.1 and Google Play rules on randomised items and in-app purchase | Global | Current | 10-10-2026 | Low. We sell no randomised items | 18-04-2027 | [L27] [L28] |
| W-17 | Loot-box law (Belgium, the Netherlands, others) | Several | Belgium: illegal gambling (2018); Netherlands: penalty overturned (2022) | 10-10-2026 | Low. No random paid items ([D-045](../../DECISIONS.md#d-045)) | 18-04-2027 | [L16] [L17] |
| W-18 | SAG-AFTRA Interactive Media Agreement (2025) | US | Ratified in 2025 with AI replica terms; its term and expiry date are not yet sourced | 10-10-2026 | **High.** Voice policy ([D-043](../../DECISIONS.md#d-043)); the agreement will probably be renegotiated before launch | 18-01-2027 | [A9] [A10] |
| W-19 | Steam AI content disclosure | Global (Steam) | Current: pre-generated and live-generated content disclosed, guardrails described | 10-10-2026 | Med. Store disclosure | 18-01-2027 | [A13] |
| W-20 | US CVAA (accessible communication) | US | Applies to in-game communication since 2019 | 10-10-2026 | Med. Parity between text and voice | 18-04-2027 | [T34] |
| W-21 | US state action on child safety in games | US (states) | Attorney-general lawsuits against Roblox (2025) | 10-10-2026 | Med. Shows where the industry is heading | 18-01-2027 | [L13] |
| W-22 | Platform age checks for chat (industry practice) | Global | Roblox age checks for chat, worldwide from 7 January 2026 | 10-10-2026 | Med. The expected norm for voice | 18-01-2027 | [L12] |

## 3. Upcoming milestones

| Date | Milestone | Rows |
| --- | --- | --- |
| By the end of 2026 | EU end-of-life code of conduct convened | W-05 |
| 18-01-2027 | First quarterly re-verification pass | All |
| Pending | EU Digital Fairness Act proposal | W-04 |
| Not yet sourced | SAG-AFTRA agreement expiry | W-18 |

## 4. Gaps in our library

The next pass (18-01-2027) adds sources for each of these, and no decision relies on them until then:

- the EU AI Act omnibus changes (W-02);
- the term of the SAG-AFTRA agreement (W-18);
- subscription and auto-renewal law in each launch market ([Monetization](compliance.md#7-monetization), LGL-C10);
- accessibility law outside the US;
- licensing and content rules in markets that need a separate game licence. Mainland China is not a launch region ([LGL-090](compliance.md#11-markets-with-separate-game-licensing)), so this gap only matters before a later market entry (LGL-C13).

<!-- citation links: generated, do not edit by hand -->

[A9]: ../../references/technology-and-ai.md
[A10]: ../../references/technology-and-ai.md
[A13]: ../../references/technology-and-ai.md
[A14]: ../../references/technology-and-ai.md
[A15]: ../../references/technology-and-ai.md
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
[L26]: ../../references/legal-and-policy.md
[L27]: ../../references/legal-and-policy.md
[L28]: ../../references/legal-and-policy.md
[L29]: ../../references/legal-and-policy.md
[R12]: ../../references/ready-player-and-lifecycle.md
[R14]: ../../references/ready-player-and-lifecycle.md
[T34]: ../../references/technology-and-ai.md
[T42]: ../../references/technology-and-ai.md
[T43]: ../../references/technology-and-ai.md
