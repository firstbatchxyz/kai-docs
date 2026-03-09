# Integrations

Connect Kai with your existing development tools to streamline your security workflow. Create issues directly from vulnerability findings, track fixes in your project management tool, and keep your team in the loop.

## Available Integrations

<CardGroup cols={2}>
  <Card title="GitHub" icon="github" href="/platform/github">
    Create GitHub issues from vulnerability findings with full exploit details and fix suggestions.
  </Card>
  <Card title="Linear" icon="circle-dot" href="/platform/linear">
    Turn security findings into Linear issues with team and project routing.
  </Card>
</CardGroup>

<Frame>
  <img src="/images/integrations_page.png" alt="Integrations page in the web dashboard" />
</Frame>

## How Integrations Work

Kai integrations follow a simple pattern:

1. **Connect** your account via OAuth from the web dashboard
2. **Use** the integration from either the web dashboard or VS Code extension
3. **Manage** connections from your workspace settings

Each integration uses OAuth for secure authentication. Kai never stores your passwords — only the access tokens needed to create issues on your behalf.

## Where to Use Integrations

Integrations are available in both the **web dashboard** and the **VS Code extension**:

| Feature | Web Dashboard | VS Code Extension |
|---------|--------------|-------------------|
| **Connect/Disconnect** | Yes | No (connect via web) |
| **Create issues from exploits** | Yes | Yes |
| **Select target project/repo** | Yes | Yes |
| **View created issues** | Link to external tool | Link to external tool |

<Tip>
**Connect first, use anywhere.** Set up integrations once in the web dashboard, then create issues from either the web dashboard or VS Code extension.
</Tip>

## Getting Started

1. Go to your workspace in the [web dashboard](https://kai.dria.co)
2. Navigate to **Integrations**
3. Connect GitHub or Linear
4. Start creating issues from your vulnerability findings
