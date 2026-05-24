# Code Hunter Documentation

![Code Hunter logo](docs/assets/logo/codehunter-logo.png)

Code Hunter is Arvanta Cyber's AI AppSec workbench for turning scanner output, code context, model review, human judgment, remediation work, and release evidence into one accountable workflow.

This repository contains product documentation only. It does not contain Code Hunter source code, build artifacts, license material, customer data, or internal runtime secrets.

## Start Here

| Guide | Use it when |
| --- | --- |
| [Get started](docs/01-get-started.md) | You need the fastest path from install to a first reviewed result. |
| [Personal end-to-end review](docs/02-personal-end-to-end.md) | One operator owns project review, evidence, report output, and scoped fix work. |
| [Team end-to-end workflow](docs/03-team-end-to-end.md) | A team needs projects, baselines, requirements, findings, tasks, verification, and release readiness. |
| [SCA release governance](docs/04-sca-release-governance.md) | Dependency risk must become a policy-backed release decision. |
| [Integrations](docs/05-integrations.md) | You are connecting GitHub, GitLab, Bitbucket, Jira, Confluence, CI, or notification tools. |
| [Reports and evidence](docs/06-reports-evidence.md) | You need to understand exported reports, evidence chains, and audit records. |
| [Administration and security](docs/07-admin-security.md) | You are managing providers, workspaces, secrets, license state, or data boundaries. |
| [Troubleshooting](docs/08-troubleshooting.md) | A run, connector, report, or release gate does not look right. |

Reference:

- [Glossary](docs/reference/glossary.md)
- [Artifact map](docs/reference/artifact-map.md)
- [Security policy](SECURITY.md)

## Product Map

Code Hunter has two product versions:

- **Personal**: desktop review for an individual operator. It starts with a local project, builds project and function context, reviews security paths with an AI provider, lets the operator confirm findings, and produces report or fix-package output.
- **Team**: shared AppSec governance workspace. It connects projects, code sources, baselines, requirements, external scanner reports, PR review, SCA policy, remediation tasks, CI evidence, and release readiness.

The common product promise is the same in both versions: do not stop at an alert. Preserve enough context for a human to decide whether the issue is real, who owns the fix, and whether the release can pass.

## What Good Looks Like

A complete Code Hunter workflow should leave behind:

1. A project or code-source record.
2. A run or baseline record with source, scope, and model/provider context.
3. Reviewed findings with severity, confidence, evidence, and remediation direction.
4. A report, fix package, remediation task, or release-readiness record.
5. Verification evidence or an explicit accepted-risk decision before a release is treated as ready.

## Support

For product access, license, or enterprise pilot questions, contact `contact@arvantacyber.com`.

