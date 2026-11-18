# UpGrow MCP server: setup, tools and a test call


UpGrow's MCP server is free and read-only and needs no key. Add https://www.upgrow.com/mcp to an MCP client as a remote server; its six tools return plans, shop products, free tools, blog posts, company facts and the sign-up link.

## MCP server

The server speaks MCP over Streamable HTTP at `https://www.upgrow.com/mcp`. It is stateless: every request is one JSON-RPC message answered with one JSON response. No key is needed.

Add it to an MCP client as a remote server. For clients that read a JSON config:

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

With the Claude Code command line:

```bash
claude mcp add --transport http upgrow https://www.upgrow.com/mcp
```

| Tool | What it returns |
| --- | --- |
| `list_plans` | Basic, Pro and Turbo with the first-month price, what each includes and the sign-up link |
| `list_products` | The one-time shop products with tiers, starting prices and product page links (optional `platform`: `instagram` or `tiktok`) |
| `list_free_tools` | The free Instagram tools with a link and one-line description |
| `search_blog` | Blog posts matching `q` (2 to 100 characters), up to `limit` results (1 to 10) |
| `get_company_facts` | What UpGrow is, how it works, guarantees and support contacts |
| `get_signup_link` | The link where a user starts, plus the pricing and shop pages |

Each tool returns readable text and `structuredContent`. Try it from a terminal:

```bash
curl -s https://www.upgrow.com/mcp \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json, text/event-stream' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"list_plans","arguments":{}}}'
```

The [server card](https://www.upgrow.com/.well-known/mcp/server-card.json) describes the endpoint. A GET request to `/mcp` returns 405 because the server opens no event stream.

## More for developers

- [UpGrow for AI agents and developers](https://www.upgrow.com/developers): every interface on one page
- [UpGrow A2A agent: agent card, endpoint and example](https://www.upgrow.com/developers/a2a-agent): agent card, the JSON-RPC endpoint, the five kinds of questions it answers, SendMessage (A2A 1.0) and message/send (A2A 0.3), with a curl example
- [UpGrow REST API: plans, shop products, free tools and blog search](https://www.upgrow.com/developers/rest-api): the five public endpoints (plans, products, free tools, blog search, health), their parameters and curl examples
- [Account access for agents: OAuth 2.1, API keys and GET /me](https://www.upgrow.com/developers/account-access): OAuth 2.1 with PKCE or a claimed API key, GET /me, the account MCP server at /mcp/account and its three tools
- [UpGrow discovery files, agent skills and WebMCP tools](https://www.upgrow.com/developers/discovery-files): API catalog, AI catalog, MCP server card, A2A agent card, skills index, OpenAPI, llms.txt and OAuth metadata, three agent skills and the six WebMCP browser tools
- [Contact UpGrow](https://www.upgrow.com/contact): questions these pages do not answer

---

Canonical version of this page: [https://www.upgrow.com/developers/mcp-server](https://www.upgrow.com/developers/mcp-server). Full developer index: [UpGrow for AI agents and developers](https://www.upgrow.com/developers).
