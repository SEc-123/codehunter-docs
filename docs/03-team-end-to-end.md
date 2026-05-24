# Team End-to-End Workflow

Code Hunter Team is the shared AppSec governance workspace. It turns requirements, code changes, scanner reports, AI review, remediation tasks, CI evidence, and release decisions into one traceable flow.

## Outcome

By the end of a complete Team workflow you should have:

- A Team project.
- A verified code source.
- A baseline or current iteration.
- Reviewed findings.
- Remediation tasks with owners.
- Verification or accepted-risk evidence.
- A release-readiness decision.
- A promoted fresh baseline when the release is accepted.

## Step 1: Create A Team Project

1. Open Team.
2. Create a project.
3. Set project name, owner, default branch, and release policy.
4. Confirm the project appears in Team Dashboard and Projects.

Use one Team project per product or service boundary. Avoid grouping unrelated repositories only because they share an owner.

## Step 2: Add A Code Source

Supported source patterns:

- Local Git repository.
- Remote Git repository.
- Patch-only source.
- PR/MR review source.

For remote Git:

1. Create an SCM profile.
2. Select provider: GitHub, GitLab, or Bitbucket.
3. Select auth mode: bearer token, basic auth, or SSH key.
4. Save the profile.
5. Create a code source that uses the profile.
6. Test connection and list refs.
7. Select branch, tag, commit, or PR/MR.

Do not treat a saved token as proof. A code source is ready only after connection test, ref listing, baseline materialization, or PR review proves live repository access.

## Step 3: Build Or Refresh The Baseline

The baseline is the persistent security reference for the project.

1. Select the project.
2. Select the code source and ref.
3. Run baseline initialization.
4. Wait for the baseline workflow to finish.
5. Open the baseline report, findings, contracts, diff, and timeline.
6. Confirm the baseline result represents the intended source state.

![Baseline project](assets/team/baseline-project.webp)

## Step 4: Create An Iteration

An iteration represents a change cycle.

1. Create an iteration from the current baseline.
2. Add requirement sources.
3. Add code changes, patch material, or PR/MR review material.
4. Add external scanner reports if available.
5. Confirm all input material is attached to the same project and iteration.

![Iteration workbench](assets/team/iteration-workbench.webp)

## Step 5: Run Requirement And Change Analysis

Typical stage order:

1. Requirement extraction.
2. Requirement impact analysis.
3. Requirement security analysis.
4. Control owner review.
5. Gate policy.
6. Change impact.
7. Delta generic risk.
8. Delta business risk.
9. Delta finding review.
10. Impact analysis.
11. Owner finding triage.

The exact stages depend on the input material. For example, a PR-only review may focus on changed code and delta risk. A requirements-heavy release should include requirement extraction, owner review, and gate policy.

## Step 6: Import External Scanner Reports

Use this when SAST, SCA, or other scanner output already exists.

1. Open Reports or External SAST intake.
2. Upload or select the report file.
3. Set scanner tool, format, project, branch, commit, and report date.
4. Preview the import.
5. Run external report analysis.
6. Review normalized findings.
7. Import only owner-approved findings into Team findings.

The goal is not to duplicate scanner output. The goal is to make existing scanner output attributable, reviewable, and actionable.

![External results](assets/team/external-results.webp)

## Step 7: Triage Findings

Open the Findings workbench.

For each finding:

1. Confirm source and affected area.
2. Read product impact and evidence.
3. Accept, reject, defer, or mark accepted risk.
4. Assign owner if remediation is required.
5. Create a remediation task.
6. Link the task to PR/MR, CI, or manual verification evidence.

Do not send raw alert lists to developers. Send developer-ready work with evidence, acceptance criteria, and a clear done condition.

## Step 8: Remediate And Verify

1. Developer or agent claims the task.
2. Developer prepares a patch or PR/MR.
3. Link the PR/MR to the remediation task.
4. Run tests and CI.
5. Attach CI result, reviewer approval, or manual verification evidence.
6. Update finding status to verified fixed, accepted risk, or pending verification.

![Remediation task](assets/team/iteration-task.webp)

## Step 9: Run Release Readiness

Release readiness evaluates:

- Blocking findings.
- Remediation task status.
- PR/MR and CI evidence.
- Fix verification.
- Accepted residual risk.
- Policy state.
- Owner approval.

Possible outcomes:

- **Blocked**: release cannot pass under current policy.
- **Pending verification**: remediation may exist but evidence is incomplete.
- **Pass with risk**: owner accepts residual risk with rationale.
- **Ready**: policy, evidence, and verification are sufficient.

## Step 10: Promote Fresh Baseline

After a release is accepted:

1. Promote the accepted state to a fresh baseline.
2. Confirm the new baseline has the correct parent and head commit.
3. Use the new baseline for the next iteration.

This prevents the next release from comparing against stale security state.

## Done Criteria

The Team workflow is complete only when:

- Findings are not raw scanner rows.
- Remediation tasks have owners and evidence.
- Release readiness uses the same project, iteration, and source scope.
- Accepted risk is explicit.
- The baseline is promoted only after the release decision is defensible.

