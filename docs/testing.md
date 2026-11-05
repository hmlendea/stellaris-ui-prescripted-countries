# Testing

## Mod Testing

This mod has no automated tests. It is pure data consumed by the Stellaris engine.

## Manual Verification Checklist

### Pre-Release Validation

| Check | Method | Pass Criteria |
|-------|--------|---------------|
| Descriptor syntax | Launch game with mod enabled | Mod appears in launcher, no error |
| Dependency resolution | Launch game with mod enabled | All 3 dependencies show loaded |
| Country parse | Start new game → Empire Selection | All 26 empires listed |
| Localisation resolve | Select each empire in turn | No raw keys in UI |
| Flag render | Select each empire in turn | Custom flag visible |
| AI spawn | Start game with max AI empires | Mod empires appear as AI |
| Fallen empire | Start game with fallen empires enabled | Drengin/Protoss can spawn as fallen |
| Save/load | Save game, reload | No corruption, empires persist |
| Multiplayer | Host game with mod | All players see same empires |

### Regression Checks

- Run full checklist after any country definition change.
- Run full checklist after localisation change.
- Run full checklist after Stellaris version update.
- Run full checklist after dependency mod updates.

## No Unit Tests

- No test framework applicable.
- No code to unit test.
- No CI pipeline for testing.

## No Integration Tests

- No external systems to integrate with.
- Engine is the only consumer.

## Related Documentation

- [Change guide](../change-guide.md)
- [Troubleshooting](../troubleshooting.md)
- [Quick start](../quick-start.md)