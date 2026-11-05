# Repository Overview — Map of Nirn

## Purpose

Map of Nirn is a curated, high-resolution world map of Nirn (the main planet in The Elder Scrolls universe) and associated crest assets. It serves as a reference resource for Elder Scrolls enthusiasts, modders, content creators, and world-builders seeking canonical and community-sourced cartographic assets.

## Scope

### In Scope
- Primary world map: `Planet Nirn.svg` — complete vector map of Nirn with landmasses, regions, cities, and crest placements
- Crest library: `src/crests/` — ~30 individual SVG crest files for cities, holds, and factions
- Distribution: Raster exports (PNG/JPG) at multiple resolutions via GitHub Releases
- Documentation: Usage, contribution, security, privacy, conduct, and architecture guides
- Attribution: Credits to Elder Kings mod team (Akavir/eastern islands) and Beyond Skyrim mod teams (crests)

### Out of Scope
- Executable applications, viewers, or tools
- Interactive web map or tile server
- Game mods or plugins (assets only)
- Canonical lore database or encyclopedia
- Real-time collaboration or editing platform
- Automated build, test, or deployment pipelines

## Entry Points

### For Consumers
- **Primary:** GitHub Releases page — download raster map images at desired resolution
- **Secondary:** Repository root — view `Planet Nirn.svg` directly in browser (GitHub SVG rendering)
- **Reference:** README.md — usage instructions, known limitations, obtaining assets

### For Contributors
- **Source:** `Planet Nirn.svg` and `src/crests/` — edit in Inkscape
- **Process:** CONTRIBUTING.md — contribution guidelines, development setup, PR workflow
- **Standards:** Code Style section — SVG structure, naming conventions, Inkscape compatibility

### For Maintainers
- **Release:** GitHub Releases UI — create tags, upload assets, publish notes
- **Configuration:** `.github/FUNDING.yml` — funding platform links
- **Governance:** CODE_OF_CONDUCT.md, SECURITY.md, PRIVACY.md — policy documents

## Principal Capabilities

| Capability | Description | Entry Point |
|------------|-------------|-------------|
| Map browsing | View high-resolution world map of Nirn | GitHub Releases (raster), GitHub web (SVG) |
| Crest library access | Browse and download individual crest SVGs | `src/crests/` directory, GitHub web |
| Asset contribution | Submit map corrections, new crests, canon improvements | CONTRIBUTING.md, GitHub Issues/PRs |
| Release consumption | Download specific resolution for offline use | GitHub Releases assets |
| Source inspection | Examine SVG structure, layers, metadata | GitHub web, local clone |

## Architectural Decomposition

```
map-of-nirn/
├── Planet Nirn.svg          # Primary map source (root level for direct GitHub rendering)
├── src/
│   └── crests/              # Crest vector assets (~30 SVG files)
├── .github/
│   └── FUNDING.yml          # Funding platform configuration
├── ARCHITECTURE.md          # Root architecture documentation
├── SECURITY.md              # Security policy
├── PRIVACY.md               # Privacy statement
├── CODE_OF_CONDUCT.md       # Community standards
├── CONTRIBUTING.md          # Contribution guidelines
├── README.md                # Project overview and user documentation
└── docs/                    # Detailed technical documentation
    ├── INDEX.md
    ├── architecture.md
    ├── design-decisions.md
    ├── invariants.md
    ├── repository-overview.md
    ├── repository-structure.md
    ├── source-map.md
    ├── data-model.md
    ├── state-and-persistence.md
    ├── build-and-deployment.md
    ├── change-guide.md
    ├── testing.md
    ├── troubleshooting.md
    ├── documentation-maintenance.md
    ├── security.md
    ├── dependencies.md
    ├── faq.md
    └── quick-start.md
```

## Component Relationships

