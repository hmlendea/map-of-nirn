# Repository Structure — Map of Nirn

## Source Tree Layout

```
map-of-nirn/
├── .github/
│   └── FUNDING.yml              # GitHub funding platform configuration
├── src/
│   └── crests/                  # Crest vector assets (SVG)
│       ├── Abah's Landing.svg
│       ├── Alinor.svg
│       ├── Anvil.svg
│       ├── Blacklight.svg
│       ├── Bravil.svg
│       ├── Camlorn.svg
│       ├── Chorrol.svg
│       ├── Cloudrest.svg
│       ├── Dawnstar.svg
│       ├── Dragonstar.svg
│       ├── Ebonheart.svg
│       ├── Elinhir.svg
│       ├── Empire.svg
│       ├── Falkreath.svg
│       ├── Gilane.svg
│       ├── Hegathe.svg
│       ├── Jehanna.svg
│       ├── Markarth.svg
│       ├── Mournhold.svg
│       ├── Northpoint (Simple).svg
│       ├── Northpoint.svg
│       ├── Riften.svg
│       ├── Rimmen.svg
│       ├── Sentinel.svg
│       ├── Skaven.svg
│       ├── Skingrad.svg
│       ├── Solitude.svg
│       ├── Sunhold.svg
│       ├── Taneth.svg
│       ├── Tear.svg
│       ├── Volatra.svg
│       ├── Wayrest.svg
│       └── Whiterun.svg
├── docs/                        # Technical documentation
│   ├── INDEX.md                 # Master documentation index
│   ├── architecture.md          # Architecture elaboration
│   ├── design-decisions.md      # Key design choices and rationale
│   ├── invariants.md            # System-wide invariants and contracts
│   ├── repository-overview.md   # This file
│   ├── repository-structure.md  # Source tree layout (this file)
│   ├── source-map.md            # Detailed asset location mapping
│   ├── data-model.md            # Domain entities and relationships
│   ├── state-and-persistence.md # State management and persistence
│   ├── build-and-deployment.md  # Manual export and release workflow
│   ├── change-guide.md          # Safe modification procedures
│   ├── testing.md               # Manual verification procedures
│   ├── troubleshooting.md       # Common issues and solutions
│   ├── documentation-maintenance.md # Documentation upkeep guide
│   ├── security.md              # Security model elaboration
│   ├── dependencies.md          # External dependencies analysis
│   ├── faq.md                   # Frequently asked questions
│   └── quick-start.md           # Newcomer getting started guide
├── Planet Nirn.svg              # Primary world map source (SVG)
├── ARCHITECTURE.md              # Root architecture documentation
├── SECURITY.md                  # Security policy
├── PRIVACY.md                   # Privacy statement
├── CODE_OF_CONDUCT.md           # Community conduct standards
├── CONTRIBUTING.md              # Contribution guidelines
└── README.md                    # Project overview and user documentation
```

## Module Organisation

### Root Level (Repository Root)

| Path | Type | Purpose | Versioned |
|------|------|---------|-----------|
| `Planet Nirn.svg` | Asset | Primary map source; rendered directly by GitHub web UI | Yes |
| `ARCHITECTURE.md` | Documentation | System architecture (root level) | Yes |
| `SECURITY.md` | Policy | Security vulnerability reporting and policy | Yes |
| `PRIVACY.md` | Policy | Data handling and privacy statement | Yes |
| `CODE_OF_CONDUCT.md` | Policy | Community behaviour standards | Yes |
| `CONTRIBUTING.md` | Documentation | Contribution guidelines and processes | Yes |
| `README.md` | Documentation | User-facing project overview | Yes |
| `.github/FUNDING.yml` | Configuration | Funding platform links for GitHub Sponsors UI | Yes |

### `src/` — Source Assets

| Path | Type | Purpose | Versioned |
|------|------|---------|-----------|
| `src/crests/` | Directory | Container for all crest vector assets | Yes |
| `src/crests/*.svg` | Assets | Individual crest files; referenced by `Planet Nirn.svg` | Yes |

