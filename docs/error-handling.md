# Error Handling

## Mod Error Handling

This mod has no error handling code. It is pure data.

## Engine Error Handling for Mod Content

| Error Type | Engine Response | User Visible |
|------------|-----------------|--------------|
| `supported_version` mismatch | Mod disabled in launcher | Launcher error dialog |
| Missing dependency | Mod disabled in launcher | Launcher error dialog |
| Country definition syntax error | Skip file, log warning | Empire missing from selection |
| Localisation syntax error | Skip file, log warning | Raw keys shown in UI |
| Duplicate empire key | Second ignored, log warning | One empire missing |
| Missing localisation key | Show raw key in UI | Raw key visible (e.g., `EMPIRE_DESIGN_...`) |
| Missing flag texture | Show placeholder flag | Generic flag shown |
| Missing name list | Show raw key | Raw key in UI |
| Missing species trait | Trait slot empty | No trait bonus/malus |

## Recovery Procedures

| Issue | Resolution |
|-------|------------|
| Mod disabled (version) | Update `supported_version` in both descriptor files |
| Mod disabled (dependency) | Subscribe to missing workshop items |
| Empire missing | Fix syntax in country definition file |
| Raw keys in UI | Add missing localisation entries |
| Placeholder flag | Verify Universum Infinitum Flags installed |
| Empty traits | Verify Universum Infinitum Species Traits installed |

## No Runtime Exceptions

- No code → no exceptions.
- No save game corruption from mod.
- No multiplayer desync from mod (data only).

## Related Documentation

- [Logging](../logging.md)
- [Troubleshooting](../troubleshooting.md)
- [Change guide](../change-guide.md)