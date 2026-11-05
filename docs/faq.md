# FAQ

## General

### What is this repository?

A static asset repository containing a world map of Nirn (the planet of The Elder Scrolls) and 30 faction crests, authored in SVG and distributed as raster exports via GitHub Releases.

### Is the map canon-accurate?

Canon geography and factions are based on Elder Scrolls lore. Community or speculative content is explicitly marked as non-canon in the source SVG. See [Source Map](source-map.md#non-canon-content-markers).

### Can I use these assets in my project?

Usage is governed by the repository licence. See the licence file and [README](../README.md). Attribution requirements must be preserved in redistribution.

### Where do I download the map?

From the [GitHub Releases](https://github.com/hmlendea/map-of-nirn/releases) page. Raster exports are available in PNG and JPG at 4K, 1080p, 720p, and thumbnail resolutions.

### Why is there no code in this repository?

This is a pure asset repository. The only "build" is manual raster export from SVG sources, performed with Inkscape. See [Architecture](../ARCHITECTURE.md).

## Assets

### What software do I need to edit the SVGs?

Inkscape 1.x. The sources use Inkscape extensions (layer metadata, anchors), so Inkscape is the reference editor. Other SVG editors work but may lose extension data.

### Why are the crests in separate files?

Each crest is an independent SVG in `src/crests/`, referenced by anchor layers in `Planet Nirn.svg`. This allows individual crest updates without touching the main map. See [Data Model](data-model.md).

### What resolutions are available?

| Resolution | Dimensions |
|------------|------------|
| 4K | 3840×2160 |
| 1080p | 1920×1080 |
| 720p | 1280×720 |
| Thumbnail | 400×225 |

### Why PNG and JPG?

PNG for lossless quality; JPG for smaller downloads where compression is acceptable.

### Can I request a new resolution or format?

Open a GitHub issue. New formats (e.g., WebP) would be added to the export pipeline and published in a subsequent release.

## Releases

### How do I verify a download?

Compute the SHA-256 checksum of the downloaded file and compare it to the value in the release notes. See [Security Model](security.md#consumer-verification).

### Why can't I find an older release asset?

Published releases are immutable and never removed. If an asset appears missing, it may not have been included in that release; check the release notes.

### How often are releases published?

There is no fixed schedule. Releases follow meaningful asset changes. See [Build and Deployment](build-and-deployment.md).

### What do version numbers mean?

Semantic versioning: major for removals or canon-breaking changes, minor for additions, patch for fixes. See [State and Persistence](state-and-persistence.md#tagging-rules).

## Contributing

### How do I report a typo or error?

Open a GitHub issue describing the problem and location. See [Contributing](../CONTRIBUTING.md).

### Can I contribute a new crest?

Yes — follow the procedure in the [Change Guide](change-guide.md#procedure-add-a-new-crest) and [Contributing](../CONTRIBUTING.md).

### How do I report a security issue?

Use GitHub Security Advisories. See [Security Policy](../SECURITY.md). Do not open a public issue for security matters.

## Troubleshooting

### The SVG looks different in my browser than in Inkscape

See [Troubleshooting](troubleshooting.md#svg-renders-differently-in-browser-vs-inkscape).

### My download seems corrupted

Verify the checksum against the release notes. If it matches, the file is intact. If not, re-download. See [Troubleshooting](troubleshooting.md#asset-upload-fails).

## Cross-References

- [Quick Start](quick-start.md)
- [Troubleshooting](troubleshooting.md)
- [Repository Overview](repository-overview.md)