**Organisation principle:** Flat directory — all crests at same level. No subdirectories by region, faction, or type. Naming convention (`<Location Name>.svg`) provides discoverability.

### `docs/` — Technical Documentation

| Path | Type | Purpose | Audience |
|------|------|---------|----------|
| `INDEX.md` | Index | Master navigation and catalogue | All |
| `architecture.md` | Architecture | Asset pipeline, workflows, operational model | Maintainers, contributors |
| `design-decisions.md` | Architecture | Key choices with rationale and consequences | Maintainers, architects |
| `invariants.md` | Architecture | System-wide contracts that must hold | Maintainers, reviewers |
| `repository-overview.md` | Overview | Purpose, scope, entry points, capabilities | Newcomers, contributors |
| `repository-structure.md` | Structure | Source tree layout and module organisation | All |
| `source-map.md` | Reference | Detailed asset-to-location mapping | Contributors, maintainers |
| `data-model.md` | Data | Domain entities, relationships, persistence | Contributors, maintainers |
| `state-and-persistence.md` | Data | Git history, release immutability, state lifecycle | Maintainers |
| `build-and-deployment.md` | Operations | Manual export, validation, release publication | Maintainers |
| `change-guide.md` | Operations | Safe modification procedures for assets | Contributors, maintainers |
| `testing.md` | Quality | Manual verification checklists | Maintainers, contributors |
| `troubleshooting.md` | Operations | Common issues: rendering, export, release | Maintainers, contributors |
| `documentation-maintenance.md` | Meta | Documentation upkeep, ownership, review cadence | Maintainers |
| `security.md` | Security | Asset integrity, supply chain, provenance | Security reviewers, maintainers |
| `dependencies.md` | Architecture | External tool dependencies and consequences | Maintainers, architects |
| `faq.md` | Reference | Common questions about assets, canon, usage | All |
| `quick-start.md` | Onboarding | Clone, edit, validate, contribute workflow | Newcomers |

## Asset Inventory

### Primary Map Asset

| Asset | Location | Format | Size (approx) | Description |
|-------|----------|--------|---------------|-------------|
| Planet Nirn.svg | Repository root | SVG | ~2-5 MB | Complete world map with all landmasses, regions, cities, crest placements, and map decorations |

### Crest Assets (30 files)

