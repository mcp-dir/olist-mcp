# Olist Tiny ERP

### Olist Tiny ERP para Claude, ChatGPT e agentes de IA

ERP de e-commerce Olist Tiny (ex-Tiny ERP) com a API REST oficial v3 completa, produtos, estoque, pedidos, notas fiscais (NF-e/NFC-e), contas a pagar e receber, contatos, expedição, ordens de compra e serviço, CRM e listas de preços. Consulta e operação. Pareia com o Banco MCP para conciliar banco e ERP. Você cria o aplicativo na sua conta Olist e autoriza com OAuth.

- 📊 **1 ferramenta**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/customize/connectors?modal=add-custom-connector&mcpName=Olist%20Tiny%20ERP&mcpServerUrl=https%3A%2F%2Fapi.mcp.ai%2Fp_olist)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors) → **+** → **Adicionar conector personalizado** → cole **Nome** `Olist Tiny ERP` e **URL** `https://api.mcp.ai/p_olist`.

### Cursor

[➕ Instalar Olist Tiny ERP no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=olist&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9vbGlzdCJ9)

### VS Code (Copilot Chat)

[➕ Instalar Olist Tiny ERP no VS Code](vscode:mcp/install?name=olist&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_olist%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_olist
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Liste os pedidos de venda dos últimos 7 dias
Qual o estoque atual do produto X?
Quais contas a receber estão em aberto este mês?
```

---

## 1 ferramenta disponível

| Tool | Descrição |
|---|---|
| `search_tools` | Single entrypoint for MCP catalog. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: Olist (Tiny), o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_olist`.


---

## Suporte

- 📧 [olist@mcp.ai](mailto:olist@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/olist-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_olist` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
