# Security Scanning

This repository is configured with automated security scanning tools that run on every push and pull request to any branch.

## Scanning Tools

### 🔍 KICS (Infrastructure as Code Security)
- **Purpose**: Scans Infrastructure as Code files (Terraform, CloudFormation, Kubernetes, etc.)
- **Triggers**: Push to any branch, PR to any branch, Weekly schedule (Mondays 2 AM)
- **Results**: Available in GitHub Security tab and as workflow artifacts

### 🛡️ Checkmarx SAST (Static Application Security Testing)
- **Purpose**: Scans source code for security vulnerabilities
- **Triggers**: Push to any branch, PR to any branch, Weekly schedule (Mondays 3 AM)
- **Results**: Available in GitHub Security tab and as workflow artifacts

### 📦 Black Duck SCA (Software Composition Analysis)
- **Purpose**: Scans dependencies for known vulnerabilities and license issues
- **Triggers**: Push to any branch, PR to any branch, Weekly schedule (Mondays 4 AM)
- **Results**: Available as workflow artifacts

## Required Secrets

This repository is configured to use organization-level secrets for security scanning. No additional configuration is required at the repository level.

### Checkmarx Secrets (Organization-Level)
- CHECKMARX_URL: Your Checkmarx server URL
- CHECKMARX_USERNAME: Checkmarx username
- CHECKMARX_PASSWORD: Checkmarx password
- CHECKMARX_CLIENT_SECRET: Checkmarx client secret

### Black Duck Secrets (Organization-Level)
- BLACKDUCK_URL: Your Black Duck server URL
- BLACKDUCK_TOKEN: Black Duck API token

## Viewing Results

1. **GitHub Security Tab**: SARIF results are automatically uploaded
2. **Workflow Artifacts**: Detailed reports available as downloadable artifacts
3. **Pull Request Comments**: Some tools may comment directly on PRs

## Customization

You can customize the scanning behavior by modifying the workflow files in `.github/workflows/`:
- `kics-scan.yml`
- `checkmarx-scan.yml`
- `blackduck-scan.yml`

## Support

For questions about security scanning configuration, contact your DevSecOps team.