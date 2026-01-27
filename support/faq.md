# Frequently Asked Questions

Get answers to common questions about using Kai, understanding results, and managing security findings.

## Getting Started

### What is Kai and how does it work?

Kai is an AI-powered security analysis platform that finds, proves, and helps fix vulnerabilities in your code. Unlike traditional static analysis tools, Kai creates working exploit code to prove that every reported vulnerability is actually exploitable, eliminating false positives.

Kai uses specialized AI agents that think like attackers to discover security issues, then verifies each finding by generating and testing actual exploit code. Only vulnerabilities that can be proven with working attacks are reported to you.

### Do I need to be a security expert to use Kai?

No. Kai is designed for developers of all security skill levels. Every vulnerability report includes:
- Plain-English explanations of what's wrong and why it matters
- Working exploit code that demonstrates the issue
- Specific fix suggestions with before/after code examples
- Explanations of how the fix addresses the security issue

Many users find Kai educational - learning about security through real examples in their own code.

### What programming languages and frameworks does Kai support?

Kai works with most popular programming languages and frameworks, including:
- **Web applications**: JavaScript/Node.js, Python, Java, PHP, Ruby, C#
- **Mobile**: Swift, Kotlin, React Native, Flutter
- **Smart contracts**: Solidity, Vyper
- **Infrastructure**: Docker, Kubernetes, Terraform

Kai adapts its analysis based on the frameworks and libraries detected in your code, providing context-specific security insights.

### How is Kai different from other security tools?

**Key differences**:
- **Verified vulnerabilities**: Every finding includes working exploit code proving it's real
- **No false positives**: If Kai can't create a working exploit, it doesn't report the vulnerability
- **Business context**: Understands your application's purpose and prioritizes vulnerabilities accordingly
- **AI reasoning**: Goes beyond pattern matching to understand complex business logic vulnerabilities
- **Fix guidance**: Provides specific code changes rather than generic advice

## Using Kai

### How long does a scan take?

Scan times depend on the mode you choose:
- **Baseline mode**: ~2 hours for quick analysis
- **Enhanced mode**: ~4 hours for comprehensive analysis (recommended)
- **Full mode**: ~8 hours for maximum thoroughness

The scan runs in Kai's cloud infrastructure, so you can close VS Code and the scan continues. You'll get a notification when results are ready.

### Can I scan private or proprietary code?

Yes. Kai is designed for proprietary and sensitive codebases:
- **Code privacy**: Your code is analyzed in isolated cloud environments and deleted after analysis
- **No data retention**: Kai doesn't store your source code permanently
- **Secure transmission**: All code uploads are encrypted in transit
- **Access controls**: Only you and your invited team members can see your scan results

### Why does my scan show so many vulnerabilities?

This is normal and actually a good thing. Most codebases have security improvements opportunities that traditional tools miss. Kai finds:
- **Real issues**: Every reported vulnerability includes proof it can be exploited
- **Various severities**: Many findings are improvements rather than critical emergencies
- **Learning opportunities**: Each vulnerability teaches you about secure coding patterns

A typical scan finds 10-25 vulnerabilities across all severity levels, with most being Medium or Low priority improvements.

### Can I use my own API keys to reduce costs?

Yes. You can configure your OpenRouter API key in VS Code settings:
1. Go to VS Code Settings
2. Search for "Kai Agent"
3. Add your OpenRouter API key
4. This uses your LLM credits instead of Kai's, potentially reducing costs

This is optional - Kai works perfectly with its own API keys if you prefer not to manage your own.

## Understanding Results

### How do I know if a vulnerability is actually exploitable?

Every vulnerability Kai reports includes working proof-of-concept exploit code. This means:
- **Verified exploitability**: The attack code compiles and successfully exploits the vulnerability
- **Demonstrated impact**: You can see exactly what an attacker could accomplish
- **No guesswork**: If Kai reports it, it's been proven to work

You can review the exploit code yourself to understand exactly how the attack works.

### What should I fix first?

Prioritize by severity level:
1. **Critical** (🔴): Fix immediately - these can cause severe damage
2. **High** (🟠): Fix within 1-2 weeks - significant security risks
3. **Medium** (🟡): Fix within 1-3 months - important improvements
4. **Low** (🟢): Fix when convenient - good security hygiene

Within each severity level, focus on:
- Public-facing components first
- Components handling sensitive data
- Core business functionality
- Areas with multiple related vulnerabilities

### Are the suggested fixes safe to implement?

Yes. Kai's fix suggestions are:
- **Tested**: Each fix is validated to ensure it prevents the original attack
- **Minimal**: Changes are surgical, modifying only what needs to change
- **Explained**: Every fix includes reasoning about why it solves the security issue
- **Functional**: Fixes preserve existing functionality while eliminating vulnerabilities

However, you should always test fixes in your development environment before deploying to production.

### What if I disagree with a vulnerability assessment?

If you believe a vulnerability is not relevant to your application:
1. **Review the exploit code** to understand the attack scenario
2. **Consider your application context** - some vulnerabilities may not apply to your specific use case
3. **Move to "Won't Do"** in the Kanban workflow if you're accepting the risk
4. **Document your reasoning** for future reference and audit purposes

You can also contact support for clarification on specific vulnerabilities.

## Technical Questions

### Does Kai work with my CI/CD pipeline?

Currently, Kai primarily works through the VS Code extension for scan initiation. However:
- **Scan results** are accessible through the web dashboard
- **API access** is available for enterprise users
- **Webhooks** can notify external systems about scan completion
- **Future integration** with CI/CD systems is planned

For now, most teams integrate Kai by running scans before major releases and including security fixes in their development workflow.

