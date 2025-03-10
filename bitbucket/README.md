# Bitbucket Pipelines Configuration

This directory contains the original Bitbucket Pipelines configuration that was migrated to GitHub Actions.

## Implementation Details

### Key Features

- Uses YAML anchors (`&trigger_dev_staging_api`, `&trigger_staging_api`) for reusable steps
- Custom pipeline for Snyk security scanning
- Branch-specific pipelines for `dev-done`, `dev-master`, and `beta-master`
- Conditional Jira update based on commit messages

### Environment Variables

- Repository variables are referenced using `${VARIABLE_NAME}` syntax
- Includes standard Bitbucket variables like `${BITBUCKET_REPO_FULL_NAME}`, `${BITBUCKET_BRANCH}`, etc.

### Docker Image

The pipeline uses a custom Docker image for security scanning:
- `etunyiashime/snyk-scanner:latest`

## Migration Notes

When migrating this configuration to GitHub Actions:

- YAML anchors were converted to separate workflow files
- Bitbucket environment variables were mapped to GitHub equivalents
- Custom Docker container configuration was adapted for GitHub's container syntax

See the [main README](../README.md) for comprehensive information about the migration process and GitHub implementation.