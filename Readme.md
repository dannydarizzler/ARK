# ARK: Survival Ascended — Server Documentation
**Patch V.2.0**

> This document serves as a reference for the server configuration, active mods, stat explanations, and loot drop contents.

---

## Table of Contents

1. [Active Mods](#1-active-mods)
2. [Player & Dino Stats](#2-player--dino-stats)
3. [Loot Drop Overview](#3-loot-drop-overview)
4. [Armor Tiers](#4-armor-tiers)
5. [Taming — Torpor Reference](#5-taming--torpor-reference)
6. [Admin Commands](#6-admin-commands)
7. [Server Settings](#7-server-settings)
8. [Class Reference](#8-class-reference)

---

## 1. Active Mods

| Mod | Description |
|-----|-------------|
| ARK Primal Chaos | Overhaul mod — fundamentally changes dinos, gameplay, and difficulty |
| Awesome Spyglass | Extended spyglass with stat display for dinos |
| Der Dino Finder | Helps locate all dinos on the map |
| Dino Depot | Dino management and storage |
| Better Breeding | Improved breeding UI and quality-of-life features |
| TG Stacking Mod 1000-50 | Increases stack sizes to 1000 (weight reduced by 50%) |
| A Simple Performance Mod (60 FPS) | Performance optimization for smoother gameplay |
| Crash Protector | Protects players from dinos and drowning when they crash |
| Tribute Table | Allows redeeming tribute items |

---

## 2. Player & Dino Stats

The `PerLevelStatsMultiplier` settings control how much a stat increases per level-up. They apply separately for players, tamed dinos, and wild dinos.

```
PerLevelStatsMultiplier_Player[ID]=Value
PerLevelStatsMultiplier_DinoTamed[ID]=Value
PerLevelStatsMultiplier_DinoWild[ID]=Value
```

### Stat Reference Table

| ID | Attribute | Default |
|----|-----------|---------|
| 0 | Health | 1.0 |
| 1 | Stamina | 1.0 |
| 2 | Torpidity | 1.0 |
| 3 | Oxygen | 1.0 |
| 4 | Food | 1.0 |
| 5 | Water | 1.0 |
| 6 | Temperature | 0.0 — not used |
| 7 | Weight | 1.0 |
| 8 | Melee Damage | 0.0 — base value, not increasable |
| 9 | Movement Speed | 0.0 — base value, not increasable |
| 10 | Temperature Fortitude | 0.0 — base value, not increasable |
| 11 | Crafting Speed | 0.0 — base value, not increasable |

---

## 3. Loot Drop Overview

Drops are structured progressively — the higher the drop color, the better the contents. Each color has a Normal and a Double variant (with ring). Flak armor is available **as Blueprint only** (no finished item). The weapon/tool slots in Blue, Yellow, and Red draw **1–5 random items** from a pool — not everything is guaranteed.

> **BP System:** Blueprints can **only appear in Double drops**. Each gear item in a Double drop pool has a **20% chance to be a Blueprint** instead of a finished item. Normal drops contain **no blueprints**.

> **Ragnarok-Wüste:** Deathsands/Green Desert nutzen andere Crate-Klassen (Scorched-Earth-System). Seit 2026-07-15 gibt es dafür zusätzliche, inhaltsgleiche Overrides — nur auf Ragnarok, siehe [Abschnitt 8](#8-class-reference).

### White — Starter Kit (fixed)
| Variant | Contents | Quality |
|---------|----------|---------|
| Normal | Toxic Hide Armor (5 pieces) + 10 Bolas + Toxic Pick + Toxic Hatchet + 10 Med Brews | Primitive |
| Double | Everything from Normal + Crossbow + 20 Potent Tranq Arrows + 1–3 Small XP Potions | Primitive |

### Green — Resources (fixed)
| Variant | Contents |
|---------|----------|
| Normal | 50–125× Polymer, Cementing Paste, Silica Pearls, Oil |
| Double | 75–200× Polymer, Cementing Paste, Silica Pearls, Oil |

### Blue — Alpha Tier (Pool: 3–8 / 3–11 Items)
Guaranteed: Potent/Alpha Tranq Arrows (15–35) · Alpha Health Potion (2–5) · Medium XP Potion (2–5)

**Gear Pool — Normal: item only | Double: 20% chance as Blueprint:**
Crossbow · Alpha Flak Helm · Alpha Flak Shirt · Alpha Flak Gloves · Alpha Flak Pants · Alpha Flak Boots · Alpha Pick · Alpha Hatchet · Alpha Sickle · Alpha Pike · Chainsaw

*Normal: 3–8 random items from pool (no BPs) · Double: 3–11 random items from pool (20% BP chance)*

### Purple — Structures (fixed)
| Variant | Contents |
|---------|----------|
| Normal | 10× Metal Foundation + 15× Metal Wall + 10× Metal Ceiling + Dino Gateway + Dino Gate |
| Double | 20× Metal Foundation + 30× Metal Wall + 20× Metal Ceiling + Dino Gateway + Dino Gate |

### Yellow — Volcanic Tier + Longneck (Pool: 3–8 Items)
Guaranteed (Normal): Tranq Dart random Elemental/Alpha/Potent (10–20) · Elemental ADV Sniper Bullets (8–16) · Large XP Potion (2–5) · Mythic Health Potion (1–5)

**Gear Pool — Normal:**
Longneck · Volcanic Flak Helm · Volcanic Flak Shirt · Volcanic Flak Gloves · Volcanic Flak Pants · Volcanic Flak Boots · Volcanic Pick · Volcanic Hatchet · Volcanic Sickle · Volcanic Pike · Chainsaw

**Gear Pool — Double (20% chance per item as Blueprint):**
Longneck · Volcanic Flak Helm · Volcanic Flak Shirt · Volcanic Flak Gloves · Volcanic Flak Pants · Volcanic Flak Boots · Volcanic Pick · Volcanic Hatchet · Volcanic Sickle · Volcanic Pike · Fab Sniper (Mastercraft) · Chainsaw

> Fab Sniper droppt nur in Double-Crates — im Normal-Pool nicht enthalten.

*Normal: 3–8 from pool (no BPs) · Double: Tranq Dart erhöht auf 15–35 + Guaranteed Elemental ADV Sniper Bullets (8–24) + 3–8 from pool (20% BP chance, keine Ausnahme für Chainsaw)*

### Red — Endgame Exclusives (Pool: 3–8 Items)
Guaranteed: Mythic/Primal ADV Sniper Bullets random (8–25) · Max XP Potion (1–2) · Nightmare Health Potion (1–2) · Primal Compound Bow Arrows (8–25)

**Gear Pool — Normal: item only | Double: 20% chance as Blueprint (keine Ausnahme für Chainsaw/Compound Bow):**
Fab Sniper · Mythic Flak Helm · Mythic Flak Shirt · Mythic Flak Gloves · Mythic Flak Pants · Mythic Flak Boots · Legend Riot Helm · Legend Riot Shirt · Legend Riot Gloves · Legend Riot Pants · Legend Riot Boots · Mythic Pick · Mythic Hatchet · Mythic Sickle · Mythic Pike · Chainsaw

*Normal: 3–8 from pool (no BPs) · Double: + Primal ADV Sniper Bullets guaranteed + Compound Bow zum Pool hinzugefügt (20% BP-Chance wie alle anderen Items) · 3–8 from pool*

### Boss Rewards (Element)

| Map | Boss | Gamma | Beta | Alpha |
|-----|------|-------|------|-------|
| Ragnarok | Nunatak (Ice Wyvern) | 250 | 500 | 1,000 |
| Valguero | Grendel | 250 | 500 | 1,000 |

---

## 4. Armor Tiers

All Primal Chaos flak armors drop **exclusively as Blueprints** (no finished item).

### Base Armor per Piece

| Tier | Base Armor |
|------|-----------|
| Alpha Flak | 500 |
| Volcanic Flak | 1,000 |
| Mythic Flak | 2,500 |
| Legend Riot | 3,000 |

### Mythic Flak — Bonuses (×4 on respective stat)

| Piece | Bonus |
|-------|-------|
| Helm | Food & Water |
| Chest | Weight |
| Gloves | Crafting Speed |
| Pants | Stamina |
| Boots | Fall Damage Reduction |

### Legend Riot — Bonuses

| Piece | Bonus |
|-------|-------|
| Helm | ×4 Health |
| Chest | ×4 Torpor Resistance |
| Gloves | ×4 Melee Damage |
| Pants | ×4 Stamina |
| Boots | +25% Movement Speed |

---

## 5. Taming — Torpor Reference

> Values measured on a Bronto at 100% weapon — varies by dino.  
> **Formula:** `Base Torpor × (Weapon % ÷ 100)`

### ADV Sniper Bullets (Fabricated Sniper)

| Type | Torpor |
|------|--------|
| Potent | 2,100 |
| Alpha | 4,600 |
| Elemental | 8,600 |
| Mythic | 13,000 |
| Primal | 20,800 |

### Tranq Darts (Longneck)

| Type | Torpor |
|------|--------|
| Potent | 1,900 |
| Alpha | 3,800 |
| Elemental | 7,400 |
| Mythic | 11,300 |

### Tranq Arrows (Crossbow)

| Type | Torpor |
|------|--------|
| Potent | 640 |
| Alpha | 1,200 |

---

## 6. Admin Commands

Cheats must first be activated with the password:
```
EnableCheats <Password>
```

| Command | Function |
|---------|----------|
| `admincheat DestroyWildDinos` | Kill all wild dinos (they respawn afterwards) |

---

## 7. Server Settings

### Engrams

**Aktuell (seit 2026-07-14):** `bAutoUnlockAllEngrams=True` in `GameUserSettings.ini` ([ServerSettings]) — alle Engramme werden automatisch mit dem jeweiligen Level freigeschaltet, kein manuelles Erlernen über Engram-Punkte nötig.

Die 105 `OverridePlayerLevelEngramPoints`-Zeilen (eine pro Level) wurden dafür aus beiden `Game.ini`-Dateien entfernt, da sie mit Auto-Unlock wirkungslos wären. In der `Game.ini` selbst steht dazu **kein** Kommentar/Vermerk (auf Wunsch entfernt, um jedes Risiko beim Parsen auszuschließen) — die vollständige Doku dazu lebt ausschließlich hier im Readme sowie in der Git-Historie.

<details>
<summary>Archiv: alte Engram-Punkte-Kurve (zum Wiederherstellen)</summary>

Smooth curve — early levels give fewer points, endgame scales moderately. **Total at max level (105): 9,200 points.**

| Level | Points/Level | Cumulative |
|-------|-------------|-----------|
| 1–10 | 30 | 300 |
| 11–20 | 50 | 800 |
| 21–50 | 60 | 2,600 |
| 51–60 | 80 | 3,400 |
| 61–70 | 100 | 4,400 |
| 71–90 | 120 | 6,800 |
| 91–100 | 150 | 8,300 |
| 101–105 | 180 | 9,200 |

**Zum Reaktivieren:** `bAutoUnlockAllEngrams=True` aus `GameUserSettings.ini` entfernen und für jedes Level (1–105) eine Zeile `OverridePlayerLevelEngramPoints=<Wert>` gemäß obiger Tabelle in `Game.ini` (nach `BabyImprintAmountMultiplier=10`) einfügen — in aufsteigender Level-Reihenfolge, ohne Lücken.

</details>

### Player Stats — Per Level-Up Multiplier

| Attribute | Multiplier | Note |
|-----------|-----------|------|
| Health | ×2.0 | |
| Stamina | ×2.0 | |
| Weight | ×10.0 | Very high — inventory rarely a problem |
| Melee Damage | ×2.0 | |
| Movement Speed | ×1.5 | Speed leveling active |
| Temp. Fortitude | ×5.0 | |
| Crafting Speed | ×20.0 | |
| Oxygen / Food / Water | ×1.0 | Default |

### Dino Stats — Tamed Dinos per Level-Up

| Attribute | Multiplier | Note |
|-----------|-----------|------|
| Health | ×1.0 | Default |
| Stamina | ×2.0 | |
| Weight | ×10.0 | Pack dinos carry a lot |
| All others | ×1.0 | Default |

> Wild dinos stay at default (×1.0) — maximum difficulty active.

### Breeding

| Setting | Value | Meaning |
|---------|-------|---------|
| Mating Interval | ×0.1 | Very fast |
| Egg Hatching | ×40 | Very fast |
| Baby Maturing | ×40 | Very fast |
| Imprint Amount | ×10 | 100% imprint in a few cuddles |
| Egg Laying Interval | ×0.25 | Eggs come frequently |

### XP Multipliers

| Source | Multiplier |
|--------|-----------|
| All XP sources | ×3 |

### World & Gameplay

| Setting | Value | Meaning |
|---------|-------|---------|
| Harvest Amount | ×5 | |
| Loot Quality Drops | ×1 | Default |
| Loot Quality Fishing | ×4 | |
| Crafting Skill Bonus | ×5 | |
| Custom Recipe Skill | ×10 | |
| Structure Damage (PvP) | ×6 | Raiding is significantly faster |
| Turret Damage | ×2.5 | |
| Respawn Interval | Active | Increases with each death |
| Flyer Speed Leveling | Disabled | |
| Structure Collision | Disabled | Free building without clip errors |
| Corpse Locator | Active | Corpse visible on map |
| Unlimited Respecs | Active | Reset engram points at any time |
| Auto Unlock All Engrams | Active | Alle Engramme werden automatisch pro Level freigeschaltet |

---

## 8. Class Reference

All known item class strings for `ConfigOverrideSupplyCrateItems` in Game.ini.

> **Blueprint:** `bForceBlueprint=true` makes any item entry a Blueprint.  
> **Quality:** `MinQuality`/`MaxQuality` — 0.0 = Primitive, 0.3 = Journeyman, 0.4 = Masterwork, 0.5+ = Ascendant.

---

### Drop Class Strings (Supply Crates)

| Color | Normal | Double (with Ring) |
|-------|--------|-------------------|
| White | `SupplyCrate_Level03_C` | `SupplyCrate_Level03_Double_C` |
| Green | `SupplyCrate_Level15_C` | `SupplyCrate_Level15_Double_C` |
| Blue | `SupplyCrate_Level25_C` | `SupplyCrate_Level25_Double_C` |
| Purple | `SupplyCrate_Level35_C` | `SupplyCrate_Level35_Double_C` |
| Yellow | `SupplyCrate_Level45_C` | `SupplyCrate_Level45_Double_C` |
| Red | `SupplyCrate_Level60_C` | `SupplyCrate_Level60_Double_C` |

### Ragnarok — Wüsten-Drops (Scorched-Earth-Klassen)

**Nur in `Nitrado settings/Ragnarok/Game.ini`** (Stand 2026-07-15) — Valguero hat kein Cluster-Sync und wurde noch nicht angepasst.

Ragnarok nutzt für die Deathsands/Green Desert eigene Supply-Crate-Klassen aus dem Scorched-Earth-Loot-System (`SupplyCrate_LevelXX_ScorchedEarth_C`), die von den Island-Klassen (`SupplyCrate_LevelXX_C`) nicht erfasst werden. Deshalb gibt es pro Farbe eine zusätzliche Zeile mit identischem Inhalt, nur der Class-String ist getauscht. SE nutzt andere Level-Stufen (03/15/30/45/55/70 statt 03/15/25/35/45/60) — Blau läuft daher auf SE-Stufe 30, Rot auf SE-Stufe 55.

| Farbe | Normal (SE) | Double (SE) |
|-------|--------|-------------------|
| White | `SupplyCrate_Level03_ScorchedEarth_C` | `SupplyCrate_Level03_Double_ScorchedEarth_C` |
| Green | `SupplyCrate_Level15_ScorchedEarth_C` | `SupplyCrate_Level15_Double_ScorchedEarth_C` |
| Blue | `SupplyCrate_Level30_ScorchedEarth_C` | `SupplyCrate_Level30_Double_ScorchedEarth_C` |
| Yellow | `SupplyCrate_Level45_ScorchedEarth_C` | `SupplyCrate_Level45_Double_ScorchedEarth_C` |
| Red | `SupplyCrate_Level55_ScorchedEarth_C` | `SupplyCrate_Level55_Double_ScorchedEarth_C` |
| Red (Level70) | `SupplyCrate_Level70_ScorchedEarth_C` | `SupplyCrate_Level70_Double_ScorchedEarth_C` |

> **Level70** ist die höchste SE-Stufe (kein Island-Äquivalent) — bekommt 1:1 denselben Loot wie Rot (Level60/55).
> **Purple (Strukturen, Level35)** hat kein SE-Äquivalent und wurde bewusst weggelassen — in der Wüste droppen keine Struktur-Crates.

### Ragnarok — Rote Wüstenkisten & Deep-Sea-Crates (Level 80)

**Nur in `Nitrado settings/Ragnarok/Game.ini`** (Stand 2026-07-15) — Valguero noch nicht angepasst.

Die kleinen roten Kisten in der Ragnarok-Wüste (Lvl-80-Anforderung) sind technisch Deep-Sea-Loot-Crates, keine Sky-Drops — eigener Class-String, von den obigen Overrides nicht erfasst. Gleiche Klasse wird auch für normale Deep-Sea-Crates im Ozean verwendet.

| Kiste | Class String |
|-------|--------------|
| Wüsten-Kiste (Ragnarok-Wüste) | `SupplyCrate_OceanInstant_High_C` |
| Deep-Sea-Crate (Ozean) | `SupplyCrate_OceanInstant_C` |

**Inhalt (beide Klassen identisch):** Immer genau **3 zufällige, garantierte Blueprints** (`bForceBlueprint=true`, keine 20%-Chance wie bei den anderen Double-Drops) aus einem gemeinsamen Pool von **37 Items** — alle Gear-Items, die auch in den Blue/Yellow/Red-Double-Pools als Blueprint droppen können (Alpha-, Volcanic-, Mythic-, Legend-Riot-Tier, Fab Sniper, Compound Bow, Chainsaw).

> **Verifikation empfohlen:** Falls die Kisten weiterhin unmoddeten Loot zeigen, stimmt der Class-String u. U. nicht exakt für ASA — vor dem produktiven Einsatz mit einem auffälligen Test-Item (z. B. 100× Thatch) im Pool gegenchecken, ob der Override überhaupt greift.

---

### Primal Chaos — XP Potions

| Item | Class Name |
|------|-----------|
| Small XP Potion | `PrimalItemConsumable_XPSmall_C` |
| Medium XP Potion | `PrimalItemConsumable_XPMedium_C` |
| Large XP Potion | `PrimalItemConsumable_XPLarge_C` |
| Max XP Potion | `PrimalItemConsumable_MaxXP_C` |

### Primal Chaos — Health Potions

| Item | Class Name |
|------|-----------|
| Toxic Health Potion | `PrimalItemConsumable_ToxicHealthPotion_C` |
| Alpha Health Potion | `PrimalItemConsumable_AlphaHealthPotion_C` |
| Mythic Health Potion | `PrimalItemConsumable_MythicHealthPotion_C` |
| Nightmare Health Potion | `PrimalItemConsumable_NightmareHealthPotion_C` |

---

### Primal Chaos — ADV Sniper Bullets

| Item | Class Name |
|------|-----------|
| Potent ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Potent_C` |
| Alpha ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Alpha_C` |
| Elemental ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Elemental_C` |
| Mythic ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Mythic_C` |
| Primal ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Primal_C` |

### Primal Chaos — Tranq Arrows

| Item | Class Name |
|------|-----------|
| Toxic Tranq Arrow | `PrimalItemAmmo_ArrowTranq_Toxic_C` |
| Alpha Tranq Arrow | `PrimalItemAmmo_ArrowTranq_Alpha_C` |
| Potent Tranq Arrow | `PrimalItemAmmo_ArrowTranq_Potent_C` |

### Primal Chaos — Tranq Darts

| Item | Class Name |
|------|-----------|
| Potent Tranq Dart | `PrimalItemAmmo_TranqDart_Potent_C` |
| Alpha Tranq Dart | `PrimalItemAmmo_TranqDart_Alpha_C` |
| Elemental Tranq Dart | `PrimalItemAmmo_TranqDart_Element_C` |
| Mythic Tranq Dart | `PrimalItemAmmo_TranqDart_Mythic_C` |

### Primal Chaos — Compound Bow Arrows

| Item | Class Name |
|------|-----------|
| Potent Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Potent_C` |
| Alpha Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Alpha_C` |
| Elemental Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Elemental_C` |
| Mythic Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Mythic_C` |
| Primal Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Primal_C` |

---

### Primal Chaos — Flak Armor (Alpha Tier)

| Item | Class Name |
|------|-----------|
| Alpha Metal Helm | `PrimalItemArmor_MetalHelmet_Alpha_C` |
| Alpha Metal Shirt | `PrimalItemArmor_MetalShirt_Alpha_C` |
| Alpha Metal Gloves | `PrimalItemArmor_MetalGloves_Alpha_C` |
| Alpha Metal Pants | `PrimalItemArmor_MetalPants_Alpha_C` |
| Alpha Metal Boots | `PrimalItemArmor_MetalBoots_Alpha_C` |

### Primal Chaos — Flak Armor (Volcanic/Elemental Tier)

| Item | Class Name |
|------|-----------|
| Volcanic Metal Helm | `PrimalItemArmor_MetalHelmet_Volcanic_C` |
| Volcanic Metal Shirt | `PrimalItemArmor_MetalShirt_Volcanic_C` |
| Volcanic Metal Gloves | `PrimalItemArmor_MetalGloves_Volcanic_C` |
| Volcanic Metal Pants | `PrimalItemArmor_MetalPants_Volcanic_C` |
| Volcanic Metal Boots | `PrimalItemArmor_MetalBoots_Volcanic_C` |

### Primal Chaos — Flak Armor (Mythic Tier)

| Item | Class Name |
|------|-----------|
| Mythic Metal Helm | `PrimalItemArmor_MetalHelmet_Mythic_C` |
| Mythic Metal Shirt | `PrimalItemArmor_MetalShirt_Mythic_C` |
| Mythic Metal Gloves | `PrimalItemArmor_MetalGloves_Mythic_C` |
| Mythic Metal Pants | `PrimalItemArmor_MetalPants_Mythic_C` |
| Mythic Metal Boots | `PrimalItemArmor_MetalBoots_Mythic_C` |

---

### Primal Chaos — Riot Armor (Legend Tier)

| Item | Class Name |
|------|-----------|
| Legend Riot Helm | `PrimalItemArmor_RiotHelmet_Legend_C` |
| Legend Riot Shirt | `PrimalItemArmor_RiotShirt_Legend_C` |
| Legend Riot Gloves | `PrimalItemArmor_RiotGloves_Legend_C` |
| Legend Riot Pants | `PrimalItemArmor_RiotPants_Legend_C` |
| Legend Riot Boots | `PrimalItemArmor_RiotBoots_Legend_C` |

---

### Primal Chaos — Hide Toxic Armor (Starter Tier)

| Item | Class Name |
|------|-----------|
| Toxic Hide Helm | `PrimalItemArmor_HideHelmet_Toxic_C` |
| Toxic Hide Shirt | `PrimalItemArmor_HideShirt_Toxic_C` |
| Toxic Hide Gloves | `PrimalItemArmor_HideGloves_Toxic_C` |
| Toxic Hide Pants | `PrimalItemArmor_HidePants_Toxic_C` |
| Toxic Hide Boots | `PrimalItemArmor_HideBoots_Toxic_C` |

---

### Primal Chaos — Tools (Metal Pick)

| Tier | Class Name |
|------|-----------|
| Toxic | `PrimalItem_WeaponMetalPick_Toxic_C` |
| Alpha | `PrimalItem_WeaponMetalPick_Alpha_C` |
| Volcanic | `PrimalItem_WeaponMetalPick_Volcanic_C` |
| Mythic | `PrimalItem_WeaponMetalPick_Mythic_C` |

### Primal Chaos — Tools (Metal Hatchet)

| Tier | Class Name |
|------|-----------|
| Toxic | `PrimalItem_WeaponMetalHatchet_Toxic_C` |
| Alpha | `PrimalItem_WeaponMetalHatchet_Alpha_C` |
| Volcanic | `PrimalItem_WeaponMetalHatchet_Volcanic_C` |
| Mythic | `PrimalItem_WeaponMetalHatchet_Mythic_C` |

### Primal Chaos — Tools (Sickle)

| Tier | Class Name |
|------|-----------|
| Toxic | `PrimalItem_WeaponSickle_Toxic_C` |
| Alpha | `PrimalItem_WeaponSickle_Alpha_C` |
| Volcanic | `PrimalItem_WeaponSickle_Volcanic_C` |
| Mythic | `PrimalItem_WeaponSickle_Mythic_C` |

### Primal Chaos — Tools (Pike)

| Tier | Class Name |
|------|-----------|
| Toxic | `PrimalItem_WeaponPike_Toxic_C` |
| Alpha | `PrimalItem_WeaponPike_Alpha_C` |
| Volcanic | `PrimalItem_WeaponPike_Volcanic_C` |
| Mythic | `PrimalItem_WeaponPike_Mythic_C` |

### Primal Chaos — Resources

| Item | Class Name |
|------|-----------|
| Element Metal Ingot | `PrimalItemResource_MetalIngot_Element_C` |
| Toxic Metal Ingot | `PrimalItemResource_MetalIngot_Toxic_C` |
| Alpha Metal Ingot | `PrimalItemResource_MetalIngot_Alpha_C` |
| Mythic Metal Ingot | `PrimalItemResource_MetalIngot_Mythic_C` |

### Primal Chaos — Structures

| Item | Class Name |
|------|-----------|
| Chaos Bed | `PrimalItemStructure_ChaosBed_C` |
| Chaos Forge | `PrimalItemStructure_Forge_Chaos_C` |
| Chaos Anvil Bench | `PrimalItemStructure_AnvilBench_Chaos_C` |
| Metal Spike Wall Toxic | `PrimalItemStructure_MetalSpikeWall_Toxic_C` |
| Metal Spike Wall Alpha | `PrimalItemStructure_MetalSpikeWall_Alpha_C` |
| Metal Spike Wall Mythic | `PrimalItemStructure_MetalSpikeWall_Mythic_C` |

---

### Vanilla ASA — Weapons

| Item | Class Name |
|------|-----------|
| Fabricated Sniper Rifle | `PrimalItem_WeaponMachinedSniper_C` |
| Longneck Rifle | `PrimalItem_WeaponOneShotRifle_C` |
| Crossbow | `PrimalItem_WeaponCrossbow_C` |
| Pump-Action Shotgun | `PrimalItem_WeaponShotgun_C` |
| Compound Bow | `PrimalItem_WeaponCompoundBow_C` |
| Pike | `PrimalItem_WeaponPike_C` |
| Sickle | `PrimalItem_WeaponSickle_C` |
| Bola | `PrimalItem_WeaponBola_C` |
| Metal Pick | `PrimalItem_WeaponMetalPick_C` |
| Metal Hatchet | `PrimalItem_WeaponMetalHatchet_C` |

### Vanilla ASA — Ammo & Consumables

| Item | Class Name |
|------|-----------|
| ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_C` |
| Tranq Arrow | `PrimalItemAmmo_ArrowTranq_C` |
| Flame Arrow | `PrimalItemAmmo_ArrowFlame_C` |
| Med Brew | `PrimalItemConsumable_HealSoup_C` |

### Vanilla ASA — Flak Armor

| Item | Class Name |
|------|-----------|
| Metal Helm | `PrimalItemArmor_MetalHelmet_C` |
| Metal Shirt | `PrimalItemArmor_MetalShirt_C` |
| Metal Gloves | `PrimalItemArmor_MetalGloves_C` |
| Metal Pants | `PrimalItemArmor_MetalPants_C` |
| Metal Boots | `PrimalItemArmor_MetalBoots_C` |

### Vanilla ASA — Resources

| Item | Class Name |
|------|-----------|
| Polymer | `PrimalItemResource_Polymer_C` |
| Cementing Paste | `PrimalItemResource_ChitinPaste_C` |
| Silica Pearls | `PrimalItemResource_Silicon_C` |
| Oil | `PrimalItemResource_Oil_C` |
| Thatch — Filler for random slots | `PrimalItemResource_Thatch_C` |

### Vanilla ASA — Structures

| Item | Class Name |
|------|-----------|
| Metal Foundation | `PrimalItemStructure_MetalFloor_C` |
| Metal Wall | `PrimalItemStructure_MetalWall_C` |
| Metal Ceiling | `PrimalItemStructure_MetalCeiling_C` |
| Dino Gateway (Frame) | `PrimalItemStructure_MetalGateframe_C` |
| Dino Gate (Door) | `PrimalItemStructure_MetalGate_C` |
| Dedicated Storage | `PrimalItemStructure_DedicatedStorage_C` |
| Industrial Forge | `PrimalItemStructure_IndustrialForge_C` |
| Industrial Grinder | `PrimalItemStructure_Grinder_C` |
