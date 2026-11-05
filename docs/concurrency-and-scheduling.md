# Concurrency and Scheduling

## Mod Concurrency Model

This mod has no concurrency concerns. It contains no executable code, no threads, no async operations.

## Engine Scheduling Relevant to Mod

| Phase | Timing | Mod Impact |
|-------|--------|------------|
| Mod loading | Game startup, before main menu | Sequential, single-threaded |
| Empire registration | During mod loading | Sequential, 26 templates |
| Localisation loading | During mod loading | Sequential, single file |
| Empire selection UI | Player interaction | Main thread, event-driven |
| Galaxy generation | New game start | Background thread (engine) |
| AI empire spawning | During galaxy generation | Background thread (engine) |

## No Mod Scheduling

- No timers
- No recurring tasks
- No background jobs
- No thread pools
- No async/await

## Thread Safety

- Mod data is immutable after load.
- Engine reads mod data from multiple threads (UI, galaxy gen) — safe because immutable.
- No shared mutable state.

## Related Documentation

- [Architecture](../architecture.md)
- [Flows](../flows.md)
- [State and persistence](../state-and-persistence.md)