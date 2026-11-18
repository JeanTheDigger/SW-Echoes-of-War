# Combatant Roster: 20 Fighters, 250/400 to 400/400 SP

**Version 2.** All fighters have new names, every fighter now has a full stat sheet and a complete equipment loadout, and two build mistakes from v1 are fixed (see *What changed* at the end).

Twenty original combatants for Echoes of War, from 250/400 to 400/400 SP, weighted toward the cap. **Eight are at exactly 400/400, and twelve are at 360 SP or more.**

Each fighter has three parts:
1. **A build a player could actually make.** Attributes, skill ranks and every perk, checked against the live rules.
2. **Gear.** All 10 equipped slots plus weapon swaps, every item a real item from the Design Bible, with its item ID, where it comes from, and the enhancements to craft into it. The stats shown include that gear.
3. **A ready-made NPC version** in the Bible's Enemy Builder Guide format, for spawning the fighter as an enemy.

---

## 1. How every number is calculated

All formulas below come from the server code (`Stat.cs`, `Native/VitalityHitPoints.cs`) or the Design Bible. Nothing is estimated.

| Stat | Formula |
|---|---|
| **Max HP** | 70 + **20 × (VIT − 10)** + gear HP (+ food). Players are NWN level 40, so each VIT modifier point adds 40 HP, and odd VIT scores get the half-step. |
| **Max STM** | 10 + ⌊1.5 × MGT⌋ + gear STM |
| **Max FP** (Force only) | 10 + 3 × WIL + gear FP |
| **Attack** (weapon) | 8 + 2 × weapon rank + damage stat + gear Attack. Damage stat is **MGT for melee** and **PER for ranged**. |
| **Accuracy** | 8 + 2 × weapon rank + accuracy stat + weapon Accuracy. Accuracy stat is **PER for melee** and **AGI for ranged**. |
| **Force Attack** | 8 + 2 × Force rank + WIL + gear Force Attack |
| **Evasion** | 8 + 2 × Armor rank + AGI + gear Evasion |
| **Physical Defense** | 8 + ⌊1.2 × Armor rank⌋ + VIT + gear Defense |
| **Force Defense** | 8 + ⌊1.2 × Armor rank⌋ + WIL + gear Force Defense |
| **Combat Readiness** | Sum of gear Combat Readiness, capped at **15%**. It boosts activated ability damage and healing. |
| **Regen per 30s** | HP: VIT + bonuses · FP: 1 + gear + ⌊WIL/4⌋ · STM: 10 + gear + ⌊MGT/4⌋ |

**Build rules:** 1 SP per skill rank, capped at 400, plus 10 starting SP (410 to spend at cap) · 1 AP per 10 SP · every attribute starts at 10, plus 15 creation points (max +6 each), plus AP, with a purchase cap of 26 and one racial +1 to 27 · rank 50 cap per skill · Lightsaber, Saberstaff and Force are Force Sensitive only, Devices and Espionage are Standard only.

> **Practical limit at 400/400:** the attribute total is 116, so a capped character can have at most **three** attributes at 26–27. The third or fourth priority always lands somewhere in the high teens.

---

## 2. How the gear works

- **Top crafted tier (Smithery, L50 gear made from L52 recipes, 2 enhancement slots each):**
  - **Chaos** is the heavy physical set. Breastplate: Def 28 · FDef 23 · HP 95.
  - **Immortal** is the stamina set.
  - **Magus** is the Force set. Tunic: FDef 28 · FP 14 · FP regen 5.
  - **Chiro** is the weapon line, plus the Chiro Lightsaber and Saberstaff Upgrade Kits.
- **Enhancements stack freely.** There's no per-stat limit in code, so a Chaos piece with two **Attack V** gives +10 Attack, and one with two **Synthmesh V** gives +80 HP. That's why crafted gear forms the backbone of most loadouts.
- **Each capstone has a themed L45 loot set** of 10–13 pieces, from a specific zone. For example, `deadhand_*` drops on Tatooine and `absdef_*` on Korriban. "w" pieces are the rarer warden/boss drops. Every set follows the same template:
  - +20 Attack weapon
  - 103 HP body armor
  - +12 Attack vambrace and gloves
  - +8 Evasion helm and boots
  - a ring with +12 Attack, +12 Force Attack or +8 Evasion

  The sets have **no set bonus**, so they're stat options, not set pieces. Their value is the +20 Attack weapons and the +12 rings, which crafting can't match.
- **Requirements:** L45 loot armor needs Armor 45, Chaos/Magus/Immortal need Armor 50, and weapons need that weapon skill at the item's level. Every item below is checked against its wearer's ranks.
- **Arms slot:** bracers and gloves share it, so you wear one or the other.
- **Power Gloves (Unarmed)** occupy both hands, and **their stats count once per hand**, so enhancements on one count double.
- **Lightsabers** aren't loot anymore. The old L45 sabers were retired into vambraces. Everyone gets a custom **Lightsaber** at start and upgrades it with Engineering kits I–V, then the **Chiro Lightsaber Upgrade Kit** (24 DMG, needs Lightsaber 50). Saberstaffs work the same way with the Saberstaff kits.
- **Enhancement key:** Attack V = *Armor Enhancement – Attack V* · Synthmesh V = +40 HP · Synthcloth V = +5 Combat Readiness · Scintathread V = +5 Evasion · Gemweb V = +5 Force Defense · Elastex V = +5 Defense · Synthatex V = +6 FP · Force Attack V = *Armor Enhancement – Force Attack V* · on weapons: Attack Bonus V = +5 Attack, Accuracy V = +5, Force Damage III = +3 Force DMG.

---

## 3. Roster at a glance

All stats are with full gear.

| # | Name | Species | Tier | SP | Role | HP | Attack | Accuracy | Evasion | Def / FDef |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Iskari Bel** ★ | Zabrak | IV | 400 | Sith lightsaber duelist | 723 | 182 | 134 | 126 | 235 / 199 |
| 2 | **Kadd Orvaak** | Human (Mandalorian clan) | IV | 400 | Heavy-blade bastion tank | 1373 | 154 | 125 | 118 | 268 / 228 |
| 3 | **Tal'ri Venno** ★ | Twi'lek | IV | 400 | Gunslinger | 735 | 198 | 135 | 182 | 225 / 179 |
| 4 | **Oyen Duur** | Mirialan | IV | 400 | Light-side saberstaff warden and healer | 863 | 140 | 130 | 122 | 211 / 253 |
| 5 | **Asra Dhel'ka** | Bothan | IV | 400 | Sniper and saboteur | 734 | 217 | 134 | 158 | 237 / 189 |
| 6 | **Ruuchakk** | Wookiee | IV | 400 | Katar guard and bare-knuckle finisher | 1087 | 199 | 134 | 122 | 250 / 201 |
| 7 | **Mags Tolver** | Human | IV | 400 | Demolitions engineer | 922 | 187 | 134 | 150 | 243 / 192 |
| 8 | **Ivo Carrick** | Human | IV | 400 | Grey twin-blade warden | 803 | 216 | 134 | 145 | 243 / 201 |
| 9 | **Rhakar** | Cathar | III | 395 | Vibroblade berserker | 847 | 212 | 134 | 134 | 248 / 198 |
| 10 | **Dun Kehl** | Kel Dor | III | 385 | Force-hunter lancer | 870 | 176 | 132 | 129 | 251 / 221 |
| 11 | **Sevral** | Chiss | III | 375 | Poison assassin | 584 | 226 | 135 | 135 | 241 / 199 |
| 12 | **Neela Ghoss & "Gutter"** | Rodian | III | 360 | Beast-handler marksman | 595 | 188 | 132 | 156 | 216 / 180 |
| 13 | **Yuraan Sel** | Echani | II | 345 | Twin-blade whirlwind | 633 | 211 | 133 | 136 | 241 / 197 |
| 14 | **Hollis Breck** | Human | II | 330 | Combat medic | 633 | 162 | 122 | 138 | 223 / 197 |
| 15 | **Vaadosk** | Trandoshan | II | 315 | Staff sentinel tank | 1413 | 153 | 128 | 118 | 268 / 212 |
| 16 | **Ondra Pell** | Human | II | 300 | Dark Force adept | 405 | 82 | 88 | 124 | 199 / 259 |
| 17 | **Jory Fass** | Human (Corellian) | I | 290 | Twin-blaster skirmisher | 768 | 179 | 140 | 168 | 232 / 185 |
| 18 | **Raana Tiv** | Togruta | I | 275 | Blade-thrower | 674 | 195 | 135 | 164 | 232 / 189 |
| 19 | **Goss Durrant** | Human | I | 260 | Soul-burner berserker | 759 | 219 | 128 | 128 | 240 / 194 |
| 20 | **Captain Jeyra Okonn** | Human | I | 250 | Squad officer | 553 | 162 | 122 | 146 | 216 / 178 |

★ = champion, built as a Group Boss for 2–4 players. Attack and Accuracy are for the main-hand weapon. Force users' Force Attack is on their dossier.

---

## 4. Fighter dossiers


### TIER IV: THE CAPPED EIGHT (400/400)

---

#### 1. Iskari Bel  ★ Champion
*Zabrak · Sith lightsaber duelist · Force Sensitive · **400/400 SP** (408/410 spent) · 40 AP · Affinity **-10** (Dark)*

A Zabrak Sith who duels with a single blade and an empty off hand. She closes the gap, Sunders the target, then knocks down the whole group.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 27* | 26 | 23 | 20 | 10 | 10 |

\* racial +1. 

**Skill ranks:** Lightsaber 50 · Force 50 · Armor 50 · First Aid 50 · Mimicry 50 · Leadership 50 · Piloting 50 · Smithery 50

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 330 | **723** | Max STM | **50** |
| Attack (Lightsaber) | 135 | **182** | Accuracy (Lightsaber) | **134** |
| Evasion | 118 | **126** | Weapon DMG / delay | **24** / 240 |
| Physical Defense | 91 | **235** | Combat Readiness | **4%** |
| Force Defense | 88 | **199** | Regen / 30s (HP · STM · FP) | 23 · 18 · 6 |
| Max FP | — | **70** | Force Attack | **152** |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Lightsaber · Severance | 60 | all | Force Sheath IV, Overpower III, Fast Strikes, Shattering Strike II, Sundering Sweep III, Weak Points, Imbuement Stance, High Ground, Focus Shift, Epicenter |
| Lightsaber · Ward | 60 | all | Saber Ward IV, Mental Fortress II, Deflecting Return III, Guardian's Challenge II, Surrounded, Not Outmatched, Force Link, Immovable Stance, Reprisal II, Center of the Storm, Aegis Eternal |
| Force · Alter | 85 | 26/32 | Force Spark II, Throw Rock III, Creeping Terror III, Force Push III, Force Choke IV, Throw Lightsaber III, Force Lightning III, Force Drain III, Devouring Strike, Unstable Pressure |
| Force · Control | 27 | 7/23 | Force Leap II, Fury Stance II, Cruel Momentum, Force Convergence, Hunger of the Dark |
| Force · Sense | 29 | 8/13 | Weaken Resolve II, Mind Trick II, Nightmare Field, Danger Sense, Collapse Will, Eclipse of Resolve |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Mimicry · Mimicry | 25 | 9/10 | Combat Analyzer IV, Analyzer Memory III, Pattern Recognition II |
| Leadership · Vanguard Command | 35 | 12/17 | Rallying Standard II, Press the Attack II, Coordinated Focus II, Mark Target II, Charge Order II, Break Morale I, Command Presence I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Lightsaber (custom) + Chiro Lightsaber Upgrade Kit | `—` | Starting grant, upgraded with Engineering kits I–V then Chiro | DMG 24 · Delay 240 | — |
| Head | Shadow Sepulcher Mask | `darkhung_w5` | Loot: Korriban | Def +17 · FDef +11 · HP +64 · Ev +8 | — |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Bonecarved Vambrace | `darkhung_w3` | Loot: Korriban | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Attack V + Improved Synthmesh V |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Attack V |
| Neck | Adrenal Pendant | `adren_pendant` | Loot: Viscara | Def +13 · FDef +11 · HP +11 · CR +4 | — |
| Ring | Darkened Bone Band | `darkhung_l6` | Loot: Korriban | FAtk +12 · Def +9 · FDef +8 · HP +7 | — |
| Ring | Eclipse-Bound Band | `eclipse_l6` | Loot: Korriban | FAtk +12 · Def +9 · FDef +8 · HP +7 | — |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Weapon swaps and situational gear**

- **Chiro Electroblade** (`chi_electroblade`, Crafted (Smithery, L50 recipe)): DMG 24 · Delay 240 · enhancements: Attack Bonus V + Force Damage III. Crafted fallback if the custom saber is not yet Chiro-tier.

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** She opens with Force Sheath and Shattering Strike to apply Sunder, spreads it with Sundering Sweep, then drops Epicenter when three or more enemies are Sundered. Imbuement Stance turns her swings into Force damage, so her two +12 Force Attack rings pay off on auto-attacks as well as powers. Under focus fire she switches to Aegis Eternal, and Hunger of the Dark heals her off the Dark damage.

**How to beat them:** Spread out, because Epicenter and the Sunder spread both depend on clumped targets. Bait Aegis Eternal (90s cooldown) before you burst her. She has only 50 STM, so drain it and her weapon abilities stop.

