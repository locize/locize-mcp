# Locize MCP server

The Locize MCP server connects AI assistants and coding agents (GitHub Copilot in VS Code, Claude, Cursor and any other [MCP](https://modelcontextprotocol.io) client) to your [Locize](https://www.locize.com) projects, with your own account and permissions. Locize is a translation management system for software teams, from the creators of [i18next](https://www.i18next.com).

- **URL:** `https://mcp.locize.app`
- **Transport:** streamable HTTP
- **Authentication:** OAuth 2.0: you sign in with your Locize account when you connect. A [personal access token](https://www.locize.com/docs/integration/personal-access-tokens) works too.

The server is hosted by Locize; there is nothing to install or run. This repository holds its description for MCP registries and galleries.

## What it can do

- See your projects, languages and translation progress, and find missing or outdated translations before a release.
- Read translations as your team edits them and as your app receives them from the CDN.
- Translate and review with your project's context: glossary terms, style guide, translation memory and screenshots of where a text appears.
- Add new keys from your code and update translations. Your project's roles, restrictions and review rules apply, and every change shows in the project's history.
- Start an AI review of existing translations and read its proposals; a person accepts or declines them in Locize.
- Manage languages, project structure and publishing to your app. Tools that overwrite or remove content are marked destructive, so your client asks before it runs them.

## Connect

### VS Code (GitHub Copilot)

[Install in VS Code](https://insiders.vscode.dev/redirect/mcp/install?name=locize&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//mcp.locize.app%22%7D), or add it to `.vscode/mcp.json`:

```json
{
  "servers": {
    "locize": { "type": "http", "url": "https://mcp.locize.app" }
  }
}
```

VS Code asks you to sign in to Locize when it first starts the server.

### Claude

- **claude.ai, Desktop, mobile, Cowork:** add Locize from [Claude's connector directory](https://claude.ai/directory/locize) and click **Connect**.
- **Claude Code:** `claude mcp add --transport http locize https://mcp.locize.app`, then run `/mcp` and sign in.

### Cursor and other clients

Add `https://mcp.locize.app` as an HTTP MCP server and complete the sign-in. Clients without OAuth can send a personal access token as `Authorization: Bearer <token>`.

## Example prompts

- "Which languages in my Locize project are below 90% translated, and which namespaces need the most work?"
- "Find the missing German translations in the `common` namespace and translate them using the project's glossary and style guide."
- "Check these new English strings against our glossary and flag any forbidden term."
- "Run an AI review of the French translations and show me what it proposes."

## Requirements

A Locize account with access to at least one project: [create one](https://www.locize.app/register?from=mcp_directory__github) (14-day free trial, no credit card required). Reading works for every project member; writing needs a matching role in the project.

## Documentation, privacy and support

- Documentation: <https://www.locize.com/docs/integration/mcp>
- Privacy policy: <https://www.locize.com/privacy>
- Support and security reports: <https://www.locize.com/support> or support@locize.com
