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

Every file follows the same top-level pattern:

```text
"<Empire Key>"={
    key="<Empire Key>"
    ship_prefix={ key="<PREFIX>" }
    species={ ... }
    name={ key="<Name Key>" }
    adjective={ key="<Adjective Key>" }
    authority="<auth_*>"
    government="<gov_*>"
    planet_name={ key="<Planet Key>" }
    planet_class="<pc_*>"
    system_name={ key="<System Key>" }
    initializer=""
    graphical_culture="<culture>"
    city_graphical_culture="<culture>"
    empire_flag={ icon={ category="<cat>" file="<file.dds>" } background={ category="<cat>" file="<file.dds>" } colors={ "<c1>" "<c2>" "<c3>" "<c4>" } }
    ruler={ ... }
    spawn_as_fallen=<yes|no>
    ignore_portrait_duplication=yes
    room="<personality_*_room>"
    spawn_enabled=yes
    ethic="<ethic_*>"
    ethic="<ethic_*>"
    civics={ "<civic_*>" "<civic_*>" }
    origin="<origin_*>"
    flags={ "human_1" "custom_start_screen" }  # optional
    advisor_voice_type="<l_*>"  # optional
    species.species_bio="<text>"  # optional
}
```

## Key Design Patterns

### Literal vs Localised Names

- Fields with `literal=yes` use the provided string directly.
- Fields without it resolve through localisation (`EMPIRE_DESIGN_<key>`).
- Most countries use localisation for `name` and `adjective`; some (e.g., Aldmeri Dominion) use `literal=yes`.

### Species Configuration

All countries use `class="HUM"` (humanoid). Portraits vary:
- Base game human portraits: `human`, `human_male_05`, etc.
- Humanoid variants: `humanoid_05`, `humanoid_04`, `humanoid_hp_12`.

### Ethics and Civics

- Fanatic ethics use `ethic_fanatic_<ethic>` (e.g., `ethic_fanatic_egalitarian`).
- Standard ethics use `ethic_<ethic>` (e.g., `ethic_pacifist`).
- Each country has exactly two civics.

### Origins

Countries use various origins:
- `origin_lost_colony` (common for human-derived)
- `origin_default`
- `origin_life_seeded`
- `origin_shoulders_of_giants`

### Fallen Empire Candidates

Countries with `spawn_as_fallen=yes`:
- Drengin Empire
- Protoss Empire

These can spawn as fallen empires during galaxy generation.

## Invariants

- Top-level block name equals `key` field.
- `ignore_portrait_duplication=yes` on every country.
- `spawn_enabled=yes` on every country.
- All referenced external keys exist in dependencies or base game.
- Localisation covers every non-literal `name` and `adjective` key.

## Related Documentation

- [Data model](../data-model.md) — field reference.
- [Localisation](./localisation.md) — display string mapping.
- [Dependencies](../dependencies.md) — cross-mod references.
- [Change guide](../change-guide.md) — adding/modifying countries.