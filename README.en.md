# Olist Tiny ERP

### Olist Tiny ERP for Claude, ChatGPT and AI agents

Olist Tiny e-commerce ERP (formerly Tiny ERP) with the full official REST API v3, products, stock, orders, fiscal invoices (NF-e/NFC-e), accounts payable and receivable, contacts, shipping, purchase and service orders, CRM and price lists. Read and write. Pairs with the Banco MCP to reconcile bank and ERP. You create the app in your Olist account and authorize via OAuth.

- 📊 **179 tools**: 73 read and 106 write
- ✍️ **Read and write**: write tools change data in your ERP
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

## 179 tools

- **73 read tools**: list and fetch orders, products, stock, invoices, payables and receivables, contacts, CRM, shipping and more.
- **106 write tools**: create, update and delete orders, products and contacts, post stock and accounts, issue and cancel NF-e invoices, settle receivables and more.

Write tools act on your real Olist account, and some (issuing or cancelling NF-e) cannot be undone. Have your MCP client ask for confirmation before calling them.

Full list by area, with write tools marked: [docs/ferramentas.md](docs/ferramentas.md) (PT-BR).

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_olist` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
