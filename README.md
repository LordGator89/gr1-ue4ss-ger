# MarvinMode – Cheat-Konsole für Gothic 1 Remake

Schaltet die (im Retail-Build entfernte) Unreal-Konsole frei und bringt den Marvin-Modus zurück:
Godmode, Stats-Editor, Teleport, Items, Talente, Zeit, Wetter, Fliegen, Noclip und mehr.

Technisch ist es eine **UE4SS-Lua-Mod**. Es werden keine Spieldateien verändert, sie lässt sich
also jederzeit wieder entfernen.

## Installation

1. Den ZIP-Inhalt nach `...\Gothic 1 Remake\G1R\Binaries\Win64\` entpacken. Dort müssen danach
   `dwmapi.dll` und der Ordner `ue4ss` liegen.
2. Spiel starten und einen Spielstand laden.

## Benutzung

Konsole öffnen mit **F10** oder **Ö** (die Taste „Tilde“ auf deutscher Tastatur), dann
`marvin` eingeben. Damit wird die komplette Befehlsliste angezeigt.
Jeder Befehl funktioniert auch wie im Original als `cheat <befehl>`, z. B. `cheat god`.
`an`/`aus` ist bei Schaltern optional; ohne Angabe wird umgeschaltet.

### Hotkeys (änderbar in `Scripts/config.lua`)

| Taste | Funktion |
|---|---|
| F6 | Godmode an/aus |
| F7 | Leben, Mana, Sauerstoff voll, Müdigkeit weg |
| F8 | Fliegen an/aus |
| Bild ↑ | 6 m nach vorne teleportieren (wie die Marvin-Taste K) |
| Pos1 | Position merken |
| Ende | Zur gemerkten Position springen |
| Bild ↓ | Zurück zur Position vor dem letzten Teleport |

### Godmode & Kampf

| Befehl | Wirkung |
|---|---|
| `god [an\|aus]` | Unverwundbar (eingebautes `m_GodMode`-Flag des Spiels) plus Dauerheilung und Sauerstoff |
| `heal` | Leben voll |
| `full` | Leben, Mana, Sauerstoff voll, Müdigkeit weg |
| `infmana [an\|aus]` | Unendlich Mana |
| `parry [an\|aus]` | Jeder Nahkampfangriff wird automatisch pariert |
| `onehit [an\|aus]` | One-Hit-Kills über +100000 Stärke/Geschick. **Vor dem Speichern ausschalten!** |

### Stats-Editor

| Befehl | Wirkung |
|---|---|
| `stats` | Alle Werte anzeigen |
| `<stat>` | Einen Wert anzeigen, z. B. `str` |
| `<stat> <wert>` | Wert setzen, z. B. `str 100` |
| `<stat> +<n>` / `<stat> -<n>` | Wert erhöhen/senken, z. B. `lp +20` |
| `setstat <stat> <wert>` / `addstat <stat> <n>` | Dasselbe in Langform |

Stats: `str` (Stärke), `dex` (Geschick), `hp`, `maxhp`, `mana`, `maxmana`, `level`,
`xp` (Erfahrung), `lp` (Lernpunkte), `speed` (Laufgeschwindigkeit, 1 = normal).
Boni von Ausrüstung bleiben beim Setzen erhalten.

### Teleport

| Befehl | Wirkung |
|---|---|
| `tp` / `orte` | Alle Ziele auflisten |
| `tp <ort>` | Zu einem Ziel springen: `altlager`, `burg`, `neulager`, `sumpf`, `altemine`, `freiemine`, `austausch` |
| `tp <x> <y>` | Schnellreise des Spiels zu Koordinaten (sucht automatisch festen Boden) |
| `tp <x> <y> <z>` | Exakt auf Koordinaten springen |
| `pos` | Aktuelle Koordinaten anzeigen |
| `savepos <name>` / `delpos <name>` | Eigene Ziele speichern/löschen (danach `tp <name>`) |
| `tpf [meter]` | Nach vorne teleportieren, auch durch Wände |
| `tpz <meter>` | Nach oben teleportieren, mit negativem Wert nach unten |
| `tpback` | Zurück zur Position vor dem letzten Teleport |
| `npcs [filter]` | Geladene NPCs/Kreaturen in der Nähe auflisten |
| `goto <name>` | Zum nächsten passenden NPC springen (Namen aus `npcs`) |

Eigene Positionen landen in `saved_positions.txt` im Mod-Ordner.

### Items & Talente

| Befehl | Wirkung |
|---|---|
| `item <ItemId> [anzahl]` | Item geben, z. B. `item ItMi_Orenugget 500` (auch `insert`/`give`) |
| `removeitem <ItemId> [anzahl]` | Item entfernen (ohne Anzahl: alle) |
| `ore <anzahl>` | Erz geben (negativ: abziehen, ohne Zahl: anzeigen) |
| `count <ItemId>` | Anzahl im Inventar |
| `skill <Name>` | Talent gratis lernen, z. B. `skill Acrobatics`, `skill Mage_Circle_6` |
| `skills` | Liste bekannter Talentnamen |

Item-IDs folgen der Gothic-Benennung: `ItMw_` Nahkampfwaffen, `ItRw_` Bögen/Armbrüste,
`ItAm_` Munition, `ItAr_` Rüstungen/Runen/Spruchrollen, `ItAt_` Amulette/Ringe, `ItFo_` Essen,
`ItMi_` Sonstiges, `ItKe_` Schlüssel, `ItWr_` Bücher/Schriftstücke.
Beispiele: `item ItRw_Bow_Long_01`, `item ItAm_Arrow 100`, `item ItAr_Rune_FireRain`.

### Bewegung, Zeit & Welt

| Befehl | Wirkung |
|---|---|
| `fly [an\|aus] [tempo]` | Freies Fliegen ohne Kollision (WASD + Maus, nach oben schauen = steigen) |
| `flyspeed <cm/s>` | Fluggeschwindigkeit (Standard 1500) |
| `noclip [an\|aus]` | Kollision aus |
| `time [HH:MM]` | Uhrzeit anzeigen/setzen |
| `skiptime <stunden>` | Zeit vorspulen |
| `freezetime [an\|aus]` | Tageszeit anhalten |
| `timescale <faktor>` | Spielgeschwindigkeit (0.5 = Zeitlupe, 2 = doppelt) |
| `weather <sonne\|regen\|starkregen\|sturm\|wolken>` | Wetter setzen |

## Hinweise

- **Vor dem Cheaten manuell speichern.** Besonders `onehit` und extreme Stat-Werte landen
  sonst dauerhaft im Spielstand.
- Fliegen/Noclip **nicht in einer Wand ausschalten**, sonst steckt man fest. Dann hilft `tpz 3`
  oder `tpback`.
- Nach einem Teleport hält die Mod den Helden ca. 2,5 s in der Luft, damit die Welt
  nachladen kann (einstellbar über `landingHold` in der Config).
- Alle Ausgaben stehen in der Ingame-Konsole und im UE4SS-Fenster bzw. in `UE4SS.log`.
- Kollidiert ein Befehlsname mit einer anderen Mod, in der Config `commandPrefix = "mm_"`
  setzen. Dann heißen alle Befehle `mm_god`, `mm_tp` usw.

## Fehlerbehebung

| Problem | Lösung |
|---|---|
| Konsole geht nicht auf | Im UE4SS-Log nach „Konsole freigeschaltet“ suchen. F10 probieren. In `ue4ss\Mods\mods.txt` sollte `ConsoleEnablerMod : 1` stehen. |
| „Kein Spieler gefunden“ | Erst einen Spielstand laden; im Hauptmenü gibt es keinen Helden. |
| Befehl wird nicht erkannt | Prüfen, ob `MarvinMode` im Log mit „v1.0.0 geladen“ auftaucht. UE4SS auf den aktuellen Experimental-Build aktualisieren. |
| Absturz nach Spiel-Update | Nach Patches zuerst UE4SS aktualisieren. |

## Credits

Die verwendeten Spiel-Schnittstellen (CombatConfig-Godmode, GAS-Mixins, Map-Teleport,
Lager-Koordinaten) wurden von der G1R-Modding-Community dokumentiert, insbesondere im
Repository [TautelliniMods](https://github.com/Tautellini/TautelliniMods).
