# Repository Overview

## Purpose

Universum Infinitum: Prescripted Countries is a content-only Stellaris mod that adds 26 prescripted countries (pre-defined empire templates) drawn from other game franchises and original human cultures. Players can select these empires when starting a new game, or the AI can spawn them during galaxy generation.

The repository contains no executable code. Every file is declarative data consumed by the Stellaris script parser at game load time.

## Scope

The mod owns:
- 26 prescripted country definition files (Clausewitz script `.txt`).
- English localisation strings for empire design names and descriptions.
- Mod descriptor metadata (version, supported game version, tags).

The mod deliberately does not own:
- Flag icon and background assets — provided by [Universum Infinitum - Flags](https://github.com/hmlendea/stellaris-ui-flags).
- Name lists (ship, planet, ruler, fleet names) — provided by [Universum Infinitum - Name Lists](https://github.com/hmlendea/stellaris-ui-name-lists).
- Custom species traits — provided by [Universum Infinitum - Species Traits](https://github.com/hmlendea/stellaris-ui-species-traits).
- Base game assets (portraits, graphical cultures, origins, civics, authorities, governments) — provided by Stellaris itself.

## Entry Points

| Entry point | Path | Consumer |
|-------------|------|----------|
| Mod descriptor (manual install) | `ui-prescripted-countries.mod` | Stellaris launcher / engine |
| Mod descriptor (workshop/Paradox Mods) | `ui-prescripted-countries/descriptor.mod` | Stellaris launcher / engine |
| Country definitions | `ui-prescripted-countries/prescripted_countries/*.txt` | Stellaris engine script parser |
| Localisation | `ui-prescripted-countries/localisation/english/ui-prescripted-countries_l_english.yml` | Stellaris localisation system |

## Country Catalogue

| Source | Countries |
|--------|-----------|
| Civilization: Beyond Earth | African Union, Brasilia, Franco-Iberia, INTEGR, Kavithan Protectorate, Pan-Asian Cooperative, Polystralia, Slavic Federation |
| The Elder Scrolls | Aldmeri Dominion, Argonia |
| Original human cultures | Arabian, Celtic, French, Hellenic, Italian, Japanese, Norse, Ottoman, Roman |
| Galactic Civilizations | Altarian Republic, Drengin Empire, Krynn Consulate, Torian Confederation, Yor Collective |
| StarCraft | Protoss Empire, Terran Dominion |

## Principal Capabilities

- Register empire templates with the Stellaris empire database at load time.
- Present the countries in the empire selection screen for player choice.
- Make the countries eligible for AI empire spawning (`spawn_enabled=yes`).
- Apply complete empire templates: species, traits, name lists, ethics, civics, origin, authority, government, ruler, flag, planet, system, graphical culture.

## Related Documentation

- [Repository structure](./repository-structure.md)
- [Architecture](./architecture.md)
- [Data model](./data-model.md)
- Root [ARCHITECTURE.md](../ARCHITECTURE.md)
- Root [README.md](../README.md)
