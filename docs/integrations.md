# Integrations

## Stellaris Engine Integration

This mod integrates with Stellaris exclusively through the empire template registration system.

### Integration Points

| Integration Point | Mechanism | Mod Contribution |
|-------------------|-----------|------------------|
| Mod loading | `.mod` descriptor | Identity, version, dependencies |
| Empire registration | `prescripted_countries/*.txt` | 26 empire templates |
| String resolution | `localisation/*.yml` | English display strings |
| Asset resolution | Dependency mods | Flags, name lists, traits |

### Engine APIs Consumed

- Empire template parser (Clausewitz script format)
- Localisation system (YAML, UTF-8 BOM)
- Flag rendering (DDS textures via category/file)
- Name list system (key-based lookup)
- Species trait system (key-based lookup)

### No Custom Engine Extensions

- No scripted effects
- No scripted triggers
- No events
- No on_actions
- No defines overrides
- No GUI modifications

## Dependency Mod Integrations

### Universum Infinitum Flags (2048949836)

Provides flag textures referenced by `empire_flag.icon` and `empire_flag.background`.

### Universum Infinitum Name Lists (2048949838)

Provides name list keys referenced by `name`, `adjective`, `planet_name`, `system_name`, `ship_prefix`.

### Universum Infinitum Species Traits (2048949839)

Provides trait keys referenced by `species.traits`.

## Distribution Platform Integrations

| Platform | Integration Method |
|----------|-------------------|
| Steam Workshop | Paradox Mod Tools upload |
| Paradox Mods | Paradox Mod Tools upload |
| Nexus Mods | Manual ZIP upload |
| GitHub Releases | Git tag + release assets |

## No External Integrations

- No web APIs
- No databases
- No message queues
- No authentication systems
- No telemetry endpoints

## Related Documentation

- [Dependencies](../dependencies.md)
- [Architecture](../architecture.md)
- [Build and deployment](../build-and-deployment.md)