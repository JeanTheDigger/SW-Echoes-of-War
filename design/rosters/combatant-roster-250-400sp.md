# Combatant Roster: 20 Fighters, 250/400 to 400/400 SP

Twenty original combatants for Echoes of War, built for characters between **250/400 and 400/400 skill points**, with most of them at or near the cap.

Each fighter has two halves:

1. **A player-equivalent build.** Skill ranks, attributes and perk spend follow the live rules exactly, so the fighter is a character a real player could build. Use it for PvP sparring partners, DM-run characters, CombatSim profiles and balance benchmarks.
2. **A Bible-format NPC build.** Level, Difficulty, Role, Creature Type, Modifier and Ability Package come from the *Enemy Builder Guide*. The stat line is taken from *Enemy Stat Presets* with the *Enemy Modifiers* applied, so it is what the Builder tab would generate. You can hand it straight to whoever builds the UTC.

Every build was checked against the rules listed below. All 20 pass.

---

## 1. Rules every build obeys

Source: `Skill.cs`, `CharacterSheetViewModel.cs`, `CharacterFullRebuildViewModel.cs` and the Design Bible.

| Rule | Value |
|---|---|
| Earned SP | 1 SP per contributing skill rank, capped at **400**. Languages don't count. |
| Spendable SP | 10 starting SP + earned SP, so **410 at cap** and 260 at 250 |
| Skill rank cap | 50 for every combat, utility and crafting skill |
| AP | 1 per 10 earned SP (**40 at cap**, 25 at 250) |
| Attributes | All start at 10, plus 15 creation points (max +6 each), plus AP. Purchased score is capped at **26**, and one racial +1 allows **27**. |
| Attribute total | 60 + 15 + AP + 1 racial = **116 at 400 SP**, 101 at 250 SP |
| Perk trees | Each weapon has 2 styles of 60 SP (120 total). General 32 (gated by Armor). Force 240. Devices 240. First Aid 110. Leadership Vanguard and Field Steward 55 each. Espionage 135. Mimicry 31. |
| Character type locks | Lightsaber, Saberstaff and Force are **Force Sensitive only**. Devices and Espionage are **Standard only**. |
| Style limit | None. A character can own both styles of one tree. No code restricts it. |
| Force affinity | Each Dark perk is −1 and each Light perk is +1, clamped to −10/+10 |

**How partial styles are counted:** a partial style buys its perks in skill-rank order up to the SP shown. For example, "Vanguard Command 28 (10/17)" means the first 10 of its 17 perks, which cost 28 SP.

**Filler ranks:** the SP has to be earned somewhere, and a real 400/400 character holds ranks in Piloting or crafting. Every build puts its spare ranks in non-combat skills. Those ranks earn SP and AP but buy no combat perks.

---

## 2. Tier structure and level mapping

All characters cap a skill at rank 50, so SP above roughly 250 buys **breadth**: more trees, more AP and more capstones, not a higher weapon rank. Enemy level is the dial the Bible already uses for capped content. Korriban already runs L55 Normal/Tough and L70 bosses for capped players, and Merit LP only comes from enemies of level 50 or higher. The roster's levels follow those anchors.

| Tier | SP range | Count | NPC level | Default difficulty | Meaning |
|---|---|---|---|---|---|
| **I. Contenders** | 250–299 | 4 | 48–50 | Tough | Main weapon maxed, thin secondaries |
| **II. Veterans** | 300–349 | 4 | 50–52 | Tough | Two to three trees complete |
| **III. Elites** | 350–399 | 4 | 53–55 | Elite | Near-capped specialists |
| **IV. The Capped Eight** | 400/400 | **8** | 57–65 | Elite, 2 Boss | Fully capped, with 2 to 5 capstones each |

That puts **12 of the 20 at 360 SP or more and 8 at exactly 400/400**, which is the emphasis on 400/400 you asked for.

---

## 3. Master roster

| # | Name | Tier | SP | Type | Archetype | Core trees | NPC build |
|---|---|---|---|---|---|---|---|
| 1 | **Kaedra Vosk** | IV ★ | 400 | Force | Sith saber duelist | Lightsaber ×2, Dark Force | L65 Boss Melee · Force User · Group Boss |
| 2 | **Torvin Ashgrave** | IV | 400 | Standard | Bastion heavy-blade tank | Heavy Vibroblade ×2, Devices, Steward | L58 Elite Tank · Humanoid · High Durability |
| 3 | **Ressa Kel'dar** | IV ★ | 400 | Standard | Gunslinger | Pistol ×2, Twin Pistol ×2, Infiltrator | L62 Boss Ranged · Humanoid · Group Boss |
| 4 | **Master Ilen Theron** | IV | 400 | Force | Light saberstaff warden-healer | Saberstaff ×2, Light Force, Trauma Medic | L58 Elite Support · Force User |
| 5 | **Vashka Dren** | IV | 400 | Standard | Sniper-saboteur | Rifle ×2, Espionage ×2, Field Engineer | L57 Elite Ranged · Humanoid · Glass Cannon |
| 6 | **Grrakhan the Anvil** | IV | 400 | Standard | Wookiee pit brawler | Katar ×2, Unarmed ×2, Vanguard | L58 Elite Melee · Humanoid · High Durability |
| 7 | **Sela Morn** | IV | 400 | Standard | Demolitions engineer | Devices ×4, Throwing ×2 | L57 Elite Controller · Humanoid |
| 8 | **Corvan Hale** | IV | 400 | Force | Grey twin-blade warden | Twin Blade ×2, Universal Force, Leadership | L60 Elite Melee · Force User · Hard to Hit |
| 9 | **Jorik Fenn** | III | 395 | Standard | Cathar berserker | Vibroblade ×2, Throwing ×2, Vanguard | L55 Elite Melee · Humanoid · High Damage |
| 10 | **Tal Ossiri** | III | 385 | Standard | Force-hunter lancer | Spear ×2, Devices ×2, Saboteur | L55 Elite Controller · Humanoid |
| 11 | **Nyx Varro** | III | 375 | Standard | Chiss poison assassin | Vibroknife ×2, Espionage ×3 | L54 Elite Melee · Humanoid · Glass Cannon |
| 12 | **Oda Rhen & "Gutter"** | III | 360 | Standard | Beast-handler marksman | Beast Mastery, Rifle ×2, Steward | L53 Elite Ranged · Humanoid, plus L53 Tough Beast pet |
| 13 | **Mirek Sabo** | II | 345 | Standard | Echani whirlwind | Twin Blade ×2, Assault Gadgets | L52 Tough Melee · Humanoid |
| 14 | **Ysolde Crane** | II | 330 | Standard | Combat medic | First Aid ×2, Pistol, Field Support | L51 Tough Support · Humanoid |
| 15 | **Garr Tevik** | II | 315 | Standard | Trandoshan staff sentinel | Staff ×2, Trauma Medic, Steward | L51 Tough Tank · Humanoid · High Durability |
| 16 | **Liss Varan** | II | 300 | Force | Dark Force adept | Dark Force, Lightsaber 30 | L50 Tough Force · Force User |
| 17 | **Dax Morrow** | I | 290 | Standard | Twin-blaster skirmisher | Twin Pistol ×2, Infiltrator 40 | L50 Tough Ranged · Humanoid |
| 18 | **Kira Solune** | I | 275 | Standard | Blade-thrower | Throwing ×2, Cutthroat 40 | L49 Tough Ranged · Humanoid |
| 19 | **Bannoc Rusk** | I | 260 | Standard | Soul-burner berserker | Heavy Vibroblade ×2, Vanguard 40 | L48 Tough Melee · Humanoid · High Damage |
| 20 | **Captain Teyla Arn** | I | 250 | Standard | Squad officer | Leadership ×2, Rifle Suppression | L48 Tough Support · Humanoid |

