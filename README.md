# codingworkflow-security-policies

Central repository for organization-wide CI/CD governance workflows.

## Required workflows

- `.github/workflows/required-zizmor.yml`
  - Reusable workflow (`workflow_call`) designed to be enforced through GitHub org rulesets.
  - Runs `zizmor` against `.github/workflows` in the caller repository.

## Governance

- Protected by repository ruleset managed through Terraform in `/workspaces/terraform/github`.
- CODEOWNERS requires owner review for all changes.
