# How Kai Works

Understand how Kai finds and verifies security vulnerabilities using AI agents that think like attackers and prove every finding with working exploit code.

## The Core Principle

Traditional security tools tell you what might be wrong. Kai proves what is actually wrong. Every vulnerability Kai reports comes with a working proof-of-concept exploit that demonstrates the security issue is real, eliminating false positives and giving you confidence that reported issues actually need to be fixed.

## The Security Analysis Process

Kai follows a systematic four-stage process to discover, verify, fix, and validate security vulnerabilities.

### Discovery: Finding Potential Vulnerabilities

Kai analyzes your code to understand its structure, purpose, and security properties. Rather than just matching patterns, Kai reasons about what your code is trying to do and what could go wrong:

- **Comprehends business logic** and data flow through your application
- **Identifies security rules** that should hold (invariants)
- **Generates hypotheses** about where these rules might be violated
- **Explores attack vectors** that could exploit potential weaknesses

This stage produces a list of potential security issues with initial risk assessments.

### Verification: Proving Vulnerabilities Are Real

Each potential vulnerability is tested with actual exploit code to confirm it's exploitable. Only vulnerabilities that can be proven with working attacks move forward:

- **Writes attack code** that attempts to exploit the vulnerability
- **Compiles and executes** the exploit in a secure, isolated environment
- **Validates impact** to confirm the attack achieves its intended effect
- **Documents successful exploits** with complete attack traces

This verification process eliminates false positives - if Kai can't prove it, it doesn't report it.

### Fix Generation: Creating Solutions

For each verified vulnerability, Kai analyzes the root cause and generates targeted code changes:

- **Root cause analysis**: Understands why the vulnerability exists
- **Minimal changes**: Creates surgical fixes that modify only what's necessary
- **Impact assessment**: Ensures existing functionality remains intact
- **Clear diffs**: Produces specific before/after code changes

### Validation: Confirming Fixes Work

Proposed fixes are tested to ensure they eliminate vulnerabilities while preserving functionality:

- **Applies fixes** in isolated test environments
- **Replays original exploits** against the fixed version
- **Verifies functionality** to ensure normal operations still work
- **Confirms protection** by ensuring attacks no longer succeed

## The AI Agent Approach

Kai uses specialized AI agents optimized for different types of security analysis rather than relying on pattern matching or single models.

### Agent Capabilities

- **Reason about code purpose** and business logic
- **Adapt dynamically** to find vulnerabilities that don't match known patterns
- **Attempt real attacks** to verify exploitability
- **Understand context** of application-specific security requirements

### Specialized Agent Types

| Agent Type | Focus Area |
|------------|------------|
| **State & Access** | Authentication, authorization, privilege issues |
| **Mathematical** | Numerical vulnerabilities, algorithmic flaws |
| **Adversarial** | Creative attack vectors, abuse scenarios |
| **Exploration** | Systematic testing, edge case discovery |
| **Verification** | Confirming exploitability of findings |
| **Fix** | Root cause analysis, generating solutions |

## Quality Assurance

Kai employs multi-layer verification with checkpoints throughout the analysis process:

- **Confidence scoring** during initial vulnerability identification
- **Isolated execution** for exploit generation and testing
- **Business context** considered in impact assessment
- **Final verification** ensures quality before reporting

### Transparency

Every finding includes complete visibility into how conclusions were reached:

- **Exploit code provided** so you can understand and verify attacks
- **Analysis reasoning explained** in plain language
- **Full documentation** of how Kai reached each conclusion

The combination of AI reasoning and rigorous verification creates a security analysis system that finds real vulnerabilities while minimizing false alarms.