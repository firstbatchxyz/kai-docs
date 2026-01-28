# Troubleshooting

Common issues and solutions for the Kai VS Code extension. Most problems can be resolved with simple configuration changes or environment fixes.

## Installation Issues

### Extension Not Appearing in Activity Bar

**Symptoms**:
- Installed Kai but don't see the icon in the left sidebar
- Extensions view shows Kai as installed but it's not accessible

**Solutions**:
1. **Restart VS Code completely** - Close all windows and reopen
2. **Check VS Code version** - Ensure you're running 1.80.0 or higher
3. **Verify installation**:
   - Go to Extensions view (`Ctrl+Shift+X`)
   - Search for "Kai Agent"
   - Should show as "Installed" with Reload/Uninstall options
4. **Reset workspace**:
   - Close VS Code
   - Delete `.vscode` folder in your project (optional)
   - Reopen project
5. **Reinstall extension**:
   - Uninstall Kai Agent
   - Restart VS Code
   - Reinstall from marketplace

### Installation Fails or Gets Stuck

**Symptoms**:
- "Installing..." status never completes
- Error messages during installation
- Partial installation with missing functionality

**Solutions**:
1. **Check network connectivity** - Ensure access to VS Code marketplace
2. **Clear VS Code cache**:
   ```bash
   # Windows
   %APPDATA%\Code\logs

   # macOS
   ~/Library/Application Support/Code/logs

   # Linux
   ~/.config/Code/logs
   ```
3. **Install manually**:
   - Download `.vsix` file from marketplace
   - Use `Extensions: Install from VSIX` command
4. **Check disk space** - Ensure sufficient storage for installation
5. **Disable other extensions temporarily** - Rule out conflicts

## Authentication Problems

### Cannot Sign In / OAuth Fails

**Symptoms**:
- Clicking "Sign In" does nothing
- Browser opens but authentication fails
- "Authentication failed" error messages

**Solutions**:
1. **Check network access**:
   - Ensure these domains are accessible:
     - `github.com`
     - `kai.dria.co`
     - `staging.kai.dria.co`
2. **Browser issues**:
   - Try signing in with an incognito/private window
   - Clear browser cache and cookies
   - Disable browser extensions temporarily
   - Try a different browser
3. **Corporate firewall**:
   - Contact IT to whitelist required domains
   - Check if OAuth redirects are blocked
   - Try from a different network (mobile hotspot)
4. **VS Code settings**:
   - Check if VS Code proxy settings are configured correctly
   - Ensure VS Code can open external URLs

### Signed In But Shows as Logged Out

**Symptoms**:
- Successfully authenticated but VS Code still shows login prompt
- Authentication seems to work but doesn't persist

**Solutions**:
1. **Clear extension state**:
   - Use command palette: `Kai: Reset State`
   - Sign in again
2. **Check VS Code storage**:
   - Restart VS Code completely
   - Try signing in immediately after restart
3. **Token issues**:
   - Sign out completely
   - Clear browser cookies for GitHub and Kai
   - Sign in again with fresh authentication

### Permission Errors During OAuth

**Symptoms**:
- GitHub OAuth shows permission errors
- "Access denied" messages during authentication

**Solutions**:
1. **Check GitHub account status** - Ensure account is in good standing
2. **Review OAuth permissions** - Make sure you're accepting necessary permissions
3. **GitHub organization restrictions** - If using organization account, check OAuth policies
4. **Try personal account** - Test with personal GitHub account first

## Scan Issues

### Cannot Start Scan / "No Files Selected" Error

**Symptoms**:
- Scan button is disabled or doesn't work
- Error message about file selection
- Files appear selected but scan won't start

**Solutions**:
1. **Verify file selection**:
   - Check that at least one file has a checkmark
   - Ensure selected files are actually code files (not config/binary)
   - Try selecting different files
2. **Check project structure**:
   - Ensure you're in a git repository: `git status`
   - Verify repository has commits: `git log --oneline`
   - Make sure working directory is clean
