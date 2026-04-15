# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **reusable GitHub Actions workflow** (`tf-ci-reusable-wf`) that provides a Terraform CI pipeline for multi-cloud deployments. It is consumed by other repositories via `workflow_call` — it is not a standalone application.

Supported cloud providers: AWS, GCP, Azure, Snowflake, Databricks. A "platform" mode runs across all providers by detecting `infra/{provider}/tf` directories.

## Repository Structure

- `.github/workflows/ci.yaml` — The main reusable CI workflow (the core deliverable of this repo)
- `.github/workflows/release.yaml` — Semantic release automation on `main` pushes
- `.github/workflows/create-branch.yaml` — Auto-creates feature branches from issue assignments
- `.github/workflows/notify.yaml` — Slack notifications for PRs/issues
- `scripts/plugins/` — Custom semantic-release plugins (commit analyzer, notes generator, etc.)
- `.releaserc.json` — Root semantic-release configuration

## Development Commands

```bash
# Install dependencies (semantic-release toolchain)
npm install

# Semantic release dry run (test release without publishing)
npx semantic-release --dry-run
```

There is no build step, test suite, or linter configured — the primary artifact is YAML workflow definitions.

## CI Workflow Architecture

The reusable workflow in `ci.yaml` runs these jobs in dependency order:

1. **print-inputs** — Debug logging of workflow inputs
2. **input-validation** — Validates backend-type, cloud-provider, and required secrets/variables
3. **terraform-lint** → depends on input-validation (uses `tf-lint-action`)
4. **terraform-tag** → depends on input-validation (YOR tagging — placeholder)
5. **terraform-validate** → depends on terraform-lint + terraform-tag (uses `tf-validate-action`)
6. **checkov-scan** → depends on terraform-validate (security scanning — placeholder)
7. **terraform-plan** → depends on terraform-validate + checkov-scan (uses `tf-plan-action`)

Jobs marked "placeholder" have `echo` steps and need real implementation.

## Key Design Patterns

- **External custom actions**: Core logic lives in separate repos under `subhamay-bhattacharyya-gha/` (tf-lint-action, tf-validate-action, tf-plan-action). Changes to Terraform step behavior typically require modifying those repos, not this one.
- **Backend types**: `s3` (AWS S3 state) or `remote` (HCP Terraform Cloud). Backend type drives which variables and authentication are needed.
- **Concurrency control**: Workflow runs are grouped by `{cloud-provider}-{branch}` to prevent parallel runs for the same provider/branch.
- **Authentication per provider**: AWS uses IAM role assumption, GCP uses Workload Identity Federation, Azure uses Service Principal, Snowflake uses base64-encoded private key, Databricks uses token auth.

## Repository Variables vs Workflow Inputs

Several provider-specific non-secret values are read from **GitHub repository/environment variables** (the `vars` context) rather than `workflow_call` inputs. This avoids repetitive caller-side boilerplate and centralises configuration in the consuming repository's settings.

| Variable Name                  | Context       | Environment | Used by provider |
|--------------------------------|---------------|-------------|------------------|
| `AWS_REGION`                   | `vars`        | `ci`        | AWS              |
| `AWS_OIDC_ROLE`                | `vars`        | `ci`        | AWS              |
| `GCP_WIF_PROVIDER`             | `vars`        | `ci`        | GCP              |
| `GCP_SERVICE_ACCOUNT`          | `vars`        | `ci`        | GCP              |
| `AZURE_CLIENT_ID`              | `vars`        | `ci`        | Azure            |
| `AZURE_TENANT_ID`              | `vars`        | `ci`        | Azure            |
| `AZURE_SUBSCRIPTION_ID`        | `vars`        | `ci`        | Azure            |
| `SNOWFLAKE_ORGANIZATION_NAME`  | `vars`        | `ci`        | Snowflake        |
| `SNOWFLAKE_ACCOUNT_NAME`       | `vars`        | `ci`        | Snowflake        |
| `SNOWFLAKE_USER`               | `vars`        | —           | Snowflake        |
| `SNOWFLAKE_ROLE`               | `vars`        | —           | Snowflake        |

These variables are read from the GitHub environment specified by the `environment` input (default: `ci`). They must be configured in the consuming repository under **Settings → Environments → [environment name] → Environment variables**. Variables marked with `—` in the Environment column are configured at the repository level. All are validated in the `Validate Input Configuration` step and will cause the workflow to fail fast if absent for the relevant provider.

All remaining provider credentials (private keys, tokens, etc.) continue to be passed as `secrets` via `workflow_call`.

## Commit Conventions

This project uses **Conventional Commits** with semantic-release for automated versioning:

- `feat:` → minor version bump
- `fix:` → patch version bump
- `feat!:` or `BREAKING CHANGE:` → major version bump

Commitizen is configured (`cz-conventional-changelog`) — use `npx cz` for guided commit messages.

## Branch Naming

Feature branches follow the pattern: `feature/GHA-{issue-number}-{description}` (auto-created by `create-branch.yaml` when issues are assigned).
