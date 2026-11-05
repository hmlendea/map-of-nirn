# Dependencies

## Overview

This document analyses the external dependencies of the Map of Nirn repository. As a static asset repository, dependencies are limited to authoring tools, distribution platforms, and validation utilities — there are no runtime, library, or package dependencies.

## Dependency Categories

| Category | Dependencies | Criticality |
|----------|--------------|-------------|
| Authoring tools | Inkscape | High (source of truth for editing) |
| Version control | Git, GitHub | High (persistence and distribution) |
| Distribution | GitHub Releases, GitHub CDN | High (consumer access) |
| Validation | ImageMagick, web browsers, `sha256sum` | Medium (quality assurance) |
| Fonts | System fonts used in SVG text | Medium (rendering fidelity) |

## Tool Dependencies

### Inkscape (Authoring)

| Aspect | Detail |
|--------|--------|
| **Role** | SVG editing and raster export |
| **Version** | 1.x (reference version) |
| **Format support** | SVG 1.1 with Inkscape extensions |
| **Replacement difficulty** | High — Inkscape extensions are embedded in sources |
| **Failure impact** | Cannot edit sources or export rasters |
| **Alternatives** | Other SVG editors possible but lose Inkscape extension data |

### Git (Version Control)

| Aspect | Detail |
|--------|--------|
| **Role** | Local version control |
| **Version** | Any recent |
| **Failure impact** | Cannot commit, tag, or push |
| **Alternatives** | None practical |

### GitHub (Hosting and Distribution)

| Aspect | Detail |
|--------|--------|
| **Role** | Remote hosting, Releases, CDN, issue tracking |
| **Failure impact** | Distribution interrupted; source still safe locally |
| **Alternatives** | Other Git hosts possible but Releases/CDN would need rework |
| **Vendor risk** | GitHub ToS or availability changes |

### ImageMagick (Validation)

| Aspect | Detail |
|--------|--------|
| **Role** | Dimension verification (`identify`) |
| **Failure impact** | Manual dimension checks via image viewer instead |
| **Alternatives** | Any image viewer with dimension display |

### Web Browsers (Validation)

| Aspect | Detail |
|--------|--------|
| **Role** | Second-renderer SVG validation |
| **Failure impact** | Reduced rendering compatibility assurance |
| **Alternatives** | Any standards-compliant SVG renderer |

### sha256sum (Integrity)

| Aspect | Detail |
|--------|--------|
| **Role** | Checksum generation and verification |
| **Failure impact** | Cannot publish verifiable checksums |
| **Alternatives** | Any SHA-256 tool |

## Content Dependencies

### Fonts

| Aspect | Detail |
|--------|--------|
| **Usage** | Text elements in `Planet Nirn.svg` and crests |
| **Risk** | Missing fonts on consumer systems cause substitution |
| **Mitigation** | Convert text to paths for maximum portability, or document required fonts |

### Elder Scrolls Lore (Content Reference)

| Aspect | Detail |
|--------|--------|
| **Usage** | Canon accuracy of geography, faction names, crest designs |
| **Risk** | Lore changes (new games, retcons) make content outdated |
| **Mitigation** | Non-canon content explicitly marked; periodic canon review |

## Dependency Risk Summary

| Dependency | Risk Level | Mitigation Strategy |
|------------|------------|---------------------|
| Inkscape | Medium (tool lock-in) | SVG 1.1 base is portable; extensions documented |
| GitHub | Medium (vendor dependency) | Local Git clone is full backup |
| Fonts | Low | Text-to-path conversion option |
| ImageMagick / browsers | Low | Easily replaceable |
| Elder Scrolls canon | Low (content drift) | Explicit canon/non-canon marking |

## No Runtime Dependencies

This repository ships static assets only. Consumers need no dependencies to use released PNG/JPG files. SVG sources require only an SVG-capable renderer.

## Cross-References

- [Build and Deployment](build-and-deployment.md)
- [Design Decisions](design-decisions.md)
- [Architecture](../ARCHITECTURE.md#external-dependencies)