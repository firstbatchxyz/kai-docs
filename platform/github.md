# GitHub Integration

Connect your GitHub account to create issues directly from Kai vulnerability findings. Each issue includes the exploit details, severity, affected file, and suggested fix — giving your team everything they need to resolve the vulnerability.

## Connecting GitHub

### From the Web Dashboard

1. Go to your workspace in the [web dashboard](https://kai.dria.co)
2. Navigate to **Integrations**
3. Click **Connect** on the GitHub card
4. Authorize Kai through GitHub OAuth
5. You'll be redirected back to your workspace

<Tip>
**Already have a GitHub connection?** If your workspace has an existing GitHub integration, you can link to it directly without going through OAuth again.
</Tip>

### What Kai Can Access

When you connect GitHub, Kai gets permission to:
- Create issues in repositories you select
- Read your repository list for the project picker

Kai does **not** get access to your code through this integration. Code access is handled separately through the scan upload process.

## Creating Issues from the Web Dashboard

1. Open a vulnerability from the Kanban board or scan results
2. Click **Create Issue**
3. Select the **GitHub** tab
4. Choose the target repository
5. Review the pre-filled issue details
6. Click **Create**

<Frame>
  <img src="/images/create_issue_drawer.png" alt="Create issue drawer with GitHub repository selector" />
</Frame>

The issue is created in your GitHub repository with:
- Vulnerability title and severity
- Detailed description of the security issue
- Exploit code demonstrating the vulnerability
- Suggested fix with code changes
- Link back to the finding in Kai

## Creating Issues from VS Code

1. Open the **Scan Results** panel in the Kai sidebar
2. Find the vulnerability you want to track
3. Click the **Create Issue** icon on the exploit item
4. Select **GitHub** from the integration picker
5. Choose the target repository from your connected repos
6. The issue is created and a link is provided

<Tip>
**No repositories showing?** Make sure you've connected GitHub from the web dashboard first. The VS Code extension uses the same connection.
</Tip>

## Disconnecting GitHub

1. Go to your workspace **Integrations** page
2. Click **Disconnect** on the GitHub card
3. Confirm the disconnection

<Warning>
Disconnecting removes Kai's ability to create issues in your GitHub repositories. Existing issues that were already created are not affected.
</Warning>

## Troubleshooting

### OAuth Callback Fails

**Problem**: The GitHub authorization page doesn't redirect back to Kai

**Solutions**:
- Check your browser's popup blocker settings
- Try using a different browser
- Ensure `kai.dria.co` is not blocked by your network

### No Repositories Found

**Problem**: The repository picker is empty when creating an issue

**Solutions**:
- Verify GitHub is connected in your workspace **Integrations** page
- Check that your GitHub account has access to the repositories you expect
- Try disconnecting and reconnecting the integration

### Issue Creation Fails

**Problem**: Error when trying to create a GitHub issue

**Solutions**:
- Ensure you have write access to the target repository
- Check that the repository allows issue creation (not disabled in settings)
- Verify your GitHub connection is still active in the **Integrations** page
