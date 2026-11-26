# Installation

## Ordner

Den Ordner `LW_RecipeFinder` nach `World of Warcraft\<Client>\Interface\AddOns\` kopieren. Beim Forever-Client heißt der Client-Ordner `_forever_`.

## Manifeste

Das Addon liefert drei Manifeste mit, weil die Clients unterschiedlich laden:

| Datei | Für |
|---|---|
| `LW_RecipeFinder_Forever.toc` | WoW Forever (Interface 16001) |
| `LW_RecipeFinder_Vanilla.toc` | Classic Era |
| `LW_RecipeFinder.toc` | Standard |

**Wichtig für Forever:** Der Client lädt nur Manifeste mit dem Suffix `_Forever`. Fehlt es, erscheint das Addon nicht in der Addon-Liste.

## Prüfen

Im Spiel im Charakterfenster „AddOns“ öffnen: „LW RecipeFinder – Leatherworking Recipes“ muss aktiviert sein. Danach `/lwr` eingeben.

## Gespeicherte Daten

Das Addon speichert in der SavedVariable `LWRecipeFinderDB` (Datei im Ordner `WTF` des Accounts).

## Optional: TomTom

Mit dem Addon TomTom setzt ein Klick auf ein Rezept zusätzlich einen Wegpunkt mit Pfeil.