3. **File size limits**:
   - Total selected files must be under 50MB
   - Uncheck large files or dependencies
   - Use `du -sh *` to check file sizes
4. **Repository requirements**:
   ```bash
   # Initialize git if needed
   git init
   git add .
   git commit -m "Initial commit"
   ```

### Scan Fails to Start / Upload Errors

**Symptoms**:
- Scan appears to start but fails immediately
- Upload progress never completes
- Network or timeout errors

**Solutions**:
1. **Network connectivity**:
   - Test internet connection
   - Try from different network if possible
   - Check if corporate proxy is interfering
2. **File content issues**:
   - Ensure files don't contain sensitive data (API keys, passwords)
   - Check for binary files accidentally included
   - Verify file encoding (UTF-8 preferred)
3. **Authentication refresh**:
   - Sign out and sign back in
   - Clear extension state and reauthenticate
4. **Retry scan**:
   - Wait a few minutes and try again
   - Try with fewer files selected
   - Contact support if consistently failing

### Scan Stuck in "Running" Status

**Symptoms**:
- Scan shows as running for many hours
- No progress updates or notifications
- Status never changes from "Running"

**Solutions**:
1. **Check normal timing**:
   - Baseline: ~2 hours is normal
   - Enhanced: ~4 hours is normal
   - Full: ~8 hours is normal
2. **Refresh status**:
   - Click refresh button in Executions panel
   - Restart VS Code and check status again
3. **Wait for completion**:
   - Large or complex projects may take longer
   - Scan continues even if VS Code is closed
4. **Contact support** if scan runs >24 hours without completion

## Results and Display Issues

### No Results Showing / Empty Results Panel

**Symptoms**:
- Scan completes but no vulnerabilities shown
- Results panel is blank or shows loading indefinitely
- "No data available" messages

**Solutions**:
1. **Refresh results view**:
   - Click refresh button in Scan Results panel
   - Select the execution again in Executions panel
2. **Check scan success**:
   - Verify scan actually completed successfully
   - Look for completion notification
   - Check execution status in Executions panel
3. **Network issues**:
   - Ensure internet connectivity for loading results
   - Try refreshing after checking network
4. **Very secure code**:
   - Some projects may genuinely have no vulnerabilities found
   - Try scanning different files or using Full mode for deeper analysis

### Cannot View Vulnerability Details

**Symptoms**:
- Can see vulnerability list but clicking doesn't show details
- Exploit code or fix suggestions not loading
- Partial information missing from vulnerability cards

**Solutions**:
1. **WebView issues**:
   - Restart VS Code to refresh webview
   - Check if VS Code webview is blocked by security software
2. **Content loading**:
   - Wait for content to load (may take a few seconds)
   - Check internet connectivity
3. **Extension conflicts**:
   - Disable other extensions temporarily
   - Test with clean VS Code profile

### Kanban Board Not Working

**Symptoms**:
- Cannot drag and drop vulnerabilities between columns
- Column changes don't save
- Board appears frozen or unresponsive

**Solutions**:
1. **Refresh interface**:
   - Reload VS Code window (`Developer: Reload Window`)
   - Click refresh in Scan Results panel
2. **WebView reset**:
   - Close and reopen Scan Results panel
   - Restart VS Code completely
3. **Network synchronization**:
   - Ensure changes are syncing to cloud
   - Check internet connectivity
   - Try making changes slowly (one at a time)

## Performance Issues

### Extension Slows Down VS Code

**Symptoms**:
- VS Code becomes sluggish when Kai is active
- High CPU or memory usage
- Typing lag or interface delays

**Solutions**:
1. **Resource optimization**:
   - Close unused VS Code windows
   - Restart VS Code to clear memory
   - Consider using smaller file selections
2. **Extension management**:
   - Disable Kai when not actively scanning
   - Close Scan Results webview when not needed