**As an NPC:** L65 · Boss · Melee · Force User · Group Boss
- HP 7878 · STM 322 · FP 56 · DMG 228 · Attack 50 · Force Attack 23 · Evasion 14 · Defense 77 · Force Defense 47 · Delay 240
- Attributes (MGT/PER/WIL/VIT/AGI) 51/42/30/42/42 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 15/14/15/15/19/-10/-15/20
- Abilities: ⇄ **Force Rend** (replaces Mauling Bite), Bonecrusher Bite, Tail Sweep, Terrifying Bellow, Chitin Guard, Rupturing Quake

---

#### 2. Kadd Orvaak
*Human (Mandalorian clan) · Heavy-blade bastion tank · Standard · **400/400 SP** (410/410 spent) · 40 AP*

A clan veteran who wears nothing but Chaos plate stuffed with Synthmesh. He holds the line and keeps his group alive while he does it.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 26 | 17 | 27* | 26 | 10 | 10 |

\* racial +1. 

**Skill ranks:** Heavy Vibroblade 50 · Armor 50 · First Aid 50 · Leadership 50 · Devices 50 · Piloting 50 · Smithery 50 · Gathering 50

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 410 | **1373** | Max STM | **49** |
| Attack (Heavy Vibroblade) | 134 | **154** | Accuracy (Heavy Vibroblade) | **125** |
| Evasion | 118 | **118** | Weapon DMG / delay | **44** / 300 |
| Physical Defense | 95 | **268** | Combat Readiness | **0%** |
| Force Defense | 94 | **228** | Regen / 30s (HP · STM) | 27 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Heavy Vibroblade · Immortal | 60 | all | Fortress Strike III, Anger Strike, Crushing Blow, Flash, Defensive Harmony, Earthshatter II, Bastion Stance, Last Stand, Guardian's Resolve, Rampart, Critical Ward, Unbreakable Will, Blood Weapon, Guardian's Reaping, Absolute Defense |
| Heavy Vibroblade · Berserker | 60 | all | Soul Strike III, Essence Tap, Essence Hunter, Sacrificial Blade, Life Siphon, Soul Burst, Soul Devourer Stance, Vampiric Fury, Soul Amplification, Soul Storm, Blazing Spikes, Soul Sacrifice, Soul Barrier, Bloodlust, Soul Reaping, Soul Ascension |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Trauma Medic | 55 | all | Med Kit IV, Treatment Kit III, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion II, Emergency Triage |
| Leadership · Field Steward | 55 | all | Watchful Presence III, Rousing Shout III, Steady Formation II, Bolster Resolve II, Field Recovery II, Cleanse Order II, Triage Protocol II, Hold the Line |
| Devices · Field Support | 60 | all | Deflector Shield III, Power Cell III, Weapon Jam, Power Surge, Rayshield Screen II, Dampening Field II, Overclock Routine, Group Deflector, Emergency Bunker |
| Devices · Grenadier | 60 | all | Frag Grenade III, Blast Radius III, Concussion Grenade II, Flash Grenade, Ion Grenade II, Adhesive Grenade II, Cluster Grenade, Disruption Pulse, Thermal Detonator |
| Leadership · Vanguard Command | 28 | 10/17 | Rallying Standard II, Press the Attack II, Coordinated Focus II, Mark Target I, Charge Order I, Break Morale I, Command Presence I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Anvilbreaker Cleaver | `absdef_w1` | Loot: Korriban | DMG 44 · Delay 300 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Improved Synthmesh V + Improved Synthmesh V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Improved Synthmesh V + Improved Synthmesh V |
| Arms | Chaos Bracer | `ch_bracer` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Synthmesh V + Improved Elastex V |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Synthmesh V + Improved Synthmesh V |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Synthmesh V + Improved Gemweb V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Improved Synthmesh V + Improved Synthmesh V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Synthmesh V + Improved Synthmesh V |
| Ring | Ember-Set Band | `absdef_l6` | Loot: Korriban | Def +14 · FDef +12 · HP +11 | — |
| Ring | Chaos Ring | `ch_ring` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Synthmesh V + Improved Synthmesh V |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **HP V + HP Regen V**.

**How they fight:** Provoke II pulls the group onto him and Bastion Stance holds it. When allies get pressured he layers Absolute Defense, Hold the Line and Emergency Bunker. A Thermal Detonator goes onto anything that clumps around him.

**How to beat them:** Ignore him and kill his support. His defensive cooldowns are 45-second windows, so wait them out. His Force Defense (228) is his lowest defense, so Force damage is the way through.

**As an NPC:** L58 · Elite · Tank · Humanoid · High Durability
- HP 5684 · STM 175 · FP 58 · DMG 78 · Attack 23 · Force Attack 1 · Evasion 9 · Defense 83 · Force Defense 52 · Delay 340
- Attributes (MGT/PER/WIL/VIT/AGI) 37/37/37/46/26 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 14/-5/14/14/-5/14/15/14
- Abilities: Iron Carapace, Chitin Guard, ⇄ **Brutal Bash** (replaces Bonecrusher Bite), Tail Sweep

---

#### 3. Tal'ri Venno  ★ Champion
*Twi'lek · Gunslinger · Standard · **400/400 SP** (408/410 spent) · 40 AP*

A Twi'lek duelist who owns both pistol trees and both twin-pistol trees. She vanishes when cornered.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 26 | 26 | 10 | 27* | 17 |

\* racial +1. 

**Skill ranks:** Pistol 50 · Twin Pistol 50 · Armor 50 · Espionage 50 · First Aid 50 · Mimicry 50 · Piloting 50 · Engineering 50

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 390 | **735** | Max STM | **33** |
| Attack (Pistol) | 134 | **198** | Accuracy (Pistol) | **135** |
| Evasion | 135 | **182** | Weapon DMG / delay | **23** / 250 |
| Physical Defense | 94 | **225** | Combat Readiness | **0%** |
| Force Defense | 78 | **179** | Regen / 30s (HP · STM) | 26 · 14 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Pistol · Gambler | 60 | all | Quick Draw IV, Lucky Chamber, Rapid Shot III, Double Shot III, Deadeye Reload, Fan the Hammer II, Gambler Stance, High Noon, Reload Tempo, Dead Man's Hand |
| Pistol · Skirmisher | 60 | all | Disarming Shot IV, Mobile Footwork, Snap Roll III, Interrupting Shot III, Kiting Instinct, Point Blank Burst II, Skirmisher Stance, Duelist's Distance, Evasive Reload, Last Word |
| Twin Pistol · Barrage | 60 | all | Paired Volley IV, Alternating Fire, Matched Rhythm III, Focused Burst III, Balanced Grip, Controlled Burst II, Akimbo Stance, Converging Fire, Cool Under Fire, Twin Suns |
| Twin Pistol · Crossfire | 60 | all | Lead Shot IV, Cadence, Steady Cadence III, Closing Shot III, Changing Angles, Tempo Shot II, Crossfire Stance, Follow Through, Second Wind, Final Salvo |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| Espionage · Infiltrator | 60 | all | Stealth IV, Slicing V, Back Attack III, Tactical Escape II, Shadow Step II, Silent Stride, Ghost Protocol |
| Espionage · Tradecraft | 15 | all | False Identities III, Cover Story II |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Mimicry · Mimicry | 6 | 3/10 | Combat Analyzer I, Analyzer Memory I, Pattern Recognition I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Final Verdict Sidearm | `lastword_w1` | Loot: Tatooine | DMG 23 · Delay 250 · Atk +20 | — |
| Head | Boot Hill Helm | `deadhand_w5` | Loot: Tatooine | Def +17 · FDef +11 · HP +64 · Ev +8 | — |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Gunslinger Rig | `gunsling_rig` | Loot: NarShaddaa | Atk +11 · Def +12 · FDef +8 · HP +46 · Ev +5 | — |
| Feet | Kill Line Boots | `deadhand_l8` | Loot: Tatooine | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Hexweave Shawl | `hexweave` | Loot: NarShaddaa | Atk +8 · Def +12 · FDef +8 · HP +46 · Ev +5 | — |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Attack V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Improved Scintathread V |
| Ring | Cold Trigger Band | `deadhand_l6` | Loot: Tatooine | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Ring | Trigger Finger Band | `lastword_l6` | Loot: Tatooine | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Weapon swaps and situational gear**

- **Chiro Twin Pistols** (`chi_twinpistol`, Crafted (Smithery, L50 recipe)): DMG 23 · Delay 250 · enhancements: Attack Bonus V + Accuracy V. Twin Pistol stance set: Barrage/Crossfire, Twin Suns, Final Salvo.
- **Undertaker's Sidearm** (`deadhand_w1`, Loot: Tatooine): DMG 23 · Delay 250 · Atk +20. Dead Man's Hand crit chain (same +20 Attack, Gambler style).

**Consumables:** L45+ meal with **STM V + STM Regen V** (ranged builds have small STM pools).

**How they fight:** With a single pistol and an empty off hand (Doublehand III, +60% weapon DMG) she runs the Gambler crit chain, then swaps to Chiro Twin Pistols to build Cadence for Final Salvo. Her six Evasion pieces put her at 182 Evasion, the highest on the roster, which keeps Last Word's Snap Roll refreshing. Ghost Protocol is her reset.

**How to beat them:** Keep Detection up for Ghost Protocol. Use abilities that don't roll against Evasion. She has 33 STM, so a long fight starves her rotation.

**As an NPC:** L62 · Boss · Ranged · Humanoid · Group Boss
- HP 6619 · STM 268 · FP 67 · DMG 208 · Attack 49 · Force Attack 23 · Evasion 16 · Defense 74 · Force Defense 46 · Delay 260
- Attributes (MGT/PER/WIL/VIT/AGI) 29/50/29/41/41 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 14/-5/14/14/-5/14/15/14
- Abilities: Tactical Mark, Suppressing Shot, Precision Shot, ⇄ **Grenade Burst** (replaces Piercing Quills), Shrapnel Burst, Overload Shot

---

#### 4. Oyen Duur
*Mirialan · Light-side saberstaff warden and healer · Force Sensitive · **400/400 SP** (403/410 spent) · 40 AP · Affinity **+10** (Light)*

A Jedi warden who is also the group's healer. He runs full Magus with Combat Readiness at the 15% cap, so every heal and strike lands harder.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 20 | 22 | 23 | 27* | 14 | 10 |

\* racial +1. 

**Skill ranks:** Saberstaff 50 · Force 50 · Armor 50 · First Aid 50 · Leadership 50 · Piloting 50 · Agriculture 50 · Engineering 50

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 330 | **863** | Max STM | **40** |
| Attack (Saberstaff) | 128 | **140** | Accuracy (Saberstaff) | **130** |
| Evasion | 122 | **122** | Weapon DMG / delay | **24** / 240 |
| Physical Defense | 91 | **211** | Combat Readiness | **15%** |
| Force Defense | 95 | **253** | Regen / 30s (HP · STM · FP) | 23 · 15 · 19 |
| Max FP | — | **170** | Force Attack | **147** |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Saberstaff · Conduit | 60 | all | Focused Arc IV, Conduit Training, Balanced Current III, Guarded Channel III, Force Lens, Sever Focus II, Conduit Stance, Energized Forms, Balanced Attunement, Infinite Conduit |
| Saberstaff · Tempest | 60 | all | Double Strike IV, Force Momentum, Spinning Deflection III, Circle Slash III, Tempest Focus, Maelstrom Arc II, Tempest Stance, Force Gyre, Flow of the Maelstrom, Saber Cyclone |
| Force · Control | 71 | 19/23 | Benevolence III, Guardian Ward IV, Protective Presence, Renewal III, Force Leap II, Serene Focus, Reflective Barrier, Force Mend, Force Sanctuary, Harmonic Restoration, Force Convergence |
| Force · Alter | 53 | 15/32 | Throw Rock III, Force Push III, Throw Lightsaber III, Radiant Lance III, Force Burst, Purifying Wave, Last Stand of the Light |
| Force · Sense | 25 | 8/13 | Force Judgment III, Mind Trick II, Courageous Resolve, Danger Sense, Force Intercept |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Trauma Medic | 55 | all | Med Kit IV, Treatment Kit III, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion II, Emergency Triage |
| Leadership · Field Steward | 47 | 15/17 | Watchful Presence III, Rousing Shout III, Steady Formation II, Bolster Resolve II, Field Recovery II, Cleanse Order II, Triage Protocol I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Training Saberstaff V + Chiro Saberstaff Upgrade Kit | `—` | Crafted (Smithery), upgraded with Engineering Chiro kit | DMG 24 · Delay 240 | — |
| Head | Magus Cap | `mag_cap` | Crafted (Smithery) | Def +13 · FDef +24 · HP +43 · FP +13 · FP regen +3 | Improved Synthcloth V + Improved Synthmesh V |
| Body | Magus Tunic | `mag_tunic` | Crafted (Smithery) | Def +17 · FDef +28 · HP +50 · FP +14 · FP regen +5 | Improved Synthcloth V + Improved Synthmesh V |
| Arms | Voltage-Forged Vambrace | `infconduit_w3` | Loot: Dantooine | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Magus Boots | `mag_boots` | Crafted (Smithery) | Def +13 · FDef +24 · HP +26 · FP +12 · FP regen +4 | Improved Synthmesh V + Improved Synthatex V |
| Cloak | Magus Cloak | `mag_cloak` | Crafted (Smithery) | Def +13 · FDef +16 · HP +6 · FP +6 | Improved Synthcloth V + Improved Synthmesh V |
| Belt | Magus Belt | `mag_belt` | Crafted (Smithery) | Def +13 · FDef +16 · HP +9 · FP +5 | Improved Synthmesh V + Improved Synthmesh V |
| Neck | Magus Necklace | `mag_necklace` | Crafted (Smithery) | Def +13 · FDef +16 · HP +6 · FP +6 | Improved Synthmesh V + Improved Synthatex V |
| Ring | Conductive Band | `infconduit_l6` | Loot: Dantooine | FAtk +12 · Def +9 · FDef +8 · HP +7 | — |
| Ring | Magus Ring | `mag_ring` | Crafted (Smithery) | Def +13 · FDef +16 · HP +6 · FP +5 | Improved Synthmesh V + Improved Synthatex V |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **FP V + FP Regen V**.

