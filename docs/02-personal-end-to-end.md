# Personal End-to-End Review

Code Hunter Personal is for a single operator who needs to understand a project, review risks with AI assistance, confirm findings, and produce report or repair output without turning the workflow into an alert dump.

## Outcome

By the end of this workflow you should have:

- A project profile.
- A function inventory.
- Reviewed generic and business-risk findings.
- A human decision for each finding.
- A report or a scoped fix package generated only from selected findings.

## Step 1: Attach The Project

1. Open Code Hunter Personal.
2. Choose the local project folder.
3. Confirm the displayed project path and project name.
4. Exclude build output, caches, vendored artifacts, and generated files if they are not part of the review scope.
5. Save the project workspace.

What to verify:

- The project overview matches the real repository or folder.
- The workspace does not point at a temporary smoke copy or unrelated directory.
- The selected scope is understandable to the reviewer.

![Project overview](assets/personal/project-overview.jpg)

## Step 2: Configure The Review

1. Open audit configuration.
2. Select the language for output.
3. Select the provider and model.
4. Choose the report output format.
5. Decide whether this run should resume an existing review or start fresh.
6. Confirm the audit depth and target phases.

Good defaults:

- Use a fresh run for first-time evidence.
- Use the same output language as the operator-facing report.
- Use a model/provider that is already verified in Settings.

![Audit configuration](assets/personal/audit-config.jpg)

## Step 3: Build Project Context

The first phases build the context that later risk judgment depends on.

1. Run `project_profile`.
2. Review framework, entry points, trust boundaries, permissions, data surfaces, and external integrations.
3. Run `feature_inventory`.
4. Review the function-level inventory before trusting risk findings.

What to look for:

- The output describes product behavior, not just file names.
- Sensitive flows such as login, admin actions, payment, tenant boundaries, file upload, and external calls are visible.
- The reviewer can explain why each risk area belongs in scope.

![Function inventory](assets/personal/function-inventory.jpg)

## Step 4: Review Risk Candidates

Run the risk and finding-review stages:

1. Run generic risk review.
2. Run business risk review.
3. Run finding review.
4. Open the findings center.
5. Read each finding's evidence, impacted behavior, severity, confidence, and proposed remediation.

Decision rules:

- **Accept** when the evidence proves a reachable or defensible risk path.
- **Downgrade** when the issue is real but impact or likelihood is lower than claimed.
- **Reject** when the evidence is wrong, unreachable, duplicate, or outside scope.
- **Queue for repair** when the finding is accepted and the fix should be generated or tracked.

![Findings](assets/personal/findings.jpg)

## Step 5: Inspect Proof

Before exporting anything, open proof and evidence views.

1. Confirm the relevant source context.
2. Confirm the affected function chain.
3. Confirm the missing or failing control.
4. Confirm the product impact.
5. Confirm the remediation direction.

A finding is not report-ready if it only contains a rule name or isolated code snippet.

![Proof evidence](assets/personal/proof-evidence.jpg)

## Step 6: Export Report Or Generate Fix Package

Report path:

1. Select reviewed findings.
2. Generate the report.
3. Review the report cover, summary, finding detail, evidence, and remediation text.
4. Store the report with the run record.

Fix package path:

1. Select a confirmed finding.
2. Generate a scoped fix package.
3. Review the proposed patch, rollback notes, tests, and assumptions.
4. Apply only after the operator understands the change.
5. Run project tests outside Code Hunter before merging or shipping.

![Scoped repair](assets/personal/batch-repair.jpg)

## Done Criteria

The Personal review is complete only when:

- Every exported finding has a reviewer decision.
- The report does not include rejected or unreviewed findings.
- Fix packages are scoped to selected findings.
- The operator can explain the evidence chain from project context to remediation.

