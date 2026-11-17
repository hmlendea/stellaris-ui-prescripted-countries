# Data Model

This document describes the domain entities, their fields, relationships, and persistence semantics for the prescripted country definitions.

## Empire Template (Country Definition)

Each file in `prescripted_countries/` defines one empire template. The top-level block key is a bare identifier derived from the filename (`-` replaced by `_`).

### Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `name` | string | Yes | Empire design localisation key (`EMPIRE_DESIGN_<key>`). |
| `adjective` | string | Yes | Empire adjective localisation key (`EMPIRE_DESIGN_<key>_adj`). |
| `spawn_enabled` | boolean | Yes | Always `yes`; makes the country available for AI and player. |
| `ignore_portrait_duplication` | boolean | Yes | Always `yes`; permits multiple countries to share portraits. |
| `ship_prefix` | string | Yes | Ship name prefix localisation key. |
| `species.class` | string | Yes | Species class; always `HUM` for humanoid. |
| `species.portrait` | string | Yes | Base game portrait key (e.g., `human`, `humanoid_05`, `humanoid_hp_12`). |
| `species.name` | string | Yes | Singular species name localisation key. |
| `species.plural` | string | Yes | Plural species name localisation key. |
| `species.adjective` | string | Yes | Adjective form localisation key. |
| `species.name_list` | string | Yes | Name list key from UI Name Lists mod or base game. |
| `species.gender` | enum | Yes | `not_set` for species without gendered portraits. |
| `species.trait` | string[] | Yes | Trait keys; `trait_organic` is mandatory (species archetype), others from UI Species Traits mod or base game (repeatable). |
| `secondary_species` | block | No | Second species block for origins such as `origin_syncretic_evolution`; same fields as `species`. |
| `room` | string | Yes | Personality room key from base game (e.g., `personality_peaceful_traders_room`). |
| `authority` | string | Yes | Authority key from base game (e.g., `auth_democratic`, `auth_imperial`, `auth_oligarchic`). |
| `civics` | string[] | Yes | Civic keys from base game (repeatable). |
| `government` | string | Yes | Government key from base game (e.g., `gov_communal_parity`, `gov_star_empire`). |
| `origin` | string | Yes | Origin key from base game (e.g., `origin_lost_colony`, `origin_default`). |
| `ethic` | string[] | Yes | Ethic keys from base game (repeatable; fanatic ethics use `ethic_fanatic_*`). |
| `planet_name` | string | Yes | Home planet name localisation key. |
| `planet_class` | string | Yes | Planet class key from base game (e.g., `pc_savannah`, `pc_arid`, `pc_continental`). |
| `system_name` | string | Yes | Home system name localisation key. |
| `initializer` | string | No | Empty string; reserved for future use. |
| `graphical_culture` | string | Yes | Graphical culture key from base game (e.g., `mammalian_01`, `avian_01`). |
| `city_graphical_culture` | string | Yes | City graphical culture key from base game. |
| `empire_flag.icon.category` | string | Yes | Flag icon category from UI Flags mod or base game. |
| `empire_flag.icon.file` | string | Yes | Flag icon filename (`.dds`). |
| `empire_flag.background.category` | string | Yes | Flag background category. |
| `empire_flag.background.file` | string | Yes | Flag background filename (`.dds`). |
| `empire_flag.colors` | string[4] | Yes | Four colour keys (primary, secondary, tertiary, quaternary); `null` for unused. |
| `ruler.gender` | enum | Yes | `male` or `female`. |
| `ruler.name` | string | Yes | Ruler full name localisation key. |
| `ruler.portrait` | string | Yes | Ruler portrait key (gender-specific variant). |
| `ruler.texture` | integer | Yes | Texture index. |
| `ruler.attachment` | integer | Yes | Attachment index. |
| `ruler.clothes` | integer | Yes | Clothes index. |
| `ruler.trait` | string | Yes | Ruler trait key from base game. |
| `ruler.leader_class` | enum | Yes | `official`, `commander`, `scientist` (4.x leader classes; legacy `governor`/`general`/`admiral` were replaced in Stellaris 4.0). |
| `ruler.ruler_title` | string | No | Ruler title localisation key. |
| `ruler.ruler_title_female` | string | No | Female ruler title localisation key. |
| `spawn_as_fallen` | boolean | Yes | `yes` for fallen empire candidates; `no` otherwise. |
| `advisor_voice_type` | string | No | Advisor voice key from base game. |

### Localisation Indirection

