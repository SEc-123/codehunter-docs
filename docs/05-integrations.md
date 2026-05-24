# Integrations

Code Hunter integrations exist to preserve delivery context. They should help the product answer: what changed, why it changed, who owns the fix, what evidence exists, and whether the release can pass.

## SCM: GitHub, GitLab, Bitbucket

Use SCM profiles for remote Git, PR/MR review, and writeback.

Required fields depend on provider and auth mode:

| Auth mode | Typical fields |
| --- | --- |
| Bearer token | Provider, token, host URL for self-managed instances, allowed repositories. |
| Basic auth | Username, token or password, host URL, repository. |
| SSH key | Private key, known host policy, repository SSH URL. |

Setup steps:

1. Create SCM profile.
2. Choose provider.
3. Enter host URL if self-managed.
4. Enter auth material.
5. Save profile.
6. Create code source using that profile.
7. Test connection.
8. List refs.
9. Use the source for baseline, change set, PR/MR review, or writeback.

Rules:

- A saved credential is not enough. Test a live source.
- PR review is for PR/MR diff review. Full repository posture belongs to baseline.
- Writeback should be used for review comments, commit status, or release evidence after the finding is reviewed.

## Jira

Use Jira when requirements, security acceptance criteria, or remediation tasks are managed in Jira.

Required context:

- Jira base URL.
- Auth mode and credential.
- Project key.
- JQL or issue selector.
- Target Team project and iteration.

Setup steps:

1. Create Jira connector.
2. Test the connector.
3. Import requirement source into an iteration.
4. Run requirement extraction.
5. Review and save structured requirements.
6. Link findings or remediation tasks back to Jira if your workflow uses Jira as the owner-facing queue.

## Confluence

Use Confluence when architecture, threat model, product requirements, or release notes live in pages.

Required context:

- Confluence base URL.
- Auth mode and credential.
- Page IDs or search scope.
- Target Team project and iteration.

Setup steps:

1. Create Confluence connector.
2. Test the connector.
3. Import pages into an iteration as requirement or context sources.
4. Run extraction and impact analysis.
5. Review structured output before using it for gate decisions.

## CI Evidence

Code Hunter reads CI evidence. It does not create your CI pipeline.

Supported patterns include:

- GitHub Actions.
- GitLab CI.
- Jenkins.
- Manual evidence when external CI access is not available.

Setup steps:

1. Create CI connector.
2. Provide repository, project, job, or base URL context.
3. Test connector.
4. Link CI evidence to PR/MR, remediation task, or release readiness.
5. Confirm the CI result belongs to the same source scope as the finding.

## Notifications

Notifications can send workflow state to Slack, Microsoft Teams, Lark, or other configured channels.

Use notifications for visibility, not as security evidence. The evidence remains in Code Hunter: finding, task, PR/MR, CI result, verification, accepted risk, and release-readiness records.

## External Scanner Reports

Use external report import for SAST, SCA, or other scanner outputs that already exist.

1. Upload or select report.
2. Identify scanner and format.
3. Bind report to project, branch, commit, or baseline.
4. Preview.
5. Import.
6. Run external report analysis.
7. Promote only reviewed findings.

