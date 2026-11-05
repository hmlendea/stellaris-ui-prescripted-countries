# Troubleshooting

## Mod Not Loading

| Symptom | Cause | Fix |
|---------|-------|-----|
| Mod not in launcher list | `.mod` file not in mod directory | Place `ui-prescripted-countries.mod` in Stellaris mod directory |
| Mod disabled (red) | `supported_version` mismatch | Update descriptor to match installed Stellaris version |
| Mod disabled (red) | Missing dependency | Subscribe to all 3 workshop items |
| Mod loads but no empires | Parse error in country files | Check `error.log` for warnings |

## Empires Missing or Broken

| Symptom | Cause | Fix |
|---------|-------|-----|
| Empire missing from list | Syntax error in its `.txt` file | Fix syntax, verify braces/brackets |
| Name shows `EMPIRE_DESIGN_...` | Missing localisation entry | Add entry to `ui-prescripted-countries_l_english.yml` |
| Flag is generic placeholder | Flags mod not loaded | Enable Universum Infinitum Flags |
| Traits empty | Species Traits mod not loaded | Enable Universum Infinitum Species Traits |
| Ship names show keys | Name Lists mod not loaded | Enable Universum Infinitum Name Lists |

## Save Game Issues

| Symptom | Cause | Fix |
|---------|-------|-----|
| Save won't load after mod update | Empire template changed | Revert mod or start new game |
| Crash on load | Removed empire referenced in save | Don't remove empires; disable instead |

## Multiplayer Issues

| Symptom | Cause | Fix |
|---------|-------|-----|
| Desync on join | Mod version mismatch | All players use same mod version |
| Missing empires for client | Client missing dependencies | All players enable all 3 dependencies |
| Different flags | Different Flags mod version | All players update Flags mod |

## Log Files

- Launcher log: `~/Paradox Interactive/Stellaris/logs/launcher.log` (Linux)
- Game log: `~/Paradox Interactive/Stellaris/logs/error.log` (Linux)
- Windows: `%USERPROFILE%\Documents\Paradox Interactive\Stellaris\logs\`

## Debug Steps

1. Verify all 3 dependencies enabled in launcher.
2. Check `error.log` for `[warning]` lines mentioning mod name.
3. Verify `supported_version` matches game version exactly.
4. Try loading only this mod + dependencies (disable others).
5. Verify localisation file has UTF-8 BOM: `file localisation/english/*.yml`.

## Related Documentation

- [Error handling](../error-handling.md)
- [Logging](../logging.md)
- [Dependencies](../dependencies.md)
- [Change guide](../change-guide.md)