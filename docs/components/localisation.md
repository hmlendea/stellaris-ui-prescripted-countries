# Localisation

## Purpose

Maps localisation keys to English display strings. The Stellaris engine resolves every `name`, `adjective`, `planet_name`, `system_name`, `ship_prefix`, species name/plural/adjective, and ruler name/title through this file.

## File

`ui-prescripted-countries/localisation/english/ui-prescripted-countries_l_english.yml`

## Structure

```yaml
l_english:
  EMPIRE_DESIGN_<empire_key>:0 "<Display Name>"
  EMPIRE_DESIGN_<empire_key>_desc:0 "<Description>"
  EMPIRE_DESIGN_<empire_key>_adj:0 "<Adjective>"
  <empire_key>_species_name:0 "<Species>"
  <empire_key>_species_plural:0 "<Species plural>"
  <empire_key>_species_adjective:0 "<Species adjective>"
  <empire_key>_planet_name:0 "<Homeworld Name>"
  <empire_key>_system_name:0 "<System Name>"
  <empire_key>_ship_prefix:0 "<Ship Prefix>"
  <empire_key>_ruler_name:0 "<Ruler Name>"
  <empire_key>_ruler_title:0 "<Ruler Title>"
  <empire_key>_ruler_title_female:0 "<Female Ruler Title>"
```

## Key Naming Convention

| Field in country definition | Localisation key pattern |
|----------------------------|--------------------------|
| `name` | `EMPIRE_DESIGN_<empire_key>` |
| `adjective` | `EMPIRE_DESIGN_<empire_key>_adj` |
| `species.name` | `<empire_key>_species_name` |
| `species.plural` | `<empire_key>_species_plural` |
| `species.adjective` | `<empire_key>_species_adjective` |
| `planet_name` | `<empire_key>_planet_name` |
| `system_name` | `<empire_key>_system_name` |
| `ship_prefix` | `<empire_key>_ship_prefix` |
| `ruler.name` | `<empire_key>_ruler_name` |
| `ruler.ruler_title` | `<empire_key>_ruler_title` |
| `ruler.ruler_title_female` | `<empire_key>_ruler_title_female` |

`empire_key` is the filename stem with hyphens replaced by underscores, for example `ui_civbe_franco_iberia`.

## Shared Human Strings

Human-derived designs reuse vanilla species strings through `$KEY$` indirection:

```yaml
 ui_civbe_africa_species_name:0 "$PRESCRIPTED_species_name_humans1$"
 ui_civbe_africa_species_plural:0 "$PRESCRIPTED_species_plural_humans1$"
 ui_civbe_africa_species_adjective:0 "$PRESCRIPTED_species_adjective_humans1$"
```

## Coverage

All 26 countries have entries for:
- `name` and `adjective`
- species name, plural, and adjective
- `planet_name`, `system_name`, `ship_prefix`
- `ruler_name`, and ruler titles where defined

Description (`_desc`) entries exist for 5 countries only; the rest omit the key rather than declaring empty text.

## YAML Format Rules

- File encoding: UTF-8 with BOM (required by Stellaris).
- Indentation: 2 spaces.
- Keys unquoted; values double-quoted.
- Special characters escaped per YAML spec.
- No inline comments (Stellaris parser may reject).

## Invariants

- Every non-literal key in country definitions has a matching localisation entry.
- No orphan localisation keys (every key is referenced by at least one country).
- UTF-8 BOM present.
- Single `l_english:` root key.

## Related Documentation

- [Data model](../data-model.md) — field reference.
- [Country definitions](./country-definitions.md) — key usage.
- [Change guide](../change-guide.md) — adding localisation.