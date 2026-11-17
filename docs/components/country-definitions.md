# Country Definitions

## Purpose

Each file in `prescripted_countries/` defines one complete empire template that the Stellaris engine registers at load time. The engine presents these templates in the empire selection screen and makes them available for AI spawning.

## File Inventory

| File | Empire key | Source franchise |
|------|-----------|------------------|
| `ui_civbe_africa.txt` | People's African Union | Civilization: Beyond Earth |
| `ui_civbe_brasilia.txt` | Brasília | Civilization: Beyond Earth |
| `ui_civbe_franco-iberia.txt` | Franco-Iberia | Civilization: Beyond Earth |
| `ui_civbe_integr.txt` | INTEGR | Civilization: Beyond Earth |
| `ui_civbe_kavithan-protectorate.txt` | Kavithan Protectorate | Civilization: Beyond Earth |
| `ui_civbe_panasian-cooperative.txt` | Pan-Asian Cooperative | Civilization: Beyond Earth |
| `ui_civbe_polystralia.txt` | Polystralia | Civilization: Beyond Earth |
| `ui_civbe_slavic_federation.txt` | Slavic Federation | Civilization: Beyond Earth |
| `ui_elderscrolls_aldmeri.txt` | Aldmeri Dominion | The Elder Scrolls |
| `ui_elderscrolls_argonia.txt` | Argonia | The Elder Scrolls |
| `ui_extra_human_arabian.txt` | Arabian empire | Original |
| `ui_extra_human_celtic.txt` | Celtic empire | Original |
| `ui_extra_human_french.txt` | French empire | Original |
| `ui_extra_human_hellenic.txt` | Hellenic empire | Original |
| `ui_extra_human_italian.txt` | Italian empire | Original |
| `ui_extra_human_japanese.txt` | Japanese empire | Original |
| `ui_extra_human_norse.txt` | Norse empire | Original |
| `ui_extra_human_ottoman.txt` | Ottoman empire | Original |
| `ui_extra_human_roman.txt` | Roman empire | Original |
| `ui_galciv_altarian.txt` | Altarian Republic | Galactic Civilizations |
| `ui_galciv_drengin.txt` | Drengin Empire | Galactic Civilizations |
| `ui_galciv_krynn.txt` | Krynn Consulate | Galactic Civilizations |
| `ui_galciv_torian.txt` | Torian Confederation | Galactic Civilizations |
| `ui_galciv_yor.txt` | Yor Collective | Galactic Civilizations |
| `ui_starcraft_protoss.txt` | Protoss Empire | StarCraft |
| `ui_starcraft_terran.txt` | Terran Dominion | StarCraft |

## Structure

Every file follows the same top-level pattern (Stellaris 4.5 schema):

```text
<empire_key> = {
    name = "EMPIRE_DESIGN_<empire_key>"
    adjective = "EMPIRE_DESIGN_<empire_key>_adj"
    spawn_enabled = yes
    ignore_portrait_duplication = yes
    ship_prefix = "<empire_key>_ship_prefix"
    species = {
        class = "HUM"
        portrait = "<portrait>"
        name = "<empire_key>_species_name"
        plural = "<empire_key>_species_plural"
        adjective = "<empire_key>_species_adjective"
        name_list = "<name_list>"
        gender = not_set
        trait = "trait_organic"
        trait = "<trait>"
    }
    room = "<personality_*_room>"
    authority = "<auth_*>"
    civics = { "<civic_*>" "<civic_*>" }
    government = <gov_*>
    origin = "<origin_*>"
    ethic = "<ethic_*>"
    ethic = "<ethic_*>"
    planet_name = "<empire_key>_planet_name"
    planet_class = "<pc_*>"
    system_name = "<empire_key>_system_name"
    initializer = ""
    graphical_culture = "<culture>"
    city_graphical_culture = "<culture>"
    empire_flag = {
        icon = { category = "<cat>" file = "<file.dds>" }
        background = { category = "<cat>" file = "<file.dds>" }
        colors = { "<c1>" "<c2>" "<null>" "<null>" }
    }
    ruler = {
        gender = <male|female>
        name = "<empire_key>_ruler_name"
        portrait = "<portrait>"
        texture = <n>
        attachment = <n>
        clothes = <n>
        ruler_title = "<empire_key>_ruler_title"
        ruler_title_female = "<empire_key>_ruler_title_female"
        trait = "<trait_ruler_*>"
        leader_class = <official|commander|scientist>
    }
    spawn_as_fallen = <yes|no>
    advisor_voice_type = "<l_*>"  # optional
}
```

`secondary_species` is used instead of, or alongside, `species` when the origin requires a second species (for example `origin_syncretic_evolution`).

## Key Design Patterns

### Names and Localisation

- The top-level block key is a bare identifier derived from the filename with hyphens replaced by underscores (for example `ui_civbe_franco_iberia`).
- Every human-readable field holds a localisation key string; there is no `literal` mechanism and no `{ key = ... }` wrapper. Literal display text lives in the localisation file.
- Keys follow `<empire_key>_<field>` for species, planet, system, ship prefix, and ruler data.

### Species Configuration

All countries use `class="HUM"` (humanoid). Portraits vary:
- Base game human portraits: `human`, `human_male_05`, etc.
- Humanoid variants: `humanoid_05`, `humanoid_04`, `humanoid_hp_12`.
- Every species block includes `trait = "trait_organic"`; Stellaris 4.5 rejects designs without a species archetype trait.

### Ethics and Civics

- Fanatic ethics use `ethic_fanatic_<ethic>` (e.g., `ethic_fanatic_egalitarian`).
- Standard ethics use `ethic_<ethic>` (e.g., `ethic_pacifist`).
- Each country has exactly two civics.

### Origins

Countries use various origins:
- `origin_lost_colony` (common for human-derived)
- `origin_default`
- `origin_life_seeded`
- `origin_syncretic_evolution`

### Fallen Empire Candidates

Countries with `spawn_as_fallen=yes`:
- Drengin Empire
- Krynn Syndicate
- Sovereign Argonian Confederation
- Protoss Empire

These can spawn as fallen empires during galaxy generation.

## Invariants

- Filename stem (with `-` replaced by `_`) equals the top-level block key.
- `ignore_portrait_duplication=yes` on every country.
- `spawn_enabled=yes` on every country.
- Every species block starts with `trait = "trait_organic"`.
- No field uses `key=`, `literal=`, `species_name`, `species_plural`, `species_adjective`, `full_names`, or `flags={...}`.
- All referenced external keys exist in dependencies or base game.
- Localisation covers every resolved key string.

## Related Documentation

- [Data model](../data-model.md) — field reference.
- [Localisation](./localisation.md) — display string mapping.
- [Dependencies](../dependencies.md) — cross-mod references.
- [Change guide](../change-guide.md) — adding/modifying countries.