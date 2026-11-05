# Ambiguities and Open Questions

## Unresolved Design Questions

| ID | Question | Context | Status |
|----|----------|---------|--------|
| AQ-001 | Should more franchises be added? | Current: 5 franchises, 26 empires. Requests for Mass Effect, Halo, 40K. | Open |
| AQ-002 | Should non-humanoid species be added? | All current empires use HUM class. Some franchises have non-humanoid races. | Open |
| AQ-003 | Should localisations be added for other languages? | Currently English only. Community translations possible. | Open |
| AQ-004 | Should empire balance be adjusted for multiplayer? | Current stats mirror base game. Competitive players may want tuning. | Open |
| AQ-005 | Should fallen empire candidates be expanded? | Only 2 currently. More could add variety. | Open |

## Technical Uncertainties

| ID | Uncertainty | Impact | Mitigation |
|----|-------------|--------|------------|
| TU-001 | Stellaris 4.0 breaking changes | Empire template format may change | Monitor dev diaries, test on beta |
| TU-002 | Dependency mod breaking changes | Keys may change, breaking references | Coordinate with dependency maintainers |
| TU-003 | Workshop upload limits | File count/size limits may be hit | Current 28 files well under limits |

## Known Limitations

| Limitation | Workaround |
|------------|------------|
| No custom portraits | Use base game humanoid variants |
| No custom ship sets | Use graphical_culture from base game |
| No custom city appearances | Use city_graphical_culture from base game |
| No custom advisor voices | Limited to base game voice types |
| English only | Community translations welcome |

## Dependency Risks

| Risk | Likelihood | Impact | Contingency |
|------|------------|--------|-------------|
| Dependency mod abandoned | Low | High (broken flags/names/traits) | Fork dependencies, self-host |
| Workshop ID changes | Very low | Medium | Update descriptor workshop IDs |
| Paradox Mods deprecation | Low | Medium | GitHub Releases + Nexus as fallback |

## Future Investigation

- Investigate scripted localisation for dynamic names.
- Explore `create_country` effect for dynamic empire creation.
- Research `on_game_start` for custom initialisation.
- Evaluate `country_type` for special empire categories.

## Related Documentation

- [Design decisions](../design-decisions.md)
- [Change guide](../change-guide.md)
- [Dependencies](../dependencies.md)