# Invariants — Map of Nirn

This document records system-wide invariants and contracts that must remain true for the repository to function correctly.

## Source Asset Invariants

### SVG Format Compatibility
- **Invariant:** All source SVG files (`Planet Nirn.svg`, `src/crests/*.svg`) must be valid SVG 1.1 and render correctly in Inkscape.
- **Verification:** Open in Inkscape; no parsing errors; all layers/groups visible as intended.
- **Violation consequence:** Export failures, rendering artefacts, contributor inability to edit.

### Inkscape Feature Constraint
- **Invariant:** Source SVGs use only Inkscape-compatible SVG features (standard SVG 1.1 + Inkscape extensions).
- **Verification:** Manual review; no proprietary Adobe Illustrator, CorelDRAW, or other vendor-specific extensions.
- **Violation consequence:** Editing failures in Inkscape; inconsistent rendering across tools.

### Crest Naming Convention
- **Invariant:** Every file in `src/crests/` follows the pattern `<Location Name>.svg` where `<Location Name>` matches the location label on the map.
- **Verification:** `ls src/crests/` matches crest placements in `Planet Nirn.svg`.
- **Violation consequence:** Broken references in map composition; contributor confusion; automation failures.

### Crest Independence
- **Invariant:** Each crest SVG is a self-contained, independently renderable asset with no external dependencies.
- **Verification:** Open each `src/crests/*.svg` in isolation; renders correctly without `Planet Nirn.svg`.
- **Violation consequence:** Cannot reuse crests independently; map composition fails if crest references external resources.

### Map Composition Integrity
- **Invariant:** `Planet Nirn.svg` references all crests via relative paths to `src/crests/` and renders completely without missing assets.
- **Verification:** Open `Planet Nirn.svg` in Inkscape; all crest images visible at correct positions and scales.
- **Violation consequence:** Incomplete map renders; missing symbols in exports.

## Distribution Invariants

### Release Asset Immutability
- **Invariant:** Once a GitHub Release is published, its attached raster assets are never modified, replaced, or deleted.
- **Verification:** Release asset SHAs remain constant; GitHub Release API shows no asset updates after publication.
- **Violation consequence:** Consumers receive different files for same release tag; cache invalidation; trust erosion.

### Release Tag Correspondence
- **Invariant:** Every GitHub Release corresponds to a Git tag on `master` branch, and the tag points to the commit containing the source assets used for that release's exports.
- **Verification:** `git tag -l` matches GitHub Releases; `git show <tag>:Planet Nirn.svg` matches source used for export.
- **Violation consequence:** Inability to reproduce release from source; broken provenance chain.

### Resolution Completeness
- **Invariant:** Each release includes raster exports at all advertised resolutions (as documented in release notes and README).
- **Verification:** Manual checklist at release time; release asset list matches resolution matrix.
- **Violation consequence:** Consumers cannot obtain needed resolution; incomplete distribution.

### Asset Provenance Traceability
- **Invariant:** Every raster asset in a release can be traced to specific source SVG commits.
- **Verification:** Release notes reference Git commit SHA; source assets at that commit reproduce the exports.
- **Violation consequence:** Cannot verify asset integrity; supply-chain audit failure.

## Process Invariants

### Manual Validation Gate
- **Invariant:** No release is published without the maintainer visually validating all raster exports in an image viewer.
- **Verification:** Release checklist includes validation step; no automated bypass exists.
- **Violation consequence:** Rendering artefacts, incorrect resolutions, or colour shifts distributed to users.

### Single-Maintainer Release Authority
- **Invariant:** Only the repository maintainer (hmlendea) can publish GitHub Releases.
- **Verification:** GitHub repository settings; release history shows single publisher.
- **Violation consequence:** Unauthorised or unvalidated releases; supply-chain compromise.

### Documentation Synchronisation
- **Invariant:** When asset inventory changes (crests added/removed, map layers changed), README.md project structure table and ARCHITECTURE.md source map are updated in the same commit.
- **Verification:** Commit diff shows asset changes + documentation updates together.
- **Violation consequence:** Documentation drift; contributors and users misled about asset inventory.

## Legal and Attribution Invariants

### Fan Project Disclaimer
- **Invariant:** README.md Legal Disclaimer section states the project is fan-made and identifies Bethesda/ZeniMax as IP owners.
- **Verification:** README.md contains the disclaimer text.
- **Violation consequence:** Legal risk; misrepresentation of IP ownership.

### Community Attribution Preservation
- **Invariant:** README.md Acknowledgements section credits Elder Kings mod team (Akavir/eastern islands) and Beyond Skyrim mod teams (crests).
- **Verification:** README.md acknowledgements match actual asset provenance.
- **Violation consequence:** Attribution violation; community goodwill loss; potential licence breach.

### No Commercial Distribution
- **Invariant:** Assets are not sold, licensed commercially, or distributed via paid channels.
- **Verification:** Distribution only via free GitHub Releases; FUNDING.yml links to donations only.
- **Violation consequence:** IP infringement; violation of fan project understanding with rights holders.

## Configuration Invariants

### Funding Configuration Consistency
- **Invariant:** `.github/FUNDING.yml` references only the maintainer's verified funding platforms (github, patreon, ko_fi, liberapay, buy_me_a_coffee, custom).
- **Verification:** File contents match known maintainer accounts.
- **Violation consequence:** Donor confusion; potential fraud; brand dilution.

### Branch Protection
- **Invariant:** `master` branch is the sole development branch; no protected branch rules enforce reviews (single maintainer model).
- **Verification:** GitHub branch protection settings; commit history shows direct pushes to master.
- **Violation consequence:** Workflow inconsistency; unexpected CI requirements.

## Cross-Cutting Invariants

### No Executable Code
- **Invariant:** Repository contains no executable code, scripts, binaries, or build artefacts (except documentation).
- **Verification:** `find . -type f -executable` returns only directories; no `.exe`, `.dll`, `.so`, `.sh`, `.py`, `.js` files with execute bits.
- **Violation consequence:** Security surface expansion; build pipeline expectation mismatch; CI/CD confusion.

### No Runtime Dependencies
- **Invariant:** Consuming the distributed assets requires no runtime, interpreter, framework, or library beyond an image viewer.
- **Verification:** Release assets are standard PNG/JPG files; no installers, no dependencies listed.
- **Violation consequence:** Consumer friction; platform compatibility issues; support burden.

### No Persistent State at Consumption
- **Invariant:** Assets are stateless files; no configuration, cache, database, or user data is created or required when viewing maps.
- **Verification:** Assets are standalone image files; no side effects on open.
- **Violation consequence:** Privacy concerns; resource consumption; deployment complexity.