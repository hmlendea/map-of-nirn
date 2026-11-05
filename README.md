[![Donate](https://img.shields.io/badge/-%E2%99%A5%20Donate-%23ff69b4)](https://hmlendea.go.ro/funding)
[![Latest Release](https://img.shields.io/github/v/release/hmlendea/map-of-nirn)](https://github.com/hmlendea/map-of-nirn/releases/latest)

# Map of Nirn

A high-resolution world map of Nirn, the main planet in The Elder Scrolls universe, curated for reference and browsing.

## 📑 Table of Contents

- [Features](#features)
- [Usage](#usage)
- [Known Limitations](#known-limitations)
- [Obtaining](#obtaining)
- [Development](#development)
  - [Requirements](#requirements)
  - [Setup](#setup)
- [Project Structure](#project-structure)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)
- [Legal Disclaimer](#legal-disclaimer)
- [Code of Conduct](#code-of-conduct)
- [Privacy and Data](#privacy-and-data)
- [Helping out](#helping-out)
- [License](#license)

## ✨ Features

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

## 📦 Obtaining

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

See [ARCHITECTURE.md](./ARCHITECTURE.md) for the system context, architectural style, data architecture, dependency rules, deployment model, compatibility contracts, and design constraints.

## 🤝 Contributing

You are welcome to submit any suggestion, feedback, or modification to this project.

When doing so, please:
- Submit focused pull requests that conform to the existing code style
- Maintain your branch synchronised with `master`
- Revise the documentation when functionality changes
- Raise a new [issue](https://github.com/hmlendea/map-of-nirn/issues) for problems or suggestions

See the [Contributing Guidelines](./CONTRIBUTING.md) for details on how to report issues, suggest enhancements, and submit changes.

## 🙏 Acknowledgements

- Numerous non-canon landmasses, including Akavir and eastern islands, were originally created by the Elder Kings mod team.
- Numerous crests were originally designed by diverse Beyond Skyrim mod teams.
- Additional community content was integrated for regions lacking canon cartographic sources.

## ⚖️ Legal Disclaimer

This is a fan-made project.
The Elder Scrolls, Nirn, and all associated intellectual property are owned by Bethesda Softworks LLC and/or ZeniMax Media Inc.

## 📜 Code of Conduct

This project follows the [Code of Conduct](./CODE_OF_CONDUCT.md).

## 🛡️ Privacy and Data

For the detailed description of how the application handles privacy and personal data, see the [Privacy Statement](./PRIVACY.md).

## 🔒 Security

Map of Nirn is a static asset repository with no executable code or runtime dependencies. The security policy covers the integrity of released assets and the reporting process for concerns related to distributed files.

For information on reporting security vulnerabilities, see the [Security Policy](./SECURITY.md).

## 💝 Helping out

Discovered a problem or have a suggestion? [Open an issue](https://github.com/hmlendea/map-of-nirn/issues)!

If you find this project useful, consider [funding it](https://hmlendea.go.ro/funding) or starring ⭐️ it on GitHub!

[![Donate](https://raw.githubusercontent.com/hmlendea/readme-assets/master/donate_generic.png)](https://hmlendea.go.ro/funding)
