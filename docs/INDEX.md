# Documentation Index

## Repository Summary

**Stellaris UI Prescripted Countries** — A content-only mod adding 26 prescripted empires from 5 franchises (Civilization: Beyond Earth, The Elder Scrolls, Original, Galactic Civilizations, StarCraft) for Stellaris 3.9.*.

- **Type**: Data-only mod (no code, no scripts, no build)
- **Engine**: Stellaris (Clausewitz script + YAML localisation)
- **Dependencies**: 3 required companion mods (Flags, Name Lists, Species Traits)
- **Distribution**: Steam Workshop, Paradox Mods, Nexus Mods, GitHub Releases

## Root Document Map

| Document | Purpose |
|----------|---------|
| [README.md](../../README.md) | Project overview, installation, links |
| [ARCHITECTURE.md](../../ARCHITECTURE.md) | High-level architecture, data flows, invariants |
| [CONTRIBUTING.md](../../CONTRIBUTING.md) | Contribution guidelines |
| [SECURITY.md](../../SECURITY.md) | Security model, vulnerability reporting |
| [PRIVACY.md](../../PRIVACY.md) | Data handling (none) |
| [CODE_OF_CONDUCT.md](../../CODE_OF_CONDUCT.md) | Community standards |
| [LICENSE](../../LICENSE) | MIT License |

## Documentation Catalogue

### Overview & Structure

| Document | Description |
|----------|-------------|
| [Repository Overview](./repository-overview.md) | Purpose, scope, entry points, country catalogue, capabilities |
| [Repository Structure](./repository-structure.md) | Source tree, module organisation, naming conventions, file inventory |
| [Architecture](./architecture.md) | Complements root ARCHITECTURE.md; Mermaid diagram, data flow boundaries |

### Components (Deep Dives)

| Document | Description |
|----------|-------------|
| [Components Index](./components.md) | Component overview and cross-component relationships |
| [Mod Descriptor](./components/mod-descriptor.md) | Load-time contract, fields, engine behaviour |
| [Country Definitions](./components/country-definitions.md) | 26 empire templates, structure, design patterns |
| [Localisation](./components/localisation.md) | YAML structure, key mapping, coverage, format rules |

### Flows (End-to-End Execution)

| Document | Description |
|----------|-------------|
| [Flows Index](./flows.md) | Flow overview and relationships |
| [Mod Load & Empire Registration](./flows/mod-load-and-empire-registration.md) | Startup sequence, validation, registration |
| [Empire Selection Screen](./flows/empire-selection-screen.md) | UI presentation, filtering, selection outcome |
| [Galaxy Generation & AI Spawning](./flows/galaxy-generation-and-ai-spawning.md) | AI pool, fallen empires, diversity weighting |

### Behaviour (User-Facing)

| Document | Description |
|----------|-------------|
| [Behaviour Index](./behaviour.md) | Behaviour overview |
| [Browse & Select Empires](./behaviour/browse-and-select-empires.md) | Selection screen interaction, filters, search |
| [Preview Empire Details](./behaviour/preview-empire-details.md) | Details panel, displayed fields, completeness |

### Reference

| Document | Description |
|----------|-------------|
| [Data Model](./data-model.md) | Complete field reference (40+ fields), cross-mod reference table |
| [Dependencies](./dependencies.md) | 3 required mods, cross-mod references, failure modes |
| [Configuration](./configuration.md) | Game settings affecting mod, no user config |
| [Invariants](./invariants.md) | Mod-level, country-level, cross-mod invariants + verification script |
| [Integrations](./integrations.md) | Engine integration points, dependency integrations, platforms |

### Operations

| Document | Description |
|----------|-------------|
| [Logging](./logging.md) | Engine logging relevant to mod, debugging steps |
| [Error Handling](./error-handling.md) | Engine error responses, recovery procedures |
| [Testing](./testing.md) | Manual verification checklist, no automated tests |
| [Security](./security.md) | No attack surface, supply chain, multiplayer |
| [Build and Deployment](./build-and-deployment.md) | Packaging for 4 channels, versioning, checklist, rollback |
| [Change Guide](./change-guide.md) | Add/modify/remove empires, version updates, dependency updates |

### Design & Decisions

| Document | Description |
|----------|-------------|
| [Design Decisions](./design-decisions.md) | Decision log (10 decisions), architectural principles |
| [Ambiguities and Open Questions](./ambiguities-and-open-questions.md) | Unresolved questions, technical uncertainties, limitations |

### User Guides

| Document | Description |
|----------|-------------|
| [Quick Start](./quick-start.md) | Player installation, first game, contributor setup |
| [FAQ](./faq.md) | General, installation, gameplay, troubleshooting, development |
| [Troubleshooting](./troubleshooting.md) | Symptom-cause-fix tables, log locations, debug steps |

### Meta

| Document | Description |
|----------|-------------|
| [Documentation Maintenance](./documentation-maintenance.md) | Update triggers, review checklist, versioning |
| [State and Persistence](./state-and-persistence.md) | Save game compatibility, multiplayer sync |
| [Concurrency and Scheduling](./concurrency-and-scheduling.md) | No mod concurrency, engine scheduling phases |

## Navigation Aids

### By Audience

| Audience | Start Here |
|----------|------------|
| **Player** | [Quick Start](./quick-start.md) → [FAQ](./faq.md) → [Troubleshooting](./troubleshooting.md) |
| **Contributor** | [Quick Start](./quick-start.md#for-contributors) → [Change Guide](./change-guide.md) → [Testing](./testing.md) |
| **Maintainer** | [Architecture](./architecture.md) → [Invariants](./invariants.md) → [Build and Deployment](./build-and-deployment.md) |
| **Researcher** | [Repository Overview](./repository-overview.md) → [Data Model](./data-model.md) → [Design Decisions](./design-decisions.md) |

### By Task

| Task | Documents |
|------|-----------|
| Add new empire | [Change Guide](./change-guide.md#adding-a-new-empire) → [Country Definitions](./components/country-definitions.md) → [Localisation](./components/localisation.md) → [Testing](./testing.md) |
| Update for Stellaris version | [Change Guide](./change-guide.md#updating-for-new-stellaris-version) → [Mod Descriptor](./components/mod-descriptor.md) → [Testing](./testing.md) |
| Debug missing empire | [Troubleshooting](./troubleshooting.md) → [Error Handling](./error-handling.md) → [Logging](./logging.md) |
| Verify release | [Build and Deployment](./build-and-deployment.md#deployment-checklist) → [Testing](./testing.md) → [Invariants](./invariants.md) |

## Maintenance Metadata

- **Generated**: 2025-01-15 (session)
- **Mod version**: 1.2.2
- **Stellaris target**: 3.9.*
- **Document count**: 24 files in `docs/`
- **Last full review**: This session
- **Next review triggers**: Stellaris 3.10 release, dependency updates, new empire additions

## Cross-Reference Integrity

All internal links verified to resolve within this documentation set. Root document links point to repository root (`../../`). Component/flow/behaviour links use relative paths within `docs/`.