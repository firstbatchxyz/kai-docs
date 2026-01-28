# Kai Documentation Review: Current Content vs Recommendations

## *Editable review document (English \+ Technical feedback)*

Site: https://dria-5b806eb3.mintlify.app/  
Date: January 28, 2026

# **Highest-impact fixes (prioritized)**

1. Fix broken outbound links

* “Report bugs / GitHub Issues” link resolves to a 404 page — update to the correct repo/issues URL.  
* Footer “X” link resolves to a 404 page — update to the correct handle.  
* VS Code Marketplace listing repeats the broken GitHub links (issues \+ LICENSE).

2. Resolve feature-status inconsistencies

* Docs label OpenRouter API key \+ Default Scan Mode as “Coming Soon”, but troubleshooting and Marketplace content imply these settings exist now. Align the truth everywhere.

3. Align CI/CD messaging

* One page suggests Baseline is good for CI integration, while FAQ says CI/CD integration is planned. Either document the current CI path (CLI/API/webhooks) or remove CI claims.

4. Normalize workspace roles and permissions

* Workspaces/Team Collaboration describe Viewer/Member/Admin, while FAQ introduces Owner. Choose a canonical RBAC model and reflect it consistently.

5. Clarify what is uploaded to the cloud

* Several pages imply a full codebase clone to the cloud, while others emphasize selecting a subset of files. Security-conscious teams need a precise, consistent explanation.

# **Site-wide notes**

## **English (writing)**

* Standardize heading style (Title Case vs sentence case) and decide on emoji usage (consistent everywhere or limited to marketing pages).  
* Reduce repeated marketing phrases across multiple pages; keep them in the Introduction and use task-focused language elsewhere.  
* Convert run-on paragraphs (notably in Security Analysis and Fix suggestions) into scannable bullet lists.

## **Technical (product / dev-docs)**

* Create a dedicated Security & Privacy page (upload scope, retention, isolation/sandbox, secrets handling, auth scopes). Link it from Introduction, Getting Started, FAQ, and Troubleshooting.  
* Adopt a single convention for feature status (Available / Beta / Coming soon) to prevent contradictions.  
* Add automated link checking to docs CI to prevent outbound 404 regressions.

# **Page-by-page feedback**

## **Home**

### **Index (Home)**

Path: /

Current content (as written now):

* Minimal landing page with a single CTA: “Get Started →”.

Recommendations \- English:

* Add 1–2 lines answering: Who is this for? What do I do next? The current page is very sparse.  
* Avoid repeating the product name in multiple places (e.g., header \+ H1) if it feels redundant.

Recommendations \- Technical:

* Add quick links to the most common first actions: Install extension, Run first scan, Privacy & security.

## 

## 

## 

## 

## **Get Started**

### **Introduction**

Path: /get-started/introduction

Current content (as written now):

* Positioning and differentiators (execution-verified exploits, parallel agents).  
* High-level workflow: Scan → Find → Prove → Fix → Review.  
* Primary audiences and use cases.

Recommendations \- English:

* Tighten the opening sentences; a line break or punctuation would improve readability.  
* Consider replacing or defining informal phrases like “vibe-coded prototypes” for enterprise readers.  
* If you keep emoji in headings, make that a consistent site-wide choice.

Recommendations \- Technical:

* Clarify precisely what “clones your codebase to the cloud” means (full repo vs selected files; whether git history is included).  
* Define what “unverified” means in terms of failure modes (e.g., missing deps, exploit didn’t execute, environment mismatch) and link to a security/privacy page.

### **Getting started**

Path: /get-started/getting-started

Current content (as written now):

* Prerequisites and step-by-step setup in VS Code through first scan and review workflow.  
* Notes about exclusions, expected results, and getting help.

Recommendations \- English:

* Remove duplicated text in the “Get Help” section (FAQ line appears twice).  
* Convert “What to Expect…” into bullets with bold labels (Timeline / Results / Learning / False positives).  
* Replace “go offline” with clearer wording: analysis continues in the cloud; you can close VS Code.

Recommendations \- Technical:

* Be explicit about how git history is used and whether it is uploaded.  
* Replace vague exclusion claims with an exact default exclusion list/patterns and how to override safely.  
* Mention the 50MB file limit here so users learn it early.  
* Fix “Coming Soon” contradictions around OpenRouter API key and Default Scan Mode.

## **Using Kai**

### **First scan**

Path: /using-kai/first-scan

Current content (as written now):

* Walkthrough of selecting files, choosing scan mode, monitoring progress, and reviewing first results.  
* Explains what happens behind the scenes and common first-scan issues.

Recommendations \- English:

* Break dense step text into bullets (panel list: Account / Files / Executions / Scan Results).  
* Avoid repeating specific result-number ranges across pages; if you keep numbers, qualify with “depends on repo size and selection.”

Recommendations \- Technical:

