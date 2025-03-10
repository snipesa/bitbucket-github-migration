# GitHub Actions Workflows

This directory contains the GitHub Actions workflow files that replace the Bitbucket Pipelines configuration.

## Files Overview

- **dev-done.yml**: Workflow for the `dev-done` branch that triggers both DEV and PROD API endpoints and runs Snyk scan
- **dev-master.yml**: Workflow for the `dev-master` branch that triggers PROD API endpoint
- **beta-master.yml**: Workflow for the `beta-master` branch that triggers PROD API endpoint
- **snyk-scan.yml**: Reusable workflow for Snyk security scanning
- **jira-ticket.yml**: Workflow that handles Jira updates when PRs are merged

## Implementation Notes

- GitHub Actions uses separate workflow files (vs. Bitbucket's single YAML with anchors)
- Reusable workflows are implemented using the `workflow_call` trigger
- Environment variables and secrets use the `${{ secrets.SECRET_NAME }}` and `${{ vars.VARIABLE_NAME }}` syntax

## Required Repository Configuration

### Secrets
- `DEV_API_KEY`
- `PROD_API_KEY`
- `SNYK_AUTH_TOKEN`

### Variables
- `DEV_API_GATEWAY_URL`
- `PROD_API_GATEWAY_URL`
- `JIRA_DEV_SOURCE_BRANCH`
- `JIRA_STAGING_SOURCE_BRANCH`

See the [main README](../README.md) for more detailed information about the migration.