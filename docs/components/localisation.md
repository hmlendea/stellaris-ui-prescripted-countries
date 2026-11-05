# Localisation

## Purpose

Maps localisation keys to English display strings. The Stellaris engine resolves every non-literal `name`, `adjective`, `planet_name`, `system_name`, `ship_prefix`, and `species_bio` through this file.

## File

`ui-prescripted-countries/localisation/english/ui-prescripted-countries_l_english.yml`

## Structure

```yaml
l_english:
  EMPIRE_DESIGN_<key>: "<Display Name>"
  EMPIRE_DESIGN_<key>_ADJ: "<Adjective>"
  EMPIRE_DESIGN_<key>_PLANET: "<Homeworld Name>"
  EMPIRE_DESIGN_<key>_SYSTEM: "<System Name>"
  EMPIRE_DESIGN_<key>_SHIP_PREFIX: "<Ship Prefix>"
  EMPIRE_DESIGN_<key>_SPECIES_BIO: "<Flavour Text>"
```

## Key Naming Convention

| Field in country definition | Localisation key suffix |
|----------------------------|------------------------|
| `name` | `_` (base key) |
| `adjective` | `_ADJ` |
| `planet_name` | `_PLANET` |
| `system_name` | `_SYSTEM` |
| `ship_prefix` | `_SHIP_PREFIX` |
| `species_bio` | `_SPECIES_BIO` |

Base key format: `EMPIRE_DESIGN_<UPPERCASE_EMPIRE_KEY>`

Example: `ui_civbe_africa.txt` → `EMPIRE_DESIGN_PEOPLES_AFRICAN_UNION`

## Coverage

All 26 countries have entries for:
- `name` (base key)
- `adjective` (`_ADJ`)
- `planet_name` (`_PLANET`)
- `system_name` (`_SYSTEM`)
- `ship_prefix` (`_SHIP_PREFIX`)

Only some countries have `species_bio` (`_SPECIES_BIO`):
- Aldmeri Dominion
- Argonia
- Arabian, Celtic, French, Hellenic, Italian, Japanese, Norse, Ottoman, Roman
- Altarian Republic, Drengin Empire, Krynn Consulate, Torian Confederation, Yor Collective
- Protoss Empire, Terran Dominion

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