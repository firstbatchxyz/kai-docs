# Kai Security

**AI security agents that find, prove, and fix real vulnerabilities in your code.**

Kai Security uses specialized AI agents to discover security issues in your codebase, verify each finding by generating and testing actual exploit code, and suggest targeted fixes. Unlike traditional static analysis tools, Kai only reports vulnerabilities it can prove with a working proof-of-concept. No false positives, no guesswork.

## How It Works

1. **Scan**: Agents analyze your codebase to understand its structure, entry points, and business logic
2. **Find**: Specialized agents search for different types of vulnerabilities using advanced reasoning
3. **Prove**: Each potential vulnerability is tested with working exploit code to confirm it's real
4. **Fix**: Verified vulnerabilities get targeted patches, tested to ensure they work
5. **Review**: You get detailed results with exploit code, fix suggestions, and clear explanations

## Key Capabilities

- **Verified vulnerabilities**: Every finding includes working exploit code proving it's real
- **Zero false positives**: If Kai can't create a working exploit, it doesn't report the vulnerability
- **Business context**: Understands your application's purpose and prioritizes accordingly
- **Fix guidance**: Provides specific code changes rather than generic advice
- **Parallel agents**: Dozens of agents work simultaneously, completing in hours what takes teams days

## Where to Use Kai Security

Kai Security is available across all Kai surfaces:

- **[VS Code Extension](../platform/vs-code-extension)**: Scan directly from your IDE, review findings inline, view fix diffs, and create issues from exploits
- **[Web Dashboard](../platform/web-dashboard)**: Manage vulnerabilities with the Kanban board, collaborate with your team, generate audit reports, and track analytics
- **[MCP Server](../platform/mcp-server)**: Run scans, review exploits, and create issues programmatically from any MCP-compatible client

## Next Steps

- [Running Your First Scan](first-scan) - Complete walkthrough of the scanning process
- [Understanding Results](understanding-results) - Deep dive into vulnerability reports
- [Managing Vulnerabilities](managing-vulnerabilities) - Master the Kanban workflow
- [Scan Modes](scan-modes) - Choose the right analysis depth
- [Security Reports](reports) - Generate audit reports from completed scans
