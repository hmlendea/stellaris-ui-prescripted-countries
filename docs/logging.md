# Logging

## Mod Logging

This mod produces no logs. It contains no executable code.

## Engine Logging Relevant to Mod

| Log Source | Event | Log Level |
|------------|-------|-----------|
| Launcher | Mod load success/failure | Info / Error |
| Engine | Country definition parse errors | Warning |
| Engine | Localisation parse errors | Warning |
| Engine | Missing dependency detection | Error |
| Engine | Duplicate empire key detection | Warning |

## Debugging Mod Issues

1. Check launcher log for mod load status.
2. Check `error.log` in Stellaris user directory for parse warnings.
3. Verify all 3 dependencies show as loaded in launcher.
4. Verify `supported_version` matches installed game version.

## No Mod-Specific Log Files

- No log output from country definition files.
- No log output from localisation files.
- No custom log categories.

## Related Documentation

- [Troubleshooting](../troubleshooting.md)
- [Error handling](../error-handling.md)