★ = champion (Group Boss, meant for 2–4 players).

All 13 weapon skills appear at least once. Force, Devices, Beast Mastery, First Aid, Leadership, Espionage and Mimicry all appear in at least one build.

---

## 4. Fighter cards

Attribute order is MGT / PER / VIT / WIL / AGI / SOC. An asterisk marks the racial +1.
"Package" is the Bible ability package for the role and difficulty. **⇄** marks the single approved creature-type swap.

---

### TIER IV: THE CAPPED EIGHT (400/400)

#### 1. Kaedra Vosk, "The Red Verdict" ★ Champion
*Zabrak Sith duelist. She closes the gap, Sunders the target, then knocks down the whole pack.*

- **Type:** Force Sensitive · Affinity **−10 (Dark)**
- **Attributes:** 27\* / 26 / 23 / 20 / 10 / 10
- **Ranks:** Lightsaber 50 · Force 50 · Armor 50 · First Aid 50 · Mimicry 50 · Leadership 50 · Piloting 50 · Smithery 50
- **Perks (408/410):** Severance 60 · Ward 60 · Force, Dark + Universal only: Alter 85 (26/32), Control 27 (7/23), Sense 29 (8/13) · General 32 · Combat Pharmacology 55 · Mimicry 25 (9/10) · Vanguard Command 35 (12/17)
- **Signature kit:** **Epicenter** (6m knockdown and Sunder, up to 5 targets) · **Aegis Eternal** · Imbuement Stance · Fury Stance II · **Hunger of the Dark** (heals 12% of Dark damage dealt) · **Eclipse of Resolve** (−12% accuracy and evasion aura) · Emergency Cocktail
- **Fights like:** She Sunders a target with Shattering Strike, spreads Sunder with Sundering Sweep, then drops Epicenter on the pack. When focused she switches to Aegis Eternal and turns physical damage into Force damage.
- **Counterplay:** Spread out to blunt Epicenter and Sunder spreading. Bait Aegis Eternal (90s cooldown), then burst her. Mobility resistance helps against Epicenter's knockdown.
- **NPC:** L65 · Boss · Melee · Force User · **Group Boss**
  - HP **7878** · STM 322 · FP 56 · DMG **228** · Atk 50 · FAtk 23 · Ev 14 · Def 77 · FDef 47 · Delay 240
  - Package: ⇄ **Force Rend** (replaces Mauling Bite), Bonecrusher Bite, Tail Sweep, Terrifying Bellow, Chitin Guard, Rupturing Quake

#### 2. Torvin Ashgrave, "The Wall of Concordia"
*Mandalorian-clan veteran. He holds the line and keeps his party alive while doing it.*

- **Type:** Standard · **Attributes:** 26 / 17 / 27\* / 26 / 10 / 10
- **Ranks:** Heavy Vibroblade 50 · Armor 50 · First Aid 50 · Leadership 50 · Devices 50 · Piloting 50 · Smithery 50 · Gathering 50
- **Perks (410/410):** Immortal 60 · Berserker 60 · General 32 · Trauma Medic 55 · Field Steward 55 · Field Support 60 · Grenadier 60 · Vanguard Command 28 (10/17)
- **Signature kit:** **Absolute Defense** (party −15% damage, immune to knockdown and daze) · **Soul Ascension** · Bastion Stance · **Hold the Line** · **Emergency Bunker** · Emergency Triage · Thermal Detonator
- **Fights like:** Provoke II pulls the pack onto him, Bastion Stance holds it, and he stacks Absolute Defense with Hold the Line and Emergency Bunker when allies are pressured. He drops a Thermal Detonator on clumped enemies.
- **Counterplay:** He is an attrition tank, so ignore him and kill his allies. His defensive cooldowns all last 45s, so wait them out. Force damage gets past his high VIT.
- **NPC:** L58 · Elite · Tank · Humanoid · High Durability
  - HP **5684** · STM 175 · FP 58 · DMG 78 · Atk 23 · FAtk 1 · Ev 9 · Def **83** · FDef 52 · Delay 340
  - Package: Iron Carapace, Chitin Guard, ⇄ **Brutal Bash** (replaces Bonecrusher Bite), Tail Sweep

