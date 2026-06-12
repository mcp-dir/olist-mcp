# Olist Tiny ERP

### Olist Tiny ERP for Claude, ChatGPT and AI agents

Olist Tiny e-commerce ERP (formerly Tiny ERP) with the full official REST API v3, products, stock, orders, fiscal invoices (NF-e/NFC-e), accounts payable and receivable, contacts, shipping, purchase and service orders, CRM and price lists. Read and write. Pairs with the Banco MCP to reconcile bank and ERP. You create the app in your Olist account and authorize via OAuth.

- 📊 **1 tool**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/customize/connectors?modal=add-custom-connector&mcpName=Olist%20Tiny%20ERP&mcpServerUrl=https%3A%2F%2Fapi.mcp.ai%2Fp_olist)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors) → **+** → **Add custom connector** → name `Olist Tiny ERP`, URL `https://api.mcp.ai/p_olist`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=olist&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9vbGlzdCJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=olist&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_olist%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_olist
```

---

## 1 tool

| Tool | Description |
|---|---|
| `search_tools` | Single entrypoint for MCP catalog. |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_olist` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
