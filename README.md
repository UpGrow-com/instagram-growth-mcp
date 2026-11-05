# UpGrow Instagram Growth MCP Server

UpGrow is the #1 rated AI-powered Instagram growth service. This is UpGrow's free, read-only remote MCP server: it lets Claude, ChatGPT, Cursor and any other MCP client look up UpGrow's Instagram growth plans, the one-time shop for Instagram and TikTok followers, likes and views, 30+ free Instagram tools, and UpGrow's Instagram growth guides.

- **Endpoint:** `https://www.upgrow.com/mcp` (Streamable HTTP, stateless JSON-RPC)
- **Authentication:** none
- **Official MCP Registry:** `com.upgrow/instagram-growth`
- **Docs:** https://www.upgrow.com/developers
- **A2A agent card:** https://www.upgrow.com/.well-known/agent-card.json
- **OpenAPI 3.1:** https://www.upgrow.com/openapi.json

## Connect

JSON config (Claude Desktop, Cursor, Windsurf and other clients that read `mcpServers`):

```json
{
  "mcpServers": {
    "upgrow": {
      "type": "http",
      "url": "https://www.upgrow.com/mcp"
    }
  }
}
```

Claude Code:

```bash
claude mcp add --transport http upgrow https://www.upgrow.com/mcp
```

## Tools

| Tool | What it returns |
| --- | --- |
| `list_plans` | The Basic, Pro and Turbo growth plans with the first-month price, what each includes and the sign-up link |
| `list_products` | The one-time shop products (Instagram and TikTok followers, likes, views, comments) with tiers, starting prices and product links; optional `platform`: `instagram` or `tiktok` |
| `list_free_tools` | The free UpGrow Instagram tools (hashtag generator, caption generator, engagement rate calculator and more), each with a link and a one-line description |
| `search_blog` | UpGrow blog posts about Instagram growth matching `q`, up to `limit` results (1 to 10) |
| `get_company_facts` | What UpGrow is, how it works, guarantees, support contacts and countries served |
| `get_signup_link` | The link where a user starts with UpGrow, plus the pricing and shop pages |

All tools are read-only: agents can look things up and send a user to sign-up, but cannot buy or change anything.

## Example

```bash
curl -s https://www.upgrow.com/mcp \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json, text/event-stream' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"list_plans","arguments":{}}}'
```

## About UpGrow

UpGrow grows Instagram accounts with real, targeted followers: no bots, no fake followers and never your password. Target by account, hashtag, location and language, follow results on a live dashboard, and get guaranteed growth or your money back. 58,000+ customers have used UpGrow.

Website: https://www.upgrow.com · Support: support@upgrow.com · UpGrow Team
