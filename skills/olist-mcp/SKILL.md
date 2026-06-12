---
name: olist-mcp
description: Skill da REST API do Olist Tiny ERP na MCP.AI: 179 endpoints em /api/olist. ERP de e-commerce Olist Tiny (ex-Tiny ERP) com a API REST oficial v3 completa, produtos, estoque, pedidos, notas fiscais (NF-e/NFC-e), contas a pagar e receber, contatos, expedição, ordens de compra e serviço, CRM e listas de preços. Consulta e operação. Pareia com o Banco MCP para conciliar banco e ERP. Você cria o aplicativo na sua conta Olist e autoriza com OAuth. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Olist Tiny ERP — REST API skill

Você tem acesso à **Olist Tiny ERP** REST API na MCP.AI.

> ERP de e-commerce Olist Tiny (ex-Tiny ERP) com a API REST oficial v3 completa, produtos, estoque, pedidos, notas fiscais (NF-e/NFC-e), contas a pagar e receber, contatos, expedição, ordens de compra e serviço, CRM e listas de preços. Consulta e operação. Pareia com o Banco MCP para conciliar banco e ERP. Você cria o aplicativo na sua conta Olist e autoriza com OAuth.

## Base URL

```
https://api.mcp.ai/api/olist
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/olist/categorias/create \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/olist/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (179)

#### `olist_categorias_create`

Criar categoria de produto (POST /categorias). _(POST /api/olist/categorias/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_categorias_delete`