**How they fight:** He keeps FP and STM above 70% to hold Infinite Conduit's +20 damage window, and weaves Guardian Ward IV and Emergency Triage between Tempest areas. Last Stand of the Light is saved for the group's worst moment.

**How to beat them:** Resource drain wins this fight, because his whole kit assumes high FP and STM. Bait Last Stand first. His Physical Defense (211) is much lower than his Force Defense (253), so hit him physically.

**As an NPC:** L58 · Elite · Support · Force User · None
- HP 2857 · STM 121 · FP 151 · DMG 77 · Attack 22 · Force Attack 25 · Evasion 12 · Defense 72 · Force Defense 46 · Delay 300
- Attributes (MGT/PER/WIL/VIT/AGI) 26/37/46/37/26 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 13/12/13/13/17/-10/-15/18
- Abilities: Iron Carapace, Chitin Guard, Savage Roar, ⇄ **Force Sunder** (replaces Tactical Mark)

---

#### 5. Asra Dhel'ka
*Bothan · Sniper and saboteur · Standard · **400/400 SP** (402/410 spent) · 40 AP*

A Bothan marksman who prepares the killing ground with traps and turrets before anyone knows she's there. She is built entirely for Attack.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 27* | 26 | 10 | 26 | 17 |

\* racial +1. 

**Skill ranks:** Rifle 50 · Espionage 50 · Armor 50 · Devices 50 · First Aid 50 · Piloting 50 · Smithery 50 · Fabrication 50

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 390 | **734** | Max STM | **33** |
| Attack (Rifle) | 135 | **217** | Accuracy (Rifle) | **134** |
| Evasion | 134 | **158** | Weapon DMG / delay | **40** / 300 |
| Physical Defense | 94 | **237** | Combat Readiness | **0%** |
| Force Defense | 78 | **189** | Regen / 30s (HP · STM) | 26 · 14 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Rifle · Marksman | 60 | all | Aimed Shot IV, Steady Aim, Patience III, Piercing Round III, Scope Calibration, Headshot II, Sniper Stance, Dead Center, Breach Round, One Shot |
| Rifle · Suppression | 60 | all | Suppressing Shot IV, Pinning Fire, Sustained Fire III, Crippling Shot III, Spotter's Rhythm, Suppressive Line II, Suppression Stance, Overwatch, Containment Net, Kill Box |
| Espionage · Infiltrator | 60 | all | Stealth IV, Slicing V, Back Attack III, Tactical Escape II, Shadow Step II, Silent Stride, Ghost Protocol |
| Espionage · Saboteur | 60 | all | Poisoncraft V, Trapcraft IV, Venom Expertise II, Razor Trap II, Trap Management II, Shock Trap, Lasting Coatings, Master Saboteur |
| Espionage · Tradecraft | 15 | all | False Identities III, Cover Story II |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| Devices · Field Engineer | 60 | all | Blaster Beacon III, Beacon Targeting II, Incendiary Field III, Remote Charge II, Signal Jammer, Shock Beacon II, Diagnostic Sweep, Killzone Beacon |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Oneshot Executioner Rifle | `oneshot_w1` | Loot: NarShaddaa | DMG 40 · Delay 300 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Attack V + Attack V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Sureshot Vambrace | `oneshot_w3` | Loot: NarShaddaa | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Steady Aim Boots | `oneshot_l8` | Loot: NarShaddaa | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Attack V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Ring | Sureshot Band | `oneshot_l6` | Loot: NarShaddaa | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Ring | Target Lock Band | `killbox_l6` | Loot: NarShaddaa | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Weapon swaps and situational gear**

- **Killbox Enforcer Rifle** (`killbox_w1`, Loot: NarShaddaa): DMG 40 · Delay 300 · Atk +20. Suppression rotation: Kill Box, Suppressive Line.

**Consumables:** L45+ meal with **STM V + STM Regen V** (ranged builds have small STM pools).

**How they fight:** She plants Razor and Shock traps and a Killzone Beacon on the approach, opens from stealth with One Shot (217 Attack, +25% crit, ignores 25% Defense after 3 idle seconds), then swaps to the Killbox Enforcer for Kill Box.

**How to beat them:** Detection, and an approach that avoids the trapped lane. Keep pressure on so she never gets her 3 idle seconds. Her 734 HP is low for her tier, so once you reach her she falls fast.

**As an NPC:** L57 · Elite · Ranged · Humanoid · Glass Cannon
- HP 1716 · STM 134 · FP 33 · DMG 136 · Attack 31 · Force Attack 7 · Evasion 13 · Defense 67 · Force Defense 39 · Delay 260
- Attributes (MGT/PER/WIL/VIT/AGI) 26/45/26/37/37 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 10/-5/10/10/-5/10/11/10
- Abilities: Tactical Mark, Precision Shot, ⇄ **Suppressing Shot** (replaces Piercing Quills), Grenade Burst

---

#### 6. Ruuchakk
*Wookiee · Katar guard and bare-knuckle finisher · Standard · **400/400 SP** (410/410 spent) · 40 AP*

A Wookiee pit champion who guards with katars and finishes with his fists.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 27* | 26 | 26 | 13 | 14 | 10 |

\* racial +1. 

**Skill ranks:** Katar 50 · Unarmed 50 · Armor 50 · First Aid 50 · Leadership 50 · Gathering 50 · Smithery 50 · Piloting 50

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 390 | **1087** | Max STM | **50** |
| Attack (Katar) | 135 | **199** | Accuracy (Katar) | **134** |
| Evasion | 122 | **122** | Weapon DMG / delay | **19** / 220 |
| Physical Defense | 94 | **250** | Combat Readiness | **0%** |
| Force Defense | 81 | **201** | Regen / 30s (HP · STM) | 26 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Katar · Iron Guard | 60 | all | Guard Counter III, Iron Guard Training III, Redirecting Counter, Steel Shoulder, Iron Elbows, Whirling Guard, Covering Claws, Guard Reversal, Tag In, Retaliatory Flow, Impenetrable Grip, Iron Wall Stance, Guardian Reflexes, Adamantine Guard |
| Katar · Scrapper | 60 | all | Hooking Strike IV, Guard Training, Scrapper Control III, Joint Lock III, Redirecting Guard, Interrupting Sweep II, Scrapper Stance, Breaker Reversal, Iron Grip, Scrapheap Lockdown |
| Unarmed · Brawler | 60 | all | Dirty Jab IV, Dirty Fighting, Uppercut III, Heavy Blows III, Hard Knocks, Low Kick II, Bruiser Stance, Catch Your Breath, Payback, Haymaker |
| Unarmed · Martial Artist | 60 | all | Jab IV, Flowing Form, Palm Strike III, Practiced Form III, Measured Technique, Finishing Combination II, Flow Stance, Controlled Breathing, Rooted Technique, Perfect Form |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Leadership · Vanguard Command | 55 | all | Rallying Standard II, Press the Attack III, Coordinated Focus III, Mark Target II, Charge Order II, Break Morale II, Command Presence II, Decisive Command |
| Leadership · Field Steward | 28 | 10/17 | Watchful Presence II, Rousing Shout II, Steady Formation II, Bolster Resolve I, Field Recovery I, Cleanse Order I, Triage Protocol I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Breaker Yard Fistblade | `adamguard_w1` | Loot: CZ220 | DMG 19 · Delay 220 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Improved Synthmesh V + Improved Synthmesh V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Improved Synthmesh V |
| Arms | Riveted Salvage Vambrace | `adamguard_w3` | Loot: CZ220 | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Synthmesh V + Attack V |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Improved Synthmesh V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Improved Synthmesh V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Synthmesh V + Improved Synthmesh V |
| Ring | Bent Conduit Band | `adamguard_l6` | Loot: CZ220 | Def +14 · FDef +12 · HP +11 | — |
| Ring | Warped Bolt Ring | `scraplock_l6` | Loot: CZ220 | Atk +12 · Def +9 · FDef +8 · HP +7 | — |
| Off hand | Empty | | | | |

**Weapon swaps and situational gear**

- **Chiro Power Glove** (`chi_pglove`, Crafted (Smithery, L50 recipe)): DMG 19 · Delay 220 · enhancements: Attack Bonus V + Attack Bonus V. Unarmed finisher set: Haymaker / Perfect Form. Power Glove stats count once per hand, so these two enhancements give +20 Attack.
- **Deadbolt Fistpiercer** (`scraplock_w1`, Loot: CZ220): DMG 19 · Delay 220 · Atk +20. Scrapper katar for Scrapheap Lockdown pulls.

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** In katars he is a guard-tank with Iron Wall Stance and Adamantine Guard, and Scrapheap Lockdown dazes and hamstrings groups. He swaps to the Chiro Power Glove (its stats count once per hand) for Haymaker and Perfect Form on dazed targets.

**How to beat them:** Guard only reduces the hits it catches, so Force and elemental damage go around it. Kite him, and use Mind resistance against his dazes.

**As an NPC:** L58 · Elite · Melee · Humanoid · High Durability
- HP 4210 · STM 191 · FP 33 · DMG 97 · Attack 26 · Force Attack 1 · Evasion 11 · Defense 79 · Force Defense 49 · Delay 250
- Attributes (MGT/PER/WIL/VIT/AGI) 46/37/26/37/37 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 14/-5/14/14/-5/14/15/14
- Abilities: Pouncing Strike, ⇄ **Brutal Bash** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow

---

#### 7. Mags Tolver
*Human · Demolitions engineer · Standard · **400/400 SP** (410/410 spent) · 40 AP*

A demolitions specialist who owns all four Devices styles and both Throwing styles, with Combat Readiness at 14% to amplify every gadget.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 27* | 26 | 10 | 26 | 17 |

\* racial +1. 

**Skill ranks:** Devices 50 · Throwing 50 · Armor 50 · Engineering 50 · Fabrication 50 · Piloting 50 · Gathering 50 · Mimicry 30 · Agriculture 20

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 390 | **922** | Max STM | **25** |
| Attack (Throwing) | 135 | **187** | Accuracy (Throwing) | **134** |
| Evasion | 134 | **150** | Weapon DMG / delay | **19** / 220 |
| Physical Defense | 94 | **243** | Combat Readiness | **14%** |
| Force Defense | 78 | **192** | Regen / 30s (HP · STM) | 26 · 14 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Devices · Grenadier | 60 | all | Frag Grenade III, Blast Radius III, Concussion Grenade II, Flash Grenade, Ion Grenade II, Adhesive Grenade II, Cluster Grenade, Disruption Pulse, Thermal Detonator |
| Devices · Field Engineer | 60 | all | Blaster Beacon III, Beacon Targeting II, Incendiary Field III, Remote Charge II, Signal Jammer, Shock Beacon II, Diagnostic Sweep, Killzone Beacon |
| Devices · Field Support | 60 | all | Deflector Shield III, Power Cell III, Weapon Jam, Power Surge, Rayshield Screen II, Dampening Field II, Overclock Routine, Group Deflector, Emergency Bunker |
| Devices · Assault Gadgets | 60 | all | Flamethrower III, Wrist Rocket III, Sonic Burst III, Gadget Harness, Arc Projector III, Ion Lance III, Rail Dart III, Tactical Uplink, Cryo Sprayer, Overload Barrage |
| Throwing · Ordnance | 60 | all | Explosive Toss IV, Payload Pouch, Shrapnel Casing III, Flash Toss III, Cluster Pouch, Concussive Toss II, Ordnance Stance, Saturation Toss, Bombardier's Rhythm, Rain of Steel |
| Throwing · Flurry | 60 | all | Piercing Toss IV, Returning Grip, Flurry Bleed III, Pinning Toss III, Ricochet Toss, Severing Toss II, Flurry Stance, Deep Wound, Bleeding Tempo, Perfect Flurry |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| Mimicry · Mimicry | 18 | 7/10 | Combat Analyzer III, Analyzer Memory II, Pattern Recognition II |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Rainsteel Flechette Blades | `rainsteel_w1` | Loot: NarShaddaa | DMG 19 · Delay 220 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Improved Synthcloth V + Improved Synthcloth V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Improved Synthmesh V |
| Arms | Dart Launcher Vambrace | `rainsteel_w3` | Loot: NarShaddaa | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Synthmesh V + Improved Synthmesh V |
| Cloak | Circle Mantle | `circle_mantle` | Loot: Viscara | Def +13 · FDef +11 · HP +11 · CR +4 | — |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Improved Synthmesh V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Ring | Flechette Band | `rainsteel_l6` | Loot: NarShaddaa | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Ring | Homing Signal Band | `killbeacon_l4` | Loot: Viscara | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Weapon swaps and situational gear**

