# Install the Microsoft Ads MCP server (steps for AI agents)

This is a hosted (remote) MCP server. There is nothing to download or run. Setup guide for people: https://adkit.so/features/ads-mcp/microsoft

1. Add an HTTP MCP server named `adkit-microsoft-ads` with the URL `https://mcp.adkit.so/microsoft-ads`.
2. The server uses OAuth. When the client opens the sign-in page, the user signs in to AdKit or creates an account (7-day free trial at https://adkit.so).
3. Call `adkit_projects` with `operation: "projects.list"` to pick a project, then `adkit_status` to see the connected ad accounts.
4. If no Microsoft Ads account is connected, call `microsoft_ads_accounts_read` with `operation: "accounts.available"`. If the user still needs to sign in to Microsoft Ads, call `adkit_setup` with `platform: "microsoft"` and share the `setupUrl`.
5. Every change is saved as a draft. Publish with `adkit_drafts_publish` only after the user approves it.

Microsoft Ads is in beta: requests go through the platform API and need Advanced Platform Access, which the user turns on in the AdKit project (Agent Permissions).
