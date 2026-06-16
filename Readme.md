# ARK: Survival Ascended — Server Dokumentation

> Dieses Dokument dient als Referenz für die Serverkonfiguration, aktive Mods, Stat-Erklärungen und die Inhalte der Loot Drops.

---

## Inhaltsverzeichnis

1. [Aktive Mods](#1-aktive-mods)
2. [Spieler & Dino Stats](#2-spieler--dino-stats)
3. [Loot Drop Übersicht](#3-loot-drop-übersicht)
4. [Admin Commands](#4-admin-commands)
5. [Server Einstellungen](#5-server-einstellungen)
6. [Klassen-Referenz](#6-klassen-referenz)

---

## 1. Aktive Mods

| Mod | Beschreibung |
|-----|-------------|
| ARK Primal Chaos | Overhaul-Mod — verändert Dinos, Gameplay und Schwierigkeitsgrad grundlegend |
| Awesome Spyglass | Erweitertes Fernglas mit Stat-Anzeige für Dinos |
| Dino Depot | Dino-Verwaltung und Lagerung |
| A Simple Performance Mod (60 FPS) | Performance-Optimierung für flüssigeres Gameplay |
| Tribute Table | Ermöglicht das Einlösen von Tribute-Items |
| Der Dino Finder | Hilft beim Auffinden aller Dinos auf der Map |
| TG Stacking Mod 1000-50 | Erhöht Stack-Grössen auf 1000 (Gewicht ist um 50% reduziert) |
| Crash Protector | Schützt Spieler wenn sie crashen |
| Upgrade Station | Ermöglicht das Upgraden von Items auf höhere Qualitätsstufen |

---

## 2. Spieler & Dino Stats

Die `PerLevelStatsMultiplier`-Einstellungen steuern, wie stark ein Stat pro Level-Up zunimmt. Sie gelten separat für Spieler, gezähmte Dinos und wilde Dinos.

```
PerLevelStatsMultiplier_Player[ID]=Wert
PerLevelStatsMultiplier_DinoTamed[ID]=Wert
PerLevelStatsMultiplier_DinoWild[ID]=Wert
```

### Stat-Referenztabelle

| ID | Attribut | Standard |
|----|----------|---------|
| 0 | Health (Leben) | 1.0 |
| 1 | Stamina (Ausdauer) | 1.0 |
| 2 | Torpidity (Betäubung) | 1.0 |
| 3 | Oxygen (Sauerstoff) | 1.0 |
| 4 | Food (Nahrung) | 1.0 |
| 5 | Water (Wasser) | 1.0 |
| 6 | Temperature (Temperatur) | 0.0 — nicht verwendet |
| 7 | Weight (Gewicht) | 1.0 |
| 8 | Melee Damage | 0.0 — Basiswert, nicht erhöhbar |
| 9 | Movement Speed | 0.0 — Basiswert, nicht erhöhbar |
| 10 | Temperature Fortitude | 0.0 — Basiswert, nicht erhöhbar |
| 11 | Crafting Speed | 0.0 — Basiswert, nicht erhöhbar |

---

## 3. Loot Drop Übersicht

Die Drops sind progressiv aufgebaut — je höher die Drop-Farbe, desto besser der Inhalt. Jede Farbe hat eine Normal- und eine Double-Variante (mit Ring). Flak-Rüstung gibt es **nur als Blueprint** (kein fertiges Item). Die Waffen-/Tool-Slots in Blau, Gelb und Rot ziehen **zufällig 1–5 Items** aus einem Pool — nicht alles ist garantiert.

> **BP-System (Blau/Gelb/Rot):** Jedes Item im Gear-Pool hat **85% Chance als fertiger Gegenstand** und **15% Chance als Blueprint**. Pro Drop werden **3–10 Items** zufällig aus dem Pool gezogen (Double: 5–10).

### Weiß — Starter Kit (fix)
| Variante | Inhalt | Qualität |
|----------|--------|----------|
| Normal | Hide Toxic Rüstung (5 Teile) + 10 Bolas + Metal Pick + Metal Hatchet + 10 Med Brews | Primitiv |
| Double | Alles aus Normal + Crossbow + 25 Tranq Arrows + 1–3 Small XP Potions | Primitiv |

### Grün — Ressourcen (fix)
| Variante | Inhalt |
|----------|--------|
| Normal | 75–175× Polymer, Zement (Cementing Paste), Siliziumperlen, Öl |
| Double | 125–250× Polymer, Zement, Siliziumperlen, Öl |

### Blau — Alpha Tier (Pool: 3–8 / 5–10 Items)
Garantiert: Potent/Alpha Tranq Arrows (15–35) · Alpha Health Potion (2–5) · Medium XP Potion (2–5)

**Gear-Pool — jedes Item: 85% als Gegenstand / 15% als Blueprint:**
Crossbow · Alpha Flak Helm · Alpha Flak Shirt · Alpha Flak Gloves · Alpha Flak Pants · Alpha Flak Boots · Alpha Pick · Alpha Hatchet · Alpha Sickle · Alpha Pike

*Normal: 3–8 zufällige Items aus dem Pool · Double: 5–10 zufällige Items*

### Lila — Strukturen (fix)
| Variante | Inhalt |
|----------|--------|
| Normal | 10× Metal Foundation + 15× Metal Wall + 10× Metal Ceiling + Dino Gateway + Dino Gate + 3× Dedicated Storage |
| Double | 20× Metal Foundation + 30× Metal Wall + 20× Metal Ceiling + Dino Gateway + Dino Gate + 5× Dedicated Storage |

### Gelb — Volcanic Tier + Longneck (Pool: 3–8 / 5–10 Items)
Garantiert: Tranq Dart zufällig Elemental/Alpha/Potent (15–35) · Elemental ADV Sniper Bullets (8–25) · Large XP Potion (2–5) · Mythic Health Potion (1–5)

**Gear-Pool — jedes Item: 85% als Gegenstand / 15% als Blueprint:**
Longneck · Volcanic Flak Helm · Volcanic Flak Shirt · Volcanic Flak Gloves · Volcanic Flak Pants · Volcanic Flak Boots · Volcanic Pick · Volcanic Hatchet · Volcanic Sickle · Volcanic Pike

*Normal: 3–8 aus Pool (10 Items) · Double: 5–10 aus Pool (11 Items, + Fab Sniper Mastercraft) + Elemental Compound Bow Arrows garantiert*

### Rot — Endgame Exclusives (Pool: 3–8 / 5–10 Items)
Garantiert: Mythic/Primal ADV Sniper Bullets zufällig (8–25) · Max XP Potion (1–2) · Nightmare Health Potion (1–2)

**Gear-Pool — jedes Item: 85% als Gegenstand / 15% als Blueprint:**
Fab Sniper · Mythic Flak Helm · Mythic Flak Shirt · Mythic Flak Gloves · Mythic Flak Pants · Mythic Flak Boots · Legend Riot Helm · Legend Riot Shirt · Legend Riot Gloves · Legend Riot Pants · Legend Riot Boots

*Normal: 3–8 aus Pool (11 Items) · Double: 5–10 aus Pool + Primal ADV Sniper Bullets garantiert*



---

## 4. Admin Commands

Cheats müssen zuerst mit dem Passwort aktiviert werden:
```
EnableCheats <Passwort>
```

| Command | Funktion |
|---------|----------|
| `admincheat DestroyWildDinos` | Alle wilden Dinos töten (spawnen danach neu) |

---

## 5. Server Einstellungen

### Spieler Stats — pro Level-Up Multiplikator

| Attribut | Multiplikator | Hinweis |
|----------|--------------|---------|
| Health | ×2.0 | |
| Stamina | ×2.0 | |
| Weight | ×10.0 | sehr hoch — Inventar kaum ein Problem |
| Melee Damage | ×2.0 | |
| Movement Speed | ×2.0 | Speed-Leveling aktiv |
| Temp. Fortitude | ×5.0 | |
| Crafting Speed | ×50.0 | |
| Oxygen / Food / Water | ×1.0 | Standard |

### Dino Stats — gezähmte Dinos pro Level-Up

| Attribut | Multiplikator | Hinweis |
|----------|--------------|---------|
| Health | ×1.0 | Standard |
| Stamina | ×2.0 | |
| Weight | ×10.0 | Lastdinos tragen viel |
| Alle anderen | ×1.0 | Standard |

> Wilde Dinos bleiben auf Standard (×1.0) — maximale Schwierigkeit aktiv.

### Breeding

| Einstellung | Wert | Bedeutung |
|-------------|------|-----------|
| Paarungsintervall | ×0.1 | sehr schnell |
| Ei schlüpfen | ×40 | sehr schnell |
| Baby aufwachsen | ×40 | sehr schnell |
| Imprint-Menge | ×10 | 100 % Imprint in wenigen Cuddles |
| Ei-Legeintervall | ×0.25 | Eier kommen häufig |

### XP Multiplikatoren

| Quelle | Multiplikator |
|--------|--------------|
| Alle XP-Quellen | ×3 |

### Welt & Gameplay

| Einstellung | Wert | Bedeutung |
|-------------|------|-----------|
| Harvest-Menge | ×5 | |
| Loot-Qualität Drops | ×1 | Standard |
| Loot-Qualität Fischen | ×4 | |
| Crafting Skill Bonus | ×25 | Handwerk lohnt sich stark |
| Custom Recipe Skill | ×10 | |
| Struktur-Schaden (PvP) | ×6 | Raiding geht deutlich schneller |
| Turret-Schaden | ×2.5 | |
| Respawn Interval | aktiv | erhöht sich mit jedem Tod |
| Flyer Speed-Leveling | deaktiviert | |
| Struktur-Kollision | deaktiviert | freies Bauen ohne Clip-Fehler |
| Corpse Locator | aktiv | Leiche auf der Karte sichtbar |
| Unlimited Respecs | aktiv | Engram-Punkte jederzeit zurücksetzen |

---

## 6. Klassen-Referenz

Alle bekannten Item Class Strings für `ConfigOverrideSupplyCrateItems` in der Game.ini.

> **Blueprint:** `bForceBlueprint=true` macht jeden Item-Eintrag zum Blueprint.  
> **Qualität:** `MinQuality`/`MaxQuality` — 0.0 = Primitiv, 0.3 = Journeyman, 0.4 = Meisterwerk, 0.5+ = Aufgestiegen.

---

### Drop Class Strings (Supply Crates)

| Farbe | Normal | Double (mit Ring) |
|-------|--------|-------------------|
| Weiß | `SupplyCrate_Level03_C` | `SupplyCrate_Level03_Double_C` |
| Grün | `SupplyCrate_Level15_C` | `SupplyCrate_Level15_Double_C` |
| Blau | `SupplyCrate_Level25_C` | `SupplyCrate_Level25_Double_C` |
| Lila | `SupplyCrate_Level35_C` | `SupplyCrate_Level35_Double_C` |
| Gelb | `SupplyCrate_Level45_C` | `SupplyCrate_Level45_Double_C` |
| Rot | `SupplyCrate_Level60_C` | `SupplyCrate_Level60_Double_C` |

---

### Primal Chaos — XP Tränke

| Item | Klassenname |
|------|-------------|
| Small XP Potion | `PrimalItemConsumable_XPSmall_C` |
| Medium XP Potion | `PrimalItemConsumable_XPMedium_C` |
| Large XP Potion | `PrimalItemConsumable_XPLarge_C` |
| Max XP Potion | `PrimalItemConsumable_MaxXP_C` |

### Primal Chaos — Gesundheitstränke

| Item | Klassenname |
|------|-------------|
| Toxic Health Potion | `PrimalItemConsumable_ToxicHealthPotion_C` |
| Alpha Health Potion | `PrimalItemConsumable_AlphaHealthPotion_C` |
| Mythic Health Potion | `PrimalItemConsumable_MythicHealthPotion_C` |
| Nightmare Health Potion | `PrimalItemConsumable_NightmareHealthPotion_C` |

---

### Primal Chaos — ADV Sniper Bullets

| Item | Klassenname |
|------|-------------|
| Potent ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Potent_C` |
| Alpha ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Alpha_C` |
| Elemental ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Elemental_C` |
| Mythic ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Mythic_C` |
| Primal ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_Primal_C` |

### Primal Chaos — Tranq Arrows

| Item | Klassenname |
|------|-------------|
| Toxic Tranq Arrow | `PrimalItemAmmo_ArrowTranq_Toxic_C` |
| Alpha Tranq Arrow | `PrimalItemAmmo_ArrowTranq_Alpha_C` |
| Potent Tranq Arrow | `PrimalItemAmmo_ArrowTranq_Potent_C` |

### Primal Chaos — Tranq Darts

| Item | Klassenname |
|------|-------------|
| Potent Tranq Dart | `PrimalItemAmmo_TranqDart_Potent_C` |
| Alpha Tranq Dart | `PrimalItemAmmo_TranqDart_Alpha_C` |
| Elemental Tranq Dart | `PrimalItemAmmo_TranqDart_Element_C` |
| Mythic Tranq Dart | `PrimalItemAmmo_TranqDart_Mythic_C` |

### Primal Chaos — Compound Bow Arrows

| Item | Klassenname |
|------|-------------|
| Potent Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Potent_C` |
| Alpha Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Alpha_C` |
| Elemental Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Elemental_C` |
| Mythic Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Mythic_C` |
| Primal Compound Bow Arrow | `PrimalItemAmmo_CompoundBowArrow_Primal_C` |

---

### Primal Chaos — Flak Rüstung (Alpha-Tier)

| Item | Klassenname |
|------|-------------|
| Alpha Metal Helm | `PrimalItemArmor_MetalHelmet_Alpha_C` |
| Alpha Metal Shirt | `PrimalItemArmor_MetalShirt_Alpha_C` |
| Alpha Metal Handschuhe | `PrimalItemArmor_MetalGloves_Alpha_C` |
| Alpha Metal Hose | `PrimalItemArmor_MetalPants_Alpha_C` |
| Alpha Metal Stiefel | `PrimalItemArmor_MetalBoots_Alpha_C` |

### Primal Chaos — Flak Rüstung (Volcanic/Elemental-Tier)

| Item | Klassenname |
|------|-------------|
| Volcanic Metal Helm | `PrimalItemArmor_MetalHelmet_Volcanic_C` |
| Volcanic Metal Shirt | `PrimalItemArmor_MetalShirt_Volcanic_C` |
| Volcanic Metal Handschuhe | `PrimalItemArmor_MetalGloves_Volcanic_C` |
| Volcanic Metal Hose | `PrimalItemArmor_MetalPants_Volcanic_C` |
| Volcanic Metal Stiefel | `PrimalItemArmor_MetalBoots_Volcanic_C` |

### Primal Chaos — Flak Rüstung (Mythic-Tier)

| Item | Klassenname |
|------|-------------|
| Mythic Metal Helm | `PrimalItemArmor_MetalHelmet_Mythic_C` |
| Mythic Metal Shirt | `PrimalItemArmor_MetalShirt_Mythic_C` |
| Mythic Metal Handschuhe | `PrimalItemArmor_MetalGloves_Mythic_C` |
| Mythic Metal Hose | `PrimalItemArmor_MetalPants_Mythic_C` |
| Mythic Metal Stiefel | `PrimalItemArmor_MetalBoots_Mythic_C` |

---

### Primal Chaos — Riot Rüstung (Legend-Tier)

| Item | Klassenname |
|------|-------------|
| Legend Riot Helm | `PrimalItemArmor_RiotHelmet_Legend_C` |
| Legend Riot Shirt | `PrimalItemArmor_RiotShirt_Legend_C` |
| Legend Riot Handschuhe | `PrimalItemArmor_RiotGloves_Legend_C` |
| Legend Riot Hose | `PrimalItemArmor_RiotPants_Legend_C` |
| Legend Riot Stiefel | `PrimalItemArmor_RiotBoots_Legend_C` |

---

### Primal Chaos — Hide Toxic Rüstung (Starter-Tier)

| Item | Klassenname |
|------|-------------|
| Toxic Hide Helm | `PrimalItemArmor_HideHelmet_Toxic_C` |
| Toxic Hide Shirt | `PrimalItemArmor_HideShirt_Toxic_C` |
| Toxic Hide Handschuhe | `PrimalItemArmor_HideGloves_Toxic_C` |
| Toxic Hide Hose | `PrimalItemArmor_HidePants_Toxic_C` |
| Toxic Hide Stiefel | `PrimalItemArmor_HideBoots_Toxic_C` |

---

### Primal Chaos — Werkzeuge (Metal Pick)

| Tier | Klassenname |
|------|-------------|
| Toxic | `PrimalItem_WeaponMetalPick_Toxic_C` |
| Alpha | `PrimalItem_WeaponMetalPick_Alpha_C` |
| Volcanic | `PrimalItem_WeaponMetalPick_Volcanic_C` |
| Mythic | `PrimalItem_WeaponMetalPick_Mythic_C` |

### Primal Chaos — Werkzeuge (Metal Hatchet)

| Tier | Klassenname |
|------|-------------|
| Toxic | `PrimalItem_WeaponMetalHatchet_Toxic_C` |
| Alpha | `PrimalItem_WeaponMetalHatchet_Alpha_C` |
| Volcanic | `PrimalItem_WeaponMetalHatchet_Volcanic_C` |
| Mythic | `PrimalItem_WeaponMetalHatchet_Mythic_C` |

### Primal Chaos — Werkzeuge (Sichel / Sickle)

| Tier | Klassenname |
|------|-------------|
| Toxic | `PrimalItem_WeaponSickle_Toxic_C` |
| Alpha | `PrimalItem_WeaponSickle_Alpha_C` |
| Volcanic | `PrimalItem_WeaponSickle_Volcanic_C` |
| Mythic | `PrimalItem_WeaponSickle_Mythic_C` |

### Primal Chaos — Werkzeuge (Pike)

| Tier | Klassenname |
|------|-------------|
| Toxic | `PrimalItem_WeaponPike_Toxic_C` |
| Alpha | `PrimalItem_WeaponPike_Alpha_C` |
| Volcanic | `PrimalItem_WeaponPike_Volcanic_C` |
| Mythic | `PrimalItem_WeaponPike_Mythic_C` |

### Primal Chaos — Ressourcen

| Item | Klassenname |
|------|-------------|
| Element Metal Ingot | `PrimalItemResource_MetalIngot_Element_C` |
| Toxic Metal Ingot | `PrimalItemResource_MetalIngot_Toxic_C` |
| Alpha Metal Ingot | `PrimalItemResource_MetalIngot_Alpha_C` |
| Mythic Metal Ingot | `PrimalItemResource_MetalIngot_Mythic_C` |

### Primal Chaos — Strukturen

| Item | Klassenname |
|------|-------------|
| Chaos Bed | `PrimalItemStructure_ChaosBed_C` |
| Chaos Forge | `PrimalItemStructure_Forge_Chaos_C` |
| Chaos Anvil Bench | `PrimalItemStructure_AnvilBench_Chaos_C` |
| Metal Spike Wall Toxic | `PrimalItemStructure_MetalSpikeWall_Toxic_C` |
| Metal Spike Wall Alpha | `PrimalItemStructure_MetalSpikeWall_Alpha_C` |
| Metal Spike Wall Mythic | `PrimalItemStructure_MetalSpikeWall_Mythic_C` |

---

### Vanilla ASA — Waffen

| Item | Klassenname |
|------|-------------|
| Fabricated Sniper Rifle | `PrimalItem_WeaponMachinedSniper_C` |
| Longneck Rifle | `PrimalItem_WeaponOneShotRifle_C` |
| Crossbow | `PrimalItem_WeaponCrossbow_C` |
| Pump-Action Shotgun | `PrimalItem_WeaponShotgun_C` |
| Compound Bow | `PrimalItem_WeaponCompoundBow_C` |
| Pike | `PrimalItem_WeaponPike_C` |
| Sichel | `PrimalItem_WeaponSickle_C` |
| Bola | `PrimalItem_WeaponBola_C` |
| Metal Pick | `PrimalItem_WeaponMetalPick_C` |
| Metal Hatchet | `PrimalItem_WeaponMetalHatchet_C` |

### Vanilla ASA — Munition & Verbrauchsgüter

| Item | Klassenname |
|------|-------------|
| ADV Sniper Bullet | `PrimalItemAmmo_AdvancedSniperBullet_C` |
| Tranq Arrow | `PrimalItemAmmo_ArrowTranq_C` |
| Flame Arrow | `PrimalItemAmmo_ArrowFlame_C` |
| Med Brew | `PrimalItemConsumable_HealSoup_C` |

### Vanilla ASA — Flak Rüstung

| Item | Klassenname |
|------|-------------|
| Metal Helm | `PrimalItemArmor_MetalHelmet_C` |
| Metal Shirt | `PrimalItemArmor_MetalShirt_C` |
| Metal Handschuhe | `PrimalItemArmor_MetalGloves_C` |
| Metal Hose | `PrimalItemArmor_MetalPants_C` |
| Metal Stiefel | `PrimalItemArmor_MetalBoots_C` |

### Vanilla ASA — Ressourcen

| Item | Klassenname |
|------|-------------|
| Polymer | `PrimalItemResource_Polymer_C` |
| Zement (Cementing Paste) | `PrimalItemResource_ChitinPaste_C` |
| Siliziumperlen (Silica Pearls) | `PrimalItemResource_Silicon_C` |
| Öl | `PrimalItemResource_Oil_C` |
| Stroh (Thatch) — Filler für Zufalls-Slots | `PrimalItemResource_Thatch_C` |

### Vanilla ASA — Strukturen

| Item | Klassenname |
|------|-------------|
| Metal Foundation | `PrimalItemStructure_MetalFloor_C` |
| Metal Wall | `PrimalItemStructure_MetalWall_C` |
| Metal Ceiling | `PrimalItemStructure_MetalCeiling_C` |
| Dino Gateway (Rahmen) | `PrimalItemStructure_MetalGateframe_C` |
| Dino Gate (Tür) | `PrimalItemStructure_MetalGate_C` |
| Dedicated Storage | `PrimalItemStructure_DedicatedStorage_C` |
| Industrial Forge | `PrimalItemStructure_IndustrialForge_C` |
| Industrial Grinder | `PrimalItemStructure_Grinder_C` |