#### 3. Ressa Kel'dar, "Dead Man's Hand" ★ Champion
*Twi'lek gunslinger. She owns both pistol trees and both twin-pistol trees, and vanishes when cornered.*

- **Type:** Standard · **Attributes:** 10 / 26 / 20 / 10 / 27\* / 23
- **Ranks:** Pistol 50 · Twin Pistol 50 · Armor 50 · Espionage 50 · First Aid 50 · Mimicry 50 · Piloting 50 · Engineering 50
- **Perks (408/410):** Gambler 60 · Skirmisher 60 · Barrage 60 · Crossfire 60 · General 32 · Infiltrator 60 · Tradecraft 15 · Combat Pharmacology 55 · Mimicry 6 (3/10)
- **Signature kit (5 capstones):** **Dead Man's Hand** · **Last Word** (evades refresh Snap Roll) · **Twin Suns** · **Final Salvo** · **Ghost Protocol** (−80% enmity, stealth, guaranteed-crit back attack)
- **Fights like:** She builds Cadence with twin pistols and dumps it with Final Salvo. She swaps to a single pistol and Doublehand III for the Dead Man's Hand crit chain. When pressed she uses Ghost Protocol, repositions, and opens on a back attack.
- **Counterplay:** Keep detection up against Ghost Protocol. Close to melee and pin her with a knockdown, since she has no defensive stance. Ranged deflection blunts her auto-attack damage.
- **NPC:** L62 · Boss · Ranged · Humanoid · **Group Boss**
  - HP **6619** · STM 268 · FP 67 · DMG **208** · Atk 49 · FAtk 23 · Ev 16 · Def 74 · FDef 46 · Delay 260
  - Package: Tactical Mark, Suppressing Shot, Precision Shot, ⇄ **Grenade Burst** (replaces Piercing Quills), Shrapnel Burst, Overload Shot

#### 4. Master Ilen Theron, "The Still Current"
*Mirialan Jedi warden. A saberstaff bruiser who doubles as the party's healer.*

- **Type:** Force Sensitive · Affinity **+10 (Light)** · **Attributes:** 20 / 22 / 23 / 27\* / 14 / 10
- **Ranks:** Saberstaff 50 · Force 50 · Armor 50 · First Aid 50 · Leadership 50 · Piloting 50 · Agriculture 50 · Engineering 50
- **Perks (403/410):** Conduit 60 · Tempest 60 · Force, Light + Universal: Control 71 (19/23), Alter 53 (15/32), Sense 25 (8/13) · General 32 (Dual Wield III for the double weapon) · Trauma Medic 55 · Field Steward 47 (15/17)
- **Signature kit:** **Infinite Conduit** (FP and STM refund each other) · **Saber Cyclone** · **Last Stand of the Light** (prevents one lethal hit per ally) · Guardian Ward IV · Harmonic Restoration · Force Convergence · Purifying Wave · Emergency Triage
- **Fights like:** He keeps both resource pools above 70% for the Infinite Conduit +20 damage window. He weaves Guardian Ward and Emergency Triage between Tempest areas, and holds Last Stand of the Light for the party's worst moment.
- **Counterplay:** Drain his resources, because his whole rotation depends on FP and STM staying high. Bait Last Stand of the Light first, then commit. Mind and disruption pressure counters him, but his Force User resistance package has +17 Mind.
- **NPC:** L58 · Elite · Support · Force User
  - HP 2857 · STM 121 · FP **151** · DMG 77 · Atk 22 · FAtk 25 · Ev 12 · Def 72 · FDef 46 · Delay 300
  - Package: Iron Carapace, Chitin Guard, Savage Roar, ⇄ **Force Sunder** (replaces Tactical Mark)

#### 5. Vashka Dren, "One Shot"
*Bothan sniper. She sets the killing ground with traps and turrets before anyone knows she's there.*

- **Type:** Standard · **Attributes:** 10 / 27\* / 18 / 10 / 26 / 25
- **Ranks:** Rifle 50 · Espionage 50 · Armor 50 · Devices 50 · First Aid 50 · Piloting 50 · Smithery 50 · Fabrication 50
- **Perks (402/410):** Marksman 60 · Suppression 60 · Infiltrator 60 · Saboteur 60 · Tradecraft 15 · General 32 · Field Engineer 60 · Combat Pharmacology 55
- **Signature kit (4 capstones):** **One Shot** (+50 damage, and after 3s idle +25% crit and ignores 25% Defense) · **Kill Box** · **Ghost Protocol** · **Master Saboteur** (tier-5 traps) · **Killzone Beacon**
- **Fights like:** She plants Razor and Shock traps and a Killzone Beacon on the approach, then opens from stealth with One Shot. Kill Box marks a zone where everyone's hits stack Suppression.
- **Counterplay:** Detection, and an approach that avoids the trapped lane. Her One Shot needs 3 idle seconds, so keep her under pressure. With Glass Cannon HP she dies fast once you reach her.
- **NPC:** L57 · Elite · Ranged · Humanoid · Glass Cannon
  - HP **1716** · STM 134 · FP 33 · DMG **136** · Atk 31 · FAtk 7 · Ev 13 · Def 67 · FDef 39 · Delay 260
  - Package: Tactical Mark, Precision Shot, ⇄ **Suppressing Shot** (replaces Piercing Quills), Grenade Burst

#### 6. Grrakhan the Anvil
*Wookiee pit champion. Katar guard by day, bare-knuckle haymakers by night.*

