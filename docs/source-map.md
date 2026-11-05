# Source Map — Map of Nirn

This document provides a detailed mapping of all assets to their locations, purposes, and relationships within the repository.

## Asset Location Index

### Root-Level Assets

| Asset | Path | Purpose | Referenced By |
|-------|------|---------|---------------|
| Primary Map | `Planet Nirn.svg` | Complete world map of Nirn with all landmasses, regions, cities, and crest placements | GitHub web renderer, Inkscape (export), Release process |
| Architecture Doc | `ARCHITECTURE.md` | Root architecture documentation | README.md, docs/INDEX.md |
| Security Policy | `SECURITY.md` | Vulnerability reporting and security policy | README.md, CONTRIBUTING.md, docs/INDEX.md |
| Privacy Statement | `PRIVACY.md` | Data handling disclosure | README.md, docs/INDEX.md |
| Code of Conduct | `CODE_OF_CONDUCT.md` | Community behaviour standards | README.md, CONTRIBUTING.md, docs/INDEX.md |
| Contributing Guide | `CONTRIBUTING.md` | Contribution guidelines and processes | README.md, docs/INDEX.md |
| Project README | `README.md` | User-facing project overview | GitHub repo landing page |
| Funding Config | `.github/FUNDING.yml` | GitHub Sponsors / funding platform links | GitHub UI (Sponsors button) |

### Crest Assets (`src/crests/`)

All crest assets are individual SVG files referenced by `Planet Nirn.svg` via relative paths (`../src/crests/<Name>.svg`).