- **Avalanche Throwing Blades** (`perflurry_w1`, Loot: Hutlar): DMG 19 · Delay 220 · Atk +20. Flurry/Bleed set for Perfect Flurry → Thermal Detonator combo.

**Consumables:** L45+ meal with **STM V + STM Regen V** (ranged builds have small STM pools).

**How they fight:** She is a zone controller. Killzone Beacon, Rain of Steel fragmentation zones and Incendiary Field make standing still fatal. She swaps to Avalanche Throwing Blades to spread Bleed with Perfect Flurry, then hits the bleeding targets with Thermal Detonator for +40.

**How to beat them:** Keep moving, and stack Fire resistance. She has 25 STM (tied with Jory for the lowest on the roster), so pressure her into burning it. Emergency Bunker only protects her while she stays inside it.

**As an NPC:** L57 · Elite · Controller · Humanoid · None
- HP 2494 · STM 104 · FP 134 · DMG 81 · Attack 22 · Force Attack 24 · Evasion 14 · Defense 70 · Force Defense 46 · Delay 290
- Attributes (MGT/PER/WIL/VIT/AGI) 26/37/45/26/37 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 12/-5/12/12/-5/12/13/12
- Abilities: ⇄ **Grenade Burst** (replaces Sonic Shriek), Disorienting Screech, Tactical Mark, Crippling Talons

---

#### 8. Ivo Carrick
*Human · Grey twin-blade warden · Force Sensitive · **400/400 SP** (408/410 spent) · 40 AP · Affinity **+8** (Light)*

A Force-sensitive who walked away from both Orders. He leaps in, bleeds everything nearby, and rallies the group as he goes.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 27* | 26 | 24 | 17 | 12 | 10 |

\* racial +1. 

**Skill ranks:** Twin Blade 50 · Force 50 · Armor 50 · First Aid 50 · Leadership 50 · Mimicry 50 · Piloting 50 · Smithery 50

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 350 | **803** | Max STM | **50** |
| Attack (Twin Blade) | 135 | **216** | Accuracy (Twin Blade) | **134** |
| Evasion | 120 | **145** | Weapon DMG / delay | **23** / 230 |
| Physical Defense | 92 | **243** | Combat Readiness | **0%** |
| Force Defense | 85 | **201** | Regen / 30s (HP · STM · FP) | 24 · 18 · 5 |
| Max FP | — | **61** | Force Attack | **125** |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Twin Blade · Cyclone | 60 | all | Cross Cut IV, Momentum, Spinning Rhythm III, Spinning Whirl III, Flowing Footwork, Blade Vortex II, Cyclone Stance, Sweeping Advance, Edge Rhythm, Tempest Bloom |
| Twin Blade · Lacerator | 60 | all | Lacerating Twin Cut IV, Blood Wake, Bleed Spread III, Serrated Arc III, Predatory Pressure, Twin Rupture II, Lacerator Stance, Sanguine Tempo, Arterial Reading, Red Bloom |
| Force · Alter | 29 | 9/32 | Throw Rock III, Force Push III, Throw Lightsaber III |
| Force · Control | 37 | 11/23 | Benevolence II, Guardian Ward II, Protective Presence, Renewal II, Force Leap II, Serene Focus, Force Convergence |
| Force · Sense | 10 | 3/13 | Mind Trick II, Danger Sense |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Trauma Medic | 55 | all | Med Kit IV, Treatment Kit III, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion II, Emergency Triage |
| Mimicry · Mimicry | 31 | all | Combat Analyzer IV, Analyzer Memory III, Pattern Recognition II, Overclocked Analyzer |
| Leadership · Vanguard Command | 55 | all | Rallying Standard II, Press the Attack III, Coordinated Focus III, Mark Target II, Charge Order II, Break Morale II, Command Presence II, Decisive Command |
| Leadership · Field Steward | 39 | 13/17 | Watchful Presence II, Rousing Shout III, Steady Formation II, Bolster Resolve II, Field Recovery II, Cleanse Order I, Triage Protocol I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Stormcall Twin Blade | `stormcall_blades` | Loot: NarShaddaa | DMG 23 · Delay 230 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Attack V + Attack V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Cyclone-Forged Vambrace | `sabstorm_w3` | Loot: Dantooine | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Scintathread V + Improved Synthmesh V |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Scintathread V + Improved Scintathread V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Improved Synthmesh V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Scintathread V + Improved Scintathread V |
| Ring | Spiral Crystal Band | `sabcycl_l6` | Loot: Dantooine | Atk +12 · Def +9 · FDef +8 · HP +7 | — |
| Ring | Storm-Touched Band | `sabstorm_l6` | Loot: Dantooine | Atk +12 · Def +9 · FDef +8 · HP +7 | — |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** Force Leap gets him into the group. Lacerator stacks Bleed, Red Bloom detonates it into Hemorrhage, and Tempest Bloom pulses on every area ability. Decisive Command raises the whole group's damage and crit chance.

**How to beat them:** Trauma resistance shortens his bleeds. Spread out so his areas hit fewer targets. He has a lot of Evasion (145), so use abilities that ignore it.

**As an NPC:** L60 · Elite · Melee · Force User · Hard to Hit
- HP 2683 · STM 179 · FP 31 · DMG 100 · Attack 28 · Force Attack 2 · Evasion 21 · Defense 79 · Force Defense 49 · Delay 240
- Attributes (MGT/PER/WIL/VIT/AGI) 47/38/27/38/38 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 13/12/13/13/17/-10/-15/18
- Abilities: Pouncing Strike, ⇄ **Force Sunder** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow


### TIER III: ELITES (350–399)

---

#### 9. Rhakar
*Cathar · Vibroblade berserker · Standard · **395/400 SP** (403/405 spent) · 39 AP*

A Cathar berserker with a vibroblade in hand and a bandolier of throwing blades.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 27* | 26 | 24 | 10 | 18 | 10 |

\* racial +1. 

**Skill ranks:** Vibroblade 50 · Armor 50 · First Aid 50 · Leadership 50 · Throwing 50 · Piloting 50 · Smithery 50 · Gathering 45

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 350 | **847** | Max STM | **50** |
| Attack (Vibroblade) | 135 | **212** | Accuracy (Vibroblade) | **134** |
| Evasion | 126 | **134** | Weapon DMG / delay | **24** / 230 |
| Physical Defense | 92 | **248** | Combat Readiness | **0%** |
| Force Defense | 78 | **198** | Regen / 30s (HP · STM) | 24 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Vibroblade · Frenzy | 60 | all | Riot Blade IV, Executioner II, Rundown III, Savage Cleave III, Savage Reflexes, Rending Strike II, Berserker Stance, Follow-Through, Blood Frenzy |
| Vibroblade · Bulwark | 60 | all | Shield Bash IV, Shield Training, Bulwark III, Covering Strike III, Fortification, Shield Wall II, Defensive Stance, Alacrity, Unbreakable, Invincible |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Leadership · Vanguard Command | 55 | all | Rallying Standard II, Press the Attack III, Coordinated Focus III, Mark Target II, Charge Order II, Break Morale II, Command Presence II, Decisive Command |
| Throwing · Ordnance | 60 | all | Explosive Toss IV, Payload Pouch, Shrapnel Casing III, Flash Toss III, Cluster Pouch, Concussive Toss II, Ordnance Stance, Saturation Toss, Bombardier's Rhythm, Rain of Steel |
| Throwing · Flurry | 60 | all | Piercing Toss IV, Returning Grip, Flurry Bleed III, Pinning Toss III, Ricochet Toss, Severing Toss II, Flurry Stance, Deep Wound, Bleeding Tempo, Perfect Flurry |
| Leadership · Field Steward | 21 | 8/17 | Watchful Presence II, Rousing Shout II, Steady Formation I, Bolster Resolve I, Field Recovery I, Cleanse Order I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Iron Discipline Vibroblade | `invinc_w1` | Loot: Viscara | DMG 24 · Delay 230 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Attack V + Improved Synthmesh V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Riot Line Vambrace | `invinc_w3` | Loot: Viscara | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Attack V + Improved Synthmesh V |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Attack V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Improved Synthmesh V |
| Ring | Roll Call Band | `invinc_l6` | Loot: Viscara | Def +14 · FDef +12 · HP +11 | — |
| Ring | Flurry Band | `perflurry_l6` | Loot: Hutlar | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Weapon swaps and situational gear**

- **Chaos Shield** (`ch_shield`, Crafted (Smithery)): Def +15 · FDef +12 · HP +40 · enhancements: Improved Synthmesh V + Improved Synthmesh V. Off-hand for Bulwark style (Shield Wall, Invincible). Equipping it turns off Doublehand.
- **Avalanche Throwing Blades** (`perflurry_w1`, Loot: Hutlar): DMG 19 · Delay 220 · Atk +20. Throwing set: open with Perfect Flurry at range.

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** He opens with Perfect Flurry from range to apply Bleed, closes in, and chains Blood Frenzy with Decisive Command. If he gets focused he equips the Chaos Shield and pops Invincible.

**How to beat them:** Invincible only stops physical damage, so wait out the 45 seconds or switch to Force or elemental damage. While the shield is on, he loses Doublehand and his damage drops.

**As an NPC:** L55 · Elite · Melee · Humanoid · High Damage
- HP 2371 · STM 166 · FP 29 · DMG 128 · Attack 30 · Force Attack 6 · Evasion 12 · Defense 72 · Force Defense 42 · Delay 240
- Attributes (MGT/PER/WIL/VIT/AGI) 45/37/26/37/37 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 11/-5/11/11/-5/11/12/11
- Abilities: Pouncing Strike, ⇄ **Serrated Slash** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow

---

#### 10. Dun Kehl
*Kel Dor · Force-hunter lancer · Standard · **385/400 SP** (395/395 spent) · 38 AP*

A Kel Dor bounty hunter whose kit exists to make Force users miserable. He stacks Force Defense in the cloak and ring slots.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 26 | 24* | 23 | 10 | 21 | 10 |

\* racial +1. 

**Skill ranks:** Spear 50 · Armor 50 · Devices 50 · First Aid 50 · Espionage 50 · Piloting 50 · Engineering 50 · Gathering 35

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 330 | **870** | Max STM | **49** |
| Attack (Spear) | 134 | **176** | Accuracy (Spear) | **132** |
| Evasion | 129 | **129** | Weapon DMG / delay | **42** / 280 |
| Physical Defense | 91 | **251** | Combat Readiness | **0%** |
| Force Defense | 78 | **221** | Regen / 30s (HP · STM) | 23 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Spear · Disabler | 60 | all | Disabling Strike IV, Erosion Strike, Force Warding III, Interruption Strike III, Force Piercing, Disruption Field II, Perceptive Stance, Disruption Expert, Fracture Strike, Forcebane |
| Spear · Vigor | 60 | all | Vigor Thrust IV, Lateral Footwork, High Guard III, Sweeping Flank III, Improved Attentiveness, Hampering Barrage II, Vigor Stance, Restoration Strike, Opportunist's Flow, Crippling Defense |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| Devices · Field Support | 60 | all | Deflector Shield III, Power Cell III, Weapon Jam, Power Surge, Rayshield Screen II, Dampening Field II, Overclock Routine, Group Deflector, Emergency Bunker |
| First Aid · Trauma Medic | 55 | all | Med Kit IV, Treatment Kit III, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion II, Emergency Triage |
| Devices · Field Engineer | 60 | all | Blaster Beacon III, Beacon Targeting II, Incendiary Field III, Remote Charge II, Signal Jammer, Shock Beacon II, Diagnostic Sweep, Killzone Beacon |
| Espionage · Saboteur | 60 | all | Poisoncraft V, Trapcraft IV, Venom Expertise II, Razor Trap II, Trap Management II, Shock Trap, Lasting Coatings, Master Saboteur |
| Espionage · Tradecraft | 8 | 3/5 | False Identities II, Cover Story I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Chiro Spear | `chi_spear` | Crafted (Smithery, L50 recipe) | DMG 42 · Delay 280 | Attack Bonus V + Attack Bonus V |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Attack V + Improved Synthmesh V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Improved Synthmesh V |
| Arms | Molten Proving Vambrace | `forcebane_w3` | Loot: Korriban | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Synthmesh V + Attack V |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Gemweb V + Improved Gemweb V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Improved Synthmesh V |
| Neck | Null-Field Collar | `nullfield_collar` | Crafted: SalvagedFieldGear | Def +13 · FDef +11 · HP +10 · FP +4 | — |
| Ring | Chaos Ring | `ch_ring` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Gemweb V + Improved Gemweb V |
| Ring | Grounding Band | `embunker_l4` | Loot: Viscara | Def +14 · FDef +12 · HP +11 | — |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** He traps the approach, opens on the caster with Interruption Strike, then lands Forcebane (Foggy Mind, Force Disruption, −20% ability accuracy) on the group. Weapon Jam handles gunners.

**How to beat them:** Bring physical damage. His whole kit is aimed at casters, and at 221 Force Defense he takes Force damage well. Disarm his traps before you engage.