- **Type:** Standard · **Attributes:** 27\* / 26 / 26 / 13 / 14 / 10
- **Ranks:** Katar 50 · Unarmed 50 · Armor 50 · First Aid 50 · Leadership 50 · Gathering 50 · Smithery 50 · Piloting 50
- **Perks (410/410):** Iron Guard 60 · Scrapper 60 · Brawler 60 · Martial Artist 60 · General 32 · Combat Pharmacology 55 · Vanguard Command 55 · Field Steward 28 (10/17)
- **Signature kit (4 capstones):** **Adamantine Guard** (+25 Guard) · **Scrapheap Lockdown** (5m daze and hamstring) · **Haymaker** (+50) · **Perfect Form** (+75 finisher) · Decisive Command · Iron Wall Stance
- **Fights like:** In katars, he is a guard-tank with Iron Wall Stance and Adamantine Guard, locking packs down with Scrapheap Lockdown. He swaps to fists to finish, using Perfect Form or Haymaker on dazed targets.
- **Counterplay:** Use Force or elemental damage, because Guard only reduces the hits it catches. Kite him. Mind resistance shortens his dazes.
- **NPC:** L58 · Elite · Melee · Humanoid · High Durability
  - HP **4210** · STM 191 · FP 33 · DMG 97 · Atk 26 · FAtk 1 · Ev 11 · Def 79 · FDef 49 · Delay 250
  - Package: Pouncing Strike, ⇄ **Brutal Bash** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow

#### 7. Sela Morn, "Rain of Steel"
*Human demolitions engineer. She owns all four Devices styles and both Throwing styles.*

- **Type:** Standard · **Attributes:** 10 / 27\* / 22 / 10 / 26 / 21
- **Ranks:** Devices 50 · Throwing 50 · Armor 50 · Mimicry 30 · Engineering 50 · Fabrication 50 · Piloting 50 · Gathering 50 · Agriculture 20
- **Perks (410/410):** Grenadier 60 · Field Engineer 60 · Field Support 60 · Assault Gadgets 60 · Ordnance 60 · Flurry 60 · General 32 · Mimicry 18 (7/10)
- **Signature kit:** **Thermal Detonator** (+40 vs burning or bleeding) · **Killzone Beacon** · **Emergency Bunker** · **Overload Barrage** · **Rain of Steel** (fragmentation zones) · **Perfect Flurry** (spreads Bleed)
- **Fights like:** She is a zone controller. Killzone Beacon, Rain of Steel zones and Incendiary Field make standing still lethal. Perfect Flurry spreads Bleed, which then powers Thermal Detonator.
- **Counterplay:** Keep moving, since her damage is in fields. Fire and Poison resistance help. Once a melee fighter pins her, her defensive answer is Emergency Bunker, and she loses it if she leaves the bunker.
- **NPC:** L57 · Elite · Controller · Humanoid
  - HP 2494 · STM 104 · FP 134 · DMG 81 · Atk 22 · FAtk 24 · Ev 14 · Def 70 · FDef 46 · Delay 290
  - Package: ⇄ **Grenade Burst** (replaces Sonic Shriek), Disorienting Screech, Tactical Mark, Crippling Talons

#### 8. Corvan Hale, "The Grey Warden"
*Human Force-sensitive warden who swore off both Orders. He fights with a twin blade and a commander's voice.*

- **Type:** Force Sensitive · Affinity **+8 (Light-leaning grey)** · **Attributes:** 27\* / 26 / 24 / 17 / 12 / 10
- **Ranks:** Twin Blade 50 · Force 50 · Armor 50 · First Aid 50 · Leadership 50 · Mimicry 50 · Piloting 50 · Smithery 50
- **Perks (408/410):** Cyclone 60 · Lacerator 60 · Force, Universal plus early Light Control: Alter 29 (9/32: Throw Rock, Force Push, Throw Lightsaber), Control 37 (11/23: Force Leap I–II, Force Convergence, early Light utility), Sense 10 (3/13: Mind Trick, Danger Sense) · General 32 · Trauma Medic 55 · Mimicry 31 · Vanguard Command 55 · Field Steward 39 (13/17)
- **Signature kit:** **Tempest Bloom** · **Red Bloom** (Bleed into Hemorrhage spread) · **Overclocked Analyzer** · **Decisive Command** · Force Leap · Force Push · Emergency Triage
- **Fights like:** Force Leap gets him into the pack. Lacerator stacks Bleed, Red Bloom detonates and spreads it, and Tempest Bloom pulses on every area ability. Decisive Command lifts the whole party's damage.
- **Counterplay:** Trauma resistance shortens his bleeds. Spread out so his areas hit fewer targets. The Hard to Hit modifier (+8 Ev, +4 Def) is offset by lower HP, so ability damage that ignores evasion works well.
- **NPC:** L60 · Elite · Melee · Force User · Hard to Hit
  - HP 2683 · STM 179 · FP 31 · DMG 100 · Atk 28 · FAtk 2 · Ev **21** · Def 79 · FDef 49 · Delay 240
  - Package: Pouncing Strike, ⇄ **Force Sunder** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow

---

### TIER III: ELITES (350–399)

#### 9. Jorik Fenn, "Bloodmane" · 395 SP
*Cathar berserker. A vibroblade in hand and a bandolier of throwing blades.*

- **Type:** Standard · **Attributes:** 27\* / 26 / 24 / 10 / 18 / 10
- **Ranks:** Vibroblade 50 · Armor 50 · First Aid 50 · Leadership 50 · Throwing 50 · Piloting 50 · Smithery 50 · Gathering 45
- **Perks (403/405):** Frenzy 60 · Bulwark 60 · General 32 · Combat Pharmacology 55 · Vanguard Command 55 · Ordnance 60 · Flurry 60 · Field Steward 21 (8/17)
- **Signature kit:** **Blood Frenzy** (+15% Haste, STM on hit) · **Invincible** (−50% physical damage) · Rain of Steel · Perfect Flurry · Decisive Command · Berserker Stance
- **Fights like:** He opens with Perfect Flurry to apply Bleed at range, closes in, and chains Blood Frenzy with Decisive Command. When he gets focused he pops Invincible.
- **Counterplay:** Wait out Invincible (45s) or switch to Force or elemental damage while it's up, because it only blocks physical damage.
- **NPC:** L55 · Elite · Melee · Humanoid · High Damage
  - HP 2371 · STM 166 · FP 29 · DMG **128** · Atk 30 · FAtk 6 · Ev 12 · Def 72 · FDef 42 · Delay 240
  - Package: Pouncing Strike, ⇄ **Serrated Slash** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow

