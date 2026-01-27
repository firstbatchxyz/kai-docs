# What is Kai?

**AI security agents for your entire codebase**

Kai hardens AI-generated and rapidly written code by finding, proving, and patching real vulnerabilities before they reach production. Turn vibe-coded prototypes into production-grade security.

## Why Kai?

Traditional security tools leave you guessing. Static analysis tools flood you with false positives and miss complex vulnerabilities. Manual audits are thorough but expensive and slow. Kai solves both problems with a fundamentally different approach:

**Every vulnerability Kai reports comes with a proof-of-concept exploit that actually works.**

## What Makes Kai Different

### 🎯 **Orchestrated Intelligence for Security**

Instead of relying on a single AI model, Kai orchestrates specialized agents across multiple frontier models. Each agent is optimized for different aspects of security analysis: discovery, verification, or patching. You automatically get the right capability at the right cost for every vulnerability.

### ✅ **Verified by Execution, Not Pattern Matching**

Every exploit is proven by execution. Every fix is validated the same way. If Kai can't reproduce an issue or confirm a patch works, it marks the result as unverified. Kai never claims a win it can't prove, eliminating the false positive problem that plagues other security tools.

### ⚡ **Parallel Agents Turn Days into Hours**

A single Kai runtime launches dozens of agents in parallel, scanning code, generating exploits, and iterating on fixes. What used to take a security team 36 hours of focused work now completes in about 2-3 hours end to end.

### ☁️ **Cloud Runtime, IDE Optional**

Kai runs in isolated cloud sandboxes, so you don't need powerful hardware or to keep your device open for hours. After initialization, Kai clones your codebase to the cloud and you can shut down your computer while agents run the analysis. Progress, exploit traces, and suggested code diffs are all available in the web dashboard.

### 📊 **Watch Security Evolve in Real Time**

Watch vulnerabilities move from "found" to "reproduced" to "patched" in real time. See how your codebase's security posture improves as Kai runs.

## Who Should Use Kai?

### Developers
- **Building quickly**: Whether you're prototyping with AI assistance or racing to meet deadlines, Kai ensures your code is secure before it ships
- **Working with legacy code**: Kai discovers vulnerabilities in existing codebases that have never been audited
- **Learning security**: Every finding comes with detailed explanations and suggested fixes, helping you understand security patterns

### Security Teams
- **Scaling security reviews**: Analyze multiple projects in parallel without expanding headcount
- **Reducing false positives**: Focus on real, exploitable vulnerabilities instead of chasing static analysis alerts
- **Validating fixes**: Confirm that patches actually solve the underlying security issues

### Team Leads
- **Managing risk**: Get visibility into your codebase's security posture with quantified risk metrics
- **Accelerating delivery**: Security analysis no longer becomes a bottleneck in your development process
- **Improving code quality**: Teams learn from Kai's findings and write more secure code over time

## How It Works (Simple Version)

1. **Scan**: Kai's agents analyze your codebase to understand its structure and purpose
2. **Find**: Specialized agents search for different types of vulnerabilities using advanced reasoning
3. **Prove**: Each potential vulnerability is tested with a working exploit to confirm it's real
4. **Fix**: Verified vulnerabilities get targeted patches that are tested to ensure they work
5. **Review**: You get detailed results with exploit code, fix suggestions, and clear explanations

## Ready to Get Started?

Install the VS Code extension and run your first scan in under 5 minutes. No configuration required - just select your files and go.

[Get Started →](getting-started)