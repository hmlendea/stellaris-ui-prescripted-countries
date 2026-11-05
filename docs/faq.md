# FAQ

## General

**Q: What does this mod add?**
A: 26 prescripted empires from 5 franchises (Civilization: Beyond Earth, The Elder Scrolls, Original, Galactic Civilizations, StarCraft) for use in empire selection and AI spawning.

**Q: Is this a total conversion?**
A: No. It only adds empire templates. No gameplay mechanics, events, or systems are changed.

**Q: Do I need the dependency mods?**
A: Yes. All three Universum Infinitum mods are required for flags, names, and traits to work correctly.

## Installation

**Q: How do I install manually?**
A: Place the `ui-prescripted-countries` folder in your Stellaris mod directory (typically `~/Paradox Interactive/Stellaris/mod/` on Linux, `%USERPROFILE%\Documents\Paradox Interactive\Stellaris\mod\` on Windows) and the `.mod` file in the mod directory root.

**Q: Why doesn't the mod appear in the launcher?**
A: Check that `supported_version` in the descriptor matches your Stellaris version. Check that all 3 dependencies are subscribed/enabled.

**Q: Can I use this with other empire mods?**
A: Yes, as long as they don't use duplicate empire keys.

## Gameplay

**Q: Can I play as these empires?**
A: Yes. Select them in the empire selection screen when starting a new game.

**Q: Will they spawn as AI?**
A: Yes, all 26 have `spawn_enabled=yes` and can appear as AI empires.

**Q: What are fallen empires?**
A: Drengin Empire and Protoss Empire have `spawn_as_fallen=yes` and can spawn as ancient fallen empires if the galaxy setting allows.

**Q: Can I customise a prescripted empire?**
A: Not directly. Create a custom empire in-game if you want to modify one.

## Troubleshooting

**Q: Flags show as generic placeholders.**
A: Universum Infinitum Flags mod not installed or not enabled.

**Q: Names show as raw keys (e.g., `EMPIRE_DESIGN_...`).**
A: Universum Infinitum Name Lists mod not installed, or localisation missing.

**Q: Species traits are empty.**
A: Universum Infinitum Species Traits mod not installed.

**Q: Empire missing from selection screen.**
A: Check `error.log` for parse errors in that empire's definition file.

## Development

**Q: How do I add a new empire?**
A: See [Change guide](../change-guide.md#adding-a-new-empire).

**Q: How do I update for a new Stellaris version?**
A: See [Change guide](../change-guide.md#updating-for-new-stellaris-version).

**Q: Where are the source files?**
A: `prescripted_countries/` for definitions, `localisation/english/` for strings.

## Related Documentation

- [Quick start](../quick-start.md)
- [Troubleshooting](../troubleshooting.md)
- [Change guide](../change-guide.md)
- [Dependencies](../dependencies.md)