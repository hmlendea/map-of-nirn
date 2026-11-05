# Documentation Maintenance

## Overview

This document defines how the repository's documentation is maintained: ownership, review cadence, update triggers, and quality standards.

## Documentation Inventory

| Document | Location | Purpose |
|----------|----------|---------|
| `README.md` | Root | Entry point; project overview and links |
| `CONTRIBUTING.md` | Root | Contribution guidelines |
| `SECURITY.md` | Root | Security policy and reporting |
| `ARCHITECTURE.md` | Root | High-level architecture |
| `CODE_OF_CONDUCT.md` | Root | Community standards |
| `PRIVACY.md` | Root | Data handling practices |
| `docs/INDEX.md` | docs/ | Master documentation index |
| `docs/repository-overview.md` | docs/ | Purpose, scope, capabilities |
| `docs/architecture.md` | docs/ | Detailed architecture elaboration |
| `docs/repository-structure.md` | docs/ | Source tree and asset inventory |
| `docs/source-map.md` | docs/ | Asset location and relationship mapping |
| `docs/data-model.md` | docs/ | Domain entities and relationships |
| `docs/state-and-persistence.md` | docs/ | State lifecycle and persistence |
| `docs/build-and-deployment.md` | docs/ | Export and release workflow |
| `docs/change-guide.md` | docs/ | Safe modification procedures |
| `docs/testing.md` | docs/ | Manual verification checklists |
| `docs/troubleshooting.md` | docs/ | Common issues and solutions |
| `docs/design-decisions.md` | docs/ | Key decisions with rationale |
| `docs/invariants.md` | docs/ | Rules that must always hold |
| `docs/dependencies.md` | docs/ | External dependency analysis |
| `docs/security.md` | docs/ | Security model elaboration |
| `docs/faq.md` | docs/ | Common questions |
| `docs/quick-start.md` | docs/ | Newcomer onboarding |
| `docs/documentation-maintenance.md` | docs/ | This document |

## Ownership

| Role | Responsibility |
|------|----------------|
| Repository maintainer | All documentation; final approval for changes |
| Contributors | Propose documentation changes via issues or pull requests |

## Update Triggers

Documentation MUST be updated when:

| Trigger | Affected Documents |
|---------|-------------------|
| New crest added or removed | `repository-structure.md`, `source-map.md`, `data-model.md`, `README.md` (if inventory listed) |
| Geography or layer change | `source-map.md`, `data-model.md`, `architecture.md` |
| Export resolution or format change | `build-and-deployment.md`, `testing.md`, `data-model.md` |
| Workflow change | `build-and-deployment.md`, `change-guide.md`, `state-and-persistence.md` |
| New design decision | `design-decisions.md`, `ARCHITECTURE.md` |
| New invariant identified | `invariants.md` |
| Security policy change | `SECURITY.md`, `docs/security.md`, `README.md` (Security section) |
| New dependency or tool version | `dependencies.md`, `build-and-deployment.md` |

## Review Cadence

| Review Type | Frequency | Scope |
|-------------|-----------|-------|
| Release review | Every release | All documents affected by the release |
| Link check | Quarterly | All cross-references in all documents |
| Full audit | Annually | Every document against actual repository state |
| Post-change review | After any asset change | Documents listed in update triggers |

## Quality Standards

| Standard | Requirement |
|----------|-------------|
| Accuracy | Every statement must reflect actual repository state |
| Links | All repository-relative links must resolve |
| Consistency | Terminology must match across documents |
| Structure | Documents follow established heading patterns |
| Currency | No document may reference retired workflows or assets |
| Traceability | Claims about assets must be verifiable in the repository |

## Maintenance Procedure

| Step | Action |
|------|--------|
| 1 | Identify the trigger (asset change, workflow change, scheduled review) |
| 2 | Consult the update trigger table for affected documents |
| 3 | Read each affected document before editing |
| 4 | Apply minimal, accurate updates |
| 5 | Verify all cross-references still resolve |
| 6 | Commit documentation changes with the triggering change (or separately) |
| 7 | Update `docs/INDEX.md` if new documents were added |

## Cross-References

- [Index](INDEX.md)
- [Repository Structure](repository-structure.md#documentation-architecture)
- [Contributing](../CONTRIBUTING.md)