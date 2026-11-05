# Repository Structure

## Source Tree Layout

```text
stellaris-ui-prescripted-countries/
├── .github/                          # CI workflows and repository configuration
├── ARCHITECTURE.md                   # Root architecture document
├── CODE_OF_CONDUCT.md                # Community standards
├── CONTRIBUTING.md                   # Contribution guidelines
├── LICENSE                           # GNU GPL v3.0
├── PRIVACY.md                        # Data-handling statement
├── README.md                         # Project overview
├── SECURITY.md                       # Security policy
├── docs/                             # Generated documentation (this directory)
├── ui-prescripted-countries.mod      # Mod descriptor for manual installation
└── ui-prescripted-countries/         # Mod content root
    ├── descriptor.mod                # Mod descriptor for workshop/Paradox Mods
    ├── thumbnail.png                 # Workshop thumbnail
    ├── localisation/
    │   └── english/
    │       └── ui-prescripted-countries_l_english.yml
    └── prescripted_countries/
        ├── ui_civbe_*.txt            # 8 Civilization: Beyond Earth countries
        ├── ui_elderscrolls_*.txt     # 2 The Elder Scrolls countries
        ├── ui_extra_human_*.txt      # 9 original human-culture countries
        ├── ui_galciv_*.txt           # 5 Galactic Civilizations countries
        └── ui_starcraft_*.txt        # 2 StarCraft countries
```

## Module Organisation

The repository contains a single mod with three content modules:

| Module | Path | Contents |
|--------|------|----------|
| Mod metadata | `ui-prescripted-countries.mod`, `ui-prescripted-countries/descriptor.mod` | Identity, version, supported game version, tags |
| Country definitions | `ui-prescripted-countries/prescripted_countries/` | 26 self-contained empire template files |
| Localisation | `ui-prescripted-countries/localisation/english/` | Display names and descriptions for empire designs |

## File Naming Conventions

- Country definition files: `ui_<source>_<name>.txt`, where `<source>` is one of `civbe`, `elderscrolls`, `extra_human`, `galciv`, `starcraft`.
- Localisation files: `<mod-name>_l_<language>.yml` (Stellaris requirement).
- The two descriptor files must remain synchronised in content.

## Country Definition Inventory

| File | Empire key |
|------|-----------|
| `ui_civbe_africa.txt` | People's African Union |
| `ui_civbe_brasilia.txt` | Brasília |
| `ui_civbe_franco-iberia.txt` | Franco-Iberia |
| `ui_civbe_integr.txt` | INTEGR |
| `ui_civbe_kavithan-protectorate.txt` | Kavithan Protectorate |
| `ui_civbe_panasian-cooperative.txt` | Pan-Asian Cooperative |
| `ui_civbe_polystralia.txt` | Polystralia |
| `ui_civbe_slavic_federation.txt` | Slavic Federation |
| `ui_elderscrolls_aldmeri.txt` | Aldmeri Dominion |
| `ui_elderscrolls_argonia.txt` | Argonia |
| `ui_extra_human_arabian.txt` | Arabian empire |
| `ui_extra_human_celtic.txt` | Celtic empire |
| `ui_extra_human_french.txt` | French empire |
| `ui_extra_human_hellenic.txt` | Hellenic empire |
| `ui_extra_human_italian.txt` | Italian empire |
| `ui_extra_human_japanese.txt` | Japanese empire |
| `ui_extra_human_norse.txt` | Norse empire |
| `ui_extra_human_ottoman.txt` | Ottoman empire |
| `ui_extra_human_roman.txt` | Roman empire |
| `ui_galciv_altarian.txt` | Altarian Republic |
| `ui_galciv_drengin.txt` | Drengin Empire |
| `ui_galciv_krynn.txt` | Krynn Consulate |
| `ui_galciv_torian.txt` | Torian Confederation |
| `ui_galciv_yor.txt` | Yor Collective |
| `ui_starcraft_protoss.txt` | Protoss Empire |
| `ui_starcraft_terran.txt` | Terran Dominion |

## Related Documentation

- [Repository overview](./repository-overview.md)
- [Architecture](./architecture.md)
- [Data model](./data-model.md)
