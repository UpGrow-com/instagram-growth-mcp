# UpGrow Instagram Growth MCP server and API

UpGrow is an AI-powered Instagram growth service that attracts real, targeted followers by engaging with audiences chosen from your competitors, hashtags and locations, and it never asks for your Instagram password. This documentation covers UpGrow's free, read-only interfaces for AI agents and developers: a remote MCP server, an A2A agent and a public REST API. The public data needs no account and no API key.

## What you can reach

| Interface | Address | Use it for |
| --- | --- | --- |
| MCP server | `https://www.upgrow.com/mcp` | Tools for an MCP client such as Claude, Cursor or ChatGPT |
| A2A agent | `https://www.upgrow.com/a2a` | Ask in plain language, get a message back |
| REST API | `https://www.upgrow.com/api/public/v1` | Plain JSON over HTTP, described by OpenAPI |
| OpenAPI 3.1 | [openapi.json](https://www.upgrow.com/openapi.json) | Generate a client or let an agent read the API |
| llms.txt | [llms.txt](https://www.upgrow.com/llms.txt) | A plain-text map of UpGrow for language models |

Everything here is read-only. Agents can look up growth plans, one-time shop products, free Instagram tools and blog articles, and send a user to sign-up. They cannot buy or change anything.

## Quick start

Add the MCP server to Claude Code:

```bash
claude mcp add --transport http upgrow https://www.upgrow.com/mcp
```

Or call the REST API directly:

```bash
curl -s https://www.upgrow.com/api/public/v1/free-tools
```

## Pages

- [MCP server: setup, tools and a test call](mcp-server.md)
- [A2A agent: agent card, endpoint and example](a2a-agent.md)
- [REST API: plans, shop products, free tools and blog search](rest-api.md)

## About UpGrow

- Website: [www.upgrow.com](https://www.upgrow.com/)
- [Instagram growth service](https://www.upgrow.com/instagram-growth-service)
- [Free Instagram tools](https://www.upgrow.com/free-instagram-tools): follower count tracker, engagement rate calculator, hashtag and caption generators and more, no sign-up and no password
- [Instagram growth statistics 2026](https://www.upgrow.com/instagram-growth-statistics)
- [Developers](https://www.upgrow.com/developers)
- Support: support@upgrow.com

The source of this documentation and the MCP registry files live in the [instagram-growth-mcp repository](https://github.com/UpGrow-com/instagram-growth-mcp) under the MIT license.
