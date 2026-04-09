# Connectors

## How tool references work

Plugin files use `~~category` as a placeholder for whatever tool the user connects in that category. This plugin is tool-agnostic for source connectors — it works with whatever integrations the user has authorized. The only fixed connector requirement is Synaply itself.

## Required connector

| Category | Placeholder | Notes |
|----------|-------------|-------|
| Synaply | `~~synaply` | Required. Connect your organization's Synaply MCP server. Each Synaply tenant has a unique MCP URL — get yours from your Synaply admin or your account settings. |

## Optional source connectors

The plugin synthesizes knowledge from all connected sources. The more sources connected, the richer the insights. None of these are required, but each one adds signal.

| Category | Placeholder | Options |
|----------|-------------|---------|
| Email | `~~email` | Gmail, Outlook / Microsoft 365 |
| Calendar | `~~calendar` | Google Calendar, Outlook Calendar |
| Cloud storage | `~~cloud storage` | Google Drive, OneDrive, Dropbox |
| Chat | `~~chat` | Slack, Microsoft Teams, Discord |
| Project tracker | `~~project tracker` | Linear, Asana, Jira, Notion |

## Setting up your Synaply connector

1. Open your AI assistant settings and navigate to Connectors or MCP Servers
2. Add a new MCP server using the https type
3. Enter your organization's Synaply MCP URL (provided by your Synaply admin)
4. Authenticate when prompted
5. Confirm the connector is active before running a session

Once connected, say **"run my Synaply session"** to start.
