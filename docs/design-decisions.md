# Design Decisions — Map of Nirn

This document records key architectural and design choices with their rationale and consequences.

## 1. Static Asset Repository Pattern

**Decision:** The repository contains only static SVG and raster assets with no executable code, build pipeline, or runtime.

**Rationale:**
- The deliverable is purely visual/cartographic content
- No computation, transformation, or logic is required at consumption time
- Eliminates entire categories of operational complexity (CI/CD, runtime dependencies, security surface, scaling)

**Consequences:**
- All transformations are manual (SVG → raster via Inkscape export)
- Reproducibility depends on human process discipline
- No automated regression detection for rendering changes
- Contributors need only a vector graphics editor, not a development environment

## 2. SVG as Canonical Source Format

**Decision:** All source assets use SVG (Scalable Vector Graphics) as the authoritative format.

**Rationale:**
- Infinite scalability for any output resolution
- Human-editable in standard tools (Inkscape, Illustrator, text editors)
- Version-controllable (XML-based, diffable)
- Widely supported across platforms and tools
- Preserves layer structure, object metadata, and styling

**Consequences:**
- Requires Inkscape-compatible SVG features for consistent editing
- No runtime parsing needed — consumers receive raster exports
- File sizes larger than minimal raster formats, but acceptable for source
- Text-based diffs in Git enable meaningful review of changes

## 3. Manual Export and Validation Workflow

**Decision:** Raster exports are produced and validated manually by the maintainer using Inkscape and an image viewer.

**Rationale:**
- Visual quality assessment requires human judgement (colour fidelity, artefact detection, legibility)
- Inkscape's export pipeline has subtle behaviours (DPI handling, layer visibility, filter effects) that are difficult to automate reliably
- Low release frequency (asset updates are infrequent) makes automation ROI negative
- Eliminates CI/CD infrastructure and maintenance

**Consequences:**
- Release process is time-consuming and not reproducible without identical tool versions
- No automated detection of rendering regressions
- Maintainer is a bottleneck for releases
- Human error possible in export settings or validation

## 4. GitHub Releases as Distribution Channel

**Decision:** Distribution artefacts are published exclusively via GitHub Releases.

**Rationale:**
- Free, reliable CDN with global edge distribution
- Immutable per-release artefacts with permanent URLs
- Integrated with Git version control (tags ↔ releases)
- Built-in download statistics
- No infrastructure provisioning or maintenance

**Consequences:**
- Platform lock-in to GitHub
- No control over CDN configuration or caching headers
- Download analytics limited to GitHub's provided metrics
- Consumers must have GitHub access (public repo mitigates this)

## 5. Flat Crest Directory Structure

**Decision:** All crest SVGs reside directly in `src/crests/` with no subdirectories.

**Rationale:**
- Simple discovery: `ls src/crests/` shows all crests
- Easy to reference in `Planet Nirn.svg` (relative paths)
- Low crest count (~30) doesn't justify hierarchical organisation
- Naming convention (`<Location Name>.svg`) provides implicit categorisation

**Consequences:**
- No logical grouping by region, faction, or type
- Naming collisions possible if locations share names
- Adding metadata (region, faction) requires external documentation or SVG metadata

## 6. No Automated Testing

**Decision:** No automated test suite exists; verification is entirely manual.

**Rationale:**
- No executable code to test
- Visual validation requires human perception
- Asset count and change frequency are low
- Testing infrastructure would exceed maintenance burden of manual checks

**Consequences:**
- No regression detection for rendering changes
- No enforcement of SVG structure conventions
- No validation of export resolution completeness
- Relies on maintainer diligence and checklists

## 7. Canon Accuracy vs. Community Content

**Decision:** The map includes non-canon content (Akavir, eastern islands from Elder Kings mod; crests from Beyond Skyrim mods) where canonical sources are unavailable.

**Rationale:**
- Complete world coverage is a project goal
- Canon sources are incomplete for large regions
- Community mods provide high-quality, lore-consistent content
- Transparency about sources is maintained in README Known Limitations

**Consequences:**
- Map is not purely canonical; users must understand provenance
- Legal status of derivative mod content is complex (fan project disclaimer addresses this)
- Updates to source mods may not be reflected
- Community attribution must be maintained

## 8. Single-Branch Development (master)

**Decision:** All development occurs on `master` branch; no feature branches, no release branches.

**Rationale:**
- Single maintainer; no parallel development
- Asset changes are atomic and independent
- No need for release stabilisation periods
- Simplifies Git workflow

**Consequences:**
- No isolation for experimental changes
- Broken commits directly affect `master` (mitigated by local validation before push)
- No semantic versioning via branch names
- Release tags are the only version markers

## 9. Inkscape as Reference Editor

**Decision:** Inkscape is the reference editor; SVG features must be Inkscape-compatible.

**Rationale:**
- Free, open-source, cross-platform
- Excellent SVG 1.1 support with useful extensions
- Widely used in open-source graphics workflows
- Command-line export capability (though not used in current workflow)

**Consequences:**
- Proprietary SVG features (Adobe Illustrator, etc.) are prohibited
- Contributors must use Inkscape or ensure compatibility
- Inkscape-specific layer/group semantics become de facto standard
- Version drift between Inkscape releases could affect rendering

## 10. Release Immutability

**Decision:** Once published, release artefacts are never modified; corrections require a new release.

**Rationale:**
- Immutable releases ensure consumers get consistent assets
- Git tags are immutable; releases mirror this property
- Simplifies caching and CDN behaviour
- Audit trail of what was distributed when

**Consequences:**
- Mistakes in a release require a new tag (even for minor fixes)
- Version numbers increment for any correction
- No "patch" releases without new tag