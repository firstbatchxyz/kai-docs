# Security & Privacy

Understanding how Kai handles your code and data is essential for security-conscious teams. This page explains exactly what happens to your code during analysis and how your data is protected.

## What Gets Uploaded

When you run a scan, Kai uploads only the files you explicitly select in the file tree:

- **Selected files only**: You control exactly which files are included
- **No git history**: Only current file contents, not repository history
- **Excludable content**: Use `.kaiignore` to prevent sensitive files from being selectable
- **Size limit**: Maximum 50MB per scan upload

### What's Automatically Excluded

Kai automatically excludes common non-code files:
- `node_modules/`, `vendor/`, and dependency directories
- Build outputs (`dist/`, `build/`, `.next/`)
- IDE and editor configurations
- Log files and temporary files

### What You Should Exclude

For additional security, consider excluding:
- Environment files (`.env`, `.env.local`)
- Credential files and API keys
- Database dumps and test fixtures with real data
- Internal documentation with sensitive information

## Data Handling

### During Analysis

- **Isolated environments**: Your code runs in dedicated, isolated cloud containers
- **No cross-contamination**: Each scan uses a fresh environment
- **Encrypted transmission**: All uploads use TLS encryption
- **Temporary storage**: Code exists only for the duration of analysis

### After Analysis

- **Code deletion**: Source code is deleted immediately after analysis completes
- **Results retained**: Only vulnerability findings and metadata are kept
- **No code storage**: Kai never permanently stores your source code
- **Audit trail**: Scan history shows what was analyzed, not the code itself

### What's Stored Permanently

- Vulnerability reports and findings
- Exploit descriptions (not your actual code)
- Fix suggestions and recommendations
- Scan metadata (timestamps, file counts, settings)
- Team collaboration data (comments, assignments, status changes)

## Access Control

### Authentication

- **GitHub OAuth**: Secure authentication through your existing GitHub account
- **Minimal permissions**: Kai requests only basic profile information
- **No repository access**: OAuth does not grant access to your GitHub repositories
- **Token security**: Authentication tokens are encrypted and stored securely

### Team Permissions

Control who sees your security findings:

| Role | View Results | Run Scans | Manage Settings | Invite Members |
|------|-------------|-----------|-----------------|----------------|
| **Admin** | Yes | Yes | Yes | Yes |
| **Member** | Yes | Yes | No | No |
| **Viewer** | Yes | No | No | No |

### Workspace Isolation

- Each workspace is completely isolated
- Team members only see workspaces they're invited to
- Vulnerability data never crosses workspace boundaries

## Exploit Code Safety

Kai generates proof-of-concept exploit code to verify vulnerabilities. This code is:

- **For verification only**: Demonstrates that vulnerabilities are real
- **Sandboxed execution**: Runs only in Kai's isolated analysis environments
- **Not executable locally**: Designed for demonstration, not attack use
- **Educational**: Helps you understand exactly how vulnerabilities work

### Safe Handling Guidelines

When reviewing exploit code:
- Never run exploit code against production systems
- Use isolated development environments for testing
- Understand the exploit before implementing fixes
- Keep exploit details confidential within your team

## Compliance

Kai's data handling is designed to support common compliance requirements:

- **GDPR**: Data minimization, right to deletion, secure processing
- **SOC 2**: Security controls, access management, audit trails
- **Enterprise security**: Encryption, isolation, access controls

For specific compliance documentation or security questionnaires, contact our team.

## Network Requirements

For organizations with strict network policies, Kai requires access to:

- `kai.dria.co` - Web dashboard
- `api.kai.dria.co` - API services
- `github.com` - Authentication only
- VS Code Marketplace - Extension updates

## Questions?

For security-specific questions or to request additional documentation:
- **Email**: kai@dria.co
- **Enterprise inquiries**: Contact sales for detailed security documentation
