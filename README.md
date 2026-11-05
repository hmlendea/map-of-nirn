[![Donate](https://img.shields.io/badge/-%E2%99%A5%20Donate-%23ff69b4)](https://hmlendea.go.ro/funding)
[![Latest Release](https://img.shields.io/github/v/release/hmlendea/map-of-nirn)](https://github.com/hmlendea/map-of-nirn/releases/latest)

# Map of Nirn

A high-resolution world map of Nirn, the main planet in The Elder Scrolls universe, curated for reference and browsing.

## 📑 Table of Contents

- [Capabilities](#capabilities)
- [Usage](#usage)
- [Known Limitations](#known-limitations)
- [Installation](#installation)
- [Development](#development)
- [Project Structure](#project-structure)
- [Architecture](#architecture)
- [Documentation](#documentation)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)
- [Contributing](#contributing)
- [Code of Conduct](#code-of-conduct)
- [Security](#security)
- [Privacy and Data](#privacy-and-data)
- [Project Engagement](#project-engagement)

## ✨ Capabilities

- High-resolution map assets for the world of Nirn.
- Multiple crest assets in scalable vector format.
- Release artefacts suitable for multiple resolutions.

## 🚀 Usage

1. Acquire a release image asset from the releases page.
2. Open the image in your preferred viewer.

## ⚠️ Known Limitations

- Certain landmasses are not canon, including Akavir and eastern islands originally created by the Elder Kings mod team.
- Numerous crests originated from diverse Beyond Skyrim mod teams.
- Certain regions utilise community content when canon cartographic sources are unavailable.

## 📦 Installation

[![Obtain it from GitHub](https://raw.githubusercontent.com/hmlendea/readme-assets/master/badges/stores/github.png)](https://github.com/hmlendea/map-of-nirn/releases)

Acquire your preferred image resolution from the latest release assets.

## 🛠️ Development

### Requirements

- A vector graphics editor (for example, Inkscape) for crest or source-map revisions.
- An image viewer for validation of raster exports.

### Setup

Clone the repository and commence revisions directly on the source assets.

## 🗂️ Project Structure

The key directories are:

| Directory | Purpose |
|-----------|---------|
| `src/crests/` | Crest vector assets used on the map. |

Key root files:

| Path | Purpose |
|------|---------|
| `Planet Nirn.svg` | Primary SVG source for the world map. |
| `README.md` | Project documentation. |

## 🏗️ Architecture

Map of Nirn is a static asset repository with no executable code, runtime dependencies, or build pipeline. It follows a static asset repository pattern: version-controlled SVG source assets (`Planet Nirn.svg`, `src/crests/*.svg`) with manually produced raster exports distributed via GitHub Releases.

See [Architecture Documentation](./ARCHITECTURE.md) for the system context, architectural style, data architecture, dependency rules, deployment model, compatibility contracts, and design constraints.

## 📚 Documentation

- [Documentation Index](./docs/INDEX.md) — Master index with repository summary, root document map, and documentation catalogue
- [Architecture Details](./docs/architecture.md) — Asset pipeline, maintenance workflows, operational model, dependency graph, key decisions, and extension points
- [Design Decisions](./docs/design-decisions.md) — Key architectural choices with rationale and consequences
- [Invariants](./docs/invariants.md) — System-wide invariants and contracts
- [Repository Overview](./docs/repository-overview.md) — Purpose, scope, capabilities, and architectural decomposition
- [Repository Structure](./docs/repository-structure.md) — Source tree layout, module organisation, and asset inventory
- [Source Map](./docs/source-map.md) — Detailed asset location mapping and relationship graph
- [Data Model](./docs/data-model.md) — Domain entities, relationships, and persistence
- [State and Persistence](./docs/state-and-persistence.md) — State lifecycle and persistence mechanisms
- [Build and Deployment](./docs/build-and-deployment.md) — Manual export workflow and release publication process
- [Change Guide](./docs/change-guide.md) — Safe modification procedures for assets
- [Testing](./docs/testing.md) — Manual verification checklists
- [Troubleshooting](./docs/troubleshooting.md) — Common issues and solutions
- [Documentation Maintenance](./docs/documentation-maintenance.md) — Documentation upkeep, ownership, and review cadence
- [Security Model](./docs/security.md) — Asset integrity, supply chain, and provenance
- [Dependencies](./docs/dependencies.md) — External dependency analysis
- [FAQ](./docs/faq.md) — Frequently asked questions
- [Quick Start](./docs/quick-start.md) — Newcomer onboarding guide

## 🩺 Troubleshooting

Common issues and diagnostic procedures are documented in [Troubleshooting](./docs/troubleshooting.md).

## ❓ FAQ

Frequently asked questions are answered in [FAQ](./docs/faq.md).

## 🤝 Contributing

You are welcome to submit any suggestion, feedback, or modification to this project.

When doing so, please:
- Submit focused pull requests that conform to the existing code style
- Maintain your branch synchronised with `master`
- Revise the documentation when functionality changes
- Raise a new [issue](https://github.com/hmlendea/map-of-nirn/issues) for problems or suggestions

See the [Contributing Guidelines](./CONTRIBUTING.md) for details on how to report issues, suggest enhancements, and submit changes.

## 📜 Code of Conduct

This project follows the [Code of Conduct](./CODE_OF_CONDUCT.md).

## 🔒 Security

Map of Nirn is a static asset repository with no executable code or runtime dependencies. The security policy covers the integrity of released assets and the reporting process for concerns related to distributed files.

For information on reporting security vulnerabilities, see the [Security Policy](./SECURITY.md).

## 🛡️ Privacy and Data

Map of Nirn does not collect, process, transmit, or persist user data, analytics, diagnostics, or telemetry. For the detailed privacy statement, see [PRIVACY.md](./PRIVACY.md).

## 💝 Project Engagement

Discovered a problem or have a suggestion? [Open an issue](https://github.com/hmlendea/map-of-nirn/issues)!

If you find this project useful, consider [funding it](https://hmlendea.go.ro/funding) or starring ⭐️ it on GitHub!

[![Donate](https://raw.githubusercontent.com/hmlendea/readme-assets/master/donate_generic.png)](https://hmlendea.go.ro/funding)
