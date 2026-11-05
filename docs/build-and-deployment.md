# Build and Deployment

## Build Process

No build process. Mod is pure data files.

## Packaging

### Steam Workshop / Paradox Mods

1. Ensure `ui-prescripted-countries/descriptor.mod` matches root `ui-prescripted-countries.mod`.
2. Use Paradox Mod Tools or Steam Workshop uploader.
3. Point to `ui-prescripted-countries/` folder.
4. Publish with version tag matching `version` field.

### Nexus Mods

1. Create ZIP of `ui-prescripted-countries/` folder.
2. Name: `ui-prescripted-countries-<version>.zip`.
3. Upload to Nexus Mods with version metadata.

### GitHub Releases

1. Tag commit: `v<version>` (e.g., `v1.2.2`).
2. Create release with tag.
3. Attach ZIP of `ui-prescripted-countries/` folder.
4. Include SHA256 checksum in release notes.

## Versioning

Semantic versioning: `MAJOR.MINOR.PATCH`

| Change Type | Version Bump |
|-------------|--------------|
| New empire added | MINOR |
| Empire modified (stats, ethics, etc.) | PATCH |
| Localisation fix | PATCH |
| Dependency update | MINOR |
| Stellaris version support update | MINOR |
| Breaking change (removed empire) | MAJOR |

## Deployment Checklist

- [ ] Both descriptor files identical
- [ ] `supported_version` matches target Stellaris version
- [ ] All 26 country files present
- [ ] Localisation complete (no missing keys)
- [ ] Dependencies updated to compatible versions
- [ ] Version bumped in both descriptors
- [ ] Git tag created
- [ ] GitHub release created with checksum
- [ ] Steam Workshop updated
- [ ] Paradox Mods updated
- [ ] Nexus Mods updated

## Rollback

- Previous version tags preserved in Git.
- Workshop/Paradox/Nexus allow reverting to previous upload.
- No database migrations or state changes to roll back.

## Related Documentation

- [Change guide](../change-guide.md)
- [Dependencies](../dependencies.md)
- [Testing](../testing.md)