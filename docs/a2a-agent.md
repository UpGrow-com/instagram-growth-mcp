# UpGrow A2A agent: agent card, endpoint and example


UpGrow's A2A agent takes a question in plain language at https://www.upgrow.com/a2a and answers at once with a text part and a data part. No key is needed.

## A2A agent

The agent card is at [https://www.upgrow.com/.well-known/agent-card.json](https://www.upgrow.com/.well-known/agent-card.json). Send JSON-RPC to `https://www.upgrow.com/a2a`. The agent answers at once with a message that holds a text part and a data part.

It handles five kinds of questions: plans and pricing, the one-time shop, free tools, blog articles, and getting started. It accepts `SendMessage` (A2A 1.0) and `message/send` (A2A 0.3).

```bash
curl -s https://www.upgrow.com/a2a \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"SendMessage","params":{"message":{"messageId":"m-1","role":"ROLE_USER","parts":[{"text":"What does UpGrow cost?"}]}}}'
```

## More for developers

- [UpGrow for AI agents and developers](https://www.upgrow.com/developers): every interface on one page
- [UpGrow MCP server: setup, tools and a test call](https://www.upgrow.com/developers/mcp-server): JSON config, Claude Code command, the six tools (list_plans, list_products, list_free_tools, search_blog, get_company_facts, get_signup_link) and a curl test call
- [UpGrow REST API: plans, shop products, free tools and blog search](https://www.upgrow.com/developers/rest-api): the five public endpoints (plans, products, free tools, blog search, health), their parameters and curl examples
- [Account access for agents: OAuth 2.1, API keys and GET /me](https://www.upgrow.com/developers/account-access): OAuth 2.1 with PKCE or a claimed API key, GET /me, the account MCP server at /mcp/account and its three tools
- [UpGrow discovery files, agent skills and WebMCP tools](https://www.upgrow.com/developers/discovery-files): API catalog, AI catalog, MCP server card, A2A agent card, skills index, OpenAPI, llms.txt and OAuth metadata, three agent skills and the six WebMCP browser tools
- [Contact UpGrow](https://www.upgrow.com/contact): questions these pages do not answer

---

Canonical version of this page: [https://www.upgrow.com/developers/a2a-agent](https://www.upgrow.com/developers/a2a-agent). Full developer index: [UpGrow for AI agents and developers](https://www.upgrow.com/developers).
