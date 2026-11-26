# LW RecipeFinder – Dokumentation

Dokumentation zu einem selbst entwickelten **WoW-Addon für Leatherworking (Lederverarbeitung)**, gebaut für **WoW Forever** (Classic). Dieses Repository enthält nur die Beschreibung, keinen Quellcode.

## Idee

Man öffnet eine Liste aller Leatherworking-Rezepte und sieht sofort, **wo man welches Rezept bekommt**. Ein Klick markiert den Ort auf der Weltkarte.

## Funktionen

- Liste mit **183 Rezepten**, sortiert nach Skill-Stufe
- Quellen: Händler (53), Weltdrops (38), Mob-Drops (25), Quests (17), Dungeons (14), Ruf (24), Raid (1)
- Filter nach Fraktion (Alle, Meine Fraktion, Horde, Allianz, Neutral), nach Quelle und nach gelernt oder nicht gelernt
- Suche nach Rezeptname, Händler oder Zone
- Klick auf ein Rezept: Koordinaten im Chat, Pin auf der Weltkarte und, wenn TomTom installiert ist, ein Wegpunkt
- Automatische Erkennung gelernter Rezepte beim Öffnen des Handwerksfensters
- Materialfenster mit benötigten Materialien und Farmorten
- Trainerliste der eigenen Fraktion
- Minimap-Knopf

## Befehle

| Befehl | Wirkung |
|---|---|
| `/lwr`, `/lwrecipe`, `/lwfind` | Fenster öffnen oder schließen |
| `/lwr trainer` | Trainer der eigenen Fraktion im Chat |
| `/lwr help` | Hilfe |

## Aufbau

Das Addon besteht aus drei Lua-Dateien und je einem Manifest für Forever und Classic Era:

- **Kernlogik:** Fenster, Filter, Suche, Karten-Pins, Erkennung gelernter Rezepte
- **Rezeptdaten:** Rezepte und Trainer mit Quelle, Ort, Koordinaten, Fraktion und Preis
- **Materialdaten:** Materialien mit Farmorten

Gespeichert wird in der SavedVariable `LWRecipeFinderDB`.

## Entwicklungsverlauf

1. **v1:** Nur Händlerrezepte (ca. 65, Skill 40 bis 300) mit Karten-Pin und TomTom-Unterstützung
2. **v3:** Erweitert um Mob-Drops, Dungeons, Raids, Quests, Weltdrops und Ruf, dazu Materialfenster
3. **Gelernt-Filter:** Gelernte Rezepte werden über die Handwerks-API erkannt
4. **Forever-Anpassung:** Der Client lädt nur Manifeste mit dem Suffix `_Forever`, Interface-Version `16001`. Das Ereignis `TRADE_SKILL_UPDATE` fehlt dort. Registriert wird es deshalb abgesichert, zusätzlich `TRADE_SKILL_LIST_UPDATE`.

## Status und Grenzen

- Die Daten stammen aus öffentlichen Classic-Quellen und können Fehler enthalten, besonders bei Koordinaten.
- Das Addon ist nicht in allen Funktionen im Spiel getestet.
- Die Versionsnummern der Manifeste (3.0.0) sind älter als die der Kernlogik (3.1.1).
