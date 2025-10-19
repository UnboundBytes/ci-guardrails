# UnboundBytes CI Guardrails

External, immutable CI/CD guardrails repository for UnboundBytes V2 platform.

## Purpose

This repository contains **pinned, immutable** reusable workflows that enforce:
- Zero-knowledge compliance
- Tenant isolation validation
- Security scanning
- Code quality gates
- Privacy acceptance tests

## Architecture

### Immutable Workflows
- Workflows are pinned by commit SHA
- No inline deployment jobs in product repos
- All enforcement happens here
- Product repos only call these workflows

### Required Workflows
1. **`guardrails.yml`** - Security, compliance, and quality checks
2. **`build-test-deploy.yml`** - Build, test, and deploy workflow

## Usage

Product repositories call these workflows via `workflow_call`:

```yaml
jobs:
  guardrails:
    uses: unboundbytes/ci-guardrails/.github/workflows/guardrails.yml@<pinned-sha>
    secrets: inherit
```

## Security

- **CODEOWNERS**: All changes require approval
- **Branch Protection**: Main branch protected
- **Signed Commits**: All commits must be signed
- **No Secrets**: No secrets stored in this repo

## License

UNLICENSED - UnboundBytes Proprietary
