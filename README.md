# Ready Player Zero

The design specification for *Ready Player Zero* (working title): a cross-platform open-world game where every player shares one world, and a real ten-year countdown decides whether that world survives. It covers the vision, the world and its story, every system, the AI, the technology, the platforms, the team, production and legal, all linked to a library of verified sources.

**Version:** v0.1 · **Updated:** 10-10-2026 · **Target launch:** mid-2030s

> [!NOTE]
> Inspired by Ernest Cline's [*Ready Player One*](https://en.wikipedia.org/wiki/Ready_Player_One) and [*Ready Player Two*](https://en.wikipedia.org/wiki/Ready_Player_Two). Not affiliated with or endorsed by Ernest Cline, Warner Bros. or Readyverse Studios, and not an impersonation of any existing game or product.

## The game at a glance

- **Always online, always shared**
  - One world for every player on every platform.
  - Every Returner you meet is a real person playing live: explore, trade, team up or fight together, in the moment.
  - NPCs with their own lives fill the world between them.
- **The world**
  - The Oasis: a planet with three moons and seven regions.
  - Six of the regions, the Domains, each obey their own Natural Law, set by the Celestial chained inside them.
- **The player**
  - One persistent avatar, a Returner, who comes back after every death.
  - The avatar, every Art and every item have levels from 1 to 10.
  - Player Rank and Adventure Rank run to 100.
- **The stakes**
  - On launch day a public clock starts counting down ten real years.
  - Together, the players must free six chained Celestials, defeat the False Celestial who betrayed them and forge the Dawnkey.
  - If they succeed, Oasis 2.0 opens. If they fail, the world ends.
- **The AI**
  - Players talk to NPCs in their own words, and the NPCs remember.
  - One rule keeps it fair: nothing a model says can change the game by itself.
- **Fairness**
  - Power can't be bought.
  - The store sells cosmetics only.

## Where to start

| If you want to… | Read |
| --- | --- |
| Hear the story | [The Story of the Oasis](STORY.md) |
| Understand the game and its pillars | [Vision](docs/01-vision/vision.md) |
| See what has been decided | [Decision Log](DECISIONS.md) |
| Look up a term | [Glossary](GLOSSARY.md) |
| Learn how the spec is written | [Conventions](docs/00-meta/conventions.md) |
| Suggest a change | [Contributing](CONTRIBUTING.md) |
| Check a source | [Reference Library](references/README.md) |

## How the repository is organised

The root holds the documents that apply to everything. The folders under `docs/` are numbered in reading order, and each has a README that lists its documents.

```text
README.md            this page
STORY.md             the saga: the world, the decade, the hidden truth
DECISIONS.md         every decision that spans documents, with its reason
GLOSSARY.md          one meaning per term
CONTRIBUTING.md      how the spec takes suggestions
CHANGELOG.md         what changed in each version
docs/
  00-meta/           conventions, spec template
  01-vision/         vision, art and audio direction
  02-world/          cosmology, time, world laws, geography, peoples, machines and colossi
  03-narrative/      Celestials, ten-year saga, reveal graph, Eggs, quests, tone
  04-gameplay/       core loops, progression, combat, traversal, death and return
  05-systems/        Convergence, economy, housing, law, PvP, waypoints,
                     spaceflight, machines and companions, NPC bonds, recording
  06-ai/             architecture, NPC minds, the Weaver, AI safety
  07-multiplayer/    world model, social and voice, safety and moderation
  08-technology/     engine and stack, server and backend, tech watch
  09-platforms/      platform support, controls and accessibility
  10-testing/        testing and acceptance
  11-production/     scope and horizons, live plan, team, budget, risk register
  12-legal/          legal and compliance, regulatory watch
references/          verified sources, graded, with the lesson each one teaches
```

## Reading paths

| Role | Path |
| --- | --- |
| Story and world | [The Story of the Oasis](STORY.md) → [Cosmology](docs/02-world/cosmology.md) → [Celestials](docs/03-narrative/celestials.md) → [Ten-Year Saga](docs/03-narrative/ten-year-saga.md) → [Tone and Themes](docs/03-narrative/tone-and-themes.md) |
| Game design | [Vision](docs/01-vision/vision.md) → [Core Loops](docs/04-gameplay/core-loops.md) → [Avatar and Progression](docs/04-gameplay/avatar-and-progression.md) → [Combat and Abilities](docs/04-gameplay/combat-and-abilities.md) → [World Laws](docs/02-world/world-laws.md) → [Systems](docs/05-systems/README.md) |
| Engineering | [Conventions](docs/00-meta/conventions.md) → [World Model](docs/07-multiplayer/world-model.md) → [Server and Backend](docs/08-technology/server-and-backend.md) → [Engine and Stack](docs/08-technology/engine-and-stack.md) → [Tech Watch](docs/08-technology/tech-watch.md) |
| AI | [AI Architecture](docs/06-ai/architecture.md) → [NPC Minds and Conversation](docs/06-ai/npc-minds-and-conversation.md) → [Director and World Events](docs/06-ai/director-and-world-events.md) → [AI Safety and Evaluation](docs/06-ai/safety-and-evaluation.md) |
| Art and audio | [Art and Audio Direction](docs/01-vision/art-and-audio-direction.md) → [Geography and Domains](docs/02-world/geography-and-domains.md) → [Peoples and Factions](docs/02-world/peoples-and-factions.md) → [Machines and Colossi](docs/02-world/machines-and-colossi.md) |
| Testing | [Testing and Acceptance](docs/10-testing/testing-and-acceptance.md), then the acceptance criteria at the end of each spec |
| Production and legal | [Scope and Horizons](docs/11-production/scope-and-horizons.md) → [Ten-Year Live Plan](docs/11-production/ten-year-live-plan.md) → [Team](docs/11-production/team.md) → [Budget](docs/11-production/budget.md) → [Risk Register](docs/11-production/risk-register.md) → [Legal and Compliance](docs/12-legal/compliance.md) |

## How it changes

The spec is versioned. Suggestions from the team, players and the community go through [Contributing](CONTRIBUTING.md): each one is reviewed against the vision, decided, logged in the [Decision Log](DECISIONS.md) and recorded in the [Changelog](CHANGELOG.md). Specs only ever state decisions.
