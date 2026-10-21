[![Donate](https://img.shields.io/badge/-%E2%99%A5%20Donate-%23ff69b4)](https://hmlendea.go.ro/funding)
[![Latest Release](https://img.shields.io/github/v/release/hmlendea/stellaris-ui-prescripted-countries)](https://github.com/hmlendea/stellaris-ui-prescripted-countries/releases/latest)
[![License](https://img.shields.io/github/license/hmlendea/stellaris-ui-prescripted-countries)](https://github.com/hmlendea/stellaris-ui-prescripted-countries/blob/master/LICENSE)

# Universum Infinitum: Prescripted Countries

A Stellaris mod adding prescripted countries for players to select or for the AI to use when starting a new game.

## 📑 Table of Contents

- [Capabilities](#-capabilities)
- [Use Cases](#-use-cases)
- [Usage](#-usage)
- [Known Limitations](#-known-limitations)
- [Installation](#-installation)
  - [Manual Installation](#manual-installation)
- [Localisation](#-localisation)
- [Compatibility](#-compatibility)
- [Integrations](#-integrations)
- [Privacy and Data](#-privacy-and-data)
- [Development](#-development)
  - [Requirements](#requirements)
  - [Setup](#setup)
- [Project Structure](#-project-structure)
  - [Directories](#directories)
- [Architecture](#-architecture)
- [Documentation](#-documentation)
- [Contributing](#-contributing)
- [Code of Conduct](#-code-of-conduct)
- [Related Projects](#-related-projects)
- [Security](#-security)
- [Project Engagement](#-project-engagement)
- [License](#-license)

## ✨ Capabilities

- Adds prescripted countries from Civilization: Beyond Earth, The Elder Scrolls, Galactic Civilizations, StarCraft, and original human cultures.
- Provides country definitions with custom flags, name lists, species traits, and English localisation.
- Makes the countries available for player selection and AI use.

## 🎯 Use Cases

- **Player empires:** Select a prescripted country when starting a new Stellaris game.
- **AI empires:** Enable the countries as candidates for AI empires during galaxy generation.

## 🚀 Usage

Enable this mod and its required companion mods in the Stellaris launcher. Start a new game and select one of the added prescripted countries, or allow eligible countries to spawn for AI empires.

## ⚠️ Known Limitations

- The mod metadata declares compatibility with Stellaris 3.9.*; compatibility with other game versions is not specified.
- English is the only localisation included in this repository, and some country descriptions remain marked `TODO.`.

## 📦 Installation

[![Obtain it from Steam Workshop](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/steam-workshop.png)](https://steamcommunity.com/sharedfiles/filedetails/?id=2048949837)
[![Obtain it from Paradox Mods](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/paradox-mods.png)](https://mods.paradoxplaza.com/mods/34333/Any)
[![Obtain it from Nexus Mods](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/nexus.png)](https://nexusmods.com/stellaris/mods/89)
[![Obtain it from GitHub](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/github.png)](https://github.com/hmlendea/stellaris-ui-prescripted-countries/releases)

### Manual Installation

1. Download the [latest release](https://github.com/hmlendea/stellaris-ui-prescripted-countries/releases).
2. Extract the mod into the Stellaris mod directory.
3. Install [Universum Infinitum - Flags](https://github.com/hmlendea/stellaris-ui-flags).
4. Install [Universum Infinitum - Name Lists](https://github.com/hmlendea/stellaris-ui-name-lists).
5. Install [Universum Infinitum - Species Traits](https://github.com/hmlendea/stellaris-ui-species-traits).
6. Enable this mod and its dependencies in the Stellaris launcher.

## 🌍 Localisation

The repository includes English localisation strings for country names and descriptions.

| Language | Locale | Status |
|----------|--------|--------|
| English | `en` | Partial |

## 🧩 Compatibility

| Component | Supported Versions | Notes |
|-----------|--------------------|-------|
| Stellaris | 3.9.* | Required game; version declared by the mod metadata |
| Universum Infinitum - Flags | Not version-pinned | Required companion mod |
| Universum Infinitum - Name Lists | Not version-pinned | Required companion mod |
| Universum Infinitum - Species Traits | Not version-pinned | Required companion mod |

## 🔌 Integrations

| Integration | Compatibility | Purpose | Required |
|-------------|---------------|---------|----------|
| Stellaris | 3.9.* | Loads the mod content and provides the game environment. | Yes |
| [Universum Infinitum - Flags](https://github.com/hmlendea/stellaris-ui-flags) | Not version-pinned | Provides custom flag assets referenced by country definitions. | Yes |
| [Universum Infinitum - Name Lists](https://github.com/hmlendea/stellaris-ui-name-lists) | Not version-pinned | Provides name lists referenced by country definitions. | Yes |
| [Universum Infinitum - Species Traits](https://github.com/hmlendea/stellaris-ui-species-traits) | Not version-pinned | Provides species traits referenced by country definitions. | Yes |

## 🛡️ Privacy and Data

Universum Infinitum: Prescripted Countries does not collect, process, transmit, or persist personal data. The mod contains static game configuration and localisation files.

For the detailed description of how the application handles privacy and personal data, see [PRIVACY.md](./PRIVACY.md).

## 🛠️ Development

### Requirements

- Git

### Setup

```bash
git clone https://github.com/hmlendea/stellaris-ui-prescripted-countries.git
cd stellaris-ui-prescripted-countries
```

No dependency installation or compilation is required for this content-only mod.

## 🗂️ Project Structure

The repository contains the mod descriptor and the Stellaris content files for one mod.

### Directories

| Directory | Purpose |
|-----------|---------|
| `ui-prescripted-countries/localisation/` | English country names and descriptions. |
| `ui-prescripted-countries/prescripted_countries/` | Prescripted country definitions. |

## 🏗️ Architecture

Universum Infinitum: Prescripted Countries is a data-driven content pack with no executable code.

See the [architecture documentation](./ARCHITECTURE.md) for the system context, principal components, runtime flows, ownership boundaries, dependencies, constraints, and extension points.

## 📚 Documentation

The project wiki lists the countries included in the mod.

| Resource | Description |
|----------|-------------|
| [Country additions](https://github.com/hmlendea/stellaris-ui-prescripted-countries/wiki/Additions) | Prescripted countries included in the mod. |

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

## 🔗 Related Projects

- [Character Traits](https://github.com/hmlendea/stellaris-ui-character-traits): Adds character traits for Stellaris.
- [Deposit Blockers](https://github.com/hmlendea/stellaris-ui-deposit-blockers): Adds deposit blockers for Stellaris.
- [Flags](https://github.com/hmlendea/stellaris-ui-flags): Supplies flag assets used by this mod.
- [Galaxy Sizes](https://github.com/hmlendea/stellaris-ui-galaxy-sizes): Adds galaxy size options for Stellaris.
- [Name Lists](https://github.com/hmlendea/stellaris-ui-name-lists): Supplies name lists used by this mod.
- [Planet Modifiers](https://github.com/hmlendea/stellaris-ui-planet-modifiers): Adds planet modifiers for Stellaris.
- [Species Names](https://github.com/hmlendea/stellaris-ui-species-names): Adds species names for Stellaris.
- [Species Traits](https://github.com/hmlendea/stellaris-ui-species-traits): Supplies species traits used by this mod.
- [Star Names](https://github.com/hmlendea/stellaris-ui-star-names): Adds star names for Stellaris.

## 🔒 Security

Universum Infinitum: Prescripted Countries is a content-only Stellaris mod with no executable code; security risks are limited to mod content integrity and distribution channels.

For information on reporting security vulnerabilities, see [SECURITY.md](./SECURITY.md).

## 💝 Project Engagement

Discovered a problem or have a suggestion? [Open an issue](https://github.com/hmlendea/stellaris-ui-prescripted-countries/issues)!

If you find this project useful, consider [funding it](https://hmlendea.go.ro/funding) or starring ⭐️ it on GitHub, or giving it a thumbs up and adding it as a favourite on the [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=2048949837)!

[![Donate](https://raw.githubusercontent.com/hmlendea/readme-assets/master/donate_generic.png)](https://hmlendea.go.ro/funding)

## 📄 License

This project is being distributed under the `GNU General Public License v3.0` or later.
See [LICENSE](./LICENSE) for additional information.
