# Get Started With Code Hunter

This guide gives you the shortest complete path through Code Hunter. Use Personal when one person owns the review. Use Team when security work must be assigned, verified, and used for a release decision.

## Before You Begin

You need:

- A Code Hunter license or activation grant.
- A project repository or local source folder.
- At least one AI provider profile configured in Code Hunter.
- Permission to scan the project and to store local evidence.
- For Team workflows, permission to connect the team's SCM, ticketing, CI, and notification systems.

Recommended first project:

- Small enough to understand in one session.
- Has a clear default branch or local working copy.
- Has representative security behavior, such as authentication, authorization, tenant boundary, payment, file handling, API input, dependency, or admin operation code.

## Choose Your Path

### Path A: Personal

Use this when one operator owns the review.

1. Open Code Hunter Personal.
2. Activate the product if prompted.
3. Open Settings and confirm provider routing.
4. Attach a local project folder.
5. Review the project overview.
6. Configure audit scope, language, model, and output format.
7. Run the review.
8. Inspect function inventory and progress.
9. Review candidate findings.
10. Accept, reject, downgrade, or queue each finding.
11. Export a report or generate a scoped fix package.
12. Keep the report and fix package tied to the reviewed findings.

![Personal project overview](assets/personal/project-overview.jpg)

### Path B: Team

Use this when multiple roles need the same evidence chain.

1. Open Code Hunter Team.
2. Create or select a Team project.
3. Add a code source: local Git, remote Git, patch-only, or PR/MR.
4. Test the code source and select the ref or commit.
5. Run or refresh the project baseline.
6. Create an iteration.
7. Add requirement sources, change sets, PRs, patches, or external scanner reports.
8. Run the analysis stages needed for the iteration.
9. Review findings and assign owners.
10. Create remediation tasks.
11. Link PR/MR, CI, or manual verification evidence.
12. Run release readiness.
13. Block, pass with risk, or pass the release.
14. Promote a fresh baseline after the release is accepted.

![Team baseline project](assets/team/baseline-project.webp)

## First Successful Run Checklist

Use this checklist before treating the first run as usable evidence:

- The project source is the intended repository or local folder.
- The selected branch, commit, or patch is the intended scope.
- The provider profile is valid and the run uses the intended model.
- Findings show evidence, severity, confidence, and remediation direction.
- Rejected findings have a reason.
- Accepted-risk findings have an owner and rationale.
- Reports or fix packages come only from reviewed findings.
- Team release readiness reflects task state, verification evidence, CI evidence, and accepted residual risk.

## What To Read Next

- For a single-operator review, continue with [Personal end-to-end review](02-personal-end-to-end.md).
- For shared delivery, continue with [Team end-to-end workflow](03-team-end-to-end.md).
- For dependency risk and release gates, continue with [SCA release governance](04-sca-release-governance.md).