3. **System resources**:
   - Ensure adequate RAM (8GB+ recommended)
   - Close other resource-intensive applications

### Slow File Selection / Tree Loading

**Symptoms**:
- File tree takes long time to load
- Checking/unchecking files is slow
- VS Code freezes when selecting many files

**Solutions**:
1. **Project size**:
   - Large projects (1000+ files) may be slow
   - Consider scanning subdirectories separately
2. **File system performance**:
   - Ensure project is on fast storage (SSD preferred)
   - Check if antivirus is scanning files
3. **Selective scanning**:
   - Focus on specific directories
   - Use .gitignore to exclude unnecessary files

## Configuration Issues

### Settings Not Persisting

**Symptoms**:
- Default scan mode reverts to original setting
- API key settings don't save
- Preferences reset after VS Code restart

**Solutions**:
1. **VS Code settings location**:
   - Check User vs Workspace settings
   - Ensure settings file is writable
2. **Settings sync**:
   - If using VS Code settings sync, check for conflicts
   - Try disabling sync temporarily
3. **Permissions**:
   - Ensure VS Code has write access to settings directory
   - Check file permissions in `.vscode` folder

### OpenRouter API Key Issues

**Symptoms**:
- API key setting doesn't reduce costs
- Getting charged despite setting custom key
- "Invalid API key" errors

**Solutions**:
1. **Key validation**:
   - Verify API key is correct and active
   - Check OpenRouter dashboard for key status
2. **Settings location**:
   - Ensure key is set in User Settings, not just Workspace
   - Double-check spelling and spacing
3. **Key permissions**:
   - Ensure API key has necessary permissions
   - Check usage limits and billing status

## Advanced Troubleshooting

### Extension Logs and Debugging

**Enable verbose logging**:
1. Open Command Palette (`Ctrl+Shift+P`)
2. Run `Developer: Set Log Level`
3. Select `Trace` for maximum detail
4. Check `Output` panel → `Kai Agent` for logs

**VS Code logs location**:
- Windows: `%APPDATA%\Code\logs`
- macOS: `~/Library/Application Support/Code/logs`
- Linux: `~/.config/Code/logs`

### Clean Reinstall Process

**Complete extension reset**:
1. **Uninstall extension** through Extensions view
2. **Clear settings**:
   ```json
   // Remove from settings.json
   "kai-agent.openRouterApiKey": "",
   "kai-agent.defaultScanMode": ""
   ```
3. **Clear state**: Use `Kai: Reset State` command before uninstalling
4. **Restart VS Code**
5. **Reinstall** from marketplace
6. **Reconfigure** settings as needed

### Network Diagnostics

**Test connectivity**:
```bash
# Test API endpoints
curl -I https://kai.dria.co
curl -I https://staging.kai.dria.co

# Test GitHub OAuth
curl -I https://github.com/login/oauth/authorize
```

**Check proxy configuration**:
```bash
# VS Code proxy settings
echo $HTTP_PROXY
echo $HTTPS_PROXY
```

## Getting Additional Help

### Before Contacting Support

**Gather this information**:
1. VS Code version (`Help` → `About`)
2. Extension version (Extensions view → Kai Agent → gear icon)
3. Operating system and version
4. Error messages (exact text)
5. Steps to reproduce the issue
6. Extension logs (if available)

### Support Channels

1. **Email**: kai@dria.co for bug reports and feature requests
2. **Documentation**: Check other sections of this documentation
3. **Community**: VS Code Marketplace Q&A section
4. **Web Dashboard**: Contact support directly through the dashboard

### Temporary Workarounds

**While waiting for fixes**:
1. **Use web dashboard** for vulnerability management
2. **Export results** before making changes
3. **Take screenshots** of important findings
4. **Document workarounds** for team members

Remember: Most issues are environment-related and can be resolved with the solutions above. If you're still having trouble after trying these steps, don't hesitate to reach out for support with specific details about your setup and the problem you're experiencing.