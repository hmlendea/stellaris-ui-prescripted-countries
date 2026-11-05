# Change Guide

## Adding a New Empire

### Prerequisites

- Flag textures in Universum Infinitum Flags
- Name list keys in Universum Infinitum Name Lists
- Species traits in Universum Infinitum Species Traits

### Steps

1. Create `ui-prescripted-countries/prescripted_countries/ui_<source>_<name>.txt`
2. Follow structure in [Country definitions](../components/country-definitions.md)
3. Add localisation entries to `ui-prescripted-countries/localisation/english/ui-prescripted-countries_l_english.yml`
4. Verify all cross-mod references exist in dependencies
5. Run [Testing](../testing.md) checklist
6. Bump version (MINOR)
7. Update both descriptor files
8. Deploy per [Build and deployment](../build-and-deployment.md)

### Naming Convention

`ui_<franchise>_<empire-name>.txt`

Examples: `ui_civbe_africa.txt`, `ui_elderscrolls_aldmeri.txt`, `ui_extra_human_roman.txt`

## Modifying an Existing Empire

1. Edit country definition file
2. Update localisation if name/adjective/planet/system changed
3. Run [Testing](../testing.md) checklist
4. Bump version (PATCH)
5. Update both descriptor files
6. Deploy

## Removing an Empire

1. Delete country definition file
2. Remove localisation entries (or leave as orphan — harmless)
3. Run [Testing](../testing.md) checklist
4. Bump version (MAJOR — breaking change)
5. Update both descriptor files
6. Deploy

## Updating for New Stellaris Version

1. Test mod with new Stellaris version (beta branch if available)
2. Update `supported_version` in both descriptor files (e.g., `3.10.*`)
3. Check for deprecated/changed empire template fields in patch notes
4. Update any affected country definitions
5. Run [Testing](../testing.md) checklist
6. Bump version (MINOR)
7. Deploy

## Updating Dependencies

1. Verify new dependency versions are compatible
2. Update cross-mod references if keys changed
3. Run [Testing](../testing.md) checklist
4. Bump version (MINOR)
5. Deploy all mods simultaneously

## Localisation Changes

1. Edit `ui-prescripted-countries/localisation/english/ui-prescripted-countries_l_english.yml`
2. Maintain UTF-8 BOM encoding
3. Run [Testing](../testing.md) checklist (focus on UI text)
4. Bump version (PATCH)
5. Deploy

## Version Bump Procedure

```bash
# Edit both files:
# ui-prescripted-countries.mod
# ui-prescripted-countries/descriptor.mod

version="1.2.3"  # new version
```

## Related Documentation

- [Build and deployment](../build-and-deployment.md)
- [Testing](../testing.md)
- [Dependencies](../dependencies.md)
- [Country definitions](../components/country-definitions.md)
- [Localisation](../components/localisation.md)