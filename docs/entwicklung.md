# Entwicklungsverlauf

1. **v1:** Nur Händlerrezepte (ca. 65 Stück, Skill 40 bis 300) mit Karten-Pin und TomTom-Unterstützung.
2. **v3:** Erweitert um Mob-Drops, Dungeons, Raids, Quests, Weltdrops und Ruf. Dazu kam das Materialfenster.
3. **Gelernt-Filter:** Gelernte Rezepte werden über die Handwerks-API erkannt.
4. **Anpassung an Forever:**
   - Der Client lädt nur Manifeste mit dem Suffix `_Forever` (Interface 16001).
   - Das Ereignis `TRADE_SKILL_UPDATE` gibt es dort nicht. Das Addon registriert es deshalb abgesichert, zusätzlich `TRADE_SKILL_LIST_UPDATE`.
   - Dadurch lädt das Addon auch dann, wenn einzelne Ereignisse fehlen.

## Versionsnummern

Das Forever-Manifest und die Kernlogik tragen Version 3.1.1, die beiden anderen Manifeste 3.0.0.

## Umfang

Die drei Lua-Dateien haben zusammen rund 4200 Zeilen (Daten etwa 2000, Material etwa 1000, Logik etwa 1300).
