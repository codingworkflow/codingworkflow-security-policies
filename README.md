# codingworkflow-security-policies

Central repository for organization-wide CI/CD governance workflows.

## Required workflows

- `.github/workflows/required-zizmor.yml`
  - Reusable workflow (`workflow_call`) designed to be enforced through GitHub org rulesets.
  - Runs `zizmor` against `.github/workflows` in the caller repository.
- `.github/workflows/required-poutine.yml`
  - Reusable workflow (`workflow_call`) designed to be enforced through GitHub org rulesets.
  - Runs `boostsecurityio/poutine-action` and uploads SARIF to code scanning.

## Reusable workflows

- `.github/workflows/reusable-claude-review.yml`
  - Centralized manual PR review workflow using `anthropics/claude-code-action`.
  - Supports Azure OIDC + Azure Key Vault secret retrieval in caller context.
- `.github/workflows/reusable-opencode-review.yml`
  - Centralized manual PR review workflow using `anomalyco/opencode/github`.
  - Supports both single model and multi-model matrix runs in the same workflow:
    - use `model` for a single run
    - use `models` (comma/newline list) for matrix fan-out

## Governance

- Protected by a repository ruleset managed with Terraform.
- CODEOWNERS requires owner review for all changes.
