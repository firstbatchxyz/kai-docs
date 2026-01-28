# Getting Started with Kai

Get your first security scan running in under 5 minutes. No configuration required - just install, authenticate, and scan.

## Prerequisites

Before you begin, make sure you have:

- **VS Code 1.80.0 or higher**
- **Internet connection** (selected files are uploaded to Kai's cloud for analysis)
- **Git repository** with at least one commit (Kai uses the commit hash for scan identification)

## Step 1: Install the VS Code Extension

1. Open VS Code
2. Go to the Extensions view (`Ctrl+Shift+X` or `Cmd+Shift+X`)
3. Search for "Kai Agent" by Dria
4. Click **Install**

Alternatively, [install directly from the VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=Dria.kai-vscode).

## Step 2: Open Your Project

1. Open a folder containing code you want to scan
2. Make sure it's a git repository with at least one commit
3. Look for the Kai icon in the Activity Bar (left sidebar)

<Tip>
**Not a git repository?** Run `git init && git add . && git commit -m "Initial commit"` in your project folder.
</Tip>

## Step 3: Sign In

1. Click the **Kai** icon in the Activity Bar
2. In the Kai panel, click **Sign In**
3. Your browser will open to GitHub OAuth
4. Authorize Kai to access your GitHub account
5. Return to VS Code - you should now see your account information

<Note>
Kai uses GitHub OAuth for authentication but never accesses your private repositories unless you explicitly upload code for scanning.
</Note>

## Step 4: Select Files to Scan

1. In the **Files to Review** panel, browse your project files
2. Check the boxes next to files you want to include in the scan
3. Focus on your main application code - Kai automatically excludes:
   - Configuration files (`.env`, `.gitignore`)
   - Node modules and dependencies
   - Binary files and assets

<Tip>
**Start small**: For your first scan, select 5-10 key files. You can always run additional scans with more files later. Maximum upload size is 50MB per scan.
</Tip>

## Step 5: Choose Your Scan Mode

When you're ready to scan, you'll choose from three scan modes:

- **Baseline** ⚡ - Quick scan with basic analysis (~2 hours)
- **Enhanced** 🎯 - Balanced scan with comprehensive analysis (~4 hours, recommended)
- **Full** 🔍 - Deep scan with maximum thoroughness (~8 hours)

<Tip>
**New to Kai?** Start with Enhanced mode. It provides thorough analysis without the time commitment of Full mode.
</Tip>

## Step 6: Run Your First Scan

1. With files selected, click the **Scan** button
2. Choose your scan mode (Enhanced recommended)
3. Kai will bundle your files and start the analysis in the cloud
4. You'll see progress updates in the Executions panel

**What happens next:**
- Files are securely uploaded to Kai's cloud runtime
- AI agents begin analyzing your code in parallel
- You can close VS Code - the scan continues in the cloud
- You'll get progress updates as vulnerabilities are found and verified

## Step 7: Review Your Results

Once the scan completes (you'll see a notification), you can review findings:

1. Go to the **Scan Results** view in the Kai panel
2. Browse vulnerabilities organized by severity (Critical, High, Medium, Low)
3. Click on any finding to see:
   - **Detailed explanation** of the vulnerability
   - **Working exploit code** that proves it's real
   - **Suggested fix** with code changes
   - **Impact assessment** and severity reasoning

## Step 8: Manage Vulnerabilities

Kai includes a Kanban-style workflow for tracking fixes:

- **Awaiting Verification**: Potential issues being analyzed
- **Awaiting Approval**: Confirmed vulnerabilities ready for review
- **To Be Fixed**: Approved issues ready for remediation
- **Fixed**: Resolved vulnerabilities
- **Won't Do**: Issues you've decided to skip

Drag and drop findings between columns to track your progress.

## Next Steps

### Customize Your Setup

- **Add your OpenRouter API key** (Coming Soon): Reduce costs by using your own LLM credits
- **Set default scan mode**: (Coming Soon) Choose your preferred default in Kai Settings
- **Explore the web dashboard**: View team analytics and collaborate on findings

### Learn More

- [Understanding Scan Results](using-kai/understanding-results) - Deep dive into vulnerability reports
- [Managing Vulnerabilities](using-kai/managing-vulnerabilities) - Master the Kanban workflow
- [Scan Mode Comparison](using-kai/scan-modes) - Choose the right analysis depth

### Get Help

- Check the [FAQ](support/faq) for common questions and solutions
- Review [Security & Privacy](security-privacy) for data handling details
- Contact support through the web dashboard if you're stuck

## What to Expect from Your First Scan

**Timeline**: Enhanced scans typically complete in 2-4 hours, depending on code complexity.

**Results**: Most projects have 3-15 verified vulnerabilities. Don't worry if this seems high - many are minor issues with clear fixes.

**Learning**: Each finding includes educational content explaining why it's a problem and how to fix it.

**False Positives**: Extremely rare. If Kai reports a vulnerability, it comes with working exploit code proving it's real.

Ready to secure your code? Install the extension and run your first scan today!

[Install Kai Extension →](https://marketplace.visualstudio.com/items?itemName=Dria.kai-vscode)