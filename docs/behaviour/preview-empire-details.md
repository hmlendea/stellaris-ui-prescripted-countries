# Preview Empire Details

## User Goal

Inspect a prescripted empire's full configuration before committing to play it.

## Entry Point

Empire Selection Screen → Click any empire → Details panel expands

## Displayed Information

| Section | Fields Shown | Source |
|---------|--------------|--------|
| Identity | Name, Adjective, Flag | `name`, `adjective`, `empire_flag` |
| Government | Authority, Government, Civics (2) | `authority`, `government`, `civics` |
| Ethics | Fanatic/Standard ethics (2-3 total) | `ethic` fields |
| Origin | Origin name & description | `origin` |
| Species | Portrait, Class, Traits, Name, Adjective | `species` block |
| Homeworld | Planet name, Class, System name | `planet_name`, `planet_class`, `system_name` |
| Fleet | Ship prefix | `ship_prefix` |
| Flavour | Species bio (if defined) | `species.species_bio` |

## Interaction

- Panel updates instantly on selection change.
- No editing capability — prescripted empires are read-only.
- To customise, player must create a new custom empire (base game feature).
- Scrollable if content exceeds panel height.

## Data Completeness

All 26 empires provide:
- Complete government, ethics, origin, species data.
- Flag textures (via dependency).
- Localised strings for all display fields.

Only 15 empires have `species_bio` flavour text.

## Invariants

- Details panel never shows raw keys (localisation always resolves).
- Flag always renders (dependency loaded before mod).
- No missing portrait (all use base game humanoid portraits).
- Panel updates in <100ms (static data, no computation).

## Related Documentation

- [Browse & select empires](./browse-and-select-empires.md)
- [Country definitions](../components/country-definitions.md) — field reference
- [Localisation](../components/localisation.md) — string resolution
- [Dependencies](../dependencies.md) — asset sources