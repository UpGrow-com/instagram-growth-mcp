# UpGrow REST API: plans, shop products, free tools and blog search


UpGrow's public REST API returns plain JSON with no key: growth plans, one-time shop products, free Instagram tools, blog search and a health check. Plan prices are first-month prices and shop prices are one-time prices.

## REST API

Base address: `https://www.upgrow.com/api/public/v1`. Responses are JSON, allow any origin (CORS) and are cacheable, except `/health`. The full description is in [openapi.json](https://www.upgrow.com/openapi.json).

| Request | Returns |
| --- | --- |
| `GET /` | An index of these endpoints with their full addresses |
| `GET /plans` | Basic, Pro and Turbo: first-month price, what each includes, sign-up link |
| `GET /products` | One-time shop products with tiers, starting prices and product page links |
| `GET /free-tools` | Free Instagram tools: name, link, one-line description |
| `GET /blog/search?q=&limit=` | Blog posts matching `q` (2 to 100 characters); `limit` 1 to 10, default 5; a bad value returns 400 |
| `GET /health` | `{"status":"ok"}`, never cached |

```bash
curl -s https://www.upgrow.com/api/public/v1/plans
```

```bash
curl -s 'https://www.upgrow.com/api/public/v1/blog/search?q=instagram%20reels&limit=3'
```

```bash
curl -s https://www.upgrow.com/api/public/v1/products
curl -s https://www.upgrow.com/api/public/v1/free-tools
curl -s https://www.upgrow.com/api/public/v1/health
```

## More for developers

- [UpGrow for AI agents and developers](https://www.upgrow.com/developers): every interface on one page
- [UpGrow MCP server: setup, tools and a test call](https://www.upgrow.com/developers/mcp-server): JSON config, Claude Code command, the six tools (list_plans, list_products, list_free_tools, search_blog, get_company_facts, get_signup_link) and a curl test call
- [UpGrow A2A agent: agent card, endpoint and example](https://www.upgrow.com/developers/a2a-agent): agent card, the JSON-RPC endpoint, the five kinds of questions it answers, SendMessage (A2A 1.0) and message/send (A2A 0.3), with a curl example
- [Account access for agents: OAuth 2.1, API keys and GET /me](https://www.upgrow.com/developers/account-access): OAuth 2.1 with PKCE or a claimed API key, GET /me, the account MCP server at /mcp/account and its three tools
- [UpGrow discovery files, agent skills and WebMCP tools](https://www.upgrow.com/developers/discovery-files): API catalog, AI catalog, MCP server card, A2A agent card, skills index, OpenAPI, llms.txt and OAuth metadata, three agent skills and the six WebMCP browser tools
- [Contact UpGrow](https://www.upgrow.com/contact): questions these pages do not answer

---

Canonical version of this page: [https://www.upgrow.com/developers/rest-api](https://www.upgrow.com/developers/rest-api). Full developer index: [UpGrow for AI agents and developers](https://www.upgrow.com/developers).
