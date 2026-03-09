# Severity Levels

Understand how Kai determines vulnerability severity through actual exploit testing and learn to prioritize security fixes based on real-world exploitability.

## Verification-Based Severity

Unlike traditional security tools that assign severity based on theoretical impact, Kai determines severity through actual exploitability testing and proven impact demonstration. Every vulnerability is tested with working exploit code to verify it's actually exploitable before being assigned a severity level.

Kai considers exploitability verification (does the exploit actually work?), business context (what role does this component play?), attack complexity (how difficult is this to exploit?), and real-world impact (what would actually happen if exploited?).

## The Four Severity Levels

### 🔴 Critical Severity
**Immediate, severe security risks requiring urgent attention.** Remote code execution, complete authentication bypass, administrative privilege escalation, mass data extraction, or financial system manipulation. Usually exploitable remotely with minimal technical skill required.

**Response**: Fix within 24-72 hours, consider taking systems offline until fixed.

### 🟠 High Severity
**Significant vulnerabilities with clear attack paths and substantial impact.** Authentication bypass requiring specific conditions, privilege escalation within application boundaries, sensitive data access for unauthorized users, or critical business function bypass.

**Response**: Fix within 1-2 weeks, prioritize in current development cycle.

### 🟡 Medium Severity
**Important security issues that should be addressed but don't pose immediate critical risk.** Information disclosure vulnerabilities, denial of service attacks, input validation bypasses with limited impact, or logic flaws with moderate business impact.

**Response**: Address within 1-3 months, include in regular development planning.

### 🟢 Low Severity
**Security improvements and best practices that strengthen overall security posture.** Missing security headers, weak password policies, information leakage in debug output, or insecure default configurations with limited exposure.

**Response**: Address when convenient, include in regular security maintenance.

## Severity Factors

Kai weighs exploitability (40%), impact (35%), attack vector (15%), and business context (10%) when determining severity. Environmental factors like public-facing exposure, financial transaction handling, or critical business functions can increase severity, while internal-only systems or strong compensating controls may decrease it.

## Response Planning

Always prioritize by severity first: address all Critical vulnerabilities before moving to High, balance High severity fixes with development work, include Medium fixes in regular cycles, and handle Low severity issues during maintenance periods. Consider business context when prioritizing within severity levels.

Understanding severity levels helps you make informed decisions about security investments and ensures your team focuses on vulnerabilities that pose the greatest actual risk to your application and business.