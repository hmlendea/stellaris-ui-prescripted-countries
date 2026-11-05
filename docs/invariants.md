# Invariants

## Mod-Level Invariants

| Invariant | Description | Verification |
|-----------|-------------|--------------|
| INV-001 | Both descriptor files identical | Byte comparison |
| INV-002 | `supported_version` uses wildcard patch | Regex: `^\d+\.\d+\.\*$` |
| INV-003 | Exactly 26 country definition files | `ls prescripted_countries/*.txt \| wc -l` |
| INV-004 | All country files have unique top-level keys | Parse all, check duplicates |
| INV-005 | Every non-literal key has localisation entry | Cross-reference parse |
| INV-006 | No orphan localisation keys | Cross-reference parse |
| INV-007 | All 3 dependencies declared | Descriptor workshop IDs |
| INV-008 | Localisation file has UTF-8 BOM | `file localisation/english/*.yml` |
| INV-009 | All empires have `ignore_portrait_duplication=yes` | Parse all country files |
| INV-010 | All empires have `spawn_enabled=yes` | Parse all country files |

## Country-Level Invariants (per empire)

| Invariant | Description |
|-----------|-------------|
| CINV-001 | Top-level block name equals `key` field |
| CINV-002 | `species.class="HUM"` |
| CINV-003 | Exactly 2 `ethic` entries (fanatic counts as 1 entry) |
| CINV-004 | Exactly 2 `civics` entries |
| CINV-005 | `origin` present and valid |
| CINV-006 | `authority` valid base game authority |
| CINV-007 | `government` valid for authority |
| CINV-008 | `planet_class` valid base game class |
| CINV-009 | `graphical_culture` valid |
| CINV-010 | `city_graphical_culture` valid |
| CINV-011 | `empire_flag` has icon, background, 4 colors |
| CINV-012 | `ruler` block present with name, portrait, texture |
| CINV-013 | `room` valid personality room |
| CINV-014 | `ship_prefix` has `key` field |

## Cross-Mod Reference Invariants

| Invariant | Description |
|-----------|-------------|
| XINV-001 | All `empire_flag` icon/background files exist in Flags mod |
| XINV-002 | All `name_list` keys exist in Name Lists mod |
| XINV-003 | All `species.traits` keys exist in Species Traits mod |

## Verification Script

```bash
#!/bin/bash
# verify-invariants.sh

echo "Checking INV-001: Descriptor files identical..."
diff ui-prescripted-countries.mod ui-prescripted-countries/descriptor.mod && echo "OK" || echo "FAIL"

echo "Checking INV-003: 26 country files..."
COUNT=$(ls ui-prescripted-countries/prescripted_countries/*.txt | wc -l)
[ "$COUNT" -eq 26 ] && echo "OK ($COUNT)" || echo "FAIL ($COUNT)"

echo "Checking INV-008: UTF-8 BOM..."
file ui-prescripted-countries/localisation/english/ui-prescripted-countries_l_english.yml | grep -q "UTF-8 Unicode (with BOM)" && echo "OK" || echo "FAIL"

echo "Checking CINV-001, CINV-009, CINV-010..."
for f in ui-prescripted-countries/prescripted_countries/*.txt; do
    KEY=$(basename "$f" .txt | sed 's/^ui_//')
    # Add parsing logic here
done
```

## Related Documentation

- [Architecture](../architecture.md)
- [Country definitions](../components/country-definitions.md)
- [Data model](../data-model.md)
- [Testing](../testing.md)