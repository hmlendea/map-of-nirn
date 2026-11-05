# Change Guide

## Overview

This document describes safe modification procedures for the repository's assets. All changes follow the same pattern: edit source, validate, commit, tag, release.

## Change Types

| Change Type | Affected Files | Risk Level | Version Bump |
|-------------|----------------|------------|--------------|
| Add new crest | `src/crests/*.svg`, `Planet Nirn.svg` (anchor) | Low | Minor |
| Redesign crest | `src/crests/*.svg` | Low | Minor |
| Update map geography | `Planet Nirn.svg` | Medium | Minor or Major |
| Fix label typo | `Planet Nirn.svg` | Low | Patch |
| Add non-canon marker | `Planet Nirn.svg` | Low | Minor |
| Remove asset | `src/crests/*.svg`, `Planet Nirn.svg` | High | Major |
| Documentation update | `docs/*.md`, root `*.md` | None | Patch or none |

## Procedure: Add a New Crest

| Step | Action | Verification |
|------|--------|--------------|
| 1 | Create `src/crests/{faction-name}.svg` in Inkscape | File opens without errors |
| 2 | Follow naming convention (kebab-case) | Filename matches pattern |
| 3 | Add anchor layer in `Planet Nirn.svg` referencing the crest | Anchor positioned correctly |
| 4 | Export crest at all resolutions | Dimensions match targets |
| 5 | Export updated planet map at all resolutions | Visual inspection passes |
| 6 | Commit with descriptive message | `git log` shows change |
| 7 | Tag new version | `git tag` lists new tag |
| 8 | Publish release with all new assets | Release page complete |

## Procedure: Redesign an Existing Crest

| Step | Action | Verification |
|------|--------|--------------|
| 1 | Open existing `src/crests/{faction-name}.svg` in Inkscape | File opens without errors |
| 2 | Apply design changes | Visual inspection |
| 3 | Save as SVG 1.1 | File format preserved |
| 4 | Verify anchor in `Planet Nirn.svg` still valid | Position and scale correct |
| 5 | Export at all resolutions | Dimensions match targets |
| 6 | Commit, tag, release | Standard pipeline |

## Procedure: Modify Planet Map Geography

| Step | Action | Verification |
|------|--------|--------------|
| 1 | Open `Planet Nirn.svg` in Inkscape | File opens without errors |
| 2 | Edit geography layers (not label layers first) | Layer integrity maintained |
| 3 | Adjust labels to match new geography | Labels align with features |
| 4 | Verify crest anchors still positioned correctly | Anchors on correct landmasses |
| 5 | Export at all resolutions | Visual inspection passes |
| 6 | Commit, tag, release | Standard pipeline |

## Procedure: Fix a Label Typo

| Step | Action | Verification |
|------|--------|--------------|
| 1 | Open `Planet Nirn.svg` in Inkscape | File opens without errors |
| 2 | Locate text element in labels layer | Correct element identified |
| 3 | Edit text content | Typo corrected |
| 4 | Verify no layout shift | Surrounding elements unchanged |
| 5 | Export at all resolutions | Visual inspection passes |
| 6 | Commit, tag, release | Standard pipeline |

## Procedure: Remove an Asset

| Step | Action | Verification |
|------|--------|--------------|
| 1 | Confirm removal is justified (not a redesign) | Decision documented |
| 2 | Remove anchor from `Planet Nirn.svg` | No dangling references |
| 3 | Delete `src/crests/{faction-name}.svg` | File removed from working tree |
| 4 | Export updated planet map | Visual inspection passes |
| 5 | Commit with Major version bump | `git log` shows change |
| 6 | Tag and release with removal note | Release notes document removal |

## Safety Rules

| Rule | Rationale |
|------|-----------|
| Never edit release artefacts directly | Releases are immutable; fix at source |
| Never rewrite Git history | Preserves traceability and consumer trust |
| Always export from the tagged source commit | Ensures artefact-source consistency |
| Always validate before publishing | Prevents defective releases |
| Always publish checksums | Enables consumer verification |
| Always document changes in release notes | Consumers can reason about updates |

## Common Pitfalls

| Pitfall | Symptom | Prevention |
|---------|---------|------------|
| Editing label layers before geography | Misaligned labels | Edit geography first, then labels |
| Forgetting to update anchors | Crests floating over wrong locations | Verify anchors after any geography change |
| Exporting from untagged commit | Artefact-source mismatch | Always tag before export |
| Skipping validation | Defective release published | Follow full validation checklist |
| Modifying published release | Broken immutability contract | Never edit; publish a new release |

## Cross-References

- [Build and Deployment](build-and-deployment.md)
- [Testing](testing.md)
- [Invariants](invariants.md)
- [Design Decisions](design-decisions.md)