| Crest Name | File Path | Map Region | Canon Status | Source Attribution |
|------------|-----------|------------|--------------|-------------------|
| Abah's Landing | `src/crests/Abah's Landing.svg` | Hew's Bane | Community | Beyond Skyrim |
| Alinor | `src/crests/Alinor.svg` | Summerset Isles | Community | Beyond Skyrim |
| Anvil | `src/crests/Anvil.svg` | Gold Coast | Community | Beyond Skyrim |
| Blacklight | `src/crests/Blacklight.svg` | Morrowind | Community | Beyond Skyrim |
| Bravil | `src/crests/Bravil.svg` | Nibenay Valley | Community | Beyond Skyrim |
| Camlorn | `src/crests/Camlorn.svg` | High Rock | Community | Beyond Skyrim |
| Chorrol | `src/crests/Chorrol.svg` | Colovian West | Community | Beyond Skyrim |
| Cloudrest | `src/crests/Cloudrest.svg` | Summerset Isles | Community | Beyond Skyrim |
| Dawnstar | `src/crests/Dawnstar.svg` | Skyrim | Community | Beyond Skyrim |
| Dragonstar | `src/crests/Dragonstar.svg` | Hammerfell/Skyrim | Community | Beyond Skyrim |
| Ebonheart | `src/crests/Ebonheart.svg` | Morrowind | Community | Beyond Skyrim |
| Elinhir | `src/crests/Elinhir.svg` | Hammerfell | Community | Beyond Skyrim |
| Empire | `src/crests/Empire.svg` | Cyrodiil | Canon (Imperial) | Beyond Skyrim |
| Falkreath | `src/crests/Falkreath.svg` | Skyrim | Community | Beyond Skyrim |
| Gilane | `src/crests/Gilane.svg` | Hammerfell | Community | Beyond Skyrim |
| Hegathe | `src/crests/Hegathe.svg` | Hammerfell | Community | Beyond Skyrim |
| Jehanna | `src/crests/Jehanna.svg` | High Rock | Community | Beyond Skyrim |
| Markarth | `src/crests/Markarth.svg` | Skyrim | Community | Beyond Skyrim |
| Mournhold | `src/crests/Mournhold.svg` | Morrowind | Community | Beyond Skyrim |
| Northpoint (Simple) | `src/crests/Northpoint (Simple).svg` | High Rock | Community | Beyond Skyrim |
| Northpoint | `src/crests/Northpoint.svg` | High Rock | Community | Beyond Skyrim |
| Riften | `src/crests/Riften.svg` | Skyrim | Community | Beyond Skyrim |
| Rimmen | `src/crests/Rimmen.svg` | Elsweyr | Community | Beyond Skyrim |
| Sentinel | `src/crests/Sentinel.svg` | Hammerfell | Community | Beyond Skyrim |
| Skaven | `src/crests/Skaven.svg` | Hammerfell | Community | Beyond Skyrim |
| Skingrad | `src/crests/Skingrad.svg` | Cyrodiil | Community | Beyond Skyrim |
| Solitude | `src/crests/Solitude.svg` | Skyrim | Community | Beyond Skyrim |
| Sunhold | `src/crests/Sunhold.svg` | Summerset Isles | Community | Beyond Skyrim |
| Taneth | `src/crests/Taneth.svg` | Hammerfell | Community | Beyond Skyrim |
| Tear | `src/crests/Tear.svg` | Black Marsh | Community | Beyond Skyrim |
| Volatra | `src/crests/Volatra.svg` | Unknown | Community | Beyond Skyrim |
| Wayrest | `src/crests/Wayrest.svg` | High Rock | Community | Beyond Skyrim |
| Whiterun | `src/crests/Whiterun.svg` | Skyrim | Community | Beyond Skyrim |

### Documentation Assets (`docs/`)

| Document | Path | Scope | Primary Audience |
|----------|------|-------|------------------|
| Master Index | `docs/INDEX.md` | Navigation, catalogue, root document map | All |
| Architecture | `docs/architecture.md` | Asset pipeline, workflows, operational model | Maintainers, contributors |
| Design Decisions | `docs/design-decisions.md` | Key choices with rationale and consequences | Maintainers, architects |
| Invariants | `docs/invariants.md` | System-wide contracts and invariants | Maintainers, reviewers |
| Repository Overview | `docs/repository-overview.md` | Purpose, scope, entry points, capabilities | Newcomers, contributors |
| Repository Structure | `docs/repository-structure.md` | Source tree layout, module organisation | All |
| Source Map | `docs/source-map.md` | Detailed asset location mapping | Contributors, maintainers |
| Data Model | `docs/data-model.md` | Domain entities, relationships, persistence | Contributors, maintainers |
| State & Persistence | `docs/state-and-persistence.md` | Git history, release immutability, state lifecycle | Maintainers |
| Build & Deployment | `docs/build-and-deployment.md` | Manual export, validation, release publication | Maintainers |
| Change Guide | `docs/change-guide.md` | Safe modification procedures | Contributors, maintainers |
| Testing | `docs/testing.md` | Manual verification checklists | Maintainers, contributors |
| Troubleshooting | `docs/troubleshooting.md` | Common issues and solutions | Maintainers, contributors |
| Doc Maintenance | `docs/documentation-maintenance.md` | Documentation upkeep, ownership, review cadence | Maintainers |
| Security | `docs/security.md` | Asset integrity, supply chain, provenance | Security reviewers, maintainers |
| Dependencies | `docs/dependencies.md` | External tool dependencies and consequences | Maintainers, architects |
| FAQ | `docs/faq.md` | Common questions about assets, canon, usage | All |
| Quick Start | `docs/quick-start.md` | Onboarding: clone, edit, validate, contribute | Newcomers |

## Asset Relationship Graph

```
Planet Nirn.svg (Root Map)
│
├── References (via SVG <image> or <use> elements)
│   ├── src/crests/Abah's Landing.svg
│   ├── src/crests/Alinor.svg
│   ├── src/crests/Anvil.svg
│   ├── src/crests/Blacklight.svg
│   ├── src/crests/Bravil.svg
│   ├── src/crests/Camlorn.svg
│   ├── src/crests/Chorrol.svg
│   ├── src/crests/Cloudrest.svg
│   ├── src/crests/Dawnstar.svg
│   ├── src/crests/Dragonstar.svg
│   ├── src/crests/Ebonheart.svg
│   ├── src/crests/Elinhir.svg
│   ├── src/crests/Empire.svg
│   ├── src/crests/Falkreath.svg
│   ├── src/crests/Gilane.svg
│   ├── src/crests/Hegathe.svg
│   ├── src/crests/Jehanna.svg
│   ├── src/crests/Markarth.svg
│   ├── src/crests/Mournhold.svg
│   ├── src/crests/Northpoint (Simple).svg
│   ├── src/crests/Northpoint.svg
│   ├── src/crests/Riften.svg
│   ├── src/crests/Rimmen.svg
│   ├── src/crests/Sentinel.svg
│   ├── src/crests/Skaven.svg
│   ├── src/crests/Skingrad.svg
│   ├── src/crests/Solitude.svg
│   ├── src/crests/Sunhold.svg
│   ├── src/crests/Taneth.svg
│   ├── src/crests/Tear.svg
│   ├── src/crests/Volatra.svg
│   ├── src/crests/Wayrest.svg
│   └── src/crests/Whiterun.svg
│
├── Contains (embedded or layered)
│   ├── Landmass geometries (paths, polygons)
│   ├── Region boundaries
│   ├── City/location markers
│   ├── Text labels (place names)
│   ├── Map decorations (compass, scale, borders)
│   └── Layer structure (Inkscape layers/groups)
│
└── Exports to (manual process)
    ├── GitHub Release vX.Y.Z
    │   ├── Planet_Nirn_4K.png
    │   ├── Planet_Nirn_2K.png
    │   ├── Planet_Nirn_1080p.png
    │   └── (other advertised resolutions)
    └── Future releases...