**As an NPC:** L55 · Elite · Controller · Humanoid · None
- HP 2371 · STM 101 · FP 130 · DMG 78 · Attack 22 · Force Attack 24 · Evasion 14 · Defense 70 · Force Defense 46 · Delay 290
- Attributes (MGT/PER/WIL/VIT/AGI) 26/37/45/26/37 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 11/-5/11/11/-5/11/12/11
- Abilities: ⇄ **Brutal Bash** (replaces Sonic Shriek), Disorienting Screech, Tactical Mark, Crippling Talons

---

#### 11. Sevral
*Chiss · Poison assassin · Standard · **375/400 SP** (378/385 spent) · 37 AP*

A Chiss assassin who owns every Espionage style and both Vibroknife styles. She has the roster's highest Attack (226) and only 584 HP.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 26 | 27* | 18 | 10 | 19 | 13 |

\* racial +1. 

**Skill ranks:** Vibroknife 50 · Espionage 50 · Armor 50 · First Aid 50 · Piloting 50 · Fabrication 50 · Agriculture 45 · Throwing 30

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 230 | **584** | Max STM | **57** |
| Attack (Vibroknife) | 134 | **226** | Accuracy (Vibroknife) | **135** |
| Evasion | 127 | **135** | Weapon DMG / delay | **22** / 220 |
| Physical Defense | 86 | **241** | Combat Readiness | **0%** |
| Force Defense | 78 | **199** | Regen / 30s (HP · STM) | 18 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Vibroknife · Shadow | 60 | all | Pathogen Strike IV, Hypermetabolize, Debilitate III, Virulent Blade III, Infection, Volatile Compound II, Assassin's Stance, Venom Tempo, Propagation, Viral Cascade |
| Vibroknife · Cutthroat | 60 | all | Veiled Strike IV, Butcher's Tempo, First Strike III, Crippling Slice III, Venatic Recovery, Backstab II, Shadowflow, Cheap Shot, Hobbled, Escape Artist |
| Espionage · Tradecraft | 15 | all | False Identities III, Cover Story II |
| Espionage · Infiltrator | 60 | all | Stealth IV, Slicing V, Back Attack III, Tactical Escape II, Shadow Step II, Silent Stride, Ghost Protocol |
| Espionage · Saboteur | 60 | all | Poisoncraft V, Trapcraft IV, Venom Expertise II, Razor Trap II, Trap Management II, Shock Trap, Lasting Coatings, Master Saboteur |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Throwing · Flurry | 36 | 12/18 | Piercing Toss III, Returning Grip, Flurry Bleed II, Pinning Toss II, Ricochet Toss, Severing Toss I, Flurry Stance, Deep Wound |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Warden's Blackout Vibroknife | `sysshut_w1` | Loot: Viscara | DMG 22 · Delay 220 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Attack V + Attack V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Kill Switch Vambrace | `sysshut_w3` | Loot: Viscara | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Power Cut Boots | `sysshut_l8` | Loot: Viscara | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Alarm Bell Mantle | `sysshut_l5` | Loot: Viscara | Def +15 · FDef +13 · HP +12 | — |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Attack V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Ring | Chaos Ring | `ch_ring` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Ring | Chaos Ring | `ch_ring` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Weapon swaps and situational gear**

- **Warden's Interrogation Vibroknife** (`vitrupt_w1`, Loot: Viscara): DMG 22 · Delay 220 · Atk +20. Second knife for Cutthroat openers (identical stats).

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** She opens from stealth with Ghost Protocol for a guaranteed-crit back attack with Exposed, stacks Venom and Infection, then cashes out with Viral Cascade. Escape Artist (blind plus invisibility) is her way out.

**How to beat them:** Poison resistance and Detection. With 584 HP she dies as soon as she's pinned, so make sure she can't use Escape Artist first.

**As an NPC:** L54 · Elite · Melee · Humanoid · Glass Cannon
- HP 1767 · STM 147 · FP 25 · DMG 136 · Attack 30 · Force Attack 7 · Evasion 9 · Defense 68 · Force Defense 38 · Delay 240
- Attributes (MGT/PER/WIL/VIT/AGI) 44/36/25/36/36 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 9/-5/9/9/-5/9/10/9
- Abilities: Pouncing Strike, ⇄ **Toxic Spit** (replaces Mauling Bite), Tail Sweep, Terrifying Bellow

---

#### 12. Neela Ghoss & "Gutter"
*Rodian · Beast-handler marksman · Standard · **360/400 SP** (367/370 spent) · 36 AP*

A Rodian tracker in a Dathomir 'Alpha Rhythm' beast-hunter kit, with Gutter, a scarred beast she raised from a pup.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 26* | 20 | 14 | 24 | 18 |

\* racial +1. 

**Skill ranks:** Beast Mastery 50 · Rifle 50 · Armor 50 · First Aid 50 · Leadership 50 · Gathering 50 · Agriculture 50 · Piloting 10

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 270 | **595** | Max STM | **43** |
| Attack (Rifle) | 134 | **188** | Accuracy (Rifle) | **132** |
| Evasion | 132 | **156** | Weapon DMG / delay | **40** / 300 |
| Physical Defense | 88 | **216** | Combat Readiness | **0%** |
| Force Defense | 82 | **180** | Regen / 30s (HP · STM) | 20 · 16 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Beast Mastery · Training | 42 | all | Tame V, Revive Beast III, Reward III, Stabling V, Guarding Bond Stance, Predatory Bond Stance, Soothe Pet |
| Beast Mastery · Bioengineer | 35 | all | DNA Manipulation V, Incubation Processing IV, Erratic Genius III, Incubation Management II |
| Rifle · Suppression | 60 | all | Suppressing Shot IV, Pinning Fire, Sustained Fire III, Crippling Shot III, Spotter's Rhythm, Suppressive Line II, Suppression Stance, Overwatch, Containment Net, Kill Box |
| Rifle · Marksman | 60 | all | Aimed Shot IV, Steady Aim, Patience III, Piercing Round III, Scope Calibration, Headshot II, Sniper Stance, Dead Center, Breach Round, One Shot |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Trauma Medic | 55 | all | Med Kit IV, Treatment Kit III, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion II, Emergency Triage |
| Leadership · Field Steward | 55 | all | Watchful Presence III, Rousing Shout III, Steady Formation II, Bolster Resolve II, Field Recovery II, Cleanse Order II, Triage Protocol II, Hold the Line |
| Leadership · Vanguard Command | 28 | 10/17 | Rallying Standard II, Press the Attack II, Coordinated Focus II, Mark Target I, Charge Order I, Break Morale I, Command Presence I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Killbox Enforcer Rifle | `killbox_w1` | Loot: NarShaddaa | DMG 40 · Delay 300 · Atk +20 | — |
| Head | Pack-Sight Visor | `alpharhy_l5` | Loot: Dathomir | Def +18 · FDef +11 · HP +68 · Ev +8 | — |
| Body | Alpha Rhythm Harness | `alpharhy_w1` | Loot: Dathomir | Def +30 · FDef +25 · HP +103 | — |
| Arms | Kill Lane Vambrace | `killbox_w3` | Loot: NarShaddaa | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Cadence Trailboots | `alpharhy_l6` | Loot: Dathomir | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Belt | Packlord's Sash | `alpharhy_w2` | Loot: Dathomir | Def +6 · FDef +5 · HP +7 · FP +5 · STM +10 · STM regen +2 | — |
| Neck | Alpha Rhythm Totem | `alpharhy_w5` | Loot: Dathomir | Def +11 · FDef +9 · HP +9 · FP regen +2 · STM regen +2 | — |
| Ring | Alpha Pulse Ring | `alpharhy_l4` | Loot: Dathomir | Atk +12 · Def +9 · FDef +8 · HP +7 | — |
| Ring | Target Lock Band | `killbox_l6` | Loot: NarShaddaa | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Weapon swaps and situational gear**

- **Oneshot Executioner Rifle** (`oneshot_w1`, Loot: NarShaddaa): DMG 40 · Delay 300 · Atk +20. Marksman set: One Shot from range while Gutter holds the target.

**Consumables:** L45+ meal with **STM V + STM Regen V** (ranged builds have small STM pools).

**How they fight:** Gutter pins the target while she lays down Kill Box, then swaps to the Oneshot Executioner for the kill. She revives and patches up the beast, and Hold the Line covers both of them.

**How to beat them:** Kill the pet first to split her attention, or dive her and let Gutter chase. She has 595 HP.

**As an NPC:** L53 · Elite · Ranged · Humanoid · None
- HP 2383 · STM 139 · FP 35 · DMG 94 · Attack 25 · Force Attack 2 · Evasion 14 · Defense 70 · Force Defense 42 · Delay 270
- Attributes (MGT/PER/WIL/VIT/AGI) 25/43/25/35/35 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 11/-5/11/11/-5/11/12/11
- Abilities: Tactical Mark, Precision Shot, ⇄ **Suppressing Shot** (replaces Piercing Quills), Grenade Burst
- **Gutter (pet):** L53 · Tough · Melee · Beast · HP 1706 · STM 128 · DMG 93 · Attack 24 · Evasion 10 · Defense 71 · Force Defense 41 · Delay 250 · Pouncing Strike, Rending Bite, Tail Sweep


### TIER II: VETERANS (300–349)

---

#### 13. Yuraan Sel
*Echani · Twin-blade whirlwind · Standard · **345/400 SP** (355/355 spent) · 34 AP*

An Echani blade-dancer with an Overload Barrage wrist launcher for anyone who backs away.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 26 | 25 | 20 | 10 | 18 | 10 |

\* racial +1. No racial bonus.

**Skill ranks:** Twin Blade 50 · Armor 50 · First Aid 50 · Leadership 50 · Devices 50 · Piloting 50 · Smithery 45

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 270 | **633** | Max STM | **49** |
| Attack (Twin Blade) | 134 | **211** | Accuracy (Twin Blade) | **133** |
| Evasion | 126 | **136** | Weapon DMG / delay | **23** / 230 |
| Physical Defense | 88 | **241** | Combat Readiness | **11%** |
| Force Defense | 78 | **197** | Regen / 30s (HP · STM) | 20 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Twin Blade · Cyclone | 60 | all | Cross Cut IV, Momentum, Spinning Rhythm III, Spinning Whirl III, Flowing Footwork, Blade Vortex II, Cyclone Stance, Sweeping Advance, Edge Rhythm, Tempest Bloom |
| Twin Blade · Lacerator | 60 | all | Lacerating Twin Cut IV, Blood Wake, Bleed Spread III, Serrated Arc III, Predatory Pressure, Twin Rupture II, Lacerator Stance, Sanguine Tempo, Arterial Reading, Red Bloom |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Leadership · Vanguard Command | 55 | all | Rallying Standard II, Press the Attack III, Coordinated Focus III, Mark Target II, Charge Order II, Break Morale II, Command Presence II, Decisive Command |
| Devices · Assault Gadgets | 60 | all | Flamethrower III, Wrist Rocket III, Sonic Burst III, Gadget Harness, Arc Projector III, Ion Lance III, Rail Dart III, Tactical Uplink, Cryo Sprayer, Overload Barrage |
| Devices · Grenadier | 33 | 10/16 | Frag Grenade II, Blast Radius II, Concussion Grenade II, Flash Grenade, Ion Grenade I, Adhesive Grenade I, Cluster Grenade |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Blood-Price Twin Blade | `bloodprice_edge` | Loot: NarShaddaa | DMG 23 · Delay 230 · Atk +20 | — |
| Head | Headwind Visor | `headwind_visor` | Loot: NarShaddaa | Def +21 · FDef +14 · HP +81 · CR +3 | — |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Improved Synthcloth V |
| Arms | Barrage Vambrace | `overbarr_w3` | Loot: Hutlar | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Frame-Step Boots | `frame_boots` | Loot: Viscara | Def +19 · FDef +12 · HP +68 · Ev +2 · CR +3 | — |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Attack V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Ring | Trajectory Band | `overbarr_l4` | Loot: Hutlar | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Ring | Chaos Ring | `ch_ring` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** He stacks Cyclone and Lacerator areas, detonates with Red Bloom, and punishes anyone who disengages with Overload Barrage.

**How to beat them:** Fight him at range. He has 633 HP and no self-healing beyond Emergency Cocktail.

**As an NPC:** L52 · Tough · Melee · Humanoid · None
- HP 1661 · STM 126 · FP 22 · DMG 91 · Attack 24 · Force Attack 1 · Evasion 10 · Defense 71 · Force Defense 41 · Delay 250
- Attributes (MGT/PER/WIL/VIT/AGI) 42/34/24/34/34 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 10/-5/10/10/-5/10/11/10
- Abilities: Pouncing Strike, ⇄ **Serrated Slash** (replaces Rending Bite), Tail Sweep

---

#### 14. Hollis Breck
*Human · Combat medic · Standard · **330/400 SP** (340/340 spent) · 33 AP*

A Republic field surgeon in Holdline medic gear, with Combat Readiness at 14% to push every heal.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 22 | 22 | 27* | 14 | 14 |

\* racial +1. 

