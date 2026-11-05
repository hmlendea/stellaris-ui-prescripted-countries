# State and Persistence

## Mod State

This mod has no runtime state. It is pure static data loaded at game start.

## Persistence in Save Games

| Data | Persisted? | Notes |
|------|------------|-------|
| Empire templates | Yes | Registered at load, referenced by save |
| Player's chosen empire | Yes | Full empire state saved |
| AI empires spawned from templates | Yes | Full empire state saved |
| Localisation strings | No | Resolved at load from mod files |
| Flag textures | No | Loaded from dependency mod at runtime |

## Save Game Compatibility

- Adding new empires: **Compatible** (new templates ignored by old saves)
- Modifying existing empires: **Breaking** (save references old template data)
- Removing empires: **Breaking** (save references missing template)
- Localisation changes: **Compatible** (strings re-resolved at load)
- Dependency updates: **Compatible** if keys unchanged

## No Mod-Specific Save Data

- No custom save game sections
- No persistent flags or variables
- No event chains that modify state

## Multiplayer State Sync

- All players must have identical mod + dependencies
- Empire templates synced via host's mod data
- No desync risk from mod content (deterministic data)

## Related Documentation

- [Architecture](../architecture.md)
- [Change guide](../change-guide.md)
- [Testing](../testing.md)