```
┌─────────────────────────────────────────────────────────────────┐
│                        GitHub Repository                        │
├─────────────────────────────────────────────────────────────────┤
│  ┌──────────────────┐    ┌──────────────────────────────────┐  │
│  │  Source Assets   │    │         Documentation            │  │
│  │  (Git-tracked)   │    │  (README, CONTRIBUTING, etc.)    │  │
│  ├──────────────────┤    ├──────────────────────────────────┤  │
│  │ Planet Nirn.svg  │    │ Root: ARCHITECTURE, SECURITY,    │  │
│  │ src/crests/*.svg │    │ PRIVACY, CODE_OF_CONDUCT,        │  │
│  │ .github/FUNDING  │    │ CONTRIBUTING, README             │  │
│  └────────┬─────────┘    │ Docs: architecture, design,      │  │
│           │              │ invariants, flows, components,   │  │
│           │ Manual Edit  │ data, state, build, change,      │  │
│           ▼              │ test, troubleshoot, security,    │  │
│  ┌──────────────────┐    │ deps, faq, quick-start           │  │
│  │  Inkscape Editor │    └──────────────────────────────────┘  │
│  │  (Maintainer/    │                                        │  │
│  │   Contributor)   │                                        │  │
│  └────────┬─────────┘                                        │  │
│           │ Manual Export                                    │  │
│           ▼                                                  │  │
│  ┌──────────────────┐                                        │  │
│  │  Validation      │                                        │  │
│  │  (Image Viewer)  │                                        │  │
│  └────────┬─────────┘                                        │  │
│           │ Upload                                           │  │
│           ▼                                                  │  │
│  ┌────────────────────────────────────────────────────────┐  │
│  │              GitHub Releases (Distribution)            │  │
│  │  Immutable raster assets (PNG/JPG) per release tag     │  │
│  │  Served via GitHub CDN                                 │  │
│  └────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```

## Dependency Direction

```
External Tools          Repository Assets          Distribution
─────────────          ─────────────────          ─────────────
Inkscape ──────────► Planet Nirn.svg ──────────► GitHub Releases
Image Viewer ──────► src/crests/*.svg ─────────► (CDN)
Git ──────────────► .github/FUNDING.yml          Consumers
```

- **No reverse dependencies:** Assets never depend on tools or distribution
- **No runtime dependencies:** Consumers need only image viewer
- **Single maintainer authority:** All changes flow through maintainer validation

## Major State

| State | Location | Lifecycle | Ownership |
|-------|----------|-----------|-----------|
| Source SVG assets | Git repository (`master` branch) | Mutable, versioned | Maintainer |
| Release raster assets | GitHub Releases (attached to tags) | Immutable per tag | Maintainer |
| Documentation | Git repository (`master` branch) | Mutable, versioned | Maintainer |
| Funding config | `.github/FUNDING.yml` | Mutable, versioned | Maintainer |
| Issue/PR history | GitHub Issues | Append-only | Community + Maintainer |

## Major Integrations

| Integration | Type | Purpose | Criticality |
|-------------|------|---------|-------------|
| GitHub (hosting) | Platform | Source control, releases, issues, CDN | Critical |
| Inkscape | Tool | SVG authoring and export | Critical |
| Image viewer | Tool | Export validation | Critical |
| Git | VCS | Version control, history | Critical |

## System-Wide Invariants

1. **No executable code** — Repository contains only static assets and documentation
2. **SVG source primacy** — All distribution artefacts derive from SVG sources
3. **Manual validation gate** — No release without human visual verification
4. **Release immutability** — Published releases never modified
5. **Attribution preservation** — Community credits maintained in README
6. **Fan project status** — Legal disclaimer and non-commercial distribution
7. **Inkscape compatibility** — All SVGs editable in Inkscape without loss

## Modification Impact Matrix

| Change Type | Affected Components | Required Actions |
|-------------|---------------------|------------------|
| Map geometry edit | `Planet Nirn.svg` | Edit in Inkscape → Export → Validate → Release |
| Crest addition | `src/crests/`, `Planet Nirn.svg` | Create SVG → Integrate into map → Validate → Release |
| Crest modification | `src/crests/`, `Planet Nirn.svg` | Edit SVG → Validate in map → Export → Release |
| Documentation update | Relevant `.md` files | Edit → Commit (no release needed) |
| Funding change | `.github/FUNDING.yml` | Edit → Commit (no release needed) |
| New export resolution | Release process | Add to export checklist → Next release |
| Canon correction | `Planet Nirn.svg`, README | Edit → Update Known Limitations → Release |