**Skill ranks:** First Aid 50 · Pistol 50 · Armor 50 · Devices 50 · Leadership 50 · Agriculture 50 · Engineering 30

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 310 | **633** | Max STM | **43** |
| Attack (Pistol) | 130 | **162** | Accuracy (Pistol) | **122** |
| Evasion | 122 | **138** | Weapon DMG / delay | **23** / 250 |
| Physical Defense | 90 | **223** | Combat Readiness | **14%** |
| Force Defense | 95 | **197** | Regen / 30s (HP · STM) | 22 · 19 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| First Aid · Trauma Medic | 55 | all | Med Kit IV, Treatment Kit III, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion II, Emergency Triage |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Pistol · Skirmisher | 60 | all | Disarming Shot IV, Mobile Footwork, Snap Roll III, Interrupting Shot III, Kiting Instinct, Point Blank Burst II, Skirmisher Stance, Duelist's Distance, Evasive Reload, Last Word |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| Devices · Field Support | 60 | all | Deflector Shield III, Power Cell III, Weapon Jam, Power Surge, Rayshield Screen II, Dampening Field II, Overclock Routine, Group Deflector, Emergency Bunker |
| Leadership · Field Steward | 55 | all | Watchful Presence III, Rousing Shout III, Steady Formation II, Bolster Resolve II, Field Recovery II, Cleanse Order II, Triage Protocol II, Hold the Line |
| Pistol · Gambler | 23 | 9/18 | Quick Draw II, Lucky Chamber, Rapid Shot I, Double Shot I, Deadeye Reload, Fan the Hammer I, Gambler Stance, Reload Tempo |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Final Verdict Sidearm | `lastword_w1` | Loot: Tatooine | DMG 23 · Delay 250 · Atk +20 | — |
| Head | Field Medic Visor | `holdline_l5` | Loot: Dantooine | Def +18 · FDef +11 · HP +68 · Ev +8 | — |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Improved Synthcloth V + Improved Synthcloth V |
| Arms | Bulwark Vambrace | `holdline_w3` | Loot: Dantooine | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Bracing Boots | `holdline_l6` | Loot: Dantooine | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Circle Mantle | `circle_mantle` | Loot: Viscara | Def +13 · FDef +11 · HP +11 · CR +4 | — |
| Belt | Holdline Warden Sash | `holdline_w2` | Loot: Dantooine | Def +6 · FDef +5 · HP +7 · FP +5 · STM +10 · STM regen +2 | — |
| Neck | Adrenaline Charm | `emcocktail_l7` | Loot: Dantooine | Def +12 · FDef +11 · HP +10 · FP regen +1 · STM regen +1 | — |
| Ring | Steadfast Band | `holdline_l4` | Loot: Dantooine | Def +14 · FDef +12 · HP +11 | — |
| Ring | Serum Band | `emcocktail_l4` | Loot: Dantooine | Def +12 · FDef +10 · HP +9 · STM regen +2 | — |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Consumables:** L45+ meal with **Combat Readiness V + FP Regen V** (Combat Readiness is capped at 15% total).

**How they fight:** She keeps the group alive under Emergency Bunker and Hold the Line, uses Emergency Triage (doubled under 35% HP) as her panic button, and stays mobile with Last Word.

**How to beat them:** Focus her first and interrupt her heals. She has 633 HP.

**As an NPC:** L51 · Tough · Support · Humanoid · None
- HP 1536 · STM 86 · FP 108 · DMG 64 · Attack 18 · Force Attack 21 · Evasion 10 · Defense 68 · Force Defense 42 · Delay 310
- Attributes (MGT/PER/WIL/VIT/AGI) 23/33/41/33/23 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 10/-5/10/10/-5/10/11/10
- Abilities: Iron Carapace, ⇄ **Precision Shot** (replaces Savage Roar), Tactical Mark

---

#### 15. Vaadosk
*Trandoshan · Staff sentinel tank · Standard · **315/400 SP** (325/325 spent) · 31 AP*

A Trandoshan sentinel in Synthmesh-stuffed Chaos plate. He has 1,413 HP, the most on the roster, and can't be knocked down.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 25 | 20 | 27* | 15 | 10 | 10 |

\* racial +1. 

**Skill ranks:** Staff 50 · Armor 50 · First Aid 50 · Leadership 50 · Mimicry 50 · Gathering 50 · Smithery 15

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 410 | **1413** | Max STM | **47** |
| Attack (Staff) | 133 | **153** | Accuracy (Staff) | **128** |
| Evasion | 118 | **118** | Weapon DMG / delay | **24** / 270 |
| Physical Defense | 95 | **268** | Combat Readiness | **0%** |
| Force Defense | 83 | **212** | Regen / 30s (HP · STM) | 27 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Staff · Sentinel | 60 | all | Line Breaker IV, Sentinel Guard, Staff Parry III, Leg Sweep III, Guarding Step, Sweeping Guard, Sentinel Stance, Flowing Defense, Shelter Circle, Patient Sentinel, Unmoving Center |
| Staff · Crusher | 60 | all | Slam IV, Crushing Mastery, Charged Blows III, Rib Breaker III, Heavy Hands, Ground Quake II, Crusher Stance, Break Posture, Skull Rattle, Worldbreaker |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Trauma Medic | 55 | all | Med Kit IV, Treatment Kit III, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion II, Emergency Triage |
| Leadership · Field Steward | 55 | all | Watchful Presence III, Rousing Shout III, Steady Formation II, Bolster Resolve II, Field Recovery II, Cleanse Order II, Triage Protocol II, Hold the Line |
| Mimicry · Mimicry | 31 | all | Combat Analyzer IV, Analyzer Memory III, Pattern Recognition II, Overclocked Analyzer |
| Leadership · Vanguard Command | 32 | 11/17 | Rallying Standard II, Press the Attack II, Coordinated Focus II, Mark Target II, Charge Order I, Break Morale I, Command Presence I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Unbroken Anchor Pike | `unmovctr_w1` | Loot: Tatooine | DMG 24 · Delay 270 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Improved Synthmesh V + Improved Synthmesh V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Improved Synthmesh V + Improved Synthmesh V |
| Arms | Chaos Bracer | `ch_bracer` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Synthmesh V + Improved Synthmesh V |
| Feet | Chaos Leggings | `ch_leggings` | Crafted (Smithery) | Def +22 · FDef +14 · HP +81 | Improved Synthmesh V + Improved Synthmesh V |
| Cloak | Chaos Cloak | `ch_cloak` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Synthmesh V + Improved Synthmesh V |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Improved Synthmesh V + Improved Synthmesh V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Synthmesh V + Improved Elastex V |
| Ring | Chaos Ring | `ch_ring` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Improved Synthmesh V + Improved Synthmesh V |
| Ring | Steadfast Band | `holdline_l4` | Loot: Dantooine | Def +14 · FDef +12 · HP +11 | — |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Weapon swaps and situational gear**

- **Wrecking Beam Staff** (`worldbrk_w1`, Loot: CZ220): DMG 24 · Delay 270 · Atk +20. Crusher set: Worldbreaker on controlled packs.

**Consumables:** L45+ meal with **HP V + HP Regen V**.

**How they fight:** Unmoving Center (immune to knockdown and daze, +20 melee deflection) holds the line. He swaps to the Wrecking Beam Staff to Worldbreaker groups that are already controlled.

**How to beat them:** Ranged and Force damage get past his melee deflection. His Evasion (118) is low, so ranged attacks land on him easily.

**As an NPC:** L51 · Tough · Tank · Humanoid · High Durability
- HP 3056 · STM 124 · FP 42 · DMG 65 · Attack 19 · Force Attack 0 · Evasion 7 · Defense 79 · Force Defense 48 · Delay 350
- Attributes (MGT/PER/WIL/VIT/AGI) 33/33/33/41/23 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 12/-5/12/12/-5/12/13/12
- Abilities: Iron Carapace, Chitin Guard, ⇄ **Brutal Bash** (replaces Rending Bite)

---

#### 16. Ondra Pell
*Human · Dark Force adept · Force Sensitive · **300/400 SP** (309/310 spent) · 30 AP · Affinity **-10** (Dark)*

A dark-side adept in full Magus with Force Attack enhancements. Her 229 Force Attack is the highest on the roster, and her lightsaber is only a backup.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 14 | 20 | 18 | 27* | 16 | 11 |

\* racial +1. 

**Skill ranks:** Force 50 · Armor 50 · First Aid 50 · Mimicry 50 · Piloting 50 · Lightsaber 30 · Agriculture 20

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 230 | **405** | Max STM | **31** |
| Attack (Lightsaber) | 82 | **82** | Accuracy (Lightsaber) | **88** |
| Evasion | 124 | **124** | Weapon DMG / delay | **17** / 240 |
| Physical Defense | 86 | **199** | Combat Readiness | **0%** |
| Force Defense | 95 | **259** | Regen / 30s (HP · STM · FP) | 18 · 13 · 22 |
| Max FP | — | **159** | Force Attack | **229** |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Force · Alter | 85 | 26/32 | Force Spark II, Throw Rock III, Creeping Terror III, Force Push III, Force Choke IV, Throw Lightsaber III, Force Lightning III, Force Drain III, Devouring Strike, Unstable Pressure |
| Force · Control | 27 | 7/23 | Force Leap II, Fury Stance II, Cruel Momentum, Force Convergence, Hunger of the Dark |
| Force · Sense | 29 | 8/13 | Weaken Resolve II, Mind Trick II, Nightmare Field, Danger Sense, Collapse Will, Eclipse of Resolve |
| Lightsaber · Severance | 36 | 12/18 | Force Sheath II, Overpower II, Fast Strikes, Shattering Strike II, Sundering Sweep II, Weak Points, Imbuement Stance, High Ground |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Combat Pharmacology | 55 | all | Adrenal Stim III, Shielding III, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist III, Focus Stim II, Emergency Cocktail |
| Mimicry · Mimicry | 31 | all | Combat Analyzer IV, Analyzer Memory III, Pattern Recognition II, Overclocked Analyzer |
| Lightsaber · Ward | 14 | 6/18 | Saber Ward II, Mental Fortress I, Deflecting Return I, Guardian's Challenge I, Surrounded, Not Outmatched |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Lightsaber (custom) + Lightsaber Upgrade Kit IV | `—` | Starting grant + Engineering kits II–IV | DMG 17 · Delay 240 | — |
| Head | Magus Cap | `mag_cap` | Crafted (Smithery) | Def +13 · FDef +24 · HP +43 · FP +13 · FP regen +3 | Force Attack V + Force Attack V |
| Body | Magus Tunic | `mag_tunic` | Crafted (Smithery) | Def +17 · FDef +28 · HP +50 · FP +14 · FP regen +5 | Force Attack V + Force Attack V |
| Arms | Magus Gloves | `mag_gloves` | Crafted (Smithery) | Def +13 · FDef +24 · HP +21 · FP +12 · FP regen +3 | Force Attack V + Force Attack V |
| Feet | Magus Boots | `mag_boots` | Crafted (Smithery) | Def +13 · FDef +24 · HP +26 · FP +12 · FP regen +4 | Force Attack V + Force Attack V |
| Cloak | Magus Cloak | `mag_cloak` | Crafted (Smithery) | Def +13 · FDef +16 · HP +6 · FP +6 | Force Attack V + Force Attack V |
| Belt | Magus Belt | `mag_belt` | Crafted (Smithery) | Def +13 · FDef +16 · HP +9 · FP +5 | Force Attack V + Force Attack V |
| Neck | Magus Necklace | `mag_necklace` | Crafted (Smithery) | Def +13 · FDef +16 · HP +6 · FP +6 | Force Attack V + Force Attack V |
| Ring | Darkened Bone Band | `darkhung_l6` | Loot: Korriban | FAtk +12 · Def +9 · FDef +8 · HP +7 | — |
| Ring | Eclipse-Bound Band | `eclipse_l6` | Loot: Korriban | FAtk +12 · Def +9 · FDef +8 · HP +7 | — |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Consumables:** L45+ meal with **FP V + FP Regen V**.

**How they fight:** She chains Force Lightning III, Force Choke IV and Force Drain III, sets Nightmare Field on choke points, and keeps Eclipse of Resolve up against melee.

**How to beat them:** Close the distance, because her saber is weak (17 DMG, 82 Attack). She has 405 HP and 199 Physical Defense, so physical burst kills her quickly.

**As an NPC:** L50 · Tough · Force · Force User · None
- HP 1337 · STM 48 · FP 132 · DMG 80 · Attack 18 · Force Attack 24 · Evasion 11 · Defense 67 · Force Defense 45 · Delay 300
- Attributes (MGT/PER/WIL/VIT/AGI) 23/33/41/23/33 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 11/10/11/11/15/-10/-15/16
- Abilities: Force Rend, Mind Spike, ⇄ **Chain Lightning** (replaces Dark Shock)


### TIER I: CONTENDERS (250–299)

---

#### 17. Jory Fass
*Human (Corellian) · Twin-blaster skirmisher · Standard · **290/400 SP** (300/300 spent) · 29 AP*

A Corellian skirmisher with both twin-pistol trees and half-built gadgets and stealth.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 24 | 24 | 10 | 27* | 10 |

\* racial +1. 

