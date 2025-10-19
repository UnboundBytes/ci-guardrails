# CI Guardrails Changes

## v1.0.0 - Initial Release
**Date**: 2025-10-19  
**SHA**: `[TO_BE_SET_ON_COMMIT]`

### Features
- **Zero-Knowledge Compliance Check**: Validates no plaintext storage, server-side decryption, or encryption bypass
- **Tenant Isolation Check**: Ensures all database queries include tenant_id
- **Security Scan**: Dependency audit and secret detection
- **Code Quality**: Linting and formatting checks
- **Test Coverage**: Unit and integration test execution
- **Privacy Acceptance Tests**: E2E tests with Playwright (optional)
- **Build-Test-Deploy**: Complete CI/CD pipeline with Cloudflare deployment

### Workflows
- `guardrails.yml`: Security, compliance, and quality enforcement
- `build-test-deploy.yml`: Build, test, and deploy pipeline

### Security
- All changes require CODEOWNERS approval
- No secrets stored in repository
- Immutable workflow design
- Pinned by commit SHA only

### Usage
```yaml
jobs:
  guardrails:
    uses: unboundbytes/ci-guardrails/.github/workflows/guardrails.yml@<sha>
    secrets: inherit
```