#### 10. Tal Ossiri, "The Null Lance" · 385 SP
*Kel Dor Force-hunter. He exists to make Force users miserable.*

- **Type:** Standard · **Attributes:** 26 / 24\* / 23 / 10 / 21 / 10
- **Ranks:** Spear 50 · Armor 50 · Devices 50 · First Aid 50 · Espionage 50 · Piloting 50 · Engineering 50 · Gathering 35
- **Perks (395/395):** Disabler 60 · Vigor 60 · General 32 · Field Support 60 · Trauma Medic 55 · Field Engineer 60 · Saboteur 60 · Tradecraft 8 (3/5)
- **Signature kit:** **Forcebane** (5m Foggy Mind, Force Disruption, −20% ability accuracy) · **Crippling Defense** · **Master Saboteur** · Killzone Beacon · Emergency Bunker · Weapon Jam · Signal Jammer
- **Fights like:** He traps the approach, opens with Interruption Strike on the caster, then lands Forcebane on the clump. Weapon Jam answers gunners.
- **Counterplay:** Use physical damage, since his toolkit is aimed at casters and ability users. Disarm his traps first.
- **NPC:** L55 · Elite · Controller · Humanoid
  - HP 2371 · STM 101 · FP 130 · DMG 78 · Atk 22 · FAtk 24 · Ev 14 · Def 70 · FDef 46 · Delay 290
  - Package: ⇄ **Brutal Bash** (replaces Sonic Shriek), Disorienting Screech, Tactical Mark, Crippling Talons

#### 11. Nyx Varro, "The Quiet Venom" · 375 SP
*Chiss assassin. She owns every Espionage style and both Vibroknife styles.*

- **Type:** Standard · **Attributes:** 13 / 26 / 18 / 10 / 27\* / 19
- **Ranks:** Vibroknife 50 · Espionage 50 · Armor 50 · First Aid 50 · Throwing 30 · Piloting 50 · Fabrication 50 · Agriculture 45
- **Perks (378/385):** Shadow 60 · Cutthroat 60 · Tradecraft 15 · Infiltrator 60 · Saboteur 60 · General 32 · Combat Pharmacology 55 · Flurry 36 (12/18)
- **Signature kit:** **Viral Cascade** (consumes Venom and Infection) · **Escape Artist** (blind and invisibility) · **Ghost Protocol** · **Master Saboteur** (+10% Venom damage) · Assassin's Stance
- **Fights like:** She opens from stealth with Ghost Protocol for a guaranteed-crit back attack and Exposed, stacks poison, then cashes out with Viral Cascade. Escape Artist is her exit.
- **Counterplay:** Poison resistance and detection. With Glass Cannon HP, she dies once she's pinned.
- **NPC:** L54 · Elite · Melee · Humanoid · Glass Cannon
  - HP **1767** · STM 147 · FP 25 · DMG **136** · Atk 30 · FAtk 7 · Ev 9 · Def 68 · FDef 38 · Delay 240
  - Package: Pouncing Strike, ⇄ **Toxic Spit** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow

#### 12. Oda Rhen & "Gutter" · 360 SP
*Rodian tracker with a scarred beast companion. One pins the target, the other shoots it.*

- **Type:** Standard · **Attributes:** 10 / 26\* / 20 / 14 / 24 / 18
- **Ranks:** Beast Mastery 50 · Rifle 50 · Armor 50 · First Aid 50 · Leadership 50 · Gathering 50 · Agriculture 50 · Piloting 10
- **Perks (367/370):** Training 42 · Bioengineer 35 · Suppression 60 · Marksman 60 · General 32 · Trauma Medic 55 · Field Steward 55 · Vanguard Command 28 (10/17)
- **Pet:** The beast's own style (Damage, Tank, Balanced and so on) is bought from the beast's points, not Oda's SP. Gutter is suggested as a **Tank** or **Bruiser** beast.
- **Signature kit:** **Kill Box** · **One Shot** · Guarding and Predatory Bond Stances · Revive Beast · **Hold the Line** · Emergency Triage
- **Fights like:** Gutter holds the target while Oda lays down Kill Box. She revives and heals the pet, and Hold the Line covers both of them.
- **Counterplay:** Kill the pet first to split her attention, or dive Oda and let the pet chase.
- **NPC (handler):** L53 · Elite · Ranged · Humanoid
  - HP 2383 · STM 139 · FP 35 · DMG 94 · Atk 25 · FAtk 2 · Ev 14 · Def 70 · FDef 42 · Delay 270
  - Package: Tactical Mark, Precision Shot, ⇄ **Suppressing Shot** (replaces Piercing Quills), Grenade Burst
- **NPC (Gutter):** L53 · Tough · Melee · Beast
  - HP 1706 · STM 128 · DMG 93 · Atk 24 · Ev 10 · Def 71 · FDef 41 · Delay 250
  - Package: Pouncing Strike, Rending Bite, Tail Sweep

---

### TIER II: VETERANS (300–349)

#### 13. Mirek Sabo, "The Spinning Edge" · 345 SP
*Echani twin-blade dancer with a wrist rocket for anyone who backs off.*

- **Type:** Standard · **Attributes:** 26 / 25 / 20 / 10 / 18 / 10 (no racial)
- **Ranks:** Twin Blade 50 · Armor 50 · First Aid 50 · Leadership 50 · Devices 50 · Piloting 50 · Smithery 45
- **Perks (355/355):** Cyclone 60 · Lacerator 60 · General 32 · Combat Pharmacology 55 · Vanguard Command 55 · Assault Gadgets 60 · Grenadier 33 (10/16)
- **Signature kit:** Tempest Bloom · Red Bloom · **Overload Barrage** · Decisive Command · Emergency Cocktail
- **NPC:** L52 · Tough · Melee · Humanoid
  - HP 1661 · STM 126 · DMG 91 · Atk 24 · Ev 10 · Def 71 · FDef 41 · Delay 250
  - Package: Pouncing Strike, ⇄ **Serrated Slash** (replaces Rending Bite), Tail Sweep