**Skill ranks:** Twin Pistol 50 · Armor 50 · Piloting 50 · Espionage 40 · First Aid 40 · Devices 40 · Fabrication 20

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 350 | **768** | Max STM | **25** |
| Attack (Twin Pistol) | 132 | **179** | Accuracy (Twin Pistol) | **140** |
| Evasion | 135 | **168** | Weapon DMG / delay | **23** / 250 |
| Physical Defense | 92 | **232** | Combat Readiness | **0%** |
| Force Defense | 78 | **185** | Regen / 30s (HP · STM) | 24 · 14 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Twin Pistol · Crossfire | 60 | all | Lead Shot IV, Cadence, Steady Cadence III, Closing Shot III, Changing Angles, Tempo Shot II, Crossfire Stance, Follow Through, Second Wind, Final Salvo |
| Twin Pistol · Barrage | 60 | all | Paired Volley IV, Alternating Fire, Matched Rhythm III, Focused Burst III, Balanced Grip, Controlled Burst II, Akimbo Stance, Converging Fire, Cool Under Fire, Twin Suns |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| Espionage · Infiltrator | 42 | 14/18 | Stealth IV, Slicing III, Back Attack III, Tactical Escape II, Shadow Step I, Silent Stride |
| First Aid · Combat Pharmacology | 39 | 13/17 | Adrenal Stim III, Shielding II, Coagulant II, Pain Suppressant II, Antitoxin, Field Pharmacist II, Focus Stim I |
| Devices · Assault Gadgets | 41 | 17/22 | Flamethrower III, Wrist Rocket III, Sonic Burst II, Gadget Harness, Arc Projector II, Ion Lance II, Rail Dart II, Tactical Uplink, Cryo Sprayer |
| Devices · Field Support | 26 | 8/15 | Deflector Shield II, Power Cell II, Weapon Jam, Power Surge, Rayshield Screen I, Dampening Field I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Chiro Twin Pistols | `chi_twinpistol` | Crafted (Smithery, L50 recipe) | DMG 23 · Delay 250 | Attack Bonus V + Accuracy V |
| Head | Line-Calibration Visor | `line_visor` | Loot: Hutlar | Atk +3 · Def +20 · FDef +13 · HP +75 | — |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Gunslinger Rig | `gunsling_rig` | Loot: NarShaddaa | Atk +11 · Def +12 · FDef +8 · HP +46 · Ev +5 | — |
| Feet | Black-Market Boots | `blackmkt_boots` | Loot: Viscara | Def +20 · FDef +13 · HP +74 · Ev +2 | — |
| Cloak | Hexweave Shawl | `hexweave` | Loot: NarShaddaa | Atk +8 · Def +12 · FDef +8 · HP +46 · Ev +5 | — |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Improved Synthmesh V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Improved Scintathread V |
| Ring | Cold Trigger Band | `deadhand_l6` | Loot: Tatooine | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Ring | Trigger Finger Band | `lastword_l6` | Loot: Tatooine | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **STM V + STM Regen V** (ranged builds have small STM pools).

**How they fight:** He builds Cadence with Akimbo, cashes out with Final Salvo, and uses the Twin Suns burst window. Wrist Rocket and Flamethrower handle anyone who closes in.

**How to beat them:** Close the distance. His Evasion (168) is high, so use abilities that don't roll against it.

**As an NPC:** L50 · Tough · Ranged · Humanoid · None
- HP 1416 · STM 106 · FP 26 · DMG 84 · Attack 23 · Force Attack 1 · Evasion 13 · Defense 68 · Force Defense 40 · Delay 280
- Attributes (MGT/PER/WIL/VIT/AGI) 23/41/23/33/33 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 10/-5/10/10/-5/10/11/10
- Abilities: Suppressing Shot, Precision Shot, Tactical Mark (no swap)

---

#### 18. Raana Tiv
*Togruta · Blade-thrower · Standard · **275/400 SP** (284/285 spent) · 27 AP*

A Togruta who bleeds a target from range, then knifes it up close.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 25 | 21 | 10 | 27* | 10 |

\* racial +1. 

**Skill ranks:** Throwing 50 · Armor 50 · Vibroknife 40 · Espionage 40 · Agriculture 40 · First Aid 30 · Piloting 25

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 290 | **674** | Max STM | **33** |
| Attack (Throwing) | 133 | **195** | Accuracy (Throwing) | **135** |
| Evasion | 135 | **164** | Weapon DMG / delay | **19** / 220 |
| Physical Defense | 89 | **232** | Combat Readiness | **0%** |
| Force Defense | 78 | **189** | Regen / 30s (HP · STM) | 21 · 14 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Throwing · Flurry | 60 | all | Piercing Toss IV, Returning Grip, Flurry Bleed III, Pinning Toss III, Ricochet Toss, Severing Toss II, Flurry Stance, Deep Wound, Bleeding Tempo, Perfect Flurry |
| Throwing · Ordnance | 60 | all | Explosive Toss IV, Payload Pouch, Shrapnel Casing III, Flash Toss III, Cluster Pouch, Concussive Toss II, Ordnance Stance, Saturation Toss, Bombardier's Rhythm, Rain of Steel |
| Vibroknife · Cutthroat | 50 | 16/18 | Veiled Strike IV, Butcher's Tempo, First Strike II, Crippling Slice III, Venatic Recovery, Backstab II, Shadowflow, Cheap Shot, Hobbled |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| Espionage · Infiltrator | 42 | 14/18 | Stealth IV, Slicing III, Back Attack III, Tactical Escape II, Shadow Step I, Silent Stride |
| First Aid · Combat Pharmacology | 29 | 10/17 | Adrenal Stim III, Shielding II, Coagulant I, Pain Suppressant I, Antitoxin, Field Pharmacist I, Focus Stim I |
| Espionage · Tradecraft | 11 | 4/5 | False Identities II, Cover Story II |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Avalanche Throwing Blades | `perflurry_w1` | Loot: Hutlar | DMG 19 · Delay 220 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Attack V + Attack V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Attack V |
| Arms | Rapid-Cast Vambrace | `perflurry_w3` | Loot: Hutlar | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Sprinter's Boots | `perflurry_l8` | Loot: Hutlar | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Squall Mantle | `perflurry_l5` | Loot: Hutlar | Def +15 · FDef +13 · HP +12 | — |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Improved Synthmesh V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Improved Scintathread V |
| Ring | Flurry Band | `perflurry_l6` | Loot: Hutlar | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Ring | Flechette Band | `rainsteel_l6` | Loot: NarShaddaa | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Empty, so Doublehand III applies (+60% one-handed weapon DMG) | | | | |

**Weapon swaps and situational gear**

- **Shadow Gloamsteel Knife** (`slw_gloamknife`, Slicing: Lockbox Tier 5): DMG 21 · Delay 220 · Atk +12. Close-range Cutthroat knife (highest she can use at Vibroknife 40).

**Consumables:** L45+ meal with **STM V + STM Regen V** (ranged builds have small STM pools).

**How they fight:** She stacks Bleed with Flurry, spreads it with Perfect Flurry, and finishes up close with Cutthroat's Backstab from Shadowflow.

**How to beat them:** Trauma resistance. She has 674 HP.

**As an NPC:** L49 · Tough · Ranged · Humanoid · None
- HP 1377 · STM 104 · FP 26 · DMG 82 · Attack 23 · Force Attack 1 · Evasion 12 · Defense 63 · Force Defense 38 · Delay 280
- Attributes (MGT/PER/WIL/VIT/AGI) 23/40/23/33/33 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 9/-5/9/9/-5/9/10/9
- Abilities: Suppressing Shot, Precision Shot, ⇄ **Toxic Spit** (replaces Tactical Mark)

---

#### 19. Goss Durrant
*Human · Soul-burner berserker · Standard · **260/400 SP** (270/270 spent) · 26 AP*

An Outer Rim berserker who spends his own HP to hit harder. He has 219 Attack at only 260 SP.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 27* | 20 | 23 | 10 | 12 | 10 |

\* racial +1. 

**Skill ranks:** Heavy Vibroblade 50 · Armor 50 · First Aid 40 · Leadership 40 · Mimicry 40 · Gathering 40

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 330 | **759** | Max STM | **58** |
| Attack (Heavy Vibroblade) | 135 | **219** | Accuracy (Heavy Vibroblade) | **128** |
| Evasion | 120 | **128** | Weapon DMG / delay | **44** / 300 |
| Physical Defense | 91 | **240** | Combat Readiness | **0%** |
| Force Defense | 78 | **194** | Regen / 30s (HP · STM) | 23 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Heavy Vibroblade · Berserker | 60 | all | Soul Strike III, Essence Tap, Essence Hunter, Sacrificial Blade, Life Siphon, Soul Burst, Soul Devourer Stance, Vampiric Fury, Soul Amplification, Soul Storm, Blazing Spikes, Soul Sacrifice, Soul Barrier, Bloodlust, Soul Reaping, Soul Ascension |
| Heavy Vibroblade · Immortal | 60 | all | Fortress Strike III, Anger Strike, Crushing Blow, Flash, Defensive Harmony, Earthshatter II, Bastion Stance, Last Stand, Guardian's Resolve, Rampart, Critical Ward, Unbreakable Will, Blood Weapon, Guardian's Reaping, Absolute Defense |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Trauma Medic | 39 | 13/17 | Med Kit III, Treatment Kit II, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion I |
| Leadership · Vanguard Command | 39 | 13/17 | Rallying Standard II, Press the Attack III, Coordinated Focus II, Mark Target II, Charge Order II, Break Morale I, Command Presence I |
| Mimicry · Mimicry | 22 | 8/10 | Combat Analyzer III, Analyzer Memory III, Pattern Recognition II |
| First Aid · Combat Pharmacology | 18 | 7/17 | Adrenal Stim II, Shielding I, Coagulant I, Pain Suppressant I, Antitoxin, Field Pharmacist I |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Sithforge Cleaver | `soulasc_w1` | Loot: Korriban | DMG 44 · Delay 300 · Atk +20 | — |
| Head | Chaos Helmet | `ch_helmet` | Crafted (Smithery) | Def +22 · FDef +14 · HP +83 | Attack V + Attack V |
| Body | Chaos Breastplate | `ch_armor` | Crafted (Smithery) | Def +28 · FDef +23 · HP +95 · STM regen +2 | Attack V + Improved Synthmesh V |
| Arms | Slag Warden Vambrace | `soulasc_w3` | Loot: Korriban | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Ashen Forge Boots | `soulasc_l8` | Loot: Korriban | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Slagsmoke Mantle | `soulasc_l5` | Loot: Korriban | Def +15 · FDef +13 · HP +12 | — |
| Belt | Chaos Belt | `ch_belt` | Crafted (Smithery) | Def +15 · FDef +13 · HP +16 | Attack V + Attack V |
| Neck | Chaos Necklace | `ch_necklace` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Improved Synthmesh V |
| Ring | Molten Core Band | `soulasc_l6` | Loot: Korriban | Atk +12 · Def +9 · FDef +8 · HP +7 | — |
| Ring | Chaos Ring | `ch_ring` | Crafted (Smithery) | Def +15 · FDef +13 · HP +12 | Attack V + Attack V |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **STM V + STM Regen V** cooking enhancements.

**How they fight:** Soul Devourer Stance plus Soul Ascension (+20% Attack, lifesteal) turns him into a blender. Absolute Defense is his emergency button.

**How to beat them:** He pays HP to fight, so burst him while Soul Ascension's 10% HP cost is fresh.

**As an NPC:** L48 · Tough · Melee · Humanoid · High Damage
- HP 1264 · STM 117 · FP 20 · DMG 106 · Attack 26 · Force Attack 5 · Evasion 9 · Defense 58 · Force Defense 34 · Delay 250
- Attributes (MGT/PER/WIL/VIT/AGI) 39/32/22/32/32 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 9/-5/9/9/-5/9/10/9
- Abilities: Pouncing Strike, ⇄ **Serrated Slash** (replaces Rending Bite), Tail Sweep

---

#### 20. Captain Jeyra Okonn
*Human · Squad officer · Standard · **250/400 SP** (260/260 spent) · 25 AP*

A Republic captain in Decisive Command officer gear. She's the weakest fighter on the roster, but makes everyone around her better.

**Attributes**

| MGT | PER | VIT | WIL | AGI | SOC |
|---|---|---|---|---|---|
| 10 | 22 | 18 | 10 | 14 | 27* |

\* racial +1. 

**Skill ranks:** Leadership 50 · Rifle 50 · Armor 50 · Piloting 50 · First Aid 40 · Engineering 10

**Combat stats (naked → geared)**

| Stat | Naked | Geared | Stat | Geared |
|---|---|---|---|---|
| Max HP | 230 | **553** | Max STM | **43** |
| Attack (Rifle) | 130 | **162** | Accuracy (Rifle) | **122** |
| Evasion | 122 | **146** | Weapon DMG / delay | **40** / 300 |
| Physical Defense | 86 | **216** | Combat Readiness | **0%** |
| Force Defense | 78 | **178** | Regen / 30s (HP · STM) | 18 · 18 |

**Perks**

