# Budget

What the game costs to build and run, in US dollars, from a first prototype to the end of the decade. It plans for a small, remote-first studio that grows only when the game proves itself. Every figure is an estimate with a low and a high case, worked out from the [Team](team.md) plan and the assumptions below.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Executive producer
>
> **Related:** [Team](team.md) · [Scope and Horizons](scope-and-horizons.md) · [Ten-Year Live Plan](ten-year-live-plan.md) · [Risk Register](risk-register.md) · [D-045](../../DECISIONS.md#d-045)

## 1. Summary

| Stage | Team | Length | Low | High |
| --- | --- | --- | --- | --- |
| Concept prototype | 6 | 9 months | $0.4M | $0.8M |
| First Playable (H0) | Up to 25 | 2 years | $3.7M | $6.9M |
| Production to launch (H1) | Up to 180 | 5 years | $70M | $158M |
| Launch marketing | Partners | Final 12 months | $15M | $50M |
| **Total to launch** | | About 8 years | **$89M** | **$216M** |
| Live decade (H2), per year | About 140 | Each year | $28M | $82M |
| **Lifetime** | | About 18 years | **$0.37B** | **$1.04B** |

The low case is a distributed studio paying regional salaries, with light outsourcing and a modest player base. The high case pays top-market salaries, outsources more and runs servers for a large, successful launch. Both add a 15% contingency to every stage after the prototype, except marketing.

## 2. Grounding

Small teams have reached top quality and huge audiences, so the early stages are planned at their scale:

| Game | Team | Cost |
| --- | --- | --- |
| *Clair Obscur: Expedition 33* [G21] | About 30 core staff over four years, plus partners | Under $10 million |
| *Palworld* [G22] | Grew from 4 to about 55, plus outsourcing | About $6.7 million |
| *Albion Online* [G23], a cross-platform MMO | About 30 full-time at launch, over 100 today | Not published; its CTO calls the budget small for the scope |

Ready Player Zero is bigger than any of them: a shared world on every platform, AI-driven NPCs, seven regions and ten years of live updates. That is why the launch stage costs more. It stays lean by holding launch to six first-class systems ([D-005](../../DECISIONS.md#d-005)), building on Unreal Engine and proven services, and using partners for peak work.

## 3. Assumptions

| Item | Low | High | Notes |
| --- | --- | --- | --- |
| Fully loaded cost per staff member per year | $75,000 | $140,000 | Salary, benefits, taxes, equipment and software. Remote-first with one small hub, so little is spent on offices. |
| Outsourced work, as a share of in-house cost | 30% | 50% | Art, animation, capture, testing, localisation ([Team: external partners](team.md#3-external-partners)) |
| Contingency | 15% | 15% | Every stage after the prototype, except marketing |
| Engine royalty | 3.5% of revenue | 3.5% of revenue | Paid from revenue, not from the build budget [S12] |
| Platform store fees | Per platform agreement | Per platform agreement | Taken from revenue, not from the build budget |

## 4. Stages

### 4.1 Concept prototype

Six people build a rough single-zone prototype in Unreal Engine with marketplace assets: one NPC Mind you can talk to, the deflect and glide feel, and one Weaver micro-event. It proves the idea is fun before anyone else is hired.

| Item | Low | High |
| --- | --- | --- |
| Team (6 people, 9 months) | $0.35M | $0.65M |
| Assets, tools, cloud and AI usage | $0.05M | $0.15M |
| **Total** | **$0.4M** | **$0.8M** |

### 4.2 First Playable (H0)

A small senior team, growing to 25, proves the unique bets set out in [Scope and Horizons](scope-and-horizons.md): NPC Minds, the Weaver, combat and traversal feel, a Ward house and about 50 players in one region.

| Item | Low | High |
| --- | --- | --- |
| Staff (about 36 person-years) | $2.7M | $5.0M |
| Tools, devkits, cloud and AI inference | $0.5M | $1.0M |
| Contingency | $0.5M | $0.9M |
| **Total** | **$3.7M** | **$6.9M** |

### 4.3 Production to launch (H1)

The team grows to 180 and partners carry most of the content volume in the final two years.

| Item | Low | High |
| --- | --- | --- |
| Staff (about 550 person-years) | $41M | $77M |
| Outsourced work | $12M | $39M |
| Performance capture, music and licensed voices | $3M | $8M |
| Development cloud, betas and load tests | $3M | $8M |
| Ratings, certification, legal and cultural consultants | $2M | $5M |
| Contingency | $9M | $21M |
| **Total** | **$70M** | **$158M** |

### 4.4 Launch marketing

Community-led: the countdown, the Long Night broadcasts, creators and platform features carry most of the reach, with paid media on top. A publishing partner can carry part of this cost.

| Low | High |
| --- | --- |
| $15M | $50M |

### 4.5 Live decade (H2), per year

| Item | Low | High | Notes |
| --- | --- | --- | --- |
| Staff (about 140 people) | $10.5M | $19.6M | One Age drop a year and quarterly updates |
| Partners: moderation, support, art, capture | $4M | $10M | Grows with players |
| Servers, voice, storage and bandwidth | $6M | $25M | Grows with concurrent players ([Server and Backend](../08-technology/server-and-backend.md)) |
| AI inference | $2M | $10M | Held under the [AI-112](../06-ai/architecture.md#10-performance) target by on-device models and caching |
| Marketing and live events | $2M | $8M | Age drops and Long Night broadcasts |
| Contingency | $3.4M | $9.7M | |
| **Total per year** | **$28M** | **$82M** | |

The tenth year also funds both endings and Archive Mode ([Ten-Year Live Plan](ten-year-live-plan.md)), inside the same yearly range.

## 5. Spending gates

Money is released stage by stage. Each stage starts only when the one before meets its gate, so the studio never grows ahead of the game.

| Gate | Unlocks | Passes when |
| --- | --- | --- |
| Concept prototype | First Playable funding | Playtesters describe surprising, explainable moments they want to retell |
| H0 exit ([Scope and Horizons](scope-and-horizons.md)) | Production funding | Every H0 exit criterion is met, including AI cost per player-hour |
| Vertical Slice | Full production ramp and partner contracts | One Domain at final quality on every launch platform family |
| Beta | Launch marketing at full spend | Retention and stability targets met in the open beta |
| Each Age drop | The next year's budget | The previous year stayed within its range |

## 6. How the game pays for itself

Revenue comes only from the cosmetic store and the optional Patron subscription ([D-045](../../DECISIONS.md#d-045)). After platform fees, the engine royalty and taxes, roughly two-thirds of gross revenue reaches the studio. So the lifetime cost needs about $0.6 billion in gross revenue in the low case and about $1.6 billion in the high case. Server and live costs grow with players, so a smaller audience also costs less to run. A shortfall is met by cutting or deferring scope ([Scope and Horizons](scope-and-horizons.md)), never by selling power.

<!-- citation links: generated, do not edit by hand -->

[G21]: ../../references/games.md
[G22]: ../../references/games.md
[G23]: ../../references/games.md
[S12]: ../../references/technology-and-ai.md