Excluir categoria de produto (DELETE /categorias/{idCategoria}). _(POST /api/olist/categorias/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idCategoria` | string | Sim | Path param "idCategoria" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_categorias_get`

Obter categoria por identificador (GET /categorias/{idCategoria}). _(POST /api/olist/categorias/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idCategoria` | string | Sim | Path param "idCategoria" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_categorias_receita_despesa_list`

Listar categorias de receita e despesa (GET /categorias-receita-despesa). _(POST /api/olist/categorias/receita/despesa/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_categorias_todas_list`

Listar árvore de categorias (GET /categorias/todas). _(POST /api/olist/categorias/todas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_categorias_update`

Editar categoria de produto (PUT /categorias/{idCategoria}). _(POST /api/olist/categorias/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idCategoria` | string | Sim | Path param "idCategoria" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_pagar_create`

Criar conta a pagar (POST /contas-pagar). _(POST /api/olist/contas/pagar/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_pagar_get`

Obter conta a pagar (GET /contas-pagar/{idContaPagar}). _(POST /api/olist/contas/pagar/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaPagar` | string | Sim | Path param "idContaPagar" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_pagar_list`

Listar contas a pagar (GET /contas-pagar). _(POST /api/olist/contas/pagar/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_pagar_marcadores_create`

Criar marcadores da conta a pagar (POST /contas-pagar/{idContaPagar}/marcadores). _(POST /api/olist/contas/pagar/marcadores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaPagar` | string | Sim | Path param "idContaPagar" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_pagar_marcadores_delete`

Excluir marcadores da conta a pagar (DELETE /contas-pagar/{idContaPagar}/marcadores). _(POST /api/olist/contas/pagar/marcadores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaPagar` | string | Sim | Path param "idContaPagar" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_pagar_marcadores_list`

Obter marcadores da conta a pagar (GET /contas-pagar/{idContaPagar}/marcadores). _(POST /api/olist/contas/pagar/marcadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaPagar` | string | Sim | Path param "idContaPagar" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_pagar_marcadores_update`

Atualizar marcadores da conta a pagar (PUT /contas-pagar/{idContaPagar}/marcadores). _(POST /api/olist/contas/pagar/marcadores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaPagar` | string | Sim | Path param "idContaPagar" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_pagar_recebimentos_list`

Obter recebimentos da conta a pagar (GET /contas-pagar/{idContaPagar}/recebimentos). _(POST /api/olist/contas/pagar/recebimentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaPagar` | string | Sim | Path param "idContaPagar" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_receber_baixar_create`

Baixar uma conta a receber (POST /contas-receber/{idContaReceber}/baixar). _(POST /api/olist/contas/receber/baixar/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_receber_create`

Criar conta a receber (POST /contas-receber). _(POST /api/olist/contas/receber/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_receber_get`

Obter conta a receber (GET /contas-receber/{idContaReceber}). _(POST /api/olist/contas/receber/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_receber_list`

Listar contas a receber (GET /contas-receber). _(POST /api/olist/contas/receber/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_receber_marcadores_create`

Criar marcadores da conta a receber (POST /contas-receber/{idContaReceber}/marcadores). _(POST /api/olist/contas/receber/marcadores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_receber_marcadores_delete`

Excluir marcadores da conta a receber (DELETE /contas-receber/{idContaReceber}/marcadores). _(POST /api/olist/contas/receber/marcadores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_receber_marcadores_list`

Obter marcadores da conta a receber (GET /contas-receber/{idContaReceber}/marcadores). _(POST /api/olist/contas/receber/marcadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_receber_marcadores_update`

Atualizar marcadores da conta a receber (PUT /contas-receber/{idContaReceber}/marcadores). _(POST /api/olist/contas/receber/marcadores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contas_receber_recebimentos_list`

Obter recebimentos da conta a receber (GET /contas-receber/{idContaReceber}/recebimentos). _(POST /api/olist/contas/receber/recebimentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contas_receber_update`

Atualizar conta a receber (PUT /contas-receber/{idContaReceber}). _(POST /api/olist/contas/receber/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContaReceber` | string | Sim | Path param "idContaReceber" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contatos_create`

Criar contato (POST /contatos). _(POST /api/olist/contatos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contatos_get`

Obter contato (GET /contatos/{idContato}). _(POST /api/olist/contatos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contatos_list`

Listar contatos (GET /contatos). _(POST /api/olist/contatos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contatos_pessoas_create`

Criar pessoa de contato (POST /contatos/{idContato}/pessoas). _(POST /api/olist/contatos/pessoas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contatos_pessoas_delete`

Excluir pessoa de contato (DELETE /contatos/{idContato}/pessoas/{idPessoa}). _(POST /api/olist/contatos/pessoas/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `idPessoa` | string | Sim | Path param "idPessoa" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contatos_pessoas_get`

Obter pessoa de contato (GET /contatos/{idContato}/pessoas/{idPessoa}). _(POST /api/olist/contatos/pessoas/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `idPessoa` | string | Sim | Path param "idPessoa" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contatos_pessoas_list`

Listar pessoas de contato (GET /contatos/{idContato}/pessoas). _(POST /api/olist/contatos/pessoas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contatos_pessoas_update`

Atualizar pessoa de contato (PUT /contatos/{idContato}/pessoas/{idPessoa}). _(POST /api/olist/contatos/pessoas/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `idPessoa` | string | Sim | Path param "idPessoa" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contatos_status_crm_update`

Atualizar status CRM do contato (PUT /contatos/{idContato}/status-crm). _(POST /api/olist/contatos/status/crm/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_contatos_tipos_list`

Listar tipos de contatos (GET /contatos/tipos). _(POST /api/olist/contatos/tipos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_contatos_update`

Atualizar contato (PUT /contatos/{idContato}). _(POST /api/olist/contatos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idContato` | string | Sim | Path param "idContato" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_acoes_create`

Criar ação de assunto (POST /crm/assuntos/{idAssunto}/acoes). _(POST /api/olist/crm/assuntos/acoes/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_acoes_delete`

Deletar ação de um assunto (DELETE /crm/assuntos/{idAssunto}/acoes/{idAcao}). _(POST /api/olist/crm/assuntos/acoes/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `idAcao` | string | Sim | Path param "idAcao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_acoes_get`

Obter ação de um assunto (GET /crm/assuntos/{idAssunto}/acoes/{idAcao}). _(POST /api/olist/crm/assuntos/acoes/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `idAcao` | string | Sim | Path param "idAcao" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_acoes_list`

Listar ações de um assunto (GET /crm/assuntos/{idAssunto}/acoes). _(POST /api/olist/crm/assuntos/acoes/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_acoes_update`

Atualizar ação de assunto (PUT /crm/assuntos/{idAssunto}/acoes/{idAcao}). _(POST /api/olist/crm/assuntos/acoes/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `idAcao` | string | Sim | Path param "idAcao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_anotacoes_create`

Criar anotação de assunto (POST /crm/assuntos/{idAssunto}/anotacoes). _(POST /api/olist/crm/assuntos/anotacoes/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_anotacoes_delete`

Deletar anotação de assunto (DELETE /crm/assuntos/{idAssunto}/anotacoes/{idAnotacao}). _(POST /api/olist/crm/assuntos/anotacoes/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `idAnotacao` | string | Sim | Path param "idAnotacao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_anotacoes_list`

Listar anotações de um assunto (GET /crm/assuntos/{idAssunto}/anotacoes). _(POST /api/olist/crm/assuntos/anotacoes/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_anotacoes_update`

Atualizar anotação de assunto (PUT /crm/assuntos/{idAssunto}/anotacoes/{idAnotacao}). _(POST /api/olist/crm/assuntos/anotacoes/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `idAnotacao` | string | Sim | Path param "idAnotacao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_arquivar_update`

Arquivar ou desarquivar assunto (PUT /crm/assuntos/{idAssunto}/arquivar). _(POST /api/olist/crm/assuntos/arquivar/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_create`

Criar assunto (POST /crm/assuntos). _(POST /api/olist/crm/assuntos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_delete`

Deletar assunto (DELETE /crm/assuntos/{idAssunto}). _(POST /api/olist/crm/assuntos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_estrela_update`

Atualizar estrela do assunto (PUT /crm/assuntos/{idAssunto}/estrela). _(POST /api/olist/crm/assuntos/estrela/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_get`

Obter assunto (GET /crm/assuntos/{idAssunto}). _(POST /api/olist/crm/assuntos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_list`

Listar assuntos (GET /crm/assuntos). _(POST /api/olist/crm/assuntos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_marcadores_create`

Criar marcadores do assunto (POST /crm/assuntos/{idAssunto}/marcadores). _(POST /api/olist/crm/assuntos/marcadores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_marcadores_delete`

Remover marcadores de um assunto (DELETE /crm/assuntos/{idAssunto}/marcadores). _(POST /api/olist/crm/assuntos/marcadores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_marcadores_list`

Listar marcadores de um assunto (GET /crm/assuntos/{idAssunto}/marcadores). _(POST /api/olist/crm/assuntos/marcadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_marcadores_update`

Atualizar marcadores do assunto (PUT /crm/assuntos/{idAssunto}/marcadores). _(POST /api/olist/crm/assuntos/marcadores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_assuntos_update`

Atualizar assunto (PUT /crm/assuntos/{idAssunto}). _(POST /api/olist/crm/assuntos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAssunto` | string | Sim | Path param "idAssunto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_estagios_create`

Criar estágio (POST /crm/estagios). _(POST /api/olist/crm/estagios/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_estagios_delete`

Deletar estágio (DELETE /crm/estagios/{idEstagio}). _(POST /api/olist/crm/estagios/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idEstagio` | string | Sim | Path param "idEstagio" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_crm_estagios_get`

Obter estágio (GET /crm/estagios/{idEstagio}). _(POST /api/olist/crm/estagios/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idEstagio` | string | Sim | Path param "idEstagio" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_estagios_list`

Listar estágios (GET /crm/estagios). _(POST /api/olist/crm/estagios/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_crm_estagios_update`

Atualizar estágio (PUT /crm/estagios/{idEstagio}). _(POST /api/olist/crm/estagios/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idEstagio` | string | Sim | Path param "idEstagio" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_depositos_get`

Obter depósito de estoque por ID (GET /depositos/{idDeposito}). _(POST /api/olist/depositos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idDeposito` | string | Sim | Path param "idDeposito" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_depositos_list`

Listar depósitos de estoque (GET /depositos). _(POST /api/olist/depositos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_estoque_create`

Atualizar o estoque de um produto (POST /estoque/{idProduto}). _(POST /api/olist/estoque/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_estoque_get`

Obter o estoque de um produto (GET /estoque/{idProduto}). _(POST /api/olist/estoque/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_expedicao_concluir_create`

Concluir um agrupamento de expedição (POST /expedicao/{idAgrupamento}/concluir). _(POST /api/olist/expedicao/concluir/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAgrupamento` | string | Sim | Path param "idAgrupamento" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_expedicao_create`

Criar agrupamento de expedição (POST /expedicao). _(POST /api/olist/expedicao/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_expedicao_etiquetas_list`

Obter etiquetas de um agrupamento de expedição (GET /expedicao/{idAgrupamento}/etiquetas). _(POST /api/olist/expedicao/etiquetas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAgrupamento` | string | Sim | Path param "idAgrupamento" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_expedicao_expedicao_etiquetas_list`

Obter etiquetas de uma expedição dentro de um agrupamento (GET /expedicao/{idAgrupamento}/expedicao/{idExpedicao}/etiquetas). _(POST /api/olist/expedicao/expedicao/etiquetas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAgrupamento` | string | Sim | Path param "idAgrupamento" (obrigatório) |
| `idExpedicao` | string | Sim | Path param "idExpedicao" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_expedicao_expedicao_update`

Alterar uma expedição dentro de um agrupamento (PUT /expedicao/{idAgrupamento}/expedicao/{idExpedicao}). _(POST /api/olist/expedicao/expedicao/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAgrupamento` | string | Sim | Path param "idAgrupamento" (obrigatório) |
| `idExpedicao` | string | Sim | Path param "idExpedicao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_expedicao_get`

Obter agrupamento de expedição (GET /expedicao/{idAgrupamento}). _(POST /api/olist/expedicao/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAgrupamento` | string | Sim | Path param "idAgrupamento" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_expedicao_list`

Listar agrupamentos de expedição (GET /expedicao). _(POST /api/olist/expedicao/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_expedicao_origens_create`

Adicionar origens a um agrupamento de expedição (POST /expedicao/{idAgrupamento}/origens). _(POST /api/olist/expedicao/origens/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idAgrupamento` | string | Sim | Path param "idAgrupamento" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_formas_envio_get`

Obter forma de envio (GET /formas-envio/{idFormaEnvio}). _(POST /api/olist/formas/envio/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idFormaEnvio` | string | Sim | Path param "idFormaEnvio" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_formas_envio_list`

Listar formas de envio (GET /formas-envio). _(POST /api/olist/formas/envio/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_formas_pagamento_get`

Obter forma de pagamento (GET /formas-pagamento/{idFormaPagamento}). _(POST /api/olist/formas/pagamento/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idFormaPagamento` | string | Sim | Path param "idFormaPagamento" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_formas_pagamento_list`

Listar formas de pagamento (GET /formas-pagamento). _(POST /api/olist/formas/pagamento/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_formas_recebimento_get`

Obter forma de recebimento (GET /formas-recebimento/{idFormaRecebimento}). _(POST /api/olist/formas/recebimento/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idFormaRecebimento` | string | Sim | Path param "idFormaRecebimento" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_formas_recebimento_list`

Listar formas de recebimento (GET /formas-recebimento). _(POST /api/olist/formas/recebimento/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_grupos_tags_list`

Listar grupos de tags (GET /grupos-tags). _(POST /api/olist/grupos/tags/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_info_list`

Obter informações da conta da empresa (GET /info). _(POST /api/olist/info/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_intermediadores_get`

Obter intermediador (GET /intermediadores/{idIntermediador}). _(POST /api/olist/intermediadores/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idIntermediador` | string | Sim | Path param "idIntermediador" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_intermediadores_list`

Listar intermediadores (GET /intermediadores). _(POST /api/olist/intermediadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_list_accounts`

Lista as conexões (empresas) Olist vinculadas a este install — company_id, label. _(POST /api/olist/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |

#### `olist_listas_precos_create`

Criar lista de preços (POST /listas-precos). _(POST /api/olist/listas/precos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_listas_precos_get`

Obter lista de preços (GET /listas-precos/{idListaDePreco}). _(POST /api/olist/listas/precos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idListaDePreco` | string | Sim | Path param "idListaDePreco" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_listas_precos_list`

Listar listas de preços (GET /listas-precos). _(POST /api/olist/listas/precos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_listas_precos_produtos_delete`

Excluir produto de lista de preços (DELETE /listas-precos/{idListaDePreco}/produtos/{idProduto}). _(POST /api/olist/listas/precos/produtos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idListaDePreco` | string | Sim | Path param "idListaDePreco" (obrigatório) |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_listas_precos_update`

Atualizar lista de preços (PUT /listas-precos/{idListaDePreco}). _(POST /api/olist/listas/precos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idListaDePreco` | string | Sim | Path param "idListaDePreco" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_marcas_create`

Criar marca (POST /marcas). [write, altera dados no ERP] _(POST /api/olist/marcas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_marcas_list`

Listar marcas (GET /marcas). _(POST /api/olist/marcas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_marcas_update`

Atualizar marca (PUT /marcas/{idMarca}). _(POST /api/olist/marcas/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idMarca` | string | Sim | Path param "idMarca" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_despacho_update`

Atualizar informações de rastreamento da nota fiscal (PUT /notas/{idNota}/despacho). _(POST /api/olist/notas/despacho/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_emitir_create`

Autorizar nota fiscal (POST /notas/{idNota}/emitir). _(POST /api/olist/notas/emitir/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_get`

Obter nota fiscal (GET /notas/{idNota}). _(POST /api/olist/notas/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_notas_itens_get`

Obter item da nota fiscal (GET /notas/{idNota}/itens/{idItem}). _(POST /api/olist/notas/itens/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `idItem` | string | Sim | Path param "idItem" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_notas_lancar_contas_create`

Lançar contas da nota fiscal (POST /notas/{idNota}/lancar-contas). _(POST /api/olist/notas/lancar/contas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_lancar_estoque_create`

Lançar estoque da nota fiscal (POST /notas/{idNota}/lancar-estoque). _(POST /api/olist/notas/lancar/estoque/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_link_list`

Obter link da nota fiscal (GET /notas/{idNota}/link). _(POST /api/olist/notas/link/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_notas_list`

Listar notas fiscais (GET /notas). _(POST /api/olist/notas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_notas_marcadores_create`

Criar marcadores da nota fiscal (POST /notas/{idNota}/marcadores). _(POST /api/olist/notas/marcadores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_marcadores_delete`

Excluir marcadores da nota fiscal (DELETE /notas/{idNota}/marcadores). _(POST /api/olist/notas/marcadores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_marcadores_list`

Obter marcadores da nota fiscal (GET /notas/{idNota}/marcadores). _(POST /api/olist/notas/marcadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_notas_marcadores_update`

Atualizar marcadores da nota fiscal (PUT /notas/{idNota}/marcadores). _(POST /api/olist/notas/marcadores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_nota_fiscal_consumidor_xml_create`

Incluir nota fiscal de consumidor por XML (POST /notas/nota-fiscal-consumidor/xml). _(POST /api/olist/notas/nota/fiscal/consumidor/xml/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_xml_cancelar_create`

Cancelar nota fiscal (POST /notas/xml/cancelar). _(POST /api/olist/notas/xml/cancelar/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_xml_create`

Incluir nota fiscal por XML (POST /notas/xml). _(POST /api/olist/notas/xml/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_xml_fornecedor_create`

Incluir nota fiscal de fornecedor por XML (POST /notas/xml/fornecedor). _(POST /api/olist/notas/xml/fornecedor/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_notas_xml_list`

Obter XML da nota fiscal (GET /notas/{idNota}/xml). _(POST /api/olist/notas/xml/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idNota` | string | Sim | Path param "idNota" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_ordem_compra_create`

Criar ordem de compra (POST /ordem-compra). _(POST /api/olist/ordem/compra/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_compra_get`

Obter ordem de compra (GET /ordem-compra/{idOrdemCompra}). _(POST /api/olist/ordem/compra/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_ordem_compra_lancar_contas_create`

Lançar contas da ordem de compra (POST /ordem-compra/{idOrdemCompra}/lancar-contas). _(POST /api/olist/ordem/compra/lancar/contas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_compra_lancar_estoque_create`

Lançar estoque da ordem de compra (POST /ordem-compra/{idOrdemCompra}/lancar-estoque). _(POST /api/olist/ordem/compra/lancar/estoque/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_compra_list`

Listar ordens de compra (GET /ordem-compra). _(POST /api/olist/ordem/compra/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_ordem_compra_marcadores_create`

Criar marcadores da ordem de compra (POST /ordem-compra/{idOrdemCompra}/marcadores). _(POST /api/olist/ordem/compra/marcadores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_compra_marcadores_delete`

Excluir marcadores da ordem de compra (DELETE /ordem-compra/{idOrdemCompra}/marcadores). _(POST /api/olist/ordem/compra/marcadores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_compra_marcadores_list`

Obter marcadores da ordem de compra (GET /ordem-compra/{idOrdemCompra}/marcadores). _(POST /api/olist/ordem/compra/marcadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_ordem_compra_marcadores_update`

Atualizar marcadores da ordem de compra (PUT /ordem-compra/{idOrdemCompra}/marcadores). _(POST /api/olist/ordem/compra/marcadores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_compra_situacao_update`

Atualizar situação da ordem de compra (PUT /ordem-compra/{idOrdemCompra}/situacao). _(POST /api/olist/ordem/compra/situacao/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_compra_update`

Atualizar ordem de compra (PUT /ordem-compra/{idOrdemCompra}). _(POST /api/olist/ordem/compra/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemCompra` | string | Sim | Path param "idOrdemCompra" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_create`

Criar ordem de serviço (POST /ordem-servico). _(POST /api/olist/ordem/servico/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_gerar_nota_fiscal_create`

Gerar nota fiscal para a ordem de serviço (POST /ordem-servico/{idOrdemServico}/gerar-nota-fiscal). _(POST /api/olist/ordem/servico/gerar/nota/fiscal/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_get`

Obter ordem de serviço (GET /ordem-servico/{idOrdemServico}). _(POST /api/olist/ordem/servico/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_ordem_servico_lancar_contas_create`

Lançar contas da ordem de serviço (POST /ordem-servico/{idOrdemServico}/lancar-contas). _(POST /api/olist/ordem/servico/lancar/contas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_lancar_estoque_create`

Lançar estoque da ordem de serviço (POST /ordem-servico/{idOrdemServico}/lancar-estoque). _(POST /api/olist/ordem/servico/lancar/estoque/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_list`

Listar ordem de serviço (GET /ordem-servico). _(POST /api/olist/ordem/servico/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_ordem_servico_marcadores_create`

Criar marcadores da ordem de serviço (POST /ordem-servico/{idOrdemServico}/marcadores). _(POST /api/olist/ordem/servico/marcadores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_marcadores_delete`

Excluir marcadores da ordem de serviço (DELETE /ordem-servico/{idOrdemServico}/marcadores). _(POST /api/olist/ordem/servico/marcadores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_marcadores_list`

Obter marcadores da ordem de serviço (GET /ordem-servico/{idOrdemServico}/marcadores). _(POST /api/olist/ordem/servico/marcadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_ordem_servico_marcadores_update`

Atualizar marcadores da ordem de serviço (PUT /ordem-servico/{idOrdemServico}/marcadores). _(POST /api/olist/ordem/servico/marcadores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_situacao_update`

Atualizar situação da ordem de serviço (PUT /ordem-servico/{idOrdemServico}/situacao). _(POST /api/olist/ordem/servico/situacao/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_ordem_servico_update`

Atualizar ordem de serviço (PUT /ordem-servico/{idOrdemServico}). _(POST /api/olist/ordem/servico/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idOrdemServico` | string | Sim | Path param "idOrdemServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_create`

Criar pedido (POST /pedidos). [write, altera dados no ERP] _(POST /api/olist/pedidos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_despacho_update`

Atualizar informações de rastreamento do pedido (PUT /pedidos/{idPedido}/despacho). _(POST /api/olist/pedidos/despacho/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_estornar_contas_create`

Estornar contas do pedido (POST /pedidos/{idPedido}/estornar-contas). _(POST /api/olist/pedidos/estornar/contas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_estornar_estoque_create`

Estornar estoque do pedido (POST /pedidos/{idPedido}/estornar-estoque). _(POST /api/olist/pedidos/estornar/estoque/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_gerar_nota_fiscal_create`

Gerar nota fiscal do pedido (POST /pedidos/{idPedido}/gerar-nota-fiscal). _(POST /api/olist/pedidos/gerar/nota/fiscal/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_gerar_ordem_producao_create`

Gerar ordem de produção do pedido (POST /pedidos/{idPedido}/gerar-ordem-producao). _(POST /api/olist/pedidos/gerar/ordem/producao/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_get`

Obter pedido (GET /pedidos/{idPedido}). _(POST /api/olist/pedidos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_pedidos_itens_update`

Atualizar itens do pedido (PUT /pedidos/{idPedido}/itens). _(POST /api/olist/pedidos/itens/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_lancar_contas_create`

Lançar contas do pedido (POST /pedidos/{idPedido}/lancar-contas). _(POST /api/olist/pedidos/lancar/contas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_lancar_estoque_create`

Lançar estoque do pedido (POST /pedidos/{idPedido}/lancar-estoque). _(POST /api/olist/pedidos/lancar/estoque/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_list`

Listar pedidos (GET /pedidos). _(POST /api/olist/pedidos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_pedidos_marcadores_create`

Criar marcadores do pedido (POST /pedidos/{idPedido}/marcadores). _(POST /api/olist/pedidos/marcadores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_marcadores_delete`

Excluir marcadores do pedido (DELETE /pedidos/{idPedido}/marcadores). _(POST /api/olist/pedidos/marcadores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_marcadores_list`

Obter marcadores do pedido (GET /pedidos/{idPedido}/marcadores). _(POST /api/olist/pedidos/marcadores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_pedidos_marcadores_update`

Atualizar marcadores do pedido (PUT /pedidos/{idPedido}/marcadores). _(POST /api/olist/pedidos/marcadores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_situacao_update`

Atualizar situação do pedido (PUT /pedidos/{idPedido}/situacao). _(POST /api/olist/pedidos/situacao/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_pedidos_update`

Atualizar pedido (PUT /pedidos/{idPedido}). _(POST /api/olist/pedidos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idPedido` | string | Sim | Path param "idPedido" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_create`

Criar produto (POST /produtos). _(POST /api/olist/produtos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_custos_list`

Listar custos do produto (GET /produtos/{idProduto}/custos). _(POST /api/olist/produtos/custos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_produtos_delete`

Excluir produto (DELETE /produtos/{idProduto}). _(POST /api/olist/produtos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_fabricado_list`

Obter produto fabricado (GET /produtos/{idProduto}/fabricado). _(POST /api/olist/produtos/fabricado/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_produtos_fabricado_update`

Atualizar produto fabricado (PUT /produtos/{idProduto}/fabricado). _(POST /api/olist/produtos/fabricado/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_get`

Obter produto (GET /produtos/{idProduto}). _(POST /api/olist/produtos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_produtos_kit_list`

Obter produto kit (GET /produtos/{idProduto}/kit). _(POST /api/olist/produtos/kit/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_produtos_kit_update`

Atualizar kit do produto (PUT /produtos/{idProduto}/kit). _(POST /api/olist/produtos/kit/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_list`

Listar produtos (GET /produtos). _(POST /api/olist/produtos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_produtos_preco_update`

Atualizar preço do produto (PUT /produtos/{idProduto}/preco). _(POST /api/olist/produtos/preco/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_tags_create`

Criar tags do produto (POST /produtos/{idProduto}/tags). _(POST /api/olist/produtos/tags/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_tags_delete`

Excluir tags do produto (DELETE /produtos/{idProduto}/tags). _(POST /api/olist/produtos/tags/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_tags_list`

Obter tags do produto (GET /produtos/{idProduto}/tags). _(POST /api/olist/produtos/tags/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_produtos_tags_update`

Atualizar tags do produto (PUT /produtos/{idProduto}/tags). _(POST /api/olist/produtos/tags/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_update`

Atualizar produto (PUT /produtos/{idProduto}). _(POST /api/olist/produtos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_variacoes_create`

Criar variação do produto (POST /produtos/{idProduto}/variacoes). _(POST /api/olist/produtos/variacoes/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_variacoes_delete`

Deletar variação do produto (DELETE /produtos/{idProduto}/variacoes/{idVariacao}). _(POST /api/olist/produtos/variacoes/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `idVariacao` | string | Sim | Path param "idVariacao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_produtos_variacoes_update`

Atualizar variação do produto (PUT /produtos/{idProduto}/variacoes/{idVariacao}). _(POST /api/olist/produtos/variacoes/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idProduto` | string | Sim | Path param "idProduto" (obrigatório) |
| `idVariacao` | string | Sim | Path param "idVariacao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_separacao_get`

Obter separação (GET /separacao/{idSeparacao}). _(POST /api/olist/separacao/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idSeparacao` | string | Sim | Path param "idSeparacao" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_separacao_list`

Listar separações (GET /separacao). _(POST /api/olist/separacao/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_separacao_situacao_update`

Alterar situação da separação (PUT /separacao/{idSeparacao}/situacao). _(POST /api/olist/separacao/situacao/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idSeparacao` | string | Sim | Path param "idSeparacao" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_servicos_create`

Criar serviço (POST /servicos). _(POST /api/olist/servicos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_servicos_delete`

Excluir serviço (DELETE /servicos/{idServico}). _(POST /api/olist/servicos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idServico` | string | Sim | Path param "idServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_servicos_get`

Obter serviço (GET /servicos/{idServico}). _(POST /api/olist/servicos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idServico` | string | Sim | Path param "idServico" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_servicos_list`

Listar serviços (GET /servicos). _(POST /api/olist/servicos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_servicos_transformar_produto_create`

Transformar serviço em produto (POST /servicos/{idServico}/transformar-produto). _(POST /api/olist/servicos/transformar/produto/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idServico` | string | Sim | Path param "idServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_servicos_update`

Atualizar serviço (PUT /servicos/{idServico}). _(POST /api/olist/servicos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `idServico` | string | Sim | Path param "idServico" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_tags_create`

Criar tags de produtos (POST /tags). _(POST /api/olist/tags/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Campos na doc da API Olist v3. |

#### `olist_tags_list`

Listar tags de produtos (GET /tags). _(POST /api/olist/tags/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_usuarios_list`

Listar usuários (GET /usuarios). _(POST /api/olist/usuarios/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

#### `olist_vendedores_list`

Listar vendedores (GET /vendedores). _(POST /api/olist/vendedores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Olist conectadas: company_id ou label da conexão. Veja olist_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação). Ex.: {"limit":50,"situacao":"aberto"}. Campos na doc da API Olist v3. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_olist` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