### Can I run Kai on-premises?

Kai currently operates as a cloud service for optimal performance and security:
- **Cloud benefits**: Access to latest AI models, scalable compute resources, automatic updates
- **Security**: Isolated environments ensure code privacy and security
- **Maintenance**: No infrastructure to manage or maintain

Enterprise on-premises options may be available for specific requirements - contact sales for discussion.

### What data does Kai collect and store?

Kai collects minimal data necessary for security analysis:
- **During analysis**: Source code is temporarily stored in secure, isolated environments
- **After analysis**: Code is deleted; only vulnerability findings and metadata are retained
- **Permanently stored**: Vulnerability reports, scan history, team collaboration data
- **Never stored**: Full source code, credentials, or sensitive business data

All data handling complies with GDPR and enterprise security requirements.

### How accurate are Kai's vulnerability findings?

Kai has extremely low false positive rates because:
- **Verification requirement**: Vulnerabilities must be proven with working exploits
- **Business context**: Analysis considers your specific application architecture
- **Continuous improvement**: AI models learn from feedback and new security research

Typical accuracy rates:
- **False positives**: Less than 5% (industry average is 30-50% for static analysis)
- **Verification rate**: 85-95% of reported vulnerabilities include working exploits
- **Severity accuracy**: High correlation between reported severity and actual business impact

## Billing and Pricing

### How does Kai pricing work?

Kai uses a token-based pricing model:
- **Pay per analysis**: You're charged based on the AI inference used during scans
- **Transparent costs**: See usage and costs for each scan
- **No monthly minimums**: Pay only when you scan
- **Custom API keys**: Use your own OpenRouter credits to potentially reduce costs

Contact sales for detailed pricing information and volume discounts.

### Can I get a cost estimate before scanning?

Approximate cost by scan mode:
- **Baseline**: 30-50% of Full mode costs
- **Enhanced**: 70-80% of Full mode costs
- **Full**: Maximum analysis depth and cost

Actual costs depend on:
- Codebase size and complexity
- Number of vulnerabilities found
- Analysis depth required
- Language and framework specifics

You can monitor costs in real-time during scans and set up usage alerts.

## Team and Collaboration

### How do I add team members to my workspace?

1. Go to your workspace in the web dashboard
2. Navigate to Settings → Team
3. Click "Invite Members"
4. Enter email addresses or GitHub usernames
5. Select appropriate roles (Owner, Admin, Member, Viewer)
6. Send invitations

Team members will receive email invitations to join your workspace.

### What's the difference between workspace roles?

**Owner**:
- Full control over workspace settings and billing
- Can add/remove members and change roles
- Can delete workspace or transfer ownership

**Admin**:
- Can manage team members and workspace settings
- Access to all projects and vulnerability data
- Cannot change billing or delete workspace

**Member**:
- Can access assigned projects and participate in vulnerability management
- Can comment and collaborate on findings
- Cannot manage workspace settings or team membership

**Viewer**:
- Read-only access to assigned projects
- Can view vulnerabilities and reports
- Cannot modify vulnerability status or settings

### Can I integrate Kai with Slack or other tools?

Yes, Kai offers several integration options:
- **Slack/Teams**: Notifications for new critical vulnerabilities and scan completions
- **Email**: Digest reports and alert notifications
- **Webhooks**: Custom integrations with your existing tools
- **API access**: For building custom integrations and automations

Configure integrations through the workspace settings in the web dashboard.

## Troubleshooting

### My scan is taking longer than expected

Long scan times can be caused by:
- **Large codebase**: More code requires more analysis time
- **Complex logic**: Sophisticated business logic takes longer to analyze
- **High workload**: Peak usage times may increase queue times

**What to do**:
- Wait at least 50% longer than estimated time before investigating
- Check the Executions panel for status updates
- Contact support if scan exceeds 24 hours

### I can't see my scan results

**Common solutions**:
1. **Refresh the results panel** using the refresh button
2. **Check internet connectivity** for loading scan results
3. **Verify scan completion** in the Executions panel
4. **Restart VS Code** to refresh the extension

If problems persist, contact support through the web dashboard for assistance.

### The extension isn't working properly

**Quick fixes**:
1. **Restart VS Code** completely
2. **Check extension version** and update if needed
3. **Sign out and sign back in** to refresh authentication
4. **Check internet connectivity** for cloud services

Contact support through the web dashboard for comprehensive assistance.

## Getting Help

### Where can I get more help?

**Documentation**:
- **[VS Code Extension Guide](../vs-code-extension/installation)**: Complete guide to using the extension
- **[Web Dashboard Guide](../web-dashboard)**: Team collaboration and management features

**Support channels**:
- **GitHub Issues**: [Report bugs and request features](https://github.com/firstbatchxyz/kai-vscode-extension/issues)
- **Email Support**: Contact through the web dashboard
- **Community**: VS Code Marketplace Q&A section

### How do I report a bug or request a feature?

1. **Check existing issues** on GitHub to avoid duplicates
2. **Gather information**: VS Code version, extension version, error messages
3. **Create detailed issue** with steps to reproduce the problem
4. **Include screenshots** if relevant for UI issues

For security vulnerabilities in Kai itself, please report privately through the contact form rather than public GitHub issues.

### Can I get training or consulting help?

Kai is designed to be self-service, but additional support options are available:
- **Documentation**: Comprehensive guides for all features
- **Best practices**: Security-focused development guidance
- **Enterprise support**: Dedicated support for enterprise users
- **Consulting services**: Custom security program development (contact sales)

Most users find the built-in documentation and explanations in vulnerability reports sufficient for learning and using Kai effectively.