Every human-readable field stores a localisation key; there is no `literal` flag and no `{ key = ... }` wrapper. Display text lives in the localisation file. Values may reference other localisation keys with `$KEY$` indirection, used here to reuse the vanilla human species strings (`$PRESCRIPTED_species_name_humans1$`, `$PRESCRIPTED_species_plural_humans1$`, `$PRESCRIPTED_species_adjective_humans1$`).

## Localisation Entry

Path: `localisation/english/ui-prescripted-countries_l_english.yml`

### Structure

```yaml
l_english:
  EMPIRE_DESIGN_<empire_key>:0 "Display Name"
  EMPIRE_DESIGN_<empire_key>_desc:0 "Description text"
  EMPIRE_DESIGN_<empire_key>_adj:0 "Adjective"
  <empire_key>_species_name:0 "Species"
  <empire_key>_species_plural:0 "Species plural"
  <empire_key>_species_adjective:0 "Species adjective"
  <empire_key>_planet_name:0 "Homeworld"
  <empire_key>_system_name:0 "Home system"
  <empire_key>_ship_prefix:0 "PREFIX"
  <empire_key>_ruler_name:0 "Ruler name"
  <empire_key>_ruler_title:0 "Ruler title"
  <empire_key>_ruler_title_female:0 "Female ruler title"
```

### Fields

| Key pattern | Purpose |
|-------------|---------|
| `EMPIRE_DESIGN_<empire_key>` | Empire design name shown in selection screen. |
| `EMPIRE_DESIGN_<empire_key>_desc` | Description shown in empire tooltip. |
| `EMPIRE_DESIGN_<empire_key>_adj` | Empire adjective. |
| `<empire_key>_*` | Species, planet, system, ship prefix, and ruler strings referenced by the country file. |

### Current Coverage

- 26 empire design names and adjectives defined.
- 5 empire design descriptions defined; the rest have no description entry.

## Mod Descriptor

Paths: `ui-prescripted-countries.mod`, `ui-prescripted-countries/descriptor.mod`

### Fields

| Field | Type | Description |
|-------|------|-------------|
| `version` | string | Mod version (semantic). |
| `name` | string | Display name in launcher. |
| `path` | string | Filesystem path to mod content. |
| `tags` | object | Tag set; currently `{ "Galaxy Generation" }`. |
| `supported_version` | string | Stellaris version pattern (e.g., `v4.5.*`). |

## Cross-Mod References

Country definitions reference external content by opaque string keys. The engine resolves these at load time against the loaded mod database.

| Reference type | Source mod | Example keys |
|----------------|------------|--------------|
| Name list | UI Name Lists | `ui_extra_humans_african`, `ui_elderscrolls_altmer`, `ui_starcraft_protoss` |
| Species trait | UI Species Traits / Base game | `trait_rapid_breeders`, `trait_intelligent`, `trait_decadent` |
| Flag icon | UI Flags | `ui_civbe`/`ui_africa.dds`, `ui_galciv`/`flag_ui_galciv_drengin.dds` |
| Flag background | UI Flags / Base game | `backgrounds`/`ui_hexagon.dds`, `backgrounds`/`00_solid.dds` |
| Graphical culture | Base game | `mammalian_01`, `avian_01` |
| Origin | Base game | `origin_lost_colony`, `origin_default`, `origin_shoulders_of_giants` |
| Civic | Base game | `civic_agrarian_idyll`, `civic_slaver_guilds` |
| Authority | Base game | `auth_democratic`, `auth_imperial`, `auth_oligarchic` |
| Government | Base game | `gov_communal_parity`, `gov_martial_empire` |
| Planet class | Base game | `pc_savannah`, `pc_arid`, `pc_continental` |
| Portrait | Base game | `human`, `humanoid_05`, `humanoid_hp_12` |
| Advisor voice | Base game | `l_xenophobe`, `l_authoritarian` |
| Personality room | Base game | `personality_peaceful_traders_room`, `personality_fanatic_purifier_room` |

## Invariants

- Every `key` in country definitions is unique and stable.
- Every referenced external key exists in the declared dependency mod or base game.
- Localisation covers every non-literal `name` and `adjective` key.
- `spawn_enabled=yes` for all countries.
- `ignore_portrait_duplication=yes` for all countries.

## Related Documentation

- [Architecture](./architecture.md) — load-time data flow.
- [Dependencies](./dependencies.md) — companion mod contracts.
- [Change guide](./change-guide.md) — adding or modifying countries.