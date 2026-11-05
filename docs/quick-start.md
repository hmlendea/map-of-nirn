# Quick Start

## For Consumers (Download and Use)

1. Go to [GitHub Releases](https://github.com/hmlendea/map-of-nirn/releases).
2. Choose the latest release.
3. Download the desired asset:
   - `map-of-nirn-{resolution}.png` or `.jpg` for the world map
   - `crest-{faction-name}-{resolution}.png` or `.jpg` for individual crests
4. (Recommended) Verify the download: `sha256sum <file>` and compare with the release notes.
5. Use the asset under the repository licence terms.

## For Contributors (Edit the Sources)

### Prerequisites

| Tool | Purpose |
|------|---------|
| Inkscape 1.x | SVG editing and export |
| Git | Version control |
| GitHub account | For pull requests and issues |

### Steps

1. Clone the repository.
2. Open `Planet Nirn.svg` or a crest from `src/crests/` in Inkscape.
3. Make your changes. See the [Change Guide](change-guide.md) for safe procedures.
4. Run the [pre-commit checklist](testing.md#pre-commit-checklist-source-svg).
5. Commit with a descriptive message.
6. Open a pull request or issue per [Contributing](../CONTRIBUTING.md).

### Repository Layout

| Path | Content |
|------|---------|
| `Planet Nirn.svg` | World map source |
| `src/crests/` | 30 faction crest SVGs |
| `docs/` | Detailed documentation |
| Root `*.md` | README, Contributing, Security, Architecture, etc. |

## For Maintainers (Publish a Release)

1. Finalise source changes and commit.
2. Export all assets at all resolutions. See [Build and Deployment](build-and-deployment.md).
3. Run the [pre-release checklist](testing.md#pre-release-checklist-export-validation).
4. Tag: `git tag -a v{major}.{minor}.{patch} -m "..."` and push tags.
5. Create the GitHub Release, upload assets, publish checksums.
6. Run the [post-release checklist](testing.md#post-release-checklist-publication-verification).

## Where to Go Next

| I want to… | Read |
|------------|------|
| Understand the repository | [Repository Overview](repository-overview.md) |
| Understand the architecture | [Architecture](../ARCHITECTURE.md) |
| Find a specific asset | [Source Map](source-map.md) |
| Change an asset safely | [Change Guide](change-guide.md) |
| Publish a release | [Build and Deployment](build-and-deployment.md) |
| Fix a problem | [Troubleshooting](troubleshooting.md) |
| Ask a question | [FAQ](faq.md) |
| Report a security issue | [Security Policy](../SECURITY.md) |