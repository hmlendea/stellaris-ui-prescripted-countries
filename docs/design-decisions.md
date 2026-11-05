# Design Decisions

## Decision Log

| ID | Decision | Rationale | Alternatives Considered |
|----|----------|-----------|------------------------|
| DD-001 | Pure data mod (no code) | Stellaris empire templates are declarative; no runtime logic needed | Scripted effects, events — rejected: unnecessary complexity |
| DD-002 | Separate descriptor files for manual vs Workshop | Steam Workshop requires descriptor inside mod folder; manual install uses root mod directory | Single file — rejected: breaks one installation method |
| DD-003 | Three separate dependency mods | Flags, name lists, traits are large; separate maintenance; optional for other modders | Single mega-dependency — rejected: bloats unrelated mods |
| DD-004 | All empires use humanoid species class | Source franchises are human/humanoid; base game humanoid portraits sufficient | Custom species classes — rejected: requires portrait mods |
| DD-005 | Localisation only in English | Mod author English-only; community can contribute translations | Multi-language at launch — rejected: resource constraint |
| DD-006 | `ignore_portrait_duplication=yes` on all empires | Multiple empires share portraits (e.g., human_male_05); prevents launch warnings | Unique portraits per empire — rejected: portrait limit |
| DD-007 | `spawn_enabled=yes` on all empires | All empires intended for AI spawning; player can disable in game settings | Selective spawning — rejected: arbitrary exclusion |
| DD-008 | Two fallen empire candidates only | Drengin and Protoss fit fallen empire lore (ancient, powerful); others don't | More fallen empires — rejected: lore mismatch |
| DD-009 | UTF-8 BOM required for localisation | Stellaris YAML parser requires BOM | UTF-8 without BOM — rejected: parser fails |
| DD-010 | No custom government types | Base game authorities/governments cover all franchise archetypes | Custom authorities — rejected: requires code, save incompatibility |

## Architectural Principles

1. **Data-only**: No scripts, events, or code. Engine is sole consumer.
2. **Dependency separation**: Assets decoupled into focused companion mods.
3. **Lore fidelity**: Empires match source franchise identity within game mechanics.
4. **Balance neutrality**: Stats comparable to base game empires; no overpowered designs.
5. **Maintainability**: Clear naming, consistent structure, documented cross-references.

## Related Documentation

- [Architecture](../architecture.md)
- [Country definitions](../components/country-definitions.md)
- [Dependencies](../dependencies.md)
- [Change guide](../change-guide.md)