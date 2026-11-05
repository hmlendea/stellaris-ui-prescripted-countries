# Data Model

This document describes the domain entities, their fields, relationships, and persistence semantics for the prescripted country definitions.

## Empire Template (Country Definition)

Each file in `prescripted_countries/` defines one empire template. The top-level block name and the `key` field must be identical.

### Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `key` | string | Yes | Unique empire identifier; must match the top-level block name. |
| `ship_prefix.key` | string | Yes | Ship name prefix (e.g., `PAS`, `DES`). |
| `species.class` | string | Yes | Species class; always `HUM` for humanoid. |
| `species.portrait` | string | Yes | Base game portrait key (e.g., `human`, `humanoid_05`, `humanoid_hp_12`). |
| `species.species_name.key` | string | Yes | Singular species name key (localisation or literal). |
| `species.species_plural.key` | string | Yes | Plural species name key. |
| `species.species_adjective.key` | string | Yes | Adjective form key. |
| `species.name_list` | string | Yes | Name list key from UI Name Lists mod or base game. |
| `species.gender` | enum | Yes | `not_set` for species without gendered portraits. |
| `species.trait` | string[] | Yes | Trait keys from UI Species Traits mod or base game (repeatable). |
| `name.key` | string | Yes | Empire name key (localisation or literal). |
| `adjective.key` | string | Yes | Empire adjective key (localisation or literal). |
| `authority` | string | Yes | Authority key from base game (e.g., `auth_democratic`, `auth_imperial`, `auth_oligarchic`). |
| `government` | string | Yes | Government key from base game (e.g., `gov_communal_parity`, `gov_martial_empire`). |
| `planet_name.key` | string | Yes | Home planet name key. |
| `planet_class` | string | Yes | Planet class key from base game (e.g., `pc_savannah`, `pc_arid`, `pc_continental`). |
| `system_name.key` | string | Yes | Home system name key. |
| `initializer` | string | No | Empty string; reserved for future use. |
| `graphical_culture` | string | Yes | Graphical culture key from base game (e.g., `mammalian_01`, `avian_01`). |
| `city_graphical_culture` | string | Yes | City graphical culture key from base game. |
| `empire_flag.icon.category` | string | Yes | Flag icon category from UI Flags mod or base game. |
| `empire_flag.icon.file` | string | Yes | Flag icon filename (`.dds`). |
| `empire_flag.background.category` | string | Yes | Flag background category. |
| `empire_flag.background.file` | string | Yes | Flag background filename (`.dds`). |
| `empire_flag.colors` | string[4] | Yes | Four colour keys (primary, secondary, tertiary, quaternary); `null` for unused. |
| `ruler.gender` | enum | Yes | `male` or `female`. |
| `ruler.name.full_names.key` | string | Yes | Ruler full name key. |
| `ruler.portrait` | string | Yes | Ruler portrait key (gender-specific variant). |
| `ruler.texture` | integer | Yes | Texture index. |
| `ruler.attachment` | integer | Yes | Attachment index. |
| `ruler.clothes` | integer | Yes | Clothes index. |
| `ruler.trait` | string | Yes | Ruler trait key from base game. |
| `ruler.leader_class` | enum | Yes | `governor`, `general`, `admiral`, `scientist`, `ruler`. |
| `ruler.ruler_title.key` | string | No | Custom ruler title (with `literal=yes`). |
| `ruler.ruler_title_female.key` | string | No | Female ruler title. |
| `ruler.heir_title.key` | string | No | Heir title. |
| `ruler.heir_title_female.key` | string | No | Female heir title. |
| `spawn_as_fallen` | boolean | Yes | `yes` for fallen empire candidates; `no` otherwise. |
| `ignore_portrait_duplication` | boolean | Yes | Always `yes`; permits multiple countries to share portraits. |
| `room` | string | Yes | Personality room key from base game (e.g., `personality_peaceful_traders_room`). |
| `spawn_enabled` | boolean | Yes | Always `yes`; makes the country available for AI and player. |
| `ethic` | string[] | Yes | Ethic keys from base game (repeatable; fanatic ethics use `ethic_fanatic_*`). |
| `civics` | string[] | Yes | Civic keys from base game (repeatable). |
| `origin` | string | Yes | Origin key from base game (e.g., `origin_lost_colony`, `origin_default`). |
| `flags` | string[] | No | Optional flags (e.g., `human_1`, `custom_start_screen`). |
| `advisor_voice_type` | string | No | Advisor voice key from base game. |
| `species.species_bio` | string | No | Optional species biography text. |

### Literal vs Localised Keys

Fields with `literal=yes` use the provided string directly in the UI. Fields without it resolve through the localisation system using the `key` value. The localisation file must contain corresponding `EMPIRE_DESIGN_<key>` and `EMPIRE_DESIGN_<key>_desc` entries.

## Localisation Entry

Path: `localisation/english/ui-prescripted-countries_l_english.yml`

### Structure

```yaml
l_english:
  EMPIRE_DESIGN_<country_key>:0 "Display Name"
  EMPIRE_DESIGN_<country_key>_desc:0 "Description text"
```

### Fields

| Key pattern | Purpose |
|-------------|---------|
| `EMPIRE_DESIGN_<country_key>` | Empire design name shown in selection screen. |
| `EMPIRE_DESIGN_<country_key>_desc` | Description shown in empire tooltip. |

### Current Coverage

- 26 empire design names defined.
- 7 empire design descriptions defined (others show `TODO.`).

## Mod Descriptor

Paths: `ui-prescripted-countries.mod`, `ui-prescripted-countries/descriptor.mod`

### Fields

| Field | Type | Description |
|-------|------|-------------|
| `version` | string | Mod version (semantic). |
| `name` | string | Display name in launcher. |
| `path` | string | Filesystem path to mod content. |
| `tags` | object | Tag set; currently `{ "Galaxy Generation" }`. |
| `supported_version` | string | Stellaris version pattern (e.g., `3.9.*`). |

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