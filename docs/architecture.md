# Architecture — Map of Nirn

This document complements the root [ARCHITECTURE.md](../ARCHITECTURE.md) by elaborating on the asset pipeline, maintenance workflows, and operational model specific to this static asset repository.

## Asset Pipeline Architecture

The repository implements a **manual asset pipeline** with three stages:

```
┌─────────────────┐    Manual Edit    ┌──────────────────┐    Manual Export    ┌─────────────────────┐
│  Source Assets  │ ────────────────► │  Validation      │ ──────────────────► │  Release Artefacts  │
│  (Git-tracked)  │   Inkscape/Editor │  (Image Viewer)  │   Inkscape Export   │  (GitHub Releases)  │
└─────────────────┘                   └──────────────────┘                     └─────────────────────┘
       │                                    │                                        │
       ▼                                    ▼                                        ▼
  Planet Nirn.svg                      Visual check                          PNG/JPG at
  src/crests/*.svg                     Layer structure                       multiple resolutions
  .github/FUNDING.yml                  Colour fidelity                       Immutable per tag
```

### Stage 1: Source Authoring
- **Tool:** Inkscape (or compatible SVG 1.1 editor)
- **Inputs:** Existing SVG files, canon references, community contributions
- **Outputs:** Modified `Planet Nirn.svg` and/or `src/crests/*.svg`
- **Validation:** Inkscape-native (layer visibility, object hierarchy, rendering)

### Stage 2: Export Validation
- **Tool:** Image viewer (any PNG/JPG viewer)
- **Inputs:** Raster exports from Inkscape at target resolutions
- **Checks:** Resolution accuracy, colour fidelity, absence of rendering artefacts, crest legibility
- **Output:** Verified raster files ready for release

### Stage 3: Release Publication
- **Platform:** GitHub Releases
- **Process:** Maintainer creates release tag, uploads verified raster assets, writes release notes
- **Artefacts:** Immutable per release tag; served via GitHub CDN
- **Rollback:** New release supersedes; old releases remain accessible

## Maintenance Workflows

### Routine Asset Update
1. Edit SVG source in Inkscape
2. Export raster at required resolutions
3. Validate exports in image viewer
4. Commit SVG changes to `master`
5. Create GitHub Release with raster assets
6. Update documentation if asset inventory changes

### New Crest Addition
1. Create new SVG in `src/crests/` following naming convention (`<Location Name>.svg`)
2. Integrate into `Planet Nirn.svg` (position, scaling, layer)
3. Validate combined rendering
4. Follow routine asset update workflow

### Canon Correction
1. Identify non-canon element (documented in README Known Limitations)
2. Source canonical reference or community consensus
3. Modify affected SVG assets
4. Follow routine asset update workflow

## Operational Model

| Aspect | Design |
|--------|--------|
| **Deployment unit** | GitHub Repository (source) + GitHub Releases (distribution) |
| **Process topology** | None (static files only) |
| **Persistent state** | Git history (full asset evolution); Release tags (immutable snapshots) |
| **Scaling** | GitHub CDN handles bandwidth; no application scaling concerns |
| **Availability** | GitHub SLA; no self-hosted infrastructure |
| **Rollback** | `git revert` for source; new release for distribution |
| **Monitoring** | GitHub release download stats; issue reports for asset problems |

## Dependency Graph

```
┌──────────────────┐
│   Maintainer     │
└────────┬─────────┘
         │ Uses
         ▼
┌──────────────────┐     Reads/Writes     ┌─────────────────────┐
│   Inkscape       │ ───────────────────► │  Source SVG Assets  │
│   (Editor)       │                      │  (Git-tracked)      │
└──────────────────┘                      └──────────┬──────────┘
                                                     │ Manual Export
                                                     ▼
┌──────────────────┐                      ┌─────────────────────┐
│  Image Viewer    │ ◄──── Validates ──── │  Raster Exports     │
│  (Validator)     │                      │  (Release Assets)   │
└──────────────────┘                      └──────────┬──────────┘
                                                     │ Upload
                                                     ▼
                                            ┌─────────────────────┐
                                            │  GitHub Releases    │
                                            │  (CDN Distribution) │
                                            └─────────────────────┘
```

## Key Architectural Decisions

| Decision | Rationale | Consequence |
|----------|-----------|-------------|
| No build pipeline | Eliminates CI/CD complexity; assets are manually curated | Manual reproducibility; human verification required |
| SVG as source format | Scalable, editable, version-controllable, widely supported | Requires Inkscape-compatible features; no runtime parsing |
| GitHub Releases for distribution | Free CDN, versioned, immutable, integrated with Git | Tied to GitHub platform; no self-hosting control |
| Manual export/validation | Ensures visual quality; catches rendering issues | Time-consuming per release; no automated regression detection |
| Flat crest directory | Simple organisation; easy discovery | No hierarchical grouping; naming convention critical |

## Extension Points

| Extension Point | Contract | Integration Location |
|-----------------|----------|---------------------|
| New crest | SVG file in `src/crests/`; Inkscape-compatible; follows naming convention | Added to `Planet Nirn.svg` map composition |
| New map layer | SVG layer/group in `Planet Nirn.svg`; non-destructive to existing layers | Rendered as part of map export |
| Additional export format | Raster format supported by Inkscape export | Added to release assets manually |
| Automated validation | External tool/script producing pass/fail | Could integrate in future CI workflow |