| Tree · Style | SP | Owned | Perks (highest rank owned) |
|---|---|---|---|
| Leadership · Vanguard Command | 55 | all | Rallying Standard II, Press the Attack III, Coordinated Focus III, Mark Target II, Charge Order II, Break Morale II, Command Presence II, Decisive Command |
| Leadership · Field Steward | 55 | all | Watchful Presence III, Rousing Shout III, Steady Formation II, Bolster Resolve II, Field Recovery II, Cleanse Order II, Triage Protocol II, Hold the Line |
| Rifle · Suppression | 60 | all | Suppressing Shot IV, Pinning Fire, Sustained Fire III, Crippling Shot III, Spotter's Rhythm, Suppressive Line II, Suppression Stance, Overwatch, Containment Net, Kill Box |
| General (Armor) · General | 32 | all | Provoke II, Dual Wield III, Alertness III, Doublehand III |
| First Aid · Trauma Medic | 39 | 13/17 | Med Kit III, Treatment Kit II, Medical Injector Rig II, Emergency Sealant, Kolto Mist II, Resuscitation II, Infusion I |
| Rifle · Marksman | 19 | 8/18 | Aimed Shot II, Steady Aim, Patience I, Piercing Round I, Scope Calibration, Headshot I, Breach Round |

**Equipment**

| Slot | Item | ID | Source | Stats | Enhancements |
|---|---|---|---|---|---|
| Main hand | Killbox Enforcer Rifle | `killbox_w1` | Loot: NarShaddaa | DMG 40 · Delay 300 · Atk +20 | — |
| Head | Warden's Command Helm | `deccommand_w4` | Loot: Viscara | Def +17 · FDef +11 · HP +64 · Ev +8 | — |
| Body | Command Deck Harness | `deccommand_w1` | Loot: Viscara | Def +30 · FDef +25 · HP +103 | — |
| Arms | Kill Lane Vambrace | `killbox_w3` | Loot: NarShaddaa | Atk +12 · Def +16 · FDef +10 · HP +60 | — |
| Feet | Deployable Ops Boots | `deccommand_l6` | Loot: Viscara | Def +14 · FDef +9 · HP +52 · STM +8 · Ev +8 | — |
| Cloak | Ops Center Mantle | `deccommand_l3` | Loot: Viscara | Def +15 · FDef +13 · HP +12 | — |
| Belt | Strategic Ops Sash | `deccommand_w2` | Loot: Viscara | Def +6 · FDef +5 · HP +7 · FP +5 · STM +10 · STM regen +2 | — |
| Neck | Warden's Ops Core | `deccommand_w5` | Loot: Viscara | Def +11 · FDef +9 · HP +9 · FP regen +2 · STM regen +2 | — |
| Ring | Chain of Command Band | `deccommand_l4` | Loot: Viscara | Def +12 · FDef +10 · HP +9 · STM regen +2 | — |
| Ring | Target Lock Band | `killbox_l6` | Loot: NarShaddaa | Def +9 · FDef +8 · HP +7 · Ev +8 | — |
| Off hand | Occupied by the two-handed or double weapon | | | | |

**Consumables:** L45+ meal with **STM V + STM Regen V** (ranged builds have small STM pools).

**How they fight:** She pops Decisive Command and Hold the Line on the group, then lays down Kill Box so the whole squad's shots stack Suppression.

**How to beat them:** In any group fight, kill her first.

**As an NPC:** L48 · Tough · Support · Humanoid · None
- HP 1413 · STM 81 · FP 102 · DMG 60 · Attack 17 · Force Attack 20 · Evasion 9 · Defense 57 · Force Defense 37 · Delay 310
- Attributes (MGT/PER/WIL/VIT/AGI) 22/32/39/32/22 · Resistances (Fire/Poison/Elec/Ice/Mind/Mobility/Trauma/Disruption) 9/-5/9/9/-5/9/10/9
- Abilities: Iron Carapace, ⇄ **Suppressing Shot** (replaces Savage Roar), Tactical Mark

---

## 5. Where to farm each loadout

| Zone | Themed sets that drop there | Fighters who want it |
|---|---|---|
| **Korriban** | Absolute Defense, Soul Ascension, Forcebane, Dark Hunger, Eclipse, Last Stand of the Light | Iskari, Kadd, Goss, Dun, Ondra |
| **Tatooine** | Dead Man's Hand, Last Word, Unmoving Center | Tal'ri, Hollis, Jory, Vaadosk |
| **Nar Shaddaa** | One Shot, Kill Box, Rain of Steel, plus Gunslinger Rig, Hexweave Shawl, Headwind Visor, Twin Blades | Asra, Neela, Mags, Jeyra, Ivo, Yuraan, Tal'ri, Jory |
| **Viscara** | Invincible, Decisive Command, Killzone Beacon, Emergency Bunker, the Vibroknife sets, plus Adrenal Pendant, Circle Mantle, Frame-Step / Black-Market Boots | Rhakar, Jeyra, Sevral, Mags, Hollis, Iskari |
| **Dantooine** | Infinite Conduit, Saber Cyclone, Saber Storm, Hold the Line, Emergency Cocktail | Oyen, Ivo, Hollis, Vaadosk |
| **Dathomir** | Alpha Rhythm (beast hunter) | Neela |
| **Hutlar** | Perfect Flurry, Overload Barrage, Thermal Detonator, plus Line-Calibration Visor | Raana, Rhakar, Mags, Yuraan, Jory |
| **CZ-220** | Adamantine Guard, Scrapheap Lockdown, Worldbreaker | Ruuchakk, Vaadosk |
| **Crafted** | Chaos, Magus, Chiro weapons, saber upgrade kits, all enhancements | Everyone |

---

## 6. Copy-ready NPC stat sheet

All values come from *Enemy Stat Presets* with the *Enemy Modifiers* row applied. This method reproduces the live Korriban NPCs exactly. Attributes are MGT/PER/WIL/VIT/AGI. Resistances are Fire/Poison/Electrical/Ice/Mind/Mobility/Trauma/Disruption.

| # | Name | Lvl | Diff | Role | Type | Modifier | Attributes | HP | STM | FP | DMG | Atk | FAtk | Ev | Def | FDef | Delay | Resistances |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Iskari Bel | 65 | Boss | Melee | Force User | Group Boss | 51/42/30/42/42 | 7878 | 322 | 56 | 228 | 50 | 23 | 14 | 77 | 47 | 240 | 15/14/15/15/19/-10/-15/20 |
| 2 | Kadd Orvaak | 58 | Elite | Tank | Humanoid | High Durability | 37/37/37/46/26 | 5684 | 175 | 58 | 78 | 23 | 1 | 9 | 83 | 52 | 340 | 14/-5/14/14/-5/14/15/14 |
| 3 | Tal'ri Venno | 62 | Boss | Ranged | Humanoid | Group Boss | 29/50/29/41/41 | 6619 | 268 | 67 | 208 | 49 | 23 | 16 | 74 | 46 | 260 | 14/-5/14/14/-5/14/15/14 |
| 4 | Oyen Duur | 58 | Elite | Support | Force User | None | 26/37/46/37/26 | 2857 | 121 | 151 | 77 | 22 | 25 | 12 | 72 | 46 | 300 | 13/12/13/13/17/-10/-15/18 |
| 5 | Asra Dhel'ka | 57 | Elite | Ranged | Humanoid | Glass Cannon | 26/45/26/37/37 | 1716 | 134 | 33 | 136 | 31 | 7 | 13 | 67 | 39 | 260 | 10/-5/10/10/-5/10/11/10 |
| 6 | Ruuchakk | 58 | Elite | Melee | Humanoid | High Durability | 46/37/26/37/37 | 4210 | 191 | 33 | 97 | 26 | 1 | 11 | 79 | 49 | 250 | 14/-5/14/14/-5/14/15/14 |
| 7 | Mags Tolver | 57 | Elite | Controller | Humanoid | None | 26/37/45/26/37 | 2494 | 104 | 134 | 81 | 22 | 24 | 14 | 70 | 46 | 290 | 12/-5/12/12/-5/12/13/12 |
| 8 | Ivo Carrick | 60 | Elite | Melee | Force User | Hard to Hit | 47/38/27/38/38 | 2683 | 179 | 31 | 100 | 28 | 2 | 21 | 79 | 49 | 240 | 13/12/13/13/17/-10/-15/18 |
| 9 | Rhakar | 55 | Elite | Melee | Humanoid | High Damage | 45/37/26/37/37 | 2371 | 166 | 29 | 128 | 30 | 6 | 12 | 72 | 42 | 240 | 11/-5/11/11/-5/11/12/11 |
| 10 | Dun Kehl | 55 | Elite | Controller | Humanoid | None | 26/37/45/26/37 | 2371 | 101 | 130 | 78 | 22 | 24 | 14 | 70 | 46 | 290 | 11/-5/11/11/-5/11/12/11 |
| 11 | Sevral | 54 | Elite | Melee | Humanoid | Glass Cannon | 44/36/25/36/36 | 1767 | 147 | 25 | 136 | 30 | 7 | 9 | 68 | 38 | 240 | 9/-5/9/9/-5/9/10/9 |
| 12 | Neela Ghoss & "Gutter" | 53 | Elite | Ranged | Humanoid | None | 25/43/25/35/35 | 2383 | 139 | 35 | 94 | 25 | 2 | 14 | 70 | 42 | 270 | 11/-5/11/11/-5/11/12/11 |
| 12b | Gutter (pet) | 53 | Tough | Melee | Beast | None | 42/34/24/34/34 | 1706 | 128 | 22 | 93 | 24 | 1 | 10 | 71 | 41 | 250 | −10/12/10/10/−15/13/14/−10 |
| 13 | Yuraan Sel | 52 | Tough | Melee | Humanoid | None | 42/34/24/34/34 | 1661 | 126 | 22 | 91 | 24 | 1 | 10 | 71 | 41 | 250 | 10/-5/10/10/-5/10/11/10 |
| 14 | Hollis Breck | 51 | Tough | Support | Humanoid | None | 23/33/41/33/23 | 1536 | 86 | 108 | 64 | 18 | 21 | 10 | 68 | 42 | 310 | 10/-5/10/10/-5/10/11/10 |
| 15 | Vaadosk | 51 | Tough | Tank | Humanoid | High Durability | 33/33/33/41/23 | 3056 | 124 | 42 | 65 | 19 | 0 | 7 | 79 | 48 | 350 | 12/-5/12/12/-5/12/13/12 |
| 16 | Ondra Pell | 50 | Tough | Force | Force User | None | 23/33/41/23/33 | 1337 | 48 | 132 | 80 | 18 | 24 | 11 | 67 | 45 | 300 | 11/10/11/11/15/-10/-15/16 |
| 17 | Jory Fass | 50 | Tough | Ranged | Humanoid | None | 23/41/23/33/33 | 1416 | 106 | 26 | 84 | 23 | 1 | 13 | 68 | 40 | 280 | 10/-5/10/10/-5/10/11/10 |
| 18 | Raana Tiv | 49 | Tough | Ranged | Humanoid | None | 23/40/23/33/33 | 1377 | 104 | 26 | 82 | 23 | 1 | 12 | 63 | 38 | 280 | 9/-5/9/9/-5/9/10/9 |
| 19 | Goss Durrant | 48 | Tough | Melee | Humanoid | High Damage | 39/32/22/32/32 | 1264 | 117 | 20 | 106 | 26 | 5 | 9 | 58 | 34 | 250 | 9/-5/9/9/-5/9/10/9 |
| 20 | Captain Jeyra Okonn | 48 | Tough | Support | Humanoid | None | 22/32/39/32/22 | 1413 | 81 | 102 | 60 | 17 | 20 | 9 | 57 | 37 | 310 | 9/-5/9/9/-5/9/10/9 |

---

## 7. Notes, assumptions and open decisions

1. **Ranged and caster builds have small STM pools** (25–43), because STM scales only with MGT. That's a real trade-off of the current formulas, not a build error. STM food or swapping a couple of enhancements for Zoosha Fabric V (+6 STM) eases it.
2. **Gear Attack counts for every weapon.** Swapping weapons changes only the weapon's own stats (DMG, its Attack, any enhancements). The rest of the loadout carries over.
3. **What the stats don't include:** temporary buffs (stances, Decisive Command and so on), Doublehand's DMG bonus, and food. They show the character standing still in full gear.
4. **Combat Readiness is capped at 15%.** Oyen sits exactly at the cap. Mags and Hollis are at 14%.
5. **NPC versions:** unchanged from v1, apart from the names. Tiers III and IV use Elite and Boss, which the Bible treats as group content. Drop one difficulty step for one-on-one fights. The NPC ability lists use the Bible's standard package plus its one approved swap.
6. **Modifier resistance bonus:** I applied High Durability's +2 and Glass Cannon's −2 only to positive resistances, leaving fixed weaknesses alone. Please confirm that's the intended rule.
7. **Names and characters are original.** Species and cultures are setting flavor. The names follow Old Republic conventions (short given name plus surname, single names for Wookiees, Cathar and Trandoshans, a Chiss core name), with no fantasy epithets.

## What changed from v1

- **All 20 fighters renamed.**
- **Sevral (was Nyx Varro):** v1 gave her 13 Might, but vibroknives use **Might for damage**. Her attributes are now MGT 26 / PER 27\* / VIT 18 / WIL 10 / AGI 19 / SOC 13.
- **Raana Tiv (was Kira Solune):** v1 had Armor 40, which locks out all L45+ armor. She's now Armor 50, with 10 ranks moved out of Agriculture.
- **Ranged builds** (Tal'ri, Asra, Mags, Jory, Raana) and **Captain Okonn:** spare Social moved into Vitality, or into Social itself for the officer, whose Leadership scales with it.
- **New:** full stat sheets, perk-by-perk lists, 10-slot loadouts with enhancements, weapon swaps and a farming guide.