#### 14. Ysolde Crane, "Doc" · 330 SP
*Republic field surgeon. She owns both First Aid styles and carries a blaster.*

- **Type:** Standard · **Attributes:** 10 / 22 / 22 / 27\* / 14 / 14
- **Ranks:** First Aid 50 · Pistol 50 · Armor 50 · Devices 50 · Leadership 50 · Agriculture 50 · Engineering 30
- **Perks (340/340):** Trauma Medic 55 · Combat Pharmacology 55 · Skirmisher 60 · General 32 · Field Support 60 · Field Steward 55 · Gambler 23 (9/18)
- **Signature kit:** **Emergency Triage** (doubled under 35% HP) · Resuscitation · **Emergency Cocktail** · **Emergency Bunker** · **Hold the Line** · **Last Word**
- **Fights like:** She keeps the group alive under Emergency Bunker and Hold the Line, and uses Last Word to stay mobile.
- **Counterplay:** Focus her first, because every heal she lands undoes your work. Use interrupts.
- **NPC:** L51 · Tough · Support · Humanoid
  - HP 1536 · STM 86 · FP 108 · DMG 64 · Atk 18 · FAtk 21 · Ev 10 · Def 68 · FDef 42 · Delay 310
  - Package: Iron Carapace, ⇄ **Precision Shot** (replaces Savage Roar), Tactical Mark

#### 15. Garr Tevik, "The Unmoving" · 315 SP
*Trandoshan staff sentinel who won't be knocked down.*

- **Type:** Standard · **Attributes:** 25 / 20 / 27\* / 15 / 10 / 10
- **Ranks:** Staff 50 · Armor 50 · First Aid 50 · Leadership 50 · Mimicry 50 · Gathering 50 · Smithery 15
- **Perks (325/325):** Sentinel 60 · Crusher 60 · General 32 · Trauma Medic 55 · Field Steward 55 · Mimicry 31 · Vanguard Command 32 (11/17)
- **Signature kit:** **Unmoving Center** (immune to knockdown and daze, +20 melee deflection) · **Worldbreaker** (+40 against controlled targets) · Shelter Circle · Hold the Line · Overclocked Analyzer
- **Counterplay:** Ranged and Force damage get past his melee deflection.
- **NPC:** L51 · Tough · Tank · Humanoid · High Durability
  - HP **3056** · STM 124 · FP 42 · DMG 65 · Atk 19 · Ev 7 · Def 79 · FDef 48 · Delay 350
  - Package: Iron Carapace, Chitin Guard, ⇄ **Brutal Bash** (replaces Rending Bite)

#### 16. Liss Varan, "The Pale Whisper" · 300 SP
*Human dark-side adept. Her lightsaber is only a backup.*

- **Type:** Force Sensitive · Affinity **−10 (Dark)** · **Attributes:** 14 / 20 / 18 / 27\* / 16 / 11
- **Ranks:** Force 50 · Lightsaber 30 · Armor 50 · First Aid 50 · Mimicry 50 · Piloting 50 · Agriculture 20
- **Perks (309/310):** Force, Dark + Universal: Alter 85 (26/32), Control 27 (7/23), Sense 29 (8/13) · Severance 36 (12/18) · Ward 14 (6/18) · General 32 · Combat Pharmacology 55 · Mimicry 31
- **Signature kit:** Force Lightning III · Force Choke IV · Force Drain III · Creeping Terror III · **Hunger of the Dark** · **Eclipse of Resolve** · Nightmare Field · Imbuement Stance
- **Counterplay:** Force Defense and WIL. Close the distance and interrupt her casts.
- **NPC:** L50 · Tough · Force · Force User
  - HP 1337 · STM 48 · FP **132** · DMG 80 · Atk 18 · FAtk 24 · Ev 11 · Def 67 · FDef 45 · Delay 300
  - Package: Force Rend, Mind Spike, ⇄ **Chain Lightning** (replaces Dark Shock)

---

### TIER I: CONTENDERS (250–299)

#### 17. Dax Morrow, "Two-Draw" · 290 SP
*Corellian twin-blaster skirmisher. Both twin-pistol trees, with gadgets and stealth half-built.*

- **Type:** Standard · **Attributes:** 10 / 24 / 18 / 10 / 27\* / 16
- **Ranks:** Twin Pistol 50 · Armor 50 · Espionage 40 · First Aid 40 · Devices 40 · Piloting 50 · Fabrication 20
- **Perks (300/300):** Crossfire 60 · Barrage 60 · General 32 · Infiltrator 42 (14/18) · Combat Pharmacology 39 (13/17) · Assault Gadgets 41 (17/22) · Field Support 26 (8/15)
- **Signature kit:** **Twin Suns** · **Final Salvo** · Akimbo Stance · Dual Wield III · Wrist Rocket and Flamethrower
- **NPC:** L50 · Tough · Ranged · Humanoid
  - HP 1416 · STM 106 · DMG 84 · Atk 23 · Ev 13 · Def 68 · FDef 40 · Delay 280
  - Package: Suppressing Shot, Precision Shot, Tactical Mark (no swap)

#### 18. Kira Solune, "Needle" · 275 SP
*Togruta blade-thrower. She bleeds a target from range, then knifes it up close.*

