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

`.github/workflows/nexus-mods-release.yml` automates this on a `v*.*.*` tag push or manual dispatch: it checks out the tag, sets `version` in both descriptors, zips the descriptor and content directory into `release.zip`, and uploads it to file `948787` as `ui-prescripted-countries.zip` with the changelog link.

### GitHub Releases

1. Tag commit: `v<version>` (e.g., `v1.2.2`).
2. Create and publish the release with that tag.
3. `.github/workflows/github-release.yml` runs on publication: it checks out the tagged revision, strips the leading `v` to derive the version, sets `version` in `ui-prescripted-countries.mod` and `ui-prescripted-countries/descriptor.mod` (inserting the line when absent), zips those two files with `ui-prescripted-countries/` into `ui-prescripted-countries_<version>.zip`, and attaches the archive to the release.
4. No checksum is generated; the release body is left as written by the maintainer.

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
- [ ] GitHub release published, so `github-release.yml` attaches the archive
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