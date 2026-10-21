[![Donate](https://img.shields.io/badge/-%E2%99%A5%20Donate-%23ff69b4)](https://hmlendea.go.ro/fund.html) [![Latest Release](https://img.shields.io/github/v/release/hmlendea/stellaris-ui-prescripted-countries)](https://github.com/hmlendea/stellaris-ui-prescripted-countries/releases/latest) [![License](https://img.shields.io/github/license/hmlendea/stellaris-ui-prescripted-countries)](https://github.com/hmlendea/stellaris-ui-prescripted-countries/blob/master/LICENSE)

# Universum Infinitum: Prescripted Countries

Mod for Stellaris that adds [many new prescripted countries](https://github.com/hmlendea/stellaris-ui-prescripted-countries/wiki/Additions) for the player or the AI to choose from when starting a new game.

## 📑 Table of Contents

- [Capabilities](#-capabilities)
- [Installation](#-installation)
  - [Manual Installation](#manual-installation)
- [Compatibility](#-compatibility)
- [Architecture](#-architecture)
- [Contributing](#-contributing)
- [Code of Conduct](#-code-of-conduct)
- [Security](#-security)
- [Universum Infinitum Collection](#-universum-infinitum-collection)

## ✨ Capabilities

- Adds 30+ prescripted countries from multiple franchises (Civilization: Beyond Earth, The Elder Scrolls, Galactic Civilizations, StarCraft, and original human cultures)
- Each country includes custom flags, name lists, species traits, and localisation
- Designed for both player and AI use
- Integrates with Universum Infinitum mod collection

## 📦 Installation

[![Obtain it from Steam Workshop](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/steam-workshop.png)](https://steamcommunity.com/sharedfiles/filedetails/?id=2048949837) [![Obtain it from Paradox Mods](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/paradox-mods.png)](https://mods.paradoxplaza.com/mods/34333/Any) [![Obtain it from Nexus Mods](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/nexus.png)](https://nexusmods.com/stellaris/mods/89) [![Obtain it from GitHub](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/github.png)](https://github.com/hmlendea/stellaris-ui-prescripted-countries/releases)

### Manual Installation

1. Download the [latest release](https://github.com/hmlendea/stellaris-ui-prescripted-countries/releases)
2. Extract the contents into your game's mod directory
3. Install [Universum Infinitum - Flags](https://github.com/hmlendea/stellaris-ui-flags) _(required mod)_
4. Install [Universum Infinitum - Name Lists](https://github.com/hmlendea/stellaris-ui-name-lists) _(required mod)_
5. Install [Universum Infinitum - Species Traits](https://github.com/hmlendea/stellaris-ui-species-traits) _(required mod)_

## 🧩 Compatibility

The mod is **OS-agnostic**, which means that it will work on all of the operating systems supported by the game.

It is actively tested (and developed) on **Linux**, where it is guaranteed to work with either the native version of the game or through Steam Play.

It should also be compatible with any other mods.

| Component | Supported Versions | Notes |
|-----------|--------------------|-------|
| Stellaris | Current version | Requires base game |
| UI Flags | Latest | Required dependency |
| UI Name Lists | Latest | Required dependency |
| UI Species Traits | Latest | Required dependency |

## 🏗️ Architecture

Universum Infinitum: Prescripted Countries is a data-driven content pack consisting entirely of declarative data files consumed by the Stellaris script parser. There is no runtime logic, no code compilation, and no process boundary.

See the [ARCHITECTURE.md](./ARCHITECTURE.md) for the system context, principal components, runtime flows, ownership boundaries, dependencies, constraints, and extension points.

## 🤝 Contributing

You are welcome to submit any suggestion, feedback, or modification to this project.

When doing so, please:
- Maintain cross-platform compatibility
- Submit focused pull requests that conform to the existing code style
- Maintain your branch synchronised with `master`
- Raise a new [issue](https://github.com/hmlendea/stellaris-ui-prescripted-countries/issues) for problems or suggestions

See the [contributing guidelines](./CONTRIBUTING.md) for details on how to report issues, suggest enhancements, and submit changes.

## 📜 Code of Conduct

See the [Code of Conduct](./CODE_OF_CONDUCT.md) for the standards of conduct expected in all project spaces.

## 🔒 Security

Universum Infinitum: Prescripted Countries follows a coordinated disclosure policy for security concerns. As a content-only Stellaris mod with no executable code, the attack surface is limited to mod content integrity and distribution channels.

For information on reporting security vulnerabilities, see [SECURITY.md](./SECURITY.md).

## 🌌 Universum Infinitum Collection

- [Character Traits](https://github.com/hmlendea/stellaris-ui-character-traits)
- [Deposit Blockers](https://github.com/hmlendea/stellaris-ui-deposit-blockers)
- [Flags](https://github.com/hmlendea/stellaris-ui-flags)
- [Galaxy Sizes](https://github.com/hmlendea/stellaris-ui-galaxy-sizes)
- [Name Lists](https://github.com/hmlendea/stellaris-ui-name-lists)
- [Planet Modifiers](https://github.com/hmlendea/stellaris-ui-planet-modifiers)
- [Prescripted Countries](https://github.com/hmlendea/stellaris-ui-prescripted-countries)
- [Species Names](https://github.com/hmlendea/stellaris-ui-species-names)
- [Species Traits](https://github.com/hmlendea/stellaris-ui-species-traits)
- [Star Names](https://github.com/hmlendea/stellaris-ui-star-names)
