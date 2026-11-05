# Mod Descriptor

## Purpose

The mod descriptor is the load-time contract between the mod and the Stellaris launcher/engine. It declares identity, version, supported game version, tags, and filesystem path.

## Files

| File | Installation method |
|------|---------------------|
| `ui-prescripted-countries.mod` | Manual installation (placed in Stellaris mod directory) |
| `ui-prescripted-countries/descriptor.mod` | Steam Workshop / Paradox Mods (inside mod folder) |

Both files must contain identical content.

## Fields

```text
version="1.2.2"
name="Universum Infinitum: Prescripted Countries"
path="mod/ui-prescripted-countries"
tags={
    "Galaxy Generation"
}
supported_version="3.9.*"
```

| Field | Description | Update policy |
|-------|-------------|---------------|
| `version` | Semantic version of the mod content. | Bump on every content change. |
| `name` | Display name in launcher. | Stable; change only for rebranding. |
| `path` | Filesystem path relative to Stellaris mod directory. | Must match folder name. |
| `tags` | Categorisation tags for launcher filtering. | Add tags as appropriate; do not remove existing. |
| `supported_version` | Stellaris version pattern the mod targets. | Update for each Stellaris major/minor release (e.g., `3.10.*`). |

## Engine Behaviour

1. Launcher reads descriptor.
2. Validates `supported_version` against installed game version.
3. If mismatch: mod is disabled and launcher shows error.
4. If match: launcher loads required dependencies first (by workshop ID), then this mod.
5. Engine parses `prescripted_countries/*.txt` and `localisation/*.yml`.

## Invariants

- Both descriptor files are byte-for-byte identical.
- `supported_version` uses wildcard patch (`3.9.*`).
- `path` matches the mod folder name exactly.

## Related Documentation

- [Architecture](../architecture.md) — load-time flow.
- [Dependencies](../dependencies.md) — required companion mods.
- [Change guide](../change-guide.md) — version bump procedure.