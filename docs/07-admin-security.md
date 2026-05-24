# Administration And Security

This guide covers the operating boundaries for Code Hunter workspaces, provider profiles, secrets, and product evidence.

## Provider Profiles

Use provider profiles to route AI review through an approved model provider.

Before a production run:

1. Open Settings.
2. Confirm provider base URL.
3. Confirm model.
4. Confirm auth mode.
5. Run a provider test if available.
6. Confirm output language and review depth.

Do not paste provider secrets into reports, issue descriptions, screenshots, or support tickets.

## Workspaces

Personal workspaces are operator-owned. Team workspaces are project-owned.

Workspace rules:

- Keep source path, run state, evidence, report output, and fix output together.
- Do not mix unrelated repositories in one review unless the product boundary requires it.
- Treat temporary copies as implementation details. Verify the authoritative source path before using evidence.

## Secrets

Secrets include:

- Provider API keys.
- SCM tokens.
- Jira or Confluence tokens.
- CI credentials.
- Webhook secrets.
- License or activation material.

Handling rules:

- Store secrets only in Code Hunter settings or connector stores designed for secrets.
- Do not write secrets into docs, reports, tickets, PR comments, or screenshots.
- Rotate credentials if they are pasted into the wrong place.
- Use least-privilege tokens for each integration.

## Roles

Typical Team roles:

- Security lead: defines policy and reviews release evidence.
- Project owner: decides release readiness and accepted risk.
- Developer owner: fixes or verifies assigned remediation tasks.
- Reviewer: confirms findings, false positives, and remediation state.
- Admin: manages connectors, license, provider settings, and user access.

## Data Boundaries

Code Hunter should preserve enough evidence to support decisions, but not more data than needed.

Recommended boundaries:

- Source code stays in the approved workspace.
- Reports contain reviewed evidence, not raw internal runtime paths.
- Connector secrets are write-only from the operator's perspective.
- External writeback should contain summarized decisions and links, not unnecessary source excerpts.

## Public Documentation Boundary

This docs repository is public. Do not add:

- Source code.
- License keys.
- Internal endpoint secrets.
- Customer repositories.
- Private screenshots.
- Raw production logs.

Only product documentation, public screenshots, workflow diagrams, and safe examples belong here.

