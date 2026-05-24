# Artifact Map

This page explains the main product artifacts operators should expect to see.

## Personal

| Artifact | Meaning | Used by |
| --- | --- | --- |
| Project profile | Framework, entry point, trust boundary, permission, and data-surface context. | Function inventory and risk review. |
| Function inventory | Product behavior and function map. | Generic risk, business risk, finding review. |
| Generic risk review | Security paths not tied to one business scenario. | Finding review. |
| Business risk review | Product-specific risk paths and impact. | Finding review. |
| Finding review | Human-reviewable finding candidates and decisions. | Reports and fix packages. |
| Report | Delivery artifact for reviewed findings. | Operator handoff. |
| Fix package | Scoped repair artifact for selected findings. | Developer repair and validation. |

## Team

| Artifact | Meaning | Used by |
| --- | --- | --- |
| Team project | Shared product or service boundary. | All Team workflows. |
| SCM profile | Credentialed access profile for GitHub, GitLab, Bitbucket, or self-managed providers. | Code source, PR/MR review, writeback. |
| Code source | Local, remote, patch, or PR/MR source record. | Baseline, iteration, PR/MR review. |
| Baseline | Persistent project security reference. | Iteration comparison and release governance. |
| Requirement source | Manual, Jira, Confluence, or other source material. | Requirement extraction and impact review. |
| Change set | Patch, branch diff, PR/MR, or source delta. | Change impact and delta risk. |
| External report | Imported SAST/SCA or scanner output. | External report analysis and finding promotion. |
| Team finding | Reviewed issue with owner, status, and release impact. | Remediation and release readiness. |
| Remediation task | Assigned repair work. | Developer workflow and verification. |
| CI evidence | Build, test, or pipeline result attached to the same source scope. | Fix verification and release readiness. |
| Release readiness | Gate decision for the release. | Release owner. |
| Fresh baseline | Promoted post-release reference state. | Next iteration. |

## Artifact Quality Rules

- Artifacts should point to the same project and source scope.
- Reports should come from reviewed evidence, not raw candidates.
- Verification should be attached to the finding or task it proves.
- Accepted risk should identify owner and rationale.
- Release readiness should be rerun after material evidence changes.