* Clarify how “auto-excluded” gray files relate to tests and other includable content.  
* Add a short note on build/dependency requirements and how they affect verification (verified vs unverified).  
* Document cancellation and re-run behavior (and how data is handled when canceled).

### **Understanding results**

Path: /using-kai/understanding-results

Current content (as written now):

* Where to view results, what each severity means, and what a vulnerability report contains.  
* Explains verified vs unverified and common vulnerability categories.

Recommendations \- English:

* Convert the “Anatomy” section into a clean bullet list for readability.  
* Label any example vulnerability text as “Example (fictional)” to avoid confusion.  
* Link to the deeper Severity levels page from the severity overview.

Recommendations \- Technical:

* Tighten the promise: Verified findings have executed PoCs; unverified may include attempted PoCs \+ failure context.  
* Add guidance for safe reproduction of PoCs (isolated environments; do not run in production).

### **Managing vulnerabilities**

Path: /using-kai/managing-vulnerabilities

Current content (as written now):

* Kanban workflow stages and what each column means (Awaiting Verification → … → Won’t Do).

Recommendations \- English:

* Add a one-sentence mental model: which status changes are system-driven vs user-driven.  
* Standardize emoji usage in column names (consistent everywhere or nowhere).

Recommendations \- Technical:

* Clarify permissions: who can move cards and what transitions are allowed.  
* Explain whether moving to Fixed triggers automatic revalidation, and whether there’s an audit trail.

### **Scan modes**

Path: /using-kai/scan-modes

Current content (as written now):

* Baseline vs Enhanced vs Full mode comparisons (time, depth, use cases) and selection guidance.

Recommendations \- English:

* Ensure the modes comparison renders as a clean table (spacing/line-wrapping issues).  
* Standardize naming (Full mode vs Full Mode \- Deep Analysis).

Recommendations \- Technical:

* Align CI claims: either document an actual CI workflow or remove “CI integration” language.  
* Add cost guidance (qualitative is fine) and clarify what differs across modes (depth vs verification standards).

## **VS Code Extension**

### **Installation**

Path: /vscode-extension/installation

Current content (as written now):

* Install methods, sign-in (GitHub OAuth), settings, exclusions, updating/uninstalling, next steps.

Recommendations \- English:

* Reformat “Problem / Solution” blocks with consistent line breaks and bullets.  
* Ensure git commands render cleanly as fenced code blocks.

Recommendations \- Technical:

* Fix contradictions: settings marked “Coming Soon” here appear active elsewhere (Troubleshooting/Marketplace).  
* Make auth scope language precise (what is requested, stored, and not accessed).  
* Provide an exact default exclusion list/patterns and safe override guidance.

### **Troubleshooting**

Path: /vscode-extension/troubleshooting

Current content (as written now):

* Troubleshooting for install/auth/scan/results/performance, settings, OpenRouter keys, debugging/logs, and how to get help.

Recommendations \- English:

* Add a short decision tree at the top (Can’t sign in? Scan stuck? No results?).  
* Keep scan timing guidance consistent with Scan modes and avoid sounding like a guarantee.

Recommendations \- Technical:

* Fix broken “Report bugs” (GitHub Issues) link.  
* If settings keys are real (openRouterApiKey/defaultScanMode), ensure Installation does not label them “Coming Soon”.  
* List any required domains/CDNs for uploads/webviews if users are behind strict proxies.

## **Web Dashboard**

### **Overview**

Path: /web-dashboard/overview

Current content (as written now):

* What the dashboard adds vs the extension; access steps; core features; sync claims.

Recommendations \- English:

* Clarify “results appear automatically” as “after your first scan results appear…”.  
* Ensure the dashboard vs extension table renders well on mobile.

Recommendations \- Technical:

* Define what sync is bidirectional for (status, comments, assignments, etc.) and whether it’s realtime or periodic.

### **Workspaces**

Path: /web-dashboard/workspaces

Current content (as written now):

* What workspaces are; creating them; adding repos; settings; best practices; access control.

Recommendations \- English:

* Make “By Team / By Product / By Environment” a clean nested list for better scanning.

Recommendations \- Technical:

* Clarify current repo ingestion model vs “GitHub Import (coming soon)” to avoid confusion.  
* Normalize RBAC roles (Viewer/Member/Admin vs Owner) across all pages.  
* Explain where repository settings live in the UI and how to edit them.

### **Team collaboration**

Path: /web-dashboard/team-collaboration

Current content (as written now):

* Inviting members, roles, assignments, comments/@mentions, notifications, best practices.

Recommendations \- English:

* Standardize heading capitalization (e.g., “Team collaboration” vs “Team Collaboration”).  
* Add a short note on where workspace settings live in the UI.

Recommendations \- Technical:

* Align invite mechanism: email-only vs email/GitHub usernames (FAQ vs this page).  
* Document notification channels (in-app vs email) and clarify Slack/Teams integration status.

### **Vulnerability management**

