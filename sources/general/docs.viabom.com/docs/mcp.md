# Source: https://docs.viabom.com/docs/mcp

# MCP

Copy page

Connect Via to Claude, ChatGPT, and Gemini so they can search components, edit libraries, and work with your projects through MCP.

Via exposes an [MCP](https://modelcontextprotocol.io) server so AI assistants can search components, look up part details, and work with your projects, libraries, and rulesets on your behalf.

The MCP endpoint is:

```
https://api.viabom.com/mcp
```

Sign-in uses the same Via account you already use in the app. Every tool call uses the same workspace access you already have in Via.

This page was last verified against the vendors' official docs on April 20, 2026.

## [What You Need First](https://docs.viabom.com/#what-you-need-first)

Before adding Via to an MCP-capable client, make sure:

- your Via account can already sign in normally in the browser
- the client supports remote MCP over HTTP or streaming HTTP
- pop-ups are allowed for the client app so the sign-in window can open
- you are using the exact URL above with no extra path segments

You do not need to create an API key for Via MCP. The server uses standard OAuth and prompts you to sign in during connector setup.

## [Quick Matrix](https://docs.viabom.com/#quick-matrix)

| Client | Current setup path | Publish required? |
| --- | --- | --- |
| Claude | Add Via as a custom connector in Claude or Claude Desktop, or add it in Claude Code with `claude mcp add --transport http ...` | No. Optional only if we later want Anthropic directory listing. |
| ChatGPT | Create a draft app from the Via MCP URL in ChatGPT Developer mode | No for direct or internal use. Yes if we later want ChatGPT app directory distribution. |
| Gemini | Add Via in Gemini CLI with `gemini mcp add --transport http ...` | No. Users connect it locally in Gemini CLI. |

## [What Clients Can Do](https://docs.viabom.com/#what-clients-can-do)

Once connected, an MCP-capable assistant can:

- search components with project, BOM, library, and ruleset context
- open component details with specs, datasheet metadata, and distributor pricing
- read and edit projects and BOMs
- read and edit libraries
- read and edit rulesets, including named config variants

## [Connect Claude](https://docs.viabom.com/#connect-claude)

### [Claude Web Or Claude Desktop](https://docs.viabom.com/#claude-web-or-claude-desktop)

Use Claude's custom connector flow for Via's remote MCP server. Do not put a remote Via URL in `claude_desktop_config.json`; that file is for Claude Desktop's local MCP mechanism.

1. Open `Customize -> Connectors`.
2. Click `+` and choose `Add custom connector`.
3. Name it `Via` and paste `https://api.viabom.com/mcp`.
4. Leave OAuth client credentials blank unless your Claude workspace asks you to override them.
5. Click `Add`, then `Connect`, and finish the Via sign-in flow in your browser.
6. Enable the connector for a chat from the `+` menu -> `Connectors`.

On Team and Enterprise plans, an owner has to add the custom connector first. Each user still connects their own Via account after that.

### [Claude Code](https://docs.viabom.com/#claude-code)

Add Via as a remote HTTP server:

```
claude mcp add --transport http via-bom https://api.viabom.com/mcp
```

Then run `/mcp` inside Claude Code and complete the browser sign-in when prompted.

## [Connect ChatGPT](https://docs.viabom.com/#connect-chatgpt)

ChatGPT now calls these integrations `apps`, not `connectors`.

1. In ChatGPT web, open `Settings -> Apps` (or `Apps & Connectors`) -> `Advanced settings`.
2. Turn on `Developer mode`.
3. Click `Create app`.
4. Use Via's MCP URL: `https://api.viabom.com/mcp`.
5. Finish the Via sign-in flow when ChatGPT opens the browser window.
6. The Via app will appear under `Drafts`. Enable it in a conversation from the `+` menu or the Developer Mode tool picker.

Notes:

- ChatGPT only supports remote MCP servers here, not `localhost`.
- If ChatGPT offers optional OAuth client credentials, leave them blank for Via's normal flow. Via is intended to work through OAuth metadata discovery plus dynamic client registration. If DCR is disabled on the OAuth provider, someone will need to enter static credentials manually.
- Availability depends on your ChatGPT plan and, for workspace accounts, admin settings.
- For direct or internal use, you do not need to publish anything first.

## [What ChatGPT Still Needs In 2026](https://docs.viabom.com/#what-chatgpt-still-needs-in-2026)

For direct or internal use, nothing needs to be published to OpenAI first. The remaining requirements are configuration, not publication:

- In ChatGPT, the user or workspace must have Developer mode available and enabled. Workspace plans may also require admin approval before custom apps can be created or published.
- Via's MCP server must be public over HTTPS at `https://api.viabom.com/mcp`.
- Via's OAuth discovery metadata must be reachable from `/.well-known/oauth-protected-resource` and `/.well-known/oauth-authorization-server`.
- For Via's current production deployment, the advertised OAuth issuer should be `https://login.viabom.com`, not the old staging `*.authkit.app` domain.
- Via's OAuth provider must advertise refresh-token support (`offline_access` in `scopes_supported`, plus `refresh_token` in `grant_types_supported`) so ChatGPT can stay connected cleanly after the first sign-in.
- If users are expected to paste only the Via MCP URL and not hand-enter OAuth client credentials, Via's OAuth provider must also support Client ID Metadata Document plus Dynamic Client Registration. That is Via's intended zero-touch ChatGPT setup.
- The API worker must also have `CONVEX_URL` configured in the same deployed environment. If OAuth succeeds but the first authenticated MCP request fails with `CONVEX_URL is required for MCP operations`, the Worker is missing that secret.
- The production AuthKit issuer and `MCP_RESOURCE_URL` must point at the same WorkOS environment. A production MCP URL should not advertise a staging issuer.

If we later want Via listed in the ChatGPT app directory, that is a separate OpenAI submission, verification, review, and publish flow.

## [Connect Gemini](https://docs.viabom.com/#connect-gemini)

Google's current first-party MCP docs cover Gemini CLI.

1. Install or update Gemini CLI.
 
2. Add Via as a remote HTTP server:
 
 ```
    gemini mcp add --transport http via https://api.viabom.com/mcp
    ```
 
3. Complete the Via sign-in flow if Gemini opens a browser for OAuth.
 
4. Run `/mcp list` to confirm the server is connected.
 
5. Try a prompt like `find a 1% 10k 0402 resistor`.
 

If you prefer file-based config, you can also add Via under `mcpServers` in `~/.gemini/settings.json` or `.gemini/settings.json`.

As of April 20, 2026, we have not found first-party Google docs for adding arbitrary remote MCP servers to the Gemini web app. Gemini CLI is the official Google-documented path today.

## [Do We Need To Publish Anything?](https://docs.viabom.com/#do-we-need-to-publish-anything)

- Claude: No. Anyone can add Via as a custom connector directly by URL. If we later want in-product discovery in Anthropic's Connectors Directory, that is a separate optional submission and review process.
- ChatGPT: No for direct use in Developer mode. Yes if we later want Via listed in the ChatGPT app directory. That is a separate OpenAI app-submission path with verification, review, and explicit publishing after approval. OpenAI's Apps SDK is the recommended packaging path for public app experiences, including MCP-backed apps.
- Gemini: No publication step is required for Gemini CLI. Users add the MCP server locally.

## [Sign-In And Permissions](https://docs.viabom.com/#sign-in-and-permissions)

- The assistant can use the same projects, libraries, rulesets, and search context you can already access in Via.
- You may be asked to sign in again if the client needs to refresh access.
- You can revoke a client at any time from your account settings or by removing the connector in the assistant app.

## [Troubleshooting](https://docs.viabom.com/#troubleshooting)

- **The connector setup shows a server error immediately.** This usually means the service is unavailable for a moment. Check the [status page](https://docs.viabom.com/status) and try again.
- **Claude Desktop says the server is missing when I edited `claude_desktop_config.json`.** For Via's remote MCP server, use Claude's `Customize -> Connectors` flow or Claude Code's `claude mcp add --transport http ...` command instead.
- **The sign-in window does not open.** Make sure pop-ups are allowed for the assistant app, then try adding the connector again.
- **The sign-in page says the application was not found.** This usually means the MCP client cached an older OAuth client registration after Via's advertised issuer changed. In Claude Code or other `mcp-remote` clients, remove the Via entry from `~/.mcp-auth/mcp-remote-*/` and retry, or remove and re-add the Via connector so the client performs a fresh Dynamic Client Registration against `https://login.viabom.com`.
- **ChatGPT or Claude cannot connect to the server from a private network.** These remote connector flows expect a public HTTPS MCP endpoint, not a VPN-only or `localhost` URL.
- **Tools appear but return empty results.** Confirm you are signed in to the correct workspace in Via.
- **Client cannot discover the server.** Double-check the URL is exactly `https://api.viabom.com/mcp` with no trailing slash or path.

If something is still not working, include the client name, the error you see, and the time of the attempt in a bug report.

## [Official References](https://docs.viabom.com/#official-references)

- [Claude custom connectors](https://support.claude.com/en/articles/11175166-getting-started-with-custom-integrations-using-remote-mcp)
- [Claude Code MCP](https://code.claude.com/docs/en/mcp)
- [ChatGPT Developer mode](https://developers.openai.com/api/docs/guides/developer-mode)
- [Connect from ChatGPT](https://developers.openai.com/apps-sdk/deploy/connect-chatgpt)
- [Submit and maintain your app](https://developers.openai.com/apps-sdk/deploy/submission)
- [Apps in ChatGPT](https://help.openai.com/en/articles/11487775)
- [Submitting apps to the ChatGPT app directory](https://help.openai.com/en/articles/20001040-submitting-apps-to-the-chatgpt-app-directory)
- [Gemini CLI MCP](https://geminicli.com/docs/tools/mcp-server/)

[Workspaces\\ \\ Understand how Via scopes shared projects, libraries, rulesets, and settings to the active organization workspace.](https://docs.viabom.com/docs/workspaces) [Shortcuts & Feedback\\ \\ Move faster with keyboard shortcuts and report issues clearly when search or part data is wrong.](https://docs.viabom.com/docs/shortcuts-and-feedback)

### On this page

[What You Need First](https://docs.viabom.com/#what-you-need-first) [Quick Matrix](https://docs.viabom.com/#quick-matrix) [What Clients Can Do](https://docs.viabom.com/#what-clients-can-do) [Connect Claude](https://docs.viabom.com/#connect-claude) [Claude Web Or Claude Desktop](https://docs.viabom.com/#claude-web-or-claude-desktop) [Claude Code](https://docs.viabom.com/#claude-code) [Connect ChatGPT](https://docs.viabom.com/#connect-chatgpt) [What ChatGPT Still Needs In 2026](https://docs.viabom.com/#what-chatgpt-still-needs-in-2026) [Connect Gemini](https://docs.viabom.com/#connect-gemini) [Do We Need To Publish Anything?](https://docs.viabom.com/#do-we-need-to-publish-anything) [Sign-In And Permissions](https://docs.viabom.com/#sign-in-and-permissions) [Troubleshooting](https://docs.viabom.com/#troubleshooting) [Official References](https://docs.viabom.com/#official-references)