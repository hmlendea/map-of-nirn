# Troubleshooting

## Overview

This document covers common issues with rendering, exporting, and releasing the repository's assets, along with diagnostic steps and solutions.

## Rendering Issues

### SVG Does Not Open in Inkscape

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Parse error on open | Malformed XML | Open file in text editor; fix syntax; validate XML |
| Missing layers | Layer structure corrupted | Check `<g inkscape:groupmode="layer">` elements |
| Blank canvas | viewBox missing or invalid | Verify `viewBox` attribute on root `<svg>` element |
| Fonts render as boxes | Missing fonts on system | Install required fonts; or convert text to paths |

### SVG Renders Differently in Browser vs Inkscape

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Missing elements | Inkscape-specific features unsupported | Avoid Inkscape-only filters/effects for browser compatibility |
| Different colours | Colour profile mismatch | Use sRGB; avoid CMYK values |
| Text layout shifts | Font substitution | Convert text to paths, or embed fonts |

### Crests Missing From Map

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Crest not visible | Anchor layer hidden | Check layer visibility in Inkscape Layers dialog |
| Crest in wrong position | Anchor coordinates wrong | Update anchor x/y in `Planet Nirn.svg` |
| Crest file not found | File renamed or deleted | Verify filename matches anchor reference |

## Export Issues

### Export Dimensions Wrong

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Output smaller than expected | DPI setting not adjusted | Set export width in pixels explicitly, not DPI |
| Aspect ratio distorted | Non-uniform scaling | Export with locked aspect ratio; verify viewBox ratio |
| Partial export | Selection-based export used | Use page/canvas export, not selection export |

### Export Quality Issues

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Blurry at target resolution | Source rasterised at low DPI | Re-export from vector source at correct pixel width |
| JPG artefacts | High compression | Use higher quality setting (90+) or prefer PNG |
| Missing layers in export | Layers hidden at export time | Verify all layers visible before export |

### Export Fails or Crashes

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Inkscape crashes on export | Very large canvas or complex filters | Simplify filters; export in stages |
| Out of memory | 4K export on low-RAM machine | Close other applications; use 64-bit Inkscape |

## Release Issues

### Asset Upload Fails

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Upload rejected | File exceeds GitHub size limit | Verify file size; split or compress (JPG) |
| Missing asset in release | Upload interrupted | Re-upload the missing asset |
| Checksum mismatch reported by consumer | Corrupted upload or wrong checksum | Re-download and verify; re-publish if needed |

### Tag or Release Problems

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Tag not on GitHub | Tags not pushed | `git push origin --tags` |
| Release points to wrong commit | Tag created on wrong commit | Never move tags; create corrective patch release |
| Duplicate version tags | Tagging error | Never delete published tags; use next version |

## Git Issues

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| SVG diff unreadable | SVG on single line | Format SVG with line breaks for diffability |
| Large file warnings | Raster files committed by mistake | Only SVG sources in Git; rasters go to Releases |
| Merge conflicts in SVG | Concurrent edits | Single-maintainer model; resolve manually in Inkscape |

## Diagnostic Commands

| Purpose | Command |
|---------|---------|
| Verify SVG is valid XML | `xmllint --noout <file>.svg` |
| Check image dimensions | `identify <file>.png` (ImageMagick) |
| Compute checksum | `sha256sum <file>` |
| View tag list | `git tag --list` |
| Check tag target | `git rev-parse <tag>` |
| Review pending changes | `git diff` / `git diff --staged` |

## Escalation

If an issue is not covered here:

1. Check [Testing](testing.md) checklists for missed validation steps.
2. Review [Build and Deployment](build-and-deployment.md) for pipeline deviations.
3. Open a GitHub issue with: symptom, expected behaviour, Inkscape version, and screenshots.

## Cross-References

- [Testing](testing.md)
- [Build and Deployment](build-and-deployment.md)
- [Change Guide](change-guide.md)
- [FAQ](faq.md)