Path: /web-dashboard/vulnerability-management

Current content (as written now):

* Kanban workflow, filters, bulk operations, vulnerability details, exports, integrations (coming soon).

Recommendations \- English:

* Ensure workflow tables render cleanly; extracted text suggests formatting issues.  
* If you reference a walkthrough video, verify it is actually embedded and accessible.

Recommendations \- Technical:

* Clarify who can view exploit code (role-based access) and provide safe handling guidance.  
* Add explicit steps for exporting (where to click and what options exist).  
* Align integration status language with other pages (Jira/GitHub issues/API/webhooks).

### **Analytics**

Path: /web-dashboard/analytics

Current content (as written now):

* Metrics, charts, health score ranges, reporting use cases and cadences.

Recommendations \- English:

* Avoid relying only on color words (Red/Orange/Yellow/Green); add labels for accessibility.  
* Add a light disclaimer that thresholds vary by org.

Recommendations \- Technical:

* Define how health score is calculated (formula or “heuristic factors”).  
* Define MTTR boundaries (start/end timestamps) to make metrics auditable.

## **Security Analysis**

### **How it works**

Path: /security-analysis/how-it-works

Current content (as written now):

* Four-stage pipeline (discovery/verification/fix/validation), agent types, and QA approach.

Recommendations \- English:

* Break long paragraphs into bullets for discovery and verification stages.  
* Consider a small table for agent types (Agent → Focus → Example findings).

Recommendations \- Technical:

* Add details about sandbox boundaries for exploit execution (network access, secrets, filesystem).  
* Clarify validation: rerun exploit only vs running tests, and what is required for a “verified fix”.

### **Vulnerability types**

Path: /security-analysis/vulnerability-types

Current content (as written now):

* Vulnerability categories (authz/authn, injection, business logic, crypto/config) and detection approach.

Recommendations \- English:

* Add quick bullets under each category: signals, impact, typical mitigation.

Recommendations \- Technical:

* If claiming OWASP coverage, link or provide a mapping (OWASP category → Kai category).  
* Clarify scope around dependencies/supply chain (what is included vs out of scope).

### **Severity levels**

Path: /security-analysis/severity-levels

Current content (as written now):

* Definitions for Critical/High/Medium/Low and severity weighting factors / response guidance.

Recommendations \- English:

* Soften strict time-to-fix guidance; frame as typical guidance dependent on org risk tolerance.

Recommendations \- Technical:

* If severity weighting percentages can change, label them as “current heuristic” or remove exact percentages to prevent docs drift.  
* Consider referencing CVSS as a comparison for readers familiar with standard scoring.

### **Fix suggestions**

Path: /security-analysis/fix-suggestions

Current content (as written now):

* What makes Kai fixes different, best practices for applying fixes, common fix patterns.

Recommendations \- English:

* Convert long paragraphs into a checklist/bullets (Root cause → Minimal diff → Validation steps → Alternatives).

Recommendations \- Technical:

* Add a “safe application” checklist (branch, tests, staging, rescan, monitor).  
* Clarify how fixes are delivered (diff/patch/code blocks) and whether any auto-apply exists.

## **Support**

### **FAQ**

Path: /support/faq

Current content (as written now):

* Product overview, scan timing, privacy, API keys, CI/on-prem, collaboration, integrations, pricing, and help channels.

Recommendations \- English:

* Fix rendering glitches in priority list (e.g., “Critical ()”, “High ()”).  
* Qualify numeric claims (counts, false-positive rates) to avoid sounding like guarantees.

Recommendations \- Technical:

* Align CI/CD status with other pages and document a current CI path if it exists.  
* Align pricing language across properties (token-based vs runtime-hour) and link to one canonical pricing page.  
* Fix broken GitHub issues link and normalize roles (Owner vs Viewer/Member/Admin).

# **Outbound links / sub-links health check**

* GitHub Issues / Report bugs: Resolves to a 404 page. Update to correct repo/issues URL.  
* Footer X link: Resolves to a 404 page. Update to correct handle.  
* VS Code Marketplace listing: Loads, but repeats broken GitHub links and contains copy that conflicts with “Coming Soon” settings claims.  
* Web dashboard marketing page: Loads; messaging about pricing/timing differs from FAQ — align to a canonical pricing source.  
* Embedded images: Direct fetch returned HTTP 403 in this environment; verify public accessibility / referrer restrictions.

# **Fast docs cleanup plan (5 steps)**

1. Fix broken links (GitHub Issues, LICENSE, X handle).  
2. Resolve “Coming Soon” contradictions (OpenRouter key, Default Scan Mode).  
3. Add a single Security & Privacy page and link it from the key onboarding pages.  
4. Normalize RBAC definitions across Workspaces / Team Collaboration / FAQ.  
5. Tighten claims: “every vuln has exploit” → “verified vulns have executed PoCs”; soften hard numeric guarantees unless sourced.