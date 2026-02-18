# Installing the Kai VS Code Extension

Get the Kai VS Code extension installed and configured in just a few minutes.

## Installation Methods

### Method 1: VS Code Marketplace (Recommended)

1. Open VS Code
2. Click the Extensions icon in the Activity Bar (`Ctrl+Shift+X` or `Cmd+Shift+X`)
3. Search for "Kai Agent"
4. Find the extension by **Dria** (Publisher: Dria)
5. Click **Install**

<Frame>
  <img src="/images/extension_marketplace.png" alt="Kai extension in VS Code Marketplace" />
</Frame>

### Method 2: Direct Download

1. Visit the [VS Code Marketplace page](https://marketplace.visualstudio.com/items?itemName=Dria.kai-vscode)
2. Click **Install** to launch VS Code automatically
3. Alternatively, download the `.vsix` file and install manually

### Method 3: Command Palette

1. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
2. Type `Extensions: Install Extensions`
3. Search for "Kai Agent" by Dria
4. Click **Install**


## Verification

After installation, verify Kai is working correctly:

1. **Check Activity Bar**: Look for the Kai icon (should appear in the left sidebar)
2. **Open Kai Panel**: Click the Kai icon to open the main panel
3. **Check Status**: You should see login options and extension information

## Initial Configuration

### Setting Up Authentication

1. Click the Kai icon in the Activity Bar
2. In the main panel, click **Sign In**
3. Your default browser will open to GitHub OAuth
4. Sign in to your GitHub account
5. Authorize Kai to access your account information
6. Return to VS Code - you should see your account details

<Frame>
  <img src="/images/extension login.png" alt="Kai login screen in VS Code" />
</Frame>

### Workspace Setup

1. Open a folder containing code you want to scan
2. Ensure it's a git repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```
3. The Kai panel should now show your project files

## Key Features

### Abort a Running Scan

Need to cancel a scan that's in progress? Click the **stop icon** next to the execution in the **Executions** panel. A confirmation dialog appears before the scan is aborted.

### View Fix Diffs

For each vulnerability, you can view the suggested fix as a side-by-side diff directly in VS Code. Click the **diff icon** on any exploit item in the **Scan Results** panel to see the before-and-after code changes.

<Frame>
  <img src="/images/extension_inline_diff_view.png" alt="Inline diff view showing suggested fix in VS Code" />
</Frame>

### Create Issues from Exploits

Turn vulnerability findings into trackable issues in GitHub or Linear without leaving VS Code. Click the **issues icon** on any exploit item, choose your integration, and select the target repository or team.

<Tip>
**Set up integrations first.** Connect GitHub or Linear from the [web dashboard](https://kai.dria.co) before creating issues from VS Code. See [Integrations](/integrations/overview) for setup instructions.
</Tip>

## Extension Settings

Access Kai settings through VS Code's Settings UI or the Kai Settings button:

### File Exclusions
Kai automatically excludes common files but you can customize:
- Configuration files (`.env`, `.gitignore`, etc.)
- Dependencies (`node_modules`, `vendor`, etc.)
- Binary files and assets

## Troubleshooting Installation

### Extension Not Appearing

**Problem**: Kai icon doesn't show in Activity Bar

**Solutions**:
1. Restart VS Code completely
2. Check Extensions view to confirm installation
3. Try disabling and re-enabling the extension
4. Ensure VS Code version meets requirements (1.80.0+)

### Authentication Issues

**Problem**: Can't sign in or authentication fails

**Solutions**:
1. Check your internet connection
2. Ensure GitHub is accessible from your network
3. Clear browser cache and cookies
4. Try signing in with an incognito/private browser window
5. Disable browser extensions that might block OAuth

### Permission Errors

**Problem**: Extension can't access files or git repository

**Solutions**:
1. Ensure you have read access to the project folder
2. Check git repository status: `git status`
3. Verify git is properly configured
4. Try opening VS Code as administrator (Windows) or with appropriate permissions

### Network/Firewall Issues

**Problem**: Can't connect to Kai's cloud runtime

**Solutions**:
1. Check corporate firewall settings
2. Ensure these domains are accessible:
   - `kai.dria.co`
   - `staging.kai.dria.co`
   - `github.com` (for authentication)
3. Contact your IT administrator if needed

## Updating the Extension

Kai automatically updates through VS Code's extension system:

1. Updates are downloaded automatically
2. You'll see a notification when an update is available
3. Restart VS Code to apply updates
4. Check the changelog for new features

### Manual Update Check

1. Go to Extensions view (`Ctrl+Shift+X`)
2. Find Kai Agent in your installed extensions
3. Click the gear icon → "Check for Updates"

## Uninstalling

If you need to remove Kai:

1. Go to Extensions view
2. Find Kai Agent
3. Click the gear icon → "Uninstall"
4. Restart VS Code to complete removal

**Note**: Uninstalling only removes the local extension. Your scan history and findings remain accessible through the web dashboard.

## Next Steps

Once installed and configured:

1. [Run Your First Scan](../using-kai/first-scan) - Complete walkthrough of the scanning process
2. [Understanding Results](../using-kai/understanding-results) - Learn how to interpret findings
3. [Managing Vulnerabilities](../using-kai/managing-vulnerabilities) - Master the workflow system

## Getting Help

Check the [FAQ](../support/faq) for frequently asked questions and common solutions, or contact support through the web dashboard if you need assistance.

The Kai extension integrates seamlessly into your development workflow. Once installed, you can scan any git repository for security vulnerabilities without leaving VS Code.