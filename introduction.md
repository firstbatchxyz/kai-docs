# What is Kai?

**AI agents for security and code optimization.**

Kai is a platform with two core products: **Kai Security** finds, proves, and fixes real vulnerabilities in your code. **Kai Evolve** optimizes your code through autonomous evolutionary agents. Both are available through the web dashboard, VS Code extension, and MCP server.

## Kai Security

Traditional security tools flood you with false positives and miss complex vulnerabilities. Kai Security solves this with a fundamentally different approach: every vulnerability it reports comes with a proof-of-concept exploit that actually works.

Instead of relying on pattern matching, Kai orchestrates specialized agents across multiple frontier models. Each agent handles a different aspect of security analysis: discovery, verification, or patching. If Kai can't reproduce an issue or confirm a patch works, it marks the result as unverified. No guesswork, no noise.

A single Kai runtime launches dozens of agents in parallel, completing in hours what takes security teams days of focused work.

[Get started with Kai Security →](kai-security/overview)

## Kai Evolve

Kai Evolve pairs the creative problem-solving capabilities of frontier LLMs with automated evaluators, using an evolutionary framework to iteratively improve upon the most promising solutions. Describe your optimization goal, and Evolve analyzes your code, generates evaluators, and runs hundreds of iterations to discover improvements that often surpass what experienced engineers find manually.

The approach is general-purpose. Any problem whose solution can be expressed as code and automatically evaluated is a candidate for evolution: GPU kernels, sorting algorithms, matrix operations, smart contracts, graph analytics, scientific computing, and more.

[Get started with Kai Evolve →](kai-evolve/overview)

## The Platform

Both products share a common platform:

- **[Web Dashboard](platform/web-dashboard)**: Manage workspaces, collaborate with your team, track analytics, and run both security scans and evolutions from any browser
- **[VS Code Extension](platform/vs-code-extension)**: Scan code, review findings, view fix diffs, and create issues directly from your IDE
- **[MCP Server](platform/mcp-server)**: Connect Claude Desktop, Cursor, VS Code Copilot, or any MCP-compatible client to access all of Kai's capabilities programmatically
- **[Integrations](platform/integrations)**: Push findings to GitHub or Linear for issue tracking

## Ready to Get Started?

Install the VS Code extension and run your first security scan in under 5 minutes. Or navigate to the web dashboard to start an evolution.

[Get Started →](getting-started)