- **Type:** Standard · **Attributes:** 10 / 25 / 17 / 10 / 27\* / 14
- **Ranks:** Throwing 50 · Vibroknife 40 · Armor 40 · Espionage 40 · First Aid 30 · Agriculture 50 · Piloting 25
- **Perks (284/285):** Flurry 60 · Ordnance 60 · Cutthroat 50 (16/18) · General 32 · Infiltrator 42 (14/18) · Combat Pharmacology 29 (10/17) · Tradecraft 11 (4/5)
- **Signature kit:** **Perfect Flurry** · **Rain of Steel** · Shadowflow · Backstab
- **NPC:** L49 · Tough · Ranged · Humanoid
  - HP 1377 · STM 104 · DMG 82 · Atk 23 · Ev 12 · Def 63 · FDef 38 · Delay 280
  - Package: Suppressing Shot, Precision Shot, ⇄ **Toxic Spit** (replaces Tactical Mark)

#### 19. Bannoc Rusk, "Soulburner" · 260 SP
*Outer Rim berserker who spends his own HP to hit harder.*

- **Type:** Standard · **Attributes:** 27\* / 20 / 23 / 10 / 12 / 10
- **Ranks:** Heavy Vibroblade 50 · Armor 50 · First Aid 40 · Leadership 40 · Mimicry 40 · Gathering 40
- **Perks (270/270):** Berserker 60 · Immortal 60 · General 32 · Trauma Medic 39 (13/17) · Vanguard Command 39 (13/17) · Mimicry 22 (8/10) · Combat Pharmacology 18 (7/17)
- **Signature kit:** **Soul Ascension** (+20% Attack, lifesteal) · **Absolute Defense** · Soul Devourer Stance · Soul Storm
- **NPC:** L48 · Tough · Melee · Humanoid · High Damage
  - HP 1264 · STM 117 · DMG **106** · Atk 26 · Ev 9 · Def 58 · FDef 34 · Delay 250
  - Package: Pouncing Strike, ⇄ **Serrated Slash** (replaces Rending Bite), Tail Sweep

#### 20. Captain Teyla Arn, "The Officer" · 250 SP
*Republic squad captain. She's the weakest fighter on the roster, but she makes everyone around her better.*

- **Type:** Standard · **Attributes:** 10 / 24 / 18 / 10 / 22 / 17\*
- **Ranks:** Leadership 50 · Rifle 50 · Armor 50 · First Aid 40 · Piloting 50 · Engineering 10
- **Perks (260/260):** Vanguard Command 55 · Field Steward 55 · Suppression 60 · General 32 · Trauma Medic 39 (13/17) · Marksman 19 (8/18)
- **Signature kit:** **Decisive Command** · **Hold the Line** · **Kill Box** · Rousing Shout · Cleanse Order
- **Counterplay:** Kill her first in any group fight, because her buffs carry her squad.
- **NPC:** L48 · Tough · Support · Humanoid
  - HP 1413 · STM 81 · FP 102 · DMG 60 · Atk 17 · FAtk 20 · Ev 9 · Def 57 · FDef 37 · Delay 310
  - Package: Iron Carapace, ⇄ **Suppressing Shot** (replaces Savage Roar), Tactical Mark

---

## 5. Copy-ready NPC stat sheet

All values come from *Enemy Stat Presets* with the *Enemy Modifiers* row applied, matching the World NPC rows. For example, the Korriban Temple Guardian (L70 Elite Controller with High Damage) comes out to exactly HP 2856, DMG 123 and Atk 31 this way. Attributes are the preset's MGT / PER / WIL / VIT / AGI.
Resistances are Fire / Poison / Electrical / Ice / Mind / Mobility / Trauma / Disruption.

