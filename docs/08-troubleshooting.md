# Troubleshooting

Use this guide when the UI, run output, connector, or release gate does not match the expected workflow.

## Project Looks Wrong

Symptoms:

- Findings refer to files outside the intended project.
- Screenshots show a temporary folder.
- Baseline source does not match the repo under review.

Check:

1. Project path.
2. Code source record.
3. Branch, commit, or patch.
4. Baseline source.
5. Any temporary workspace path.

Fix:

- Rebind the code source to the intended repository.
- Re-run baseline or iteration from the correct source.
- Do not reuse evidence from a smoke or temporary copy as product evidence.

## Provider Test Fails

Check:

1. Base URL.
2. Auth mode.
3. API key or token validity.
4. Model name.
5. Network access.
6. Rate limit or quota response.

Fix:

- Update the provider profile.
- Use a known working model.
- Retry after rate-limit reset.
- Keep failure messages out of public reports if they expose account details.

## Remote Git Test Passes But Baseline Fails

Check:

1. Whether the baseline uses the same SCM profile.
2. Whether clone permission is granted, not only metadata permission.
3. Whether branch or commit exists.
4. Whether SSH key or token has correct scope.
5. Whether self-managed provider base URL is correct.

Fix:

- Re-test the code source.
- Re-select auth profile.
- Re-run baseline after confirming clone access.

## Jira Or Confluence Imports Nothing

Check:

1. Base URL.
2. Credential scope.
3. Project key, JQL, page ID, or space.
4. Pagination limit.
5. Whether the connector test returns a readable remote error.

Fix:

- Narrow the query.
- Confirm the account can see the issue or page in the source system.
- Import one known item before importing a wide range.

## External Report Import Looks Empty

Check:

1. Report format.
2. Scanner tool selection.
3. File upload path.
4. Project binding.
5. Branch or commit binding.
6. Whether the report has findings after filters.

Fix:

- Re-import with the correct scanner and format.
- Confirm the report is not an empty export.
- Run external report analysis before expecting Team findings.

## Release Readiness Is Blocked

Common reasons:

- Blocking finding remains open.
- Remediation task lacks verification.
- CI evidence is missing or belongs to a different commit.
- Accepted risk lacks owner or rationale.
- SCA exception expired.
- Baseline is stale.

Fix:

1. Open release-readiness details.
2. Follow each blocker to its finding, task, CI record, or exception.
3. Resolve or document the blocker.
4. Re-run release readiness.

## Report Is Missing Findings

Check:

- Were the findings reviewed?
- Were they selected for export?
- Were they rejected or filtered?
- Did the run use the intended language and report format?

Fix:

- Return to findings review.
- Select the intended findings.
- Regenerate the report.

## When To Contact Support

Contact `contact@arvantacyber.com` when:

- License or activation does not complete.
- A provider or connector fails with a remote error you cannot interpret.
- A release gate contradicts visible evidence.
- You need enterprise setup guidance.

