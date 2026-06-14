# ARK: Survival Ascended — Server Dokumentation

> Dieses Dokument dient als Referenz für die Serverkonfiguration, aktive Mods, Stat-Erklärungen und die Inhalte der Loot Drops.

---

## Inhaltsverzeichnis

1. [Aktive Mods](#1-aktive-mods)
2. [Spieler & Dino Stats](#2-spieler--dino-stats)
3. [Loot Drop Übersicht](#3-loot-drop-übersicht)
4. [Admin Commands](#4-admin-commands)

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

Die Drops sind progressiv aufgebaut — je höher die Drop-Farbe, desto besser der Inhalt und die Qualität. Jede Farbe hat eine Normal- und eine Double-Variante (mit Ring), wobei die Double-Variante immer etwas mehr oder besseres enthält.

### Weiß — Starter Kit
| Variante | Inhalt | Qualität |
|----------|--------|----------|
| Normal | Flak-Set + 10 Bolas + Metallpickel + Metallaxt + 10 Med Brews | Primitiv → Lila |
| Double | Alles aus Normal + Crossbow + 25 Tranq Arrows | Primitiv → Lila |

### Grün — Ressourcen
| Variante | Inhalt |
|----------|--------|
| Normal | 100–200x Polymer, 100–250x Zement, 100–175x Siliziumperlen |
| Double | Alles doppelt bis dreifach |

### Blau — Waffen
| Variante | Inhalt | Qualität |
|----------|--------|----------|
| Normal | Fabrizierter Sniper + 50 ADV Sniper Bullets | Lila → Meisterwerk |
| Double | Alles aus Normal + 50% Chance: Fab Sniper Blueprint oder Crossbow bp oder Shotgun bp oder Compound Bow bp| Lila → Meisterwerk |

### Lila — Bessere Rüstung
| Variante | Inhalt | Qualität |
|----------|--------|----------|
| Normal | Pike + Sichel + Flak-Set + 50% Chance: BP (Sniper / Pike / Sichel) | Meisterwerk → Aufgestiegen |
| Double | Alles aus Normal + zusätzlich 50% Chance: Fab Sniper Blueprint | Meisterwerk → Aufgestiegen |

### Gelb — Strukturen
| Variante | Inhalt | Qualität |
|----------|--------|----------|
| Normal | 10 Metal Foundations + 15 Metal Walls + 10 Metal Ceilings + Dino Gate + Dino Door | gibt es keine |
| Double | 20 Metal Foundations + 30 Metal Walls + 20 Metal Ceilings + Dino Gate + Dino Door + Industrial Forge | gibt es keine |

### Rot — OP Waffen 
| Variante | Inhalt | Qualität |
|----------|--------|----------|
| Normal | Fabricated Sniper oder Crossbow + 25 ADV Sniper Bullets + 25 Tranq Arrows + 25 Flame Arrows + 25 Med Brews | Meisterwerk → Aufgestiegen |
| Double | Alles doppelt bis dreifach | Meisterwerk → Aufgestiegen |



---

## 4. Admin Commands

Cheats müssen zuerst mit dem Passwort aktiviert werden:
```
EnableCheats <Passwort>
```

| Command | Funktion |
|---------|----------|
| `cheat DestroyWildDinos` | Alle wilden Dinos töten (spawnen danach neu) |
| `cheat DestroyAll SupplyCrate_Level03_C` | Alle weißen Drops löschen und neu spawnen |