| # | Name | Lvl | Diff | Role | Type | Modifier | MGT/PER/WIL/VIT/AGI | HP | STM | FP | DMG | Atk | FAtk | Ev | Def | FDef | Delay | Resistances |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Kaedra Vosk | 65 | Boss | Melee | Force User | Group Boss | 51/42/30/42/42 | 7878 | 322 | 56 | 228 | 50 | 23 | 14 | 77 | 47 | 240 | 15/14/15/15/19/−10/−15/20 |
| 2 | Torvin Ashgrave | 58 | Elite | Tank | Humanoid | High Durability | 37/37/37/46/26 | 5684 | 175 | 58 | 78 | 23 | 1 | 9 | 83 | 52 | 340 | 14/−5/14/14/−5/14/15/14 |
| 3 | Ressa Kel'dar | 62 | Boss | Ranged | Humanoid | Group Boss | 29/50/29/41/41 | 6619 | 268 | 67 | 208 | 49 | 23 | 16 | 74 | 46 | 260 | 14/−5/14/14/−5/14/15/14 |
| 4 | Ilen Theron | 58 | Elite | Support | Force User | None | 26/37/46/37/26 | 2857 | 121 | 151 | 77 | 22 | 25 | 12 | 72 | 46 | 300 | 13/12/13/13/17/−10/−15/18 |
| 5 | Vashka Dren | 57 | Elite | Ranged | Humanoid | Glass Cannon | 26/45/26/37/37 | 1716 | 134 | 33 | 136 | 31 | 7 | 13 | 67 | 39 | 260 | 10/−5/10/10/−5/10/11/10 |
| 6 | Grrakhan | 58 | Elite | Melee | Humanoid | High Durability | 46/37/26/37/37 | 4210 | 191 | 33 | 97 | 26 | 1 | 11 | 79 | 49 | 250 | 14/−5/14/14/−5/14/15/14 |
| 7 | Sela Morn | 57 | Elite | Controller | Humanoid | None | 26/37/45/26/37 | 2494 | 104 | 134 | 81 | 22 | 24 | 14 | 70 | 46 | 290 | 12/−5/12/12/−5/12/13/12 |
| 8 | Corvan Hale | 60 | Elite | Melee | Force User | Hard to Hit | 47/38/27/38/38 | 2683 | 179 | 31 | 100 | 28 | 2 | 21 | 79 | 49 | 240 | 13/12/13/13/17/−10/−15/18 |
| 9 | Jorik Fenn | 55 | Elite | Melee | Humanoid | High Damage | 45/37/26/37/37 | 2371 | 166 | 29 | 128 | 30 | 6 | 12 | 72 | 42 | 240 | 11/−5/11/11/−5/11/12/11 |
| 10 | Tal Ossiri | 55 | Elite | Controller | Humanoid | None | 26/37/45/26/37 | 2371 | 101 | 130 | 78 | 22 | 24 | 14 | 70 | 46 | 290 | 11/−5/11/11/−5/11/12/11 |
| 11 | Nyx Varro | 54 | Elite | Melee | Humanoid | Glass Cannon | 44/36/25/36/36 | 1767 | 147 | 25 | 136 | 30 | 7 | 9 | 68 | 38 | 240 | 9/−5/9/9/−5/9/10/9 |
| 12 | Oda Rhen | 53 | Elite | Ranged | Humanoid | None | 25/43/25/35/35 | 2383 | 139 | 35 | 94 | 25 | 2 | 14 | 70 | 42 | 270 | 11/−5/11/11/−5/11/12/11 |
| 12b | "Gutter" (pet) | 53 | Tough | Melee | Beast | None | 42/34/24/34/34 | 1706 | 128 | 22 | 93 | 24 | 1 | 10 | 71 | 41 | 250 | −10/12/10/10/−15/13/14/−10 |
| 13 | Mirek Sabo | 52 | Tough | Melee | Humanoid | None | 42/34/24/34/34 | 1661 | 126 | 22 | 91 | 24 | 1 | 10 | 71 | 41 | 250 | 10/−5/10/10/−5/10/11/10 |
| 14 | Ysolde Crane | 51 | Tough | Support | Humanoid | None | 23/33/41/33/23 | 1536 | 86 | 108 | 64 | 18 | 21 | 10 | 68 | 42 | 310 | 10/−5/10/10/−5/10/11/10 |
| 15 | Garr Tevik | 51 | Tough | Tank | Humanoid | High Durability | 33/33/33/41/23 | 3056 | 124 | 42 | 65 | 19 | 0 | 7 | 79 | 48 | 350 | 12/−5/12/12/−5/12/13/12 |
| 16 | Liss Varan | 50 | Tough | Force | Force User | None | 23/33/41/23/33 | 1337 | 48 | 132 | 80 | 18 | 24 | 11 | 67 | 45 | 300 | 11/10/11/11/15/−10/−15/16 |
| 17 | Dax Morrow | 50 | Tough | Ranged | Humanoid | None | 23/41/23/33/33 | 1416 | 106 | 26 | 84 | 23 | 1 | 13 | 68 | 40 | 280 | 10/−5/10/10/−5/10/11/10 |
| 18 | Kira Solune | 49 | Tough | Ranged | Humanoid | None | 23/40/23/33/33 | 1377 | 104 | 26 | 82 | 23 | 1 | 12 | 63 | 38 | 280 | 9/−5/9/9/−5/9/10/9 |
| 19 | Bannoc Rusk | 48 | Tough | Melee | Humanoid | High Damage | 39/32/22/32/32 | 1264 | 117 | 20 | 106 | 26 | 5 | 9 | 58 | 34 | 250 | 9/−5/9/9/−5/9/10/9 |
| 20 | Teyla Arn | 48 | Tough | Support | Humanoid | None | 22/32/39/32/22 | 1413 | 81 | 102 | 60 | 17 | 20 | 9 | 57 | 37 | 310 | 9/−5/9/9/−5/9/10/9 |

**Delay:** the values above are preset delays. If the UTC gets a real weapon, the Bible's World NPC rule says the weapon's delay wins (down to 220).

---

## 6. Suggested uses

- **The Ladder (solo, 1v1).** Run from #20 up to #9 in order. To keep Tier III fair for one player, drop each Elite one step to Tough at the same level. The Bible's Encounter Composition treats Elite as party content.
- **Gauntlet trios (3–4 players).** Pair a frontliner, a damage dealer and a support:
  - Torvin + Vashka + Ilen
  - Grrakhan + Nyx + Ysolde
  - Garr + Dax + Teyla
- **Champion nights (2–4 players).** Run Kaedra (L65) or Ressa (L62) alone, or one of them with a Tier IV add. Both use **Group Boss**, which the Bible defines as "party bosses without premium loot tables". Swap to *Loot Boss* only for a fight that drops premium rewards.
- **Merit content.** Every roster NPC is level 48 or higher, and the 400 SP ones are all level 57 or higher, so the Tier IV fighters are valid Merit LP sources for capped players.

---

## 7. Assumptions and open decisions

1. **Gear isn't modeled.** The player builds assume at-level crafted gear. The NPC lines already include the Bible's endgame equipment defense term.
2. **Resistance modifier adjustment:** the *Resistance Adj* (High Durability +2, Glass Cannon −2) was added only to the non-negative resistance entries. Fixed weaknesses stay pinned, as the Formula Source specifies for creature-type weaknesses. Confirm that's how you want the modifier applied.
3. **NPC ability names are creature-flavored.** "Bonecrusher Bite" on a Sith duelist comes from the standard package plus one approved swap. Existing World NPCs such as the Korriban Temple Council Guardian use custom *Existing Abilities* lists instead. If you want humanoid-flavored kits (Serrated Slash, Brutal Bash, Tactical Mark, Force Sunder and so on) beyond the one-swap rule, that needs a design exception, per Builder Checklist step 5.
4. **Two stances per tree.** Several fighters own both stances of a tree (for example Kaedra's Imbuement and Immovable). Only one is meant to be active at a time. The second covers a different situation; it isn't extra power.
5. **Corvan Hale is grey in story but +8 Light by the numbers**, because his early Control utility perks are Light-aligned. For true grey (near 0), swap about 10 SP of Light Control perks for Vanguard or Field Steward perks.
6. **Names and characters are original.** No canon characters are used. Species and cultures (Zabrak, Wookiee, Mandalorian clans and so on) are setting flavor.
