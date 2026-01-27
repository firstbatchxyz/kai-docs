# How Kai Works

Understand how Kai finds and verifies security vulnerabilities using AI agents that think like attackers and prove every finding with working exploit code.

## The Core Principle

Traditional security tools tell you what might be wrong. Kai proves what is actually wrong. Every vulnerability Kai reports comes with a working proof-of-concept exploit that demonstrates the security issue is real, eliminating false positives and giving you confidence that reported issues actually need to be fixed.

## The Security Analysis Process

Kai follows a systematic four-stage process to discover, verify, fix, and validate security vulnerabilities.

### Discovery: Finding Potential Vulnerabilities

Kai analyzes your code to understand its structure, purpose, and security properties. Rather than just matching patterns, Kai reasons about what your code is trying to do and what could go wrong. It comprehends the business logic and data flow, identifies what security rules should hold, generates hypotheses about where these rules might be violated, and explores different attack vectors that could exploit potential weaknesses.

This stage produces a list of potential security issues with initial risk assessments before verification begins.

### Verification: Proving Vulnerabilities Are Real

Each potential vulnerability is tested with actual exploit code to confirm it's exploitable. Only vulnerabilities that can be proven with working attacks move forward. Kai writes actual attack code that attempts to exploit potential vulnerabilities, compiles and executes the exploit in a secure environment, validates that the attack achieves its intended impact, and documents successful exploits with complete attack traces.

This verification process eliminates false positives by ensuring only genuinely exploitable vulnerabilities are reported.

### Fix Generation: Creating Solutions

For each verified vulnerability, Kai analyzes the root cause and generates targeted code changes that address the security issue without breaking functionality. It understands why vulnerabilities exist and what needs to change, creates minimal fixes that address security issues surgically, assesses the impact to ensure existing functionality remains intact, and produces specific code changes with before/after diffs.

### Validation: Confirming Fixes Work

Proposed fixes are tested to ensure they actually eliminate vulnerabilities while preserving intended functionality. Kai applies suggested code changes in test environments, replays original exploits against fixed versions, ensures normal operations continue working correctly, and confirms attacks no longer succeed.

## The AI Agent Approach

Kai uses specialized AI agents optimized for different types of security analysis rather than relying on pattern matching or single models. These agents can reason about code purpose and business logic, adapt to find vulnerabilities that don't match known patterns, actually attempt attacks to verify exploitability, and understand application-specific security requirements.

State and access control agents focus on authentication, authorization, and privilege issues. Mathematical and logic agents specialize in numerical vulnerabilities and algorithmic flaws. Adversarial agents think like attackers looking for creative ways to abuse applications. Exploration agents perform systematic testing and edge case discovery. Verification agents ensure reported vulnerabilities are actually exploitable. Fix agents analyze root causes and generate targeted solutions.

## Quality Assurance

Kai employs multi-layer verification with checkpoints throughout the analysis process. Initial vulnerability identification includes confidence scoring, exploit generation and testing occurs in isolated environments, impact assessment considers business context, and final verification ensures quality before reporting.

This process provides complete visibility into how conclusions are reached, with every step documented and explained. Exploit code is provided so you can understand and verify attacks yourself, analysis reasoning is explained clearly, and you can see exactly how Kai reached its conclusions.

Understanding how Kai works helps you trust its findings and use them effectively. The combination of AI reasoning and rigorous verification creates a security analysis system that finds real vulnerabilities while minimizing false alarms.