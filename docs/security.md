# Security Model

## Overview

This document elaborates the security model for the Map of Nirn repository. The authoritative policy is [SECURITY.md](../SECURITY.md); this document provides additional detail on asset integrity, supply-chain considerations, and provenance.

## Security Scope

| In Scope | Out of Scope |
|----------|--------------|
| Malicious or corrupted SVG assets | Downstream forks and mirrors |
| Supply-chain tampering with releases | Third-party usage of the assets |
| Provenance misrepresentation | Canon accuracy of map content |
| Repository access compromise | Consumer-side handling after download |
| Vulnerabilities in the release process | — |

## Threat Model

| Threat | Vector | Impact | Mitigation |
|--------|--------|--------|------------|
| Malicious SVG payload | SVG containing scripts or external references | Consumer compromise on render | Manual review of all SVG content; no scripts in sources |
| Release asset tampering | Modified files on CDN | Consumers receive corrupted assets | SHA-256 checksums in release notes; release immutability |
| Provenance forgery | False claims of authorship | Misattribution; licence violations | Git history as authoritative record; licence terms |
| Repository compromise | Stolen maintainer credentials | Malicious commits or releases | GitHub account security (2FA); release review before publication |
| Supply-chain injection | Compromised export toolchain | Defective or malicious exports | Local export from trusted machine; validation checklist |

## Asset Integrity

### Source Integrity

| Control | Mechanism |
|---------|-----------|
| Content review | Every SVG manually reviewed before commit |
| No active content | SVGs contain no scripts, event handlers, or external references |
| Git history | Tamper-evident record of all changes |
| Single-branch model | All changes flow through `master`; reviewable history |

### Release Integrity

| Control | Mechanism |
|---------|-----------|
| Checksums | SHA-256 published in release notes for every artefact |
| Immutability | Published releases are never modified |
| Validation | Pre-release checklist before publication |
| Traceability | Every release references a tagged source commit |

## Consumer Verification

Consumers SHOULD verify release integrity:

1. Download the artefact from the GitHub Release page.
2. Compute the checksum: `sha256sum <file>`.
3. Compare against the value in the release notes.
4. Reject any artefact whose checksum does not match.

## Provenance

| Aspect | Guarantee |
|--------|-----------|
| Authorship | Git commit history records all contributors |
| Licensing | Repository licence governs all assets |
| Origin | GitHub repository is the sole authoritative source |
| Attribution | Licence terms must be preserved in redistribution |

## Vulnerability Reporting

Report vulnerabilities via [GitHub Security Advisories](https://github.com/hmlendea/map-of-nirn/security/advisories/new). See [SECURITY.md](../SECURITY.md) for the full coordinated disclosure policy.

| Aspect | Policy |
|--------|--------|
| Reporting channel | GitHub Security Advisories (private) |
| Response time | Best effort; no SLA |
| Coordinated disclosure | Public disclosure after fix, in coordination with reporter |
| Scope | See table above |

## Security Checklist (Maintainer)

Before every release:

| # | Check |
|---|-------|
| 1 | SVG sources contain no scripts or external references |
| 2 | Export performed on a trusted machine |
| 3 | Checksums computed and recorded |
| 4 | Release notes include checksums |
| 5 | Release reviewed before publication |
| 6 | No credentials or personal data in any committed file |

## Cross-References

- [Security Policy](../SECURITY.md) (authoritative)
- [Build and Deployment](build-and-deployment.md)
- [Testing](testing.md)
- [Invariants](invariants.md#legal-and-attribution-invariants)