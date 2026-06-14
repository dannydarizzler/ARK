# ARK: Survival Ascended — Server Dokumentation

> Dieses Dokument dient als Referenz für die Serverkonfiguration, aktive Mods, Stat-Erklärungen und die Inhalte der Loot Drops.

---

## Inhaltsverzeichnis

1. [Aktive Mods](#1-aktive-mods)
2. [Spieler & Dino Stats](#2-spieler--dino-stats)
3. [Loot Drop Übersicht](#3-loot-drop-übersicht)
4. [Admin Commands](#4-admin-commands)
5. [Server Einstellungen](#5-server-einstellungen)

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
| Normal | Pike + Sichel + Flak-Set + 50% Chance: BP (Sniper / Pike / Sichel) + 50% Chance: Crossbow BP | Meisterwerk → Aufgestiegen |
| Double | Alles aus Normal + 50% Chance: Fab Sniper BP + 50% Chance: Crossbow BP (unabhängig voneinander) | Meisterwerk → Aufgestiegen |

### Gelb — Strukturen
| Variante | Inhalt | Qualität |
|----------|--------|----------|
| Normal | 10 Metal Foundations + 15 Metal Walls + 10 Metal Ceilings + Dino Gate + Dino Door + 5 Tek Dedicated Storage | gibt es keine |
| Double | 20 Metal Foundations + 30 Metal Walls + 20 Metal Ceilings + Dino Gate + Dino Door + zufällig Industrial Forge oder Industrial Grinder + 10 Tek Dedicated Storage | gibt es keine |

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
| `admincheat DestroyWildDinos` | Alle wilden Dinos töten (spawnen danach neu) |

---

## 5. Server Einstellungen

### Spieler Stats — pro Level-Up Multiplikator

| Attribut | Multiplikator | Hinweis |
|----------|--------------|---------|
| Health | ×2.0 | |
| Stamina | ×2.0 | |
| Weight | ×15.0 | sehr hoch — Inventar kaum ein Problem |
| Melee Damage | ×2.0 | |
| Movement Speed | ×2.5 | Speed-Leveling aktiv |
| Temp. Fortitude | ×5.0 | |
| Crafting Speed | ×50.0 | |
| Oxygen / Food / Water | ×1.0 | Standard |

### Dino Stats — gezähmte Dinos pro Level-Up

| Attribut | Multiplikator | Hinweis |
|----------|--------------|---------|
| Health | ×1.0 | Standard |
| Stamina | ×2.0 | |
| Weight | ×20.0 | extrem hoch — Lastdinos tragen enorm viel |
| Alle anderen | ×1.0 | Standard |

> Wilde Dinos bleiben auf Standard (×1.0) — maximale Schwierigkeit aktiv.

### Breeding

| Einstellung | Wert | Bedeutung |
|-------------|------|-----------|
| Paarungsintervall | ×0.05 | Dauert in der regel 1-2 Stunden |
| Ei schlüpfen | ×40 | sehr schnell |
| Baby aufwachsen | ×40 | sehr schnell |
| Imprint-Menge | ×10 | 100 % Imprint in wenigen Cuddles |
| Ei-Legeintervall | ×0.1 | Eier kommen sehr häufig |

### XP Multiplikatoren

| Quelle | Multiplikator |
|--------|--------------|
| Generic (allgemein) | ×10 |
| Craft | ×6 |
| Cave Kill | ×4 |
| Boss Kill | ×5 |
| Alpha Kill | ×2 |
| Wild Kill | ×3 |
| Kill (allgemein) | ×2 |
| Harvest | ×2 |

### Welt & Gameplay

| Einstellung | Wert | Bedeutung |
|-------------|------|-----------|
| Loot-Qualität Drops | ×10 | sehr hohe Item-Qualität |
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
