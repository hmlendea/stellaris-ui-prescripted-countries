# Security

## Mod Security Model

This mod has no attack surface. It contains:
- No executable code
- No network communication
- No file I/O
- No user input processing
- No privilege escalation vectors

## Supply Chain

| Component | Source | Verification |
|-----------|--------|--------------|
| Mod content | This repository | Git history, signed releases |
| Dependencies | Steam Workshop / Paradox Mods | Platform integrity checks |
| Stellaris engine | Paradox Interactive | Platform integrity checks |

## Data Integrity

- Mod files are static assets.
- No runtime modification of mod files.
- Steam Workshop / Paradox Mods / Nexus Mods provide content-addressable distribution.
- GitHub release archives are built by `.github/workflows/github-release.yml` from the tagged revision, so they match the release tag.

## No Secrets

- No API keys, tokens, passwords, or certificates in mod.
- No telemetry or analytics.
- No user data collection.

## Multiplayer

- Mod is data-only; no desync risk from mod content.
- All players must have identical mod + dependencies for consistent experience.
- Launcher enforces version matching.

## Related Documentation

- [Privacy policy](../../PRIVACY.md)
- [Dependencies](../dependencies.md)
- [Build and deployment](../build-and-deployment.md)