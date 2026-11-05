# Map of Nirn — Documentation Index

## Repository Summary

Map of Nirn is a static asset repository containing high-resolution SVG map files and crest vectors for the world of Nirn from The Elder Scrolls universe. It has no executable code, runtime dependencies, build pipeline, or network services. Assets are curated manually and distributed via GitHub Releases as raster exports at multiple resolutions.

## Root Document Map

- [ARCHITECTURE.md](../ARCHITECTURE.md) — System context, architectural style, data architecture, dependency rules, deployment model, compatibility contracts, and design constraints
- [SECURITY.md](../SECURITY.md) — Security policy, supported versions, vulnerability reporting, scope, and disclosure policy
- [PRIVACY.md](../PRIVACY.md) — Privacy and data handling statement
- [CODE_OF_CONDUCT.md](../CODE_OF_CONDUCT.md) — Community conduct standards
- [CONTRIBUTING.md](../CONTRIBUTING.md) — Contribution guidelines, issue reporting, and code contribution process
- [README.md](../README.md) — Project overview, usage, obtaining assets, development setup, and project structure

## Documentation Catalogue

### Architecture & Design
- [architecture.md](./architecture.md) — High-level architecture complementing root ARCHITECTURE.md with focus on asset pipeline and maintenance workflows
- [design-decisions.md](./design-decisions.md) — Key architectural choices and rationale (manual SVG editing, no build pipeline, GitHub Releases distribution)
- [invariants.md](./invariants.md) — System-wide invariants and contracts (SVG format compatibility, naming conventions, release immutability)

### Repository Structure
- [repository-overview.md](./repository-overview.md) — Repository purpose, scope, and entry points
- [repository-structure.md](./repository-structure.md) — Source tree layout and module organisation
- [source-map.md](./source-map.md) — Detailed mapping of asset locations and purposes

### Asset Pipeline & Data
- [data-model.md](./data-model.md) — Domain entities (map, crests), relationships, and persistence (Git + GitHub Releases)
- [state-and-persistence.md](./state-and-persistence.md) — State management: Git history for sources, immutable releases for distribution
- [build-and-deployment.md](./build-and-deployment.md) — Manual export workflow, release publication process, GitHub CDN distribution

### Maintenance & Operations
- [change-guide.md](./change-guide.md) — How to safely modify SVG assets, add crests, and publish releases
- [testing.md](./testing.md) — Manual verification procedures (Inkscape validation, export validation, release validation)
- [troubleshooting.md](./troubleshooting.md) — Common issues: SVG rendering problems, export artefacts, release asset mismatches
- [documentation-maintenance.md](./documentation-maintenance.md) — How to keep docs current, ownership, review cadence

### Security & Compliance
- [security.md](./security.md) — Security model elaborating on root SECURITY.md: asset integrity, supply chain, provenance
- [dependencies.md](./dependencies.md) — External dependencies (Inkscape, GitHub, image viewers) and their architectural consequences

### Reference
- [faq.md](./faq.md) — Frequently asked questions about assets, canon accuracy, usage rights, and contribution process
- [quick-start.md](./quick-start.md) — Getting started guide for newcomers: clone, edit, validate, contribute

## Navigation Aids

| Audience | Start Here |
|----------|------------|
| Newcomers | [quick-start.md](./quick-start.md) → [repository-overview.md](./repository-overview.md) → [change-guide.md](./change-guide.md) |
| Asset contributors | [change-guide.md](./change-guide.md) → [data-model.md](./data-model.md) → [testing.md](./testing.md) |
| Maintainers | [build-and-deployment.md](./build-and-deployment.md) → [architecture.md](./architecture.md) → [design-decisions.md](./design-decisions.md) |
| Security reviewers | [security.md](./security.md) → [SECURITY.md](../SECURITY.md) → [dependencies.md](./dependencies.md) |

## Maintenance Metadata

- **Last reviewed:** 2026-11-05
- **Owner:** hmlendea
- **Coverage status:** Complete for static asset repository pattern
- **Next review:** On next release or significant workflow change