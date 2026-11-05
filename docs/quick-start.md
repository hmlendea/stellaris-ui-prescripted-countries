# Quick Start

## For Players

### Installation (Steam Workshop)

1. Subscribe to **Universum Infinitum: Prescripted Countries** on Steam Workshop.
2. Subscribe to the three dependencies:
   - Universum Infinitum Flags (2048949836)
   - Universum Infinitum Name Lists (2048949838)
   - Universum Infinitum Species Traits (2048949839)
3. Launch Stellaris → Mods → Enable all four.
4. Start New Game → Empire Selection → Browse 26 new empires.

### Installation (Manual)

1. Download latest release ZIP from GitHub Releases / Nexus Mods.
2. Extract `ui-prescripted-countries/` folder to Stellaris mod directory:
   - Linux: `~/Paradox Interactive/Stellaris/mod/`
   - Windows: `%USERPROFILE%\Documents\Paradox Interactive\Stellaris\mod\`
   - macOS: `~/Library/Application Support/Stellaris/mod/`
3. Place `ui-prescripted-countries.mod` in the mod directory root.
4. Install three dependency mods (same locations).
5. Enable all in launcher.

### First Game

1. New Game → Empire Selection.
2. Filter or search for "CivBE", "Elder Scrolls", "GalCiv", "StarCraft", or "Human".
3. Click an empire → preview details.
4. Confirm → configure galaxy → Start.

## For Contributors

### Repository Structure

```
stellaris-ui-prescripted-countries/
├── ui-prescripted-countries.mod          # Root descriptor (manual install)
├── ui-prescripted-countries/
│   ├── descriptor.mod                    # Workshop descriptor
│   ├── prescripted_countries/            # 26 empire definitions
│   └── localisation/english/             # English strings
└── docs/                                 # This documentation
```

### Adding an Empire

1. Ensure assets exist in dependency mods.
2. Create `ui-prescripted-countries/prescripted_countries/ui_<source>_<name>.txt`.
3. Add localisation to `ui-prescripted-countries/localisation/english/ui-prescripted-countries_l_english.yml`.
4. Test per [Testing](../testing.md).
5. Bump version, update both descriptors.
6. Submit PR.

### Key Files to Know

| File | Purpose |
|------|---------|
| `ui-prescripted-countries.mod` | Manual install descriptor |
| `ui-prescripted-countries/descriptor.mod` | Workshop descriptor |
| `prescripted_countries/*.txt` | Empire templates |
| `localisation/english/ui-prescripted-countries_l_english.yml` | Display strings |

## Related Documentation

- [Installation details](../build-and-deployment.md)
- [Change guide](../change-guide.md)
- [Testing](../testing.md)
- [Troubleshooting](../troubleshooting.md)