| Crest | File | Region/Faction | Notes |
|-------|------|----------------|-------|
| Abah's Landing | `src/crests/Abah's Landing.svg` | Hew's Bane | |
| Alinor | `src/crests/Alinor.svg` | Summerset Isles | |
| Anvil | `src/crests/Anvil.svg` | Gold Coast | |
| Blacklight | `src/crests/Blacklight.svg` | Morrowind | |
| Bravil | `src/crests/Bravil.svg` | Nibenay Valley | |
| Camlorn | `src/crests/Camlorn.svg` | High Rock | |
| Chorrol | `src/crests/Chorrol.svg` | Colovian West | |
| Cloudrest | `src/crests/Cloudrest.svg` | Summerset Isles | |
| Dawnstar | `src/crests/Dawnstar.svg` | Skyrim | |
| Dragonstar | `src/crests/Dragonstar.svg` | Hammerfell/Skyrim border | |
| Ebonheart | `src/crests/Ebonheart.svg` | Morrowind | |
| Elinhir | `src/crests/Elinhir.svg` | Hammerfell | |
| Empire | `src/crests/Empire.svg` | Cyrodiil | Imperial crest |
| Falkreath | `src/crests/Falkreath.svg` | Skyrim | |
| Gilane | `src/crests/Gilane.svg` | Hammerfell | |
| Hegathe | `src/crests/Hegathe.svg` | Hammerfell | |
| Jehanna | `src/crests/Jehanna.svg` | High Rock | |
| Markarth | `src/crests/Markarth.svg` | Skyrim | |
| Mournhold | `src/crests/Mournhold.svg` | Morrowind | |
| Northpoint (Simple) | `src/crests/Northpoint (Simple).svg` | High Rock | Simplified variant |
| Northpoint | `src/crests/Northpoint.svg` | High Rock | Standard variant |
| Riften | `src/crests/Riften.svg` | Skyrim | |
| Rimmen | `src/crests/Rimmen.svg` | Elsweyr | |
| Sentinel | `src/crests/Sentinel.svg` | Hammerfell | |
| Skaven | `src/crests/Skaven.svg` | Hammerfell | |
| Skingrad | `src/crests/Skingrad.svg` | Cyrodiil | |
| Solitude | `src/crests/Solitude.svg` | Skyrim | |
| Sunhold | `src/crests/Sunhold.svg` | Summerset Isles | |
| Taneth | `src/crests/Taneth.svg` | Hammerfell | |
| Tear | `src/crests/Tear.svg` | Black Marsh | |
| Volatra | `src/crests/Volatra.svg` | Unknown/Community | |
| Wayrest | `src/crests/Wayrest.svg` | High Rock | |
| Whiterun | `src/crests/Whiterun.svg` | Skyrim | |

## Documentation Architecture

The `docs/` directory follows a **concern-separated** structure:

```
docs/
├── INDEX.md                    # Entry point and catalogue
├── architecture.md             # High-level architecture (complements root)
├── design-decisions.md         # Decision log with rationale
├── invariants.md               # Contracts and invariants
├── repository-overview.md      # Purpose, scope, capabilities
├── repository-structure.md     # This file — tree layout
├── source-map.md               # Asset location reference
├── data-model.md               # Domain model
├── state-and-persistence.md    # State management
├── build-and-deployment.md     # Release workflow
├── change-guide.md             # Modification procedures
├── testing.md                  # Verification checklists
├── troubleshooting.md          # Problem resolution
├── documentation-maintenance.md # Doc upkeep
├── security.md                 # Security elaboration
├── dependencies.md             # External dependencies
├── faq.md                      # Common questions
└── quick-start.md              # Onboarding guide
```

### Cross-Reference Conventions

- **Root documents:** `../ARCHITECTURE.md`, `../SECURITY.md`, etc.
- **Sibling docs:** `./architecture.md`, `./design-decisions.md`, etc.
- **Asset references:** `../Planet Nirn.svg`, `../src/crests/Whiterun.svg`
- **Code symbols:** Not applicable (no executable code)

## File Naming Standards

| Category | Convention | Examples |
|----------|------------|----------|
| Documentation | kebab-case.md | `repository-structure.md`, `build-and-deployment.md` |
| SVG assets | Title Case with spaces | `Northpoint (Simple).svg`, `Abah's Landing.svg` |
| Directories | kebab-case | `src/crests/`, `docs/` |
| Configuration | UPPER_SNAKE_CASE.yml | `FUNDING.yml` |
| Root policies | UPPER_SNAKE_CASE.md | `SECURITY.md`, `PRIVACY.md` |

## Version Control Organisation

- **Single branch:** `master` — all development and releases
- **Tags:** Semantic version tags (e.g., `v1.2.0`) corresponding to GitHub Releases
- **No feature branches:** Direct commits to `master` after local validation
- **No release branches:** Tags created from `master` at release time

## GitIgnore Policy

No `.gitignore` file exists (repository contains only assets and documentation that should be tracked). If created, would exclude:
- OS metadata (`.DS_Store`, `Thumbs.db`)
- Editor temporary files (`*~`, `.*.swp`)
- Export artefacts (PNG/JPG) — these belong in Releases, not Git

## Size Characteristics

| Metric | Value |
|--------|-------|
| Repository size (Git) | ~10-50 MB (SVG assets + docs) |
| File count | ~50 files (1 map + 30 crests + 20 docs + root files) |
| Largest file | `Planet Nirn.svg` (~2-5 MB) |
| Crest files | 30 SVGs, ~10-100 KB each |
| Documentation | ~20 Markdown files, ~1-10 KB each |