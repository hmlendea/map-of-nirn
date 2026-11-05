# Testing

## Overview

This repository has no automated test suite. All verification is manual, performed at defined checkpoints in the asset pipeline. This document provides the checklists used before every commit and release.

## Test Levels

| Level | When | Scope |
|-------|------|-------|
| Pre-commit | Before every `git commit` | Source SVG integrity |
| Pre-release | Before every GitHub Release | Full export validation |
| Post-release | After publishing | Download and checksum verification |

## Pre-Commit Checklist (Source SVG)

| # | Check | Method | Pass Criteria |
|---|-------|--------|---------------|
| 1 | SVG opens without errors | Open in Inkscape | No parse errors or warnings |
| 2 | SVG opens in a second renderer | Open in web browser | Renders correctly |
| 3 | All layers present | Inkscape Layers dialog | Expected layers listed |
| 4 | Crest anchors reference existing files | Manual cross-reference | No missing crest files |
| 5 | No unintended changes | `git diff` review | Only intended modifications |
| 6 | No secrets or personal data | `git diff` review | Clean content |

## Pre-Release Checklist (Export Validation)

| # | Check | Method | Pass Criteria |
|---|-------|--------|---------------|
| 1 | All resolutions exported | File inventory | 4K, 1080p, 720p, thumbnail present |
| 2 | Both formats exported | File inventory | PNG and JPG present |
| 3 | Pixel dimensions correct | Image viewer / `identify` | Exact match to target |
| 4 | Visual fidelity | Manual inspection | No clipping, artefacts, missing layers |
| 5 | Crests render correctly | Manual inspection | All crests visible and positioned |
| 6 | Labels legible at each resolution | Manual inspection | Text readable at 1080p and above |
| 7 | File sizes within expected range | Manual review | No anomalously large/small files |
| 8 | Checksums generated | `sha256sum` | Recorded for all artefacts |

## Post-Release Checklist (Publication Verification)

| # | Check | Method | Pass Criteria |
|---|-------|--------|---------------|
| 1 | All assets uploaded | Release page review | Complete asset list |
| 2 | Assets download correctly | Download each asset | No corruption |
| 3 | Checksums match | `sha256sum` on downloads | Match published values |
| 4 | Release notes accurate | Manual review | Changes documented correctly |
| 5 | Tag matches source commit | `git tag --list` | Tag points to correct commit |

## Regression Checks (After Asset Changes)

| Change Type | Additional Checks |
|-------------|------------------|
| Geography change | All crest anchors repositioned correctly; labels aligned |
| Crest addition | New crest visible in map; no overlap with existing elements |
| Crest removal | No dangling anchor; no visual gap |
| Label change | No layout shift; no overlapping text |
| Layer restructure | All layers render; no lost content |

## Manual Test Matrix

| Asset | Resolutions | Formats | Checks |
|-------|-------------|---------|--------|
| Planet map | 4 | 2 | Dimensions, fidelity, labels, crests |
| Each crest (30) | 4 | 2 | Dimensions, fidelity, colours |

**Total artefacts per release:** 248 (31 assets × 4 resolutions × 2 formats)

## Tools

| Tool | Purpose |
|------|---------|
| Inkscape | Source rendering and inspection |
| Web browser | Second-renderer validation |
| Image viewer / ImageMagick (`identify`) | Dimension verification |
| `sha256sum` | Checksum generation and verification |
| `git diff` | Change review |

## Known Limitations

| Limitation | Impact | Mitigation |
|------------|--------|------------|
| No automated tests | Human error possible in validation | Strict checklist adherence |
| Visual checks are subjective | Minor defects may pass | Compare against previous release |
| No cross-platform rendering test | Renderer differences undetected | Browser validation covers common case |

## Cross-References

- [Build and Deployment](build-and-deployment.md)
- [Change Guide](change-guide.md)
- [Troubleshooting](troubleshooting.md)
- [Invariants](invariants.md)