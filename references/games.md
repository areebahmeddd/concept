# References: Games

Verified facts about the games we learn from, and what each one means for *Ready Player Zero*.

> **Version:** v0.1 · **Updated:** 10-10-2026 · **Owner:** Design lead
>
> **Related:** [Reference Library](README.md) · [Film, Literature and Music](film-literature-and-music.md#n-series-sources)

**Grades:** **P** primary source · **S** secondary (press, wiki) · **W** weak or vendor; corroborate before relying on it.

**Format:** **[ID]** title (studio, year) · grade · *fact* → **lesson:** what we take, and what we change · sources.

## Open worlds and world simulation

- **[G1]** *Grand Theft Auto V* (Rockstar North, 2013; PS4 and Xbox One 2014) · S
  - *Fact:* a 1 to 5 star wanted meter. Police search the last-known area, and Heat cools once the player breaks line of sight. First-person mode was added in the 2014 re-release, which needed about 3,000 rebuilt weapon animations.
  - *Fact:* GTA VI is dated 19 November 2026 on PS5 and Xbox Series (Rockstar's official page, as of October 2026).
  - → **Lesson:** we take Heat that is readable, escapable and fun to evade ([Law, Crime and Bounties](../docs/05-systems/law-crime-and-bounties.md)). We change what follows it: a lasting Record that can be cleared in several ways ([D-034](../DECISIONS.md#d-034)). Adding first-person late is expensive, so the switchable camera ([D-020](../DECISIONS.md#d-020)) is built in from the start.
  - <https://www.rockstargames.com/VI> · <https://en.wikipedia.org/wiki/Grand_Theft_Auto_V> · <https://gamespot.com/articles/gta-5-xbox-one-ps4-pc-has-first-person-mode/1100-6423366/>
- **[G2]** *Red Dead Redemption 2* (Rockstar, 2018) · S
  - *Fact:* Honor tracks how others see the player's deeds. Witnesses report crimes, and the player can stop them first. Bounties are cleared by paying at a post office, surrendering, or serving jail time, and the player can't pay while being hunted.
  - → **Lesson:** we take paying off a bounty and witnesses as the bridge between a crime and the law. We change the ways to clear a Record: a fine at a Watch post, surrender, or community service, so clearing is never only a matter of money ([D-034](../DECISIONS.md#d-034)).
  - <https://en.wikipedia.org/wiki/Red_Dead_Redemption_2> · <https://www.shacknews.com/article/108138/how-the-wanted-and-bounty-systems-work-in-red-dead-redemption-2>
- **[G3]** *Kingdom Come: Deliverance* I (2018) and II (2025) (Warhorse) · S
  - *Fact:* NPCs report crimes. Needs, gear wear, spoiling food and NPC routines are simulated. A historical consultant (Joanna Nowak) aimed for "historically credible", with compromises for fun. KCD1 sold more than 10 million by May 2025; KCD II sold 1 million in a day.
  - → **Lesson:** we take "credible, with compromises for fun" as our stance on realism; grounded simulation sells. We change the anchor: our world is a myth, so credibility comes from consistent systems (routines, wear, law) rather than from history.
  - <https://en.wikipedia.org/wiki/Kingdom_Come:_Deliverance> · <https://www.rpgsite.net/news/18937-kingdom-come-deliverance-ii-has-sold-4-million-copies>
- **[G4]** *Assassin's Creed Odyssey* (2018) and *Valhalla* (2020) (Ubisoft) · S
  - *Fact:* Odyssey explains its mythic creatures (Medusa, the Minotaur) as Isu experiments, giving myth an in-world logic. The Discovery Tour modes are combat-free and built with historians and museum collections.
  - → **Lesson:** we take the rule that myth needs an in-world logic. We change the answer: our myths are true inside the world, because the Celestials' bound power is what sets each Domain's Natural Law ([World Laws](../docs/02-world/world-laws.md)).
  - <https://en.wikipedia.org/wiki/Assassin%27s_Creed_Odyssey> · <https://www.videogameschronicle.com/news/assassins-creed-valhallas-free-viking-age-discovery-tour-expansion-is-out-now>
- **[G5]** *Watch Dogs: Legion* (Ubisoft Toronto, 2020) · P
  - *Fact:* "Census" generates demographically consistent people, keeps them persistent and schedules their days. Hocking called it "a massive relational database".
  - → **Lesson:** we take systemic, persistent NPC lives with daily schedules at city scale ([NPC Minds and Conversation](../docs/06-ai/npc-minds-and-conversation.md)). We change who writes them: named NPCs are authored by writers, and generation only fills the crowd.
  - <https://gdcvault.com/play/1027018/Census-The-Systemic-Backbone-Behind> · <https://news.ubisoft.com/en-us/article/4po3S9Pwp1YcgBmGPmQxAh/watch-dogs-legion-the-tools-that-built-london>
- **[G6]** *Horizon Zero Dawn* (2017) and *Forbidden West* (2022) (Guerrilla) · P
  - *Fact:* each machine should resemble "a combination of animals but not a literal translation of a singular one". Machines form an ecology with herd behaviour, and have readable armour, weak spots and detachable parts.
  - → **Lesson:** we take ecology and readable anatomy for Automata, Wardens and colossi ([Machines and Colossi](../docs/02-world/machines-and-colossi.md)). We change their place in the world: colossi are rare events whose arrival reshapes a region, not common prey.
  - <https://blog.playstation.com/2017/02/24/the-making-of-horizon-zero-dawns-machines/>
- **[G7]** *God of War* (2018) and *Ragnarök* (2022) (Santa Monica) · S
  - *Fact:* a single continuous camera with no cuts, chosen to tell "a much more personal story". Ragnarök won six TGA 2022 awards, including Narrative and Innovation in Accessibility.
  - → **Lesson:** we take the continuous camera for main-story scenes. We change it to respect the player's camera choice, first or third person ([D-020](../DECISIONS.md#d-020)), and allow cuts elsewhere. Ragnarök also sets the accessibility bar ([Controls, Camera and Accessibility](../docs/09-platforms/controls-camera-and-accessibility.md)).
  - <https://en.wikipedia.org/wiki/God_of_War_(2018_video_game)> · <https://www.videogameschronicle.com/news/the-game-awards-2022-full-winners-list-elden-ring-and-god-of-war-dominate>
- **[G8]** *Hyper Light Drifter* (Heart Machine, 2016) · S
  - *Fact:* no text or voiceover. The story is told through storyboard images.
  - *Fact:* development of *Hyper Light Breaker* ended about nine months into early access (2025), and one report says the studio later laid off almost all its staff (September 2026).
  - → **Lesson:** we take wordless storytelling for Eggs and environmental mysteries. Breaker is a warning that live-service ambition needs matching money and scope ([Scope and Horizons](../docs/11-production/scope-and-horizons.md)).
  - <https://www.gameinformer.com/games/hyper_light_drifter/b/pc/archive/2014/03/14/developer-covers-key-aspects-hyper-light-drifter.aspx> · <https://www.videogameschronicle.com/news/development-ends-on-hyper-light-breaker-as-studio-heart-machine-says-its-making-layoffs> · <https://massivelyop.com/2026/09/18/hyper-light-breaker-developer-heart-machine-lays-off-nearly-everyone-at-the-studio/>

## Combat

- **[G9]** *Mortal Kombat 1* (NetherRealm, 2023) · P
  - *Fact:* rated ESRB **M** for Blood and Gore and Intense Violence (Fatalities with dismemberment). The original Mortal Kombat fed into the 1993 US Senate hearings that led to the ESRB. ESRB **T** allows violence with only "minimal blood".
  - → **Lesson:** we take distinct fighter identities and memorable signature moves. We leave out the gore: the T rating line is binding ([D-006](../DECISIONS.md#d-006)).
  - <https://www.esrb.org/ratings/39503/mortal-kombat-1/> · <https://en.wikipedia.org/wiki/Entertainment_Software_Rating_Board>
- **[G10]** *Sekiro: Shadows Die Twice* (FromSoftware, 2019) · S
  - *Fact:* fights are won by breaking Posture through timed deflects, which opens a Deathblow. It was TGA 2019 Game of the Year.
  - → **Lesson:** we take Poise and the deflect as the core of combat ([Combat and Abilities](../docs/04-gameplay/combat-and-abilities.md)): weight and tension come from rhythm, not from enemies with huge health bars. We change the setting: deflect has to work in group fights and Convergence fronts as well as in duels.
  - <https://videogamecanon.com/adventurelog/2019-the-game-awards>
- **[G11]** *For Honor* (Ubisoft Montreal, 2017) · S
  - *Fact:* the "Art of Battle" uses directional guard stances (left, right, top) that both fighters can read.
  - → **Lesson:** we take readable directional intent in melee duels. Its later move to dedicated servers (M38) is why our melee is server-authoritative from the start.
  - <https://www.tomshardware.com/uk/news/for-honor-hands-on-gameplay-e3,29445.html>
- **[G14]** *PUBG* (2017) · S
  - *Fact:* separate first-person-only servers exist because a third-person camera lets players see round cover without exposing themselves ("in first person you pay for every peek").
  - → **Lesson:** we take the perspective lock for competitive rulesets. Everywhere else, players switch camera freely ([D-020](../DECISIONS.md#d-020)).
  - <https://www.pcgamer.com/pubg-first-person-servers/>

## Social worlds

- **[G12]** *Club Penguin* (2005 to 2017) and *Woozworld* · S
  - *Fact:* Ultimate Safe Chat offered preset phrases only. Standard Safe Chat filtered typed text, and blocked messages were shown only to the sender. In 2007 about 70 of roughly 100 staff were moderators. Servers closed on 30 March 2017.
  - *Fact:* Woozworld is a tween and teen virtual world (Woozworld Inc.), COPPA-compliant and still running.
  - → **Lesson:** we take two things: safety at scale is staffing and design, not just filters, and "shown only to the sender" stops harassment without a fight. We change the default for minors: open chat with non-friends starts off ([D-008](../DECISIONS.md#d-008)) rather than being limited to presets.
  - <https://en.wikipedia.org/wiki/Club_Penguin> · <https://en.wikipedia.org/wiki/Woozworld>
- **[G13]** *Roblox* (Roblox Corp.) · P
  - *Fact:* Q2 2026: 123 million daily active users, $1.469 billion revenue, and $363 million paid to creators through DevEx in the quarter.
  - → **Lesson:** we take the lesson that social identity plus creation drives scale. We change the outlet: players create through housing and Frame customisation ([Housing](../docs/05-systems/housing.md)), not open game-making, and there are no real-money payouts ([D-046](../DECISIONS.md#d-046)).
  - <https://www.sec.gov/Archives/edgar/data/0001315098/000162828026051059/ex991-robloxq22026earnin.htm>

## Spaceflight, housing and world events

- **[G15]** *Elite Dangerous* (Frontier, 2014), *Star Citizen* (CIG) and *No Man's Sky* (Hello Games, 2016) · S/P
  - *Fact (Elite):* docking needs permission. Trespass and loitering on a pad bring fines that become bounties, and then station fire.
  - *Fact (Star Citizen):* landing goes through air traffic control, and armistice zones disable weapons or fine aggression.
  - *Fact (No Man's Sky):* the official line is "fly seamlessly from the surface of a planet to another".
  - → **Lesson:** we take authorised launch and landing zones, traffic control, and fines that escalate into bounties ([Spaceflight and Moon Travel](../docs/05-systems/spaceflight-and-moon-travel.md)). Continuous surface-to-space flight has shipped before. We change the scale: the three moons are the only destinations, and distances are compressed ([D-033](../DECISIONS.md#d-033)).
  - <https://www.pcgamer.com/au/in-the-elite-dangerous-alpha-loitering-in-the-docking-bay-is-a-killable-offence> · <https://starcitizen.tools/Space_station> · <https://www.nomanssky.com/about/>
- **[G16]** *FFXIV* housing (2022), *ESO* Homestead (2017) and *Animal Crossing: New Horizons* (2020) · S
  - *Fact:* FFXIV patch 6.1 replaced first-come plot sales with a 5-day lottery. Districts have 30 wards of 60 plots.
  - *Fact:* ESO housing arrived with Homestead (6 February 2017).
  - *Fact:* in ACNH, Tom Nook's house appears **the next morning**.
  - → **Lesson:** we take ACNH's lesson that waiting for a builder is a pleasure when it feels like anticipation. We change FFXIV's scarcity: every Returner is guaranteed a Ward plot, so there is no lottery ([D-035](../DECISIONS.md#d-035)).
  - <https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1> · <https://nookipedia.com/wiki/Home_loan>
- **[G17]** Countdowns and finite worlds · S
  - *Fact:* *Majora's Mask* (2000): the moon falls after 72 in-game hours (about 54 real minutes), and the Song of Time resets the cycle.
  - *Fact:* *Outer Wilds* (2019): a 22-minute loop that ends in a supernova; three BAFTAs, including Best Game.
  - *Fact:* *Fortnite* "The End" (13 October 2019): a black hole made the game unplayable for about 36 hours, watched by more than 5.5 million on stream.
  - *Fact:* *WoW* Gates of Ahn'Qiraj (January 2006): a server-wide war effort, after which the player who rang the gong earned the unique Scarab Lord title.
  - *Fact:* *Destiny 2: The Final Shape* (2024) concluded a decade-long saga.
  - → **Lesson:** we take the falling moon and dying sun as a proven emotional engine, a real global gate with unique titles as the template for Convergence ([Celestial Convergence](../docs/05-systems/celestial-convergence.md)), and a world-ending live event as a cultural moment. We change the clock: ours runs for ten real years, once, with no reset, and each Convergence honours many world-first feats instead of one gong-ringer.
  - <https://www.npr.org/2019/10/15/770318763/fortnite-unveils-new-chapter-after-two-day-black-hole-shutdown> · <https://warcraft.wiki.gg/wiki/10_Hour_War> · <https://www.gamedeveloper.com/press-release/destiny-2-the-final-shape-launches-worldwide>
- **[G18]** The history of Easter eggs · S
  - *Fact:* *Adventure* (Atari 2600, 1980): Warren Robinett hid a credit room, and Atari kept it, naming the practice "Easter eggs".
  - *Fact:* Ernest Cline's real *Ready Player One* contest (2012) awarded a 1981 DeLorean to Craig Queen.
  - → **Lesson:** we take the lineage behind our Eggs ([Eggs and Mysteries](../docs/03-narrative/eggs-and-mysteries.md)) and the way real hunts build community legends. We change the prize: Eggs reward knowledge, titles and Adventure Rank, never power.
  - <https://en.wikipedia.org/wiki/Adventure_(1980_video_game)> · <https://boingboing.net/2012/08/31/ready-player-one-delorean.html>

## Art direction

- **[G19]** Stylisation: *Arcane* (Fortiche and Riot, 2021), *Into the Spider-Verse* (Sony Pictures Animation, 2018) and *Wind Waker* · S
  - *Fact:* Arcane combines 3D characters and hand-painted textures over painted 2D backgrounds, with 2D-drawn effects.
  - *Fact:* Spider-Verse painted lines over CG, animated on twos, and won the Oscar for Best Animated Feature.
  - *Fact:* "stylised ages better" (Wind Waker) is critical consensus, not a study.
  - → **Lesson:** we take painted surfaces over believable forms as the basis of Painted Realism ([D-044](../DECISIONS.md#d-044)). We state the limit honestly: that the look will age well is a judgement, not a proven fact.
  - <https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/> · <https://en.wikipedia.org/wiki/Spider-Man:_Into_the_Spider-Verse> · <https://www.gamegrin.com/articles/the-legend-of-zelda-the-wind-wakers-artstyle-20-years-later/>

## Adventure

- **[G20]** *Uncharted* (Naughty Dog, 2007 onward) · S
  - *Fact:* an action-adventure series of climbing and rope-swinging traversal, where treasure hunters uncover historical mysteries.
  - → **Lesson:** a treasure hunt is best when it is also a history lesson. We take it for Eggs that follow in-world history across the Domains, and for readable climbing routes.
  - <https://en.wikipedia.org/wiki/Uncharted>

## N-series games (N1 to N18)

Sources for these IDs are in the [N-series sources](film-literature-and-music.md#n-series-sources).

| ID | Game | Verified fact | Lesson: what we take, and what we change |
| --- | --- | --- | --- |
| N1 | *Outer Wilds* | GDC 2020 talk "Curiosity-Driven Exploration" | Knowledge as progression, which we turn into Adventure Rank, Eggs and Convergence Discover work |
| N2 / N3 | *Elden Ring* | Martin wrote the mythos and Miyazaki the story; the past is told in environmental fragments; TGA 2022 Game of the Year | A past told in fragments: the Seven Days surface piece by piece, released through the [Reveal Graph](../docs/03-narrative/reveal-graph.md) |
| N4 / N5 | *The Witcher 3* | The Bloody Baron (Sasko); GDC 2023 quest takeaways; TGA 2015 Game of the Year | Authored moral texture for the Returner's Path and personal quests |
| N6 / N7 | *Red Dead Redemption 2* | About 500,000 lines and 2,200 days of motion capture; crunch reporting | The real cost of authored density. We get breadth from systems and AI instead, and refuse crunch (OPS-042). |
| N8 / N9 | *Clair Obscur: Expedition 33* | Built in UE5 by about 30 core staff; TGA 2025 Game of the Year with 9 wins | A distinctive premise beats scale, and a painterly UE5 look can ship ([D-044](../DECISIONS.md#d-044)) |
| N10 | *Disco Elysium* | 24 skills that speak as inner voices | Ability systems can carry character. Ours carry it through what an Oath forbids, not through inner voices. |
| N11 | *Hollow Knight* | A 3-person team; the map grew outward from a hub | Interconnection over size: every Domain links back to the Hearthlands |
| N12 / N13 | *Titanfall 2* and *Armored Core VI* | Pilot and Titan as two pillars; parts change mobility, not just stats | Pilot and Frame are two mastery spaces: Piloting Mastery is separate from Avatar Level |
| N14 | *Shadow of the Colossus* | Each colossus was designed around how it is defeated | Orun's Convergence is a climb up a walking colossus. We change the end: the colossus is freed, not killed. |
| N15 | *Monster Hunter: World* | 22.4 million base sales, 30.4 million with Iceborne | Gear forged by an NPC smith from what you gather, and ecology-first monsters. Our Artisans add commission time and trust. |
| N17 | *Ghost of Tsushima* | The Guiding Wind replaces waypoints | Navigation that belongs to the world, different in each culture |
| N18 | *Genshin Impact* | About $4.2 billion on mobile through gacha by the end of 2022 | A cross-platform open world can work. We reject its gacha ([D-045](../DECISIONS.md#d-045)) and its host-world co-op ([D-029](../DECISIONS.md#d-029)). |

<!-- citation links: generated, do not edit by hand -->

[G1]: games.md
[G2]: games.md
[G3]: games.md
[G4]: games.md
[G5]: games.md
[G6]: games.md
[G7]: games.md
[G8]: games.md
[G9]: games.md
[G10]: games.md
[G11]: games.md
[G12]: games.md
[G13]: games.md
[G14]: games.md
[G15]: games.md
[G16]: games.md
[G17]: games.md
[G18]: games.md
[G19]: games.md
[G20]: games.md