src/crests/*.svg (each independent)
│
├── Standalone renderable (no external refs)
├── Referenced by Planet Nirn.svg
├── Versioned in Git
└── Exported as part of map (not individually released)
```

## Map Composition Details

### Layer Structure (Inkscape)

`Planet Nirn.svg` uses Inkscape layer hierarchy for organisation:

```
Layer Stack (bottom to top):
├── Background / Ocean
├── Landmass Base (continents, major islands)
├── Region Boundaries (political/geographic)
├── Non-Canon Landmasses (Akavir, eastern islands) — labelled/layered separately
├── Major Rivers / Water Bodies
├── City/Location Markers
├── Crest Placements (references to src/crests/*.svg)
├── Text Labels (place names, region names)
├── Map Decorations (compass rose, scale bar, border)
├── Legend / Key
└── Attribution / Copyright Notice
```

### Crest Integration Pattern

Each crest is integrated into `Planet Nirn.svg` as:
- **Method:** SVG `<image>` element with `xlink:href="../src/crests/<Name>.svg"`
- **Positioning:** Absolute coordinates matching city location on map
- **Scaling:** Uniform scale factor per crest (defined in map composition)
- **Layer:** Dedicated "Crests" layer for visibility toggling

### Non-Canon Content Markers

Per README Known Limitations, these regions are flagged in the SVG:
- **Akavir continent:** Separate layer/group labelled "Non-Canon: Akavir (Elder Kings)"
- **Eastern islands:** Grouped under "Non-Canon: Eastern Islands (Elder Kings)"
- **Community crests:** All crests attributed to Beyond Skyrim in metadata/comments

## Distribution Mapping

### Release Asset Naming Convention

| Resolution | Filename Pattern | Use Case |
|------------|------------------|----------|
| 4K (3840×2160+) | `Planet_Nirn_4K.png` | Print, high-DPI displays |
| 2K (2560×1440) | `Planet_Nirn_2K.png` | Standard high-res displays |
| 1080p (1920×1080) | `Planet_Nirn_1080p.png` | Full HD displays |
| Custom | `Planet_Nirn_<WIDTH>x<HEIGHT>.png` | Specific requirements |

### Release Checklist Mapping

Each release verifies:

| Check | Source Asset | Validation Method |
|-------|--------------|-------------------|
| Map renders completely | `Planet Nirn.svg` | Inkscape full render |
| All crests visible | `src/crests/*.svg` | Inkscape crest layer visibility |
| No missing references | `Planet Nirn.svg` → `src/crests/` | Inkscape link status |
| Export resolutions correct | Inkscape export dialog | Image viewer dimension check |
| Colour fidelity | Exported PNG/JPG | Visual comparison to SVG |
| No rendering artefacts | Exported PNG/JPG | Visual inspection at 100% zoom |
| File sizes reasonable | Release assets | File size check |
| Release notes complete | GitHub Release UI | Manual review |

## Configuration Mapping

### `.github/FUNDING.yml` → GitHub UI

| Config Key | GitHub UI Element | Maintainer Account |
|------------|-------------------|-------------------|
| `github` | Sponsors button | hmlendea |
| `patreon` | Sponsors button | hmlendea |
| `ko_fi` | Sponsors button | hmlendea |
| `liberapay` | Sponsors button | HMlendea |
| `buy_me_a_coffee` | Sponsors button | hmlendea |
| `custom` | Sponsors button | https://hmlendea.go.ro/funding |

## Documentation Cross-Reference Map

```
README.md
├── → ARCHITECTURE.md (Architecture section)
├── → CONTRIBUTING.md (Contributing section)
├── → SECURITY.md (Security section)
├── → PRIVACY.md (Privacy and Data section)
├── → CODE_OF_CONDUCT.md (Code of Conduct section)
└── → docs/ (via Architecture section link)

CONTRIBUTING.md
├── → CODE_OF_CONDUCT.md
├── → SECURITY.md
└── → docs/ (implicit via repository structure)

docs/INDEX.md
├── → ../ARCHITECTURE.md
├── → ../SECURITY.md
├── → ../PRIVACY.md
├── → ../CODE_OF_CONDUCT.md
├── → ../CONTRIBUTING.md
├── → ../README.md
└── → ./*.md (all docs/)

docs/architecture.md
├── → ../ARCHITECTURE.md (complements)
├── → ./design-decisions.md
├── → ./invariants.md
├── → ./build-and-deployment.md
└── → ./change-guide.md

docs/design-decisions.md
├── → ./architecture.md
├── → ./invariants.md
└── → ../ARCHITECTURE.md

docs/invariants.md
├── → ./architecture.md
├── → ./design-decisions.md
└── → ../ARCHITECTURE.md
```

## Maintenance Contact Points

| Asset Category | Primary Maintainer | Review Cadence |
|----------------|-------------------|----------------|
| Map SVG (`Planet Nirn.svg`) | hmlendea | Per release |
| Crest SVGs (`src/crests/`) | hmlendea | Per addition/modification |
| Documentation (`docs/`, root `.md`) | hmlendea | Per release or significant change |
| Release Process | hmlendea | Per release |
| Funding Config (`.github/FUNDING.yml`) | hmlendea | As needed |
| Issue/PR Triage | hmlendea | Ongoing |