# Ferramentas

Olist Tiny ERP expõe **179 ferramentas** da API REST v3 do Olist Tiny, mais algumas ferramentas da plataforma MCP.AI.

- **73 de leitura**: consultam dados (`GET` na API Olist) e não alteram nada no ERP.
- **106 de escrita**: criam, alteram ou excluem dados no ERP (`POST`, `PUT` e `DELETE` na API Olist). Isso inclui emitir e cancelar notas fiscais, baixar contas a receber, lançar estoque e mudar a situação de pedidos.

> ⚠️ As ferramentas de escrita agem na sua conta Olist de verdade. Algumas operações, como emitir ou cancelar NF-e, têm efeito fiscal e não podem ser desfeitas. Configure seu cliente MCP para pedir confirmação antes de chamar ferramentas de escrita.

Quase todas as ferramentas aceitam `account` (company_id ou label, quando há mais de uma empresa Olist conectada; veja `olist_list_accounts`). As de leitura em lista aceitam `query` (filtros e paginação como JSON string) e as de escrita aceitam `body` (campos do recurso como JSON string). Parâmetros de cada ferramenta: [skills/olist-mcp/SKILL.md](../skills/olist-mcp/SKILL.md).

## Ferramentas da plataforma

| Ferramenta | Descrição |
|---|---|
| `connect` | Mostra o status da conexão e os links pra autorizar a conta Olist. |
| `show_version` | Mostra a versão da plataforma e do adaptador Olist. |
| `toolkit_info` | Informações sobre o toolkit instalado. |
| `marketplace` | Busca e executa outros MCPs do catálogo mcp.ai. |
| `report_bug` | Reporta um erro ou resultado inesperado ao time da MCP.AI. |

## Pedidos de venda

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_pedidos_create` | **Escrita** | Criar pedido (POST /pedidos). |
| `olist_pedidos_despacho_update` | **Escrita** | Atualizar informações de rastreamento do pedido (PUT /pedidos/{idPedido}/despacho). |
| `olist_pedidos_estornar_contas_create` | **Escrita** | Estornar contas do pedido (POST /pedidos/{idPedido}/estornar-contas). |
| `olist_pedidos_estornar_estoque_create` | **Escrita** | Estornar estoque do pedido (POST /pedidos/{idPedido}/estornar-estoque). |
| `olist_pedidos_gerar_nota_fiscal_create` | **Escrita** | Gerar nota fiscal do pedido (POST /pedidos/{idPedido}/gerar-nota-fiscal). |
| `olist_pedidos_gerar_ordem_producao_create` | **Escrita** | Gerar ordem de produção do pedido (POST /pedidos/{idPedido}/gerar-ordem-producao). |
| `olist_pedidos_get` | Leitura | Obter pedido (GET /pedidos/{idPedido}). |
| `olist_pedidos_itens_update` | **Escrita** | Atualizar itens do pedido (PUT /pedidos/{idPedido}/itens). |
| `olist_pedidos_lancar_contas_create` | **Escrita** | Lançar contas do pedido (POST /pedidos/{idPedido}/lancar-contas). |
| `olist_pedidos_lancar_estoque_create` | **Escrita** | Lançar estoque do pedido (POST /pedidos/{idPedido}/lancar-estoque). |
| `olist_pedidos_list` | Leitura | Listar pedidos (GET /pedidos). |
| `olist_pedidos_marcadores_create` | **Escrita** | Criar marcadores do pedido (POST /pedidos/{idPedido}/marcadores). |
| `olist_pedidos_marcadores_delete` | **Escrita** | Excluir marcadores do pedido (DELETE /pedidos/{idPedido}/marcadores). |
| `olist_pedidos_marcadores_list` | Leitura | Obter marcadores do pedido (GET /pedidos/{idPedido}/marcadores). |
| `olist_pedidos_marcadores_update` | **Escrita** | Atualizar marcadores do pedido (PUT /pedidos/{idPedido}/marcadores). |
| `olist_pedidos_situacao_update` | **Escrita** | Atualizar situação do pedido (PUT /pedidos/{idPedido}/situacao). |
| `olist_pedidos_update` | **Escrita** | Atualizar pedido (PUT /pedidos/{idPedido}). |

## Produtos

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_produtos_create` | **Escrita** | Criar produto (POST /produtos). |
| `olist_produtos_custos_list` | Leitura | Listar custos do produto (GET /produtos/{idProduto}/custos). |
| `olist_produtos_delete` | **Escrita** | Excluir produto (DELETE /produtos/{idProduto}). |
| `olist_produtos_fabricado_list` | Leitura | Obter produto fabricado (GET /produtos/{idProduto}/fabricado). |
| `olist_produtos_fabricado_update` | **Escrita** | Atualizar produto fabricado (PUT /produtos/{idProduto}/fabricado). |
| `olist_produtos_get` | Leitura | Obter produto (GET /produtos/{idProduto}). |
| `olist_produtos_kit_list` | Leitura | Obter produto kit (GET /produtos/{idProduto}/kit). |
| `olist_produtos_kit_update` | **Escrita** | Atualizar kit do produto (PUT /produtos/{idProduto}/kit). |
| `olist_produtos_list` | Leitura | Listar produtos (GET /produtos). |
| `olist_produtos_preco_update` | **Escrita** | Atualizar preço do produto (PUT /produtos/{idProduto}/preco). |
| `olist_produtos_tags_create` | **Escrita** | Criar tags do produto (POST /produtos/{idProduto}/tags). |
| `olist_produtos_tags_delete` | **Escrita** | Excluir tags do produto (DELETE /produtos/{idProduto}/tags). |
| `olist_produtos_tags_list` | Leitura | Obter tags do produto (GET /produtos/{idProduto}/tags). |
| `olist_produtos_tags_update` | **Escrita** | Atualizar tags do produto (PUT /produtos/{idProduto}/tags). |
| `olist_produtos_update` | **Escrita** | Atualizar produto (PUT /produtos/{idProduto}). |
| `olist_produtos_variacoes_create` | **Escrita** | Criar variação do produto (POST /produtos/{idProduto}/variacoes). |
| `olist_produtos_variacoes_delete` | **Escrita** | Deletar variação do produto (DELETE /produtos/{idProduto}/variacoes/{idVariacao}). |
| `olist_produtos_variacoes_update` | **Escrita** | Atualizar variação do produto (PUT /produtos/{idProduto}/variacoes/{idVariacao}). |

## Estoque e depósitos

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_depositos_get` | Leitura | Obter depósito de estoque por ID (GET /depositos/{idDeposito}). |
| `olist_depositos_list` | Leitura | Listar depósitos de estoque (GET /depositos). |
| `olist_estoque_create` | **Escrita** | Atualizar o estoque de um produto (POST /estoque/{idProduto}). |
| `olist_estoque_get` | Leitura | Obter o estoque de um produto (GET /estoque/{idProduto}). |

## Notas fiscais (NF-e / NFC-e)

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_notas_despacho_update` | **Escrita** | Atualizar informações de rastreamento da nota fiscal (PUT /notas/{idNota}/despacho). |
| `olist_notas_emitir_create` | **Escrita** | Autorizar nota fiscal (POST /notas/{idNota}/emitir). |
| `olist_notas_get` | Leitura | Obter nota fiscal (GET /notas/{idNota}). |
| `olist_notas_itens_get` | Leitura | Obter item da nota fiscal (GET /notas/{idNota}/itens/{idItem}). |
| `olist_notas_lancar_contas_create` | **Escrita** | Lançar contas da nota fiscal (POST /notas/{idNota}/lancar-contas). |
| `olist_notas_lancar_estoque_create` | **Escrita** | Lançar estoque da nota fiscal (POST /notas/{idNota}/lancar-estoque). |
| `olist_notas_link_list` | Leitura | Obter link da nota fiscal (GET /notas/{idNota}/link). |
| `olist_notas_list` | Leitura | Listar notas fiscais (GET /notas). |
| `olist_notas_marcadores_create` | **Escrita** | Criar marcadores da nota fiscal (POST /notas/{idNota}/marcadores). |
| `olist_notas_marcadores_delete` | **Escrita** | Excluir marcadores da nota fiscal (DELETE /notas/{idNota}/marcadores). |
| `olist_notas_marcadores_list` | Leitura | Obter marcadores da nota fiscal (GET /notas/{idNota}/marcadores). |
| `olist_notas_marcadores_update` | **Escrita** | Atualizar marcadores da nota fiscal (PUT /notas/{idNota}/marcadores). |
| `olist_notas_nota_fiscal_consumidor_xml_create` | **Escrita** | Incluir nota fiscal de consumidor por XML (POST /notas/nota-fiscal-consumidor/xml). |
| `olist_notas_xml_cancelar_create` | **Escrita** | Cancelar nota fiscal (POST /notas/xml/cancelar). |
| `olist_notas_xml_create` | **Escrita** | Incluir nota fiscal por XML (POST /notas/xml). |
| `olist_notas_xml_fornecedor_create` | **Escrita** | Incluir nota fiscal de fornecedor por XML (POST /notas/xml/fornecedor). |
| `olist_notas_xml_list` | Leitura | Obter XML da nota fiscal (GET /notas/{idNota}/xml). |

## Contas a pagar

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_contas_pagar_create` | **Escrita** | Criar conta a pagar (POST /contas-pagar). |
| `olist_contas_pagar_get` | Leitura | Obter conta a pagar (GET /contas-pagar/{idContaPagar}). |
| `olist_contas_pagar_list` | Leitura | Listar contas a pagar (GET /contas-pagar). |
| `olist_contas_pagar_marcadores_create` | **Escrita** | Criar marcadores da conta a pagar (POST /contas-pagar/{idContaPagar}/marcadores). |
| `olist_contas_pagar_marcadores_delete` | **Escrita** | Excluir marcadores da conta a pagar (DELETE /contas-pagar/{idContaPagar}/marcadores). |
| `olist_contas_pagar_marcadores_list` | Leitura | Obter marcadores da conta a pagar (GET /contas-pagar/{idContaPagar}/marcadores). |
| `olist_contas_pagar_marcadores_update` | **Escrita** | Atualizar marcadores da conta a pagar (PUT /contas-pagar/{idContaPagar}/marcadores). |
| `olist_contas_pagar_recebimentos_list` | Leitura | Obter recebimentos da conta a pagar (GET /contas-pagar/{idContaPagar}/recebimentos). |

## Contas a receber

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_contas_receber_baixar_create` | **Escrita** | Baixar uma conta a receber (POST /contas-receber/{idContaReceber}/baixar). |
| `olist_contas_receber_create` | **Escrita** | Criar conta a receber (POST /contas-receber). |
| `olist_contas_receber_get` | Leitura | Obter conta a receber (GET /contas-receber/{idContaReceber}). |
| `olist_contas_receber_list` | Leitura | Listar contas a receber (GET /contas-receber). |
| `olist_contas_receber_marcadores_create` | **Escrita** | Criar marcadores da conta a receber (POST /contas-receber/{idContaReceber}/marcadores). |
| `olist_contas_receber_marcadores_delete` | **Escrita** | Excluir marcadores da conta a receber (DELETE /contas-receber/{idContaReceber}/marcadores). |
| `olist_contas_receber_marcadores_list` | Leitura | Obter marcadores da conta a receber (GET /contas-receber/{idContaReceber}/marcadores). |
| `olist_contas_receber_marcadores_update` | **Escrita** | Atualizar marcadores da conta a receber (PUT /contas-receber/{idContaReceber}/marcadores). |
| `olist_contas_receber_recebimentos_list` | Leitura | Obter recebimentos da conta a receber (GET /contas-receber/{idContaReceber}/recebimentos). |
| `olist_contas_receber_update` | **Escrita** | Atualizar conta a receber (PUT /contas-receber/{idContaReceber}). |

## Contatos

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_contatos_create` | **Escrita** | Criar contato (POST /contatos). |
| `olist_contatos_get` | Leitura | Obter contato (GET /contatos/{idContato}). |
| `olist_contatos_list` | Leitura | Listar contatos (GET /contatos). |
| `olist_contatos_pessoas_create` | **Escrita** | Criar pessoa de contato (POST /contatos/{idContato}/pessoas). |
| `olist_contatos_pessoas_delete` | **Escrita** | Excluir pessoa de contato (DELETE /contatos/{idContato}/pessoas/{idPessoa}). |
| `olist_contatos_pessoas_get` | Leitura | Obter pessoa de contato (GET /contatos/{idContato}/pessoas/{idPessoa}). |
| `olist_contatos_pessoas_list` | Leitura | Listar pessoas de contato (GET /contatos/{idContato}/pessoas). |
| `olist_contatos_pessoas_update` | **Escrita** | Atualizar pessoa de contato (PUT /contatos/{idContato}/pessoas/{idPessoa}). |
| `olist_contatos_status_crm_update` | **Escrita** | Atualizar status CRM do contato (PUT /contatos/{idContato}/status-crm). |
| `olist_contatos_tipos_list` | Leitura | Listar tipos de contatos (GET /contatos/tipos). |
| `olist_contatos_update` | **Escrita** | Atualizar contato (PUT /contatos/{idContato}). |

## CRM

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_crm_assuntos_acoes_create` | **Escrita** | Criar ação de assunto (POST /crm/assuntos/{idAssunto}/acoes). |
| `olist_crm_assuntos_acoes_delete` | **Escrita** | Deletar ação de um assunto (DELETE /crm/assuntos/{idAssunto}/acoes/{idAcao}). |
| `olist_crm_assuntos_acoes_get` | Leitura | Obter ação de um assunto (GET /crm/assuntos/{idAssunto}/acoes/{idAcao}). |
| `olist_crm_assuntos_acoes_list` | Leitura | Listar ações de um assunto (GET /crm/assuntos/{idAssunto}/acoes). |
| `olist_crm_assuntos_acoes_update` | **Escrita** | Atualizar ação de assunto (PUT /crm/assuntos/{idAssunto}/acoes/{idAcao}). |
| `olist_crm_assuntos_anotacoes_create` | **Escrita** | Criar anotação de assunto (POST /crm/assuntos/{idAssunto}/anotacoes). |
| `olist_crm_assuntos_anotacoes_delete` | **Escrita** | Deletar anotação de assunto (DELETE /crm/assuntos/{idAssunto}/anotacoes/{idAnotacao}). |
| `olist_crm_assuntos_anotacoes_list` | Leitura | Listar anotações de um assunto (GET /crm/assuntos/{idAssunto}/anotacoes). |
| `olist_crm_assuntos_anotacoes_update` | **Escrita** | Atualizar anotação de assunto (PUT /crm/assuntos/{idAssunto}/anotacoes/{idAnotacao}). |
| `olist_crm_assuntos_arquivar_update` | **Escrita** | Arquivar ou desarquivar assunto (PUT /crm/assuntos/{idAssunto}/arquivar). |
| `olist_crm_assuntos_create` | **Escrita** | Criar assunto (POST /crm/assuntos). |
| `olist_crm_assuntos_delete` | **Escrita** | Deletar assunto (DELETE /crm/assuntos/{idAssunto}). |
| `olist_crm_assuntos_estrela_update` | **Escrita** | Atualizar estrela do assunto (PUT /crm/assuntos/{idAssunto}/estrela). |
| `olist_crm_assuntos_get` | Leitura | Obter assunto (GET /crm/assuntos/{idAssunto}). |
| `olist_crm_assuntos_list` | Leitura | Listar assuntos (GET /crm/assuntos). |
| `olist_crm_assuntos_marcadores_create` | **Escrita** | Criar marcadores do assunto (POST /crm/assuntos/{idAssunto}/marcadores). |
| `olist_crm_assuntos_marcadores_delete` | **Escrita** | Remover marcadores de um assunto (DELETE /crm/assuntos/{idAssunto}/marcadores). |
| `olist_crm_assuntos_marcadores_list` | Leitura | Listar marcadores de um assunto (GET /crm/assuntos/{idAssunto}/marcadores). |
| `olist_crm_assuntos_marcadores_update` | **Escrita** | Atualizar marcadores do assunto (PUT /crm/assuntos/{idAssunto}/marcadores). |
| `olist_crm_assuntos_update` | **Escrita** | Atualizar assunto (PUT /crm/assuntos/{idAssunto}). |
| `olist_crm_estagios_create` | **Escrita** | Criar estágio (POST /crm/estagios). |
| `olist_crm_estagios_delete` | **Escrita** | Deletar estágio (DELETE /crm/estagios/{idEstagio}). |
| `olist_crm_estagios_get` | Leitura | Obter estágio (GET /crm/estagios/{idEstagio}). |
| `olist_crm_estagios_list` | Leitura | Listar estágios (GET /crm/estagios). |
| `olist_crm_estagios_update` | **Escrita** | Atualizar estágio (PUT /crm/estagios/{idEstagio}). |

## Expedição e separação

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_expedicao_concluir_create` | **Escrita** | Concluir um agrupamento de expedição (POST /expedicao/{idAgrupamento}/concluir). |
| `olist_expedicao_create` | **Escrita** | Criar agrupamento de expedição (POST /expedicao). |
| `olist_expedicao_etiquetas_list` | Leitura | Obter etiquetas de um agrupamento de expedição (GET /expedicao/{idAgrupamento}/etiquetas). |
| `olist_expedicao_expedicao_etiquetas_list` | Leitura | Obter etiquetas de uma expedição dentro de um agrupamento (GET /expedicao/{idAgrupamento}/expedicao/{idExpedicao}/etiquetas). |
| `olist_expedicao_expedicao_update` | **Escrita** | Alterar uma expedição dentro de um agrupamento (PUT /expedicao/{idAgrupamento}/expedicao/{idExpedicao}). |
| `olist_expedicao_get` | Leitura | Obter agrupamento de expedição (GET /expedicao/{idAgrupamento}). |
| `olist_expedicao_list` | Leitura | Listar agrupamentos de expedição (GET /expedicao). |
| `olist_expedicao_origens_create` | **Escrita** | Adicionar origens a um agrupamento de expedição (POST /expedicao/{idAgrupamento}/origens). |
| `olist_separacao_get` | Leitura | Obter separação (GET /separacao/{idSeparacao}). |
| `olist_separacao_list` | Leitura | Listar separações (GET /separacao). |
| `olist_separacao_situacao_update` | **Escrita** | Alterar situação da separação (PUT /separacao/{idSeparacao}/situacao). |

## Ordens de compra

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_ordem_compra_create` | **Escrita** | Criar ordem de compra (POST /ordem-compra). |
| `olist_ordem_compra_get` | Leitura | Obter ordem de compra (GET /ordem-compra/{idOrdemCompra}). |
| `olist_ordem_compra_lancar_contas_create` | **Escrita** | Lançar contas da ordem de compra (POST /ordem-compra/{idOrdemCompra}/lancar-contas). |
| `olist_ordem_compra_lancar_estoque_create` | **Escrita** | Lançar estoque da ordem de compra (POST /ordem-compra/{idOrdemCompra}/lancar-estoque). |
| `olist_ordem_compra_list` | Leitura | Listar ordens de compra (GET /ordem-compra). |
| `olist_ordem_compra_marcadores_create` | **Escrita** | Criar marcadores da ordem de compra (POST /ordem-compra/{idOrdemCompra}/marcadores). |
| `olist_ordem_compra_marcadores_delete` | **Escrita** | Excluir marcadores da ordem de compra (DELETE /ordem-compra/{idOrdemCompra}/marcadores). |
| `olist_ordem_compra_marcadores_list` | Leitura | Obter marcadores da ordem de compra (GET /ordem-compra/{idOrdemCompra}/marcadores). |
| `olist_ordem_compra_marcadores_update` | **Escrita** | Atualizar marcadores da ordem de compra (PUT /ordem-compra/{idOrdemCompra}/marcadores). |
| `olist_ordem_compra_situacao_update` | **Escrita** | Atualizar situação da ordem de compra (PUT /ordem-compra/{idOrdemCompra}/situacao). |
| `olist_ordem_compra_update` | **Escrita** | Atualizar ordem de compra (PUT /ordem-compra/{idOrdemCompra}). |

## Ordens de serviço

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_ordem_servico_create` | **Escrita** | Criar ordem de serviço (POST /ordem-servico). |
| `olist_ordem_servico_gerar_nota_fiscal_create` | **Escrita** | Gerar nota fiscal para a ordem de serviço (POST /ordem-servico/{idOrdemServico}/gerar-nota-fiscal). |
| `olist_ordem_servico_get` | Leitura | Obter ordem de serviço (GET /ordem-servico/{idOrdemServico}). |
| `olist_ordem_servico_lancar_contas_create` | **Escrita** | Lançar contas da ordem de serviço (POST /ordem-servico/{idOrdemServico}/lancar-contas). |
| `olist_ordem_servico_lancar_estoque_create` | **Escrita** | Lançar estoque da ordem de serviço (POST /ordem-servico/{idOrdemServico}/lancar-estoque). |
| `olist_ordem_servico_list` | Leitura | Listar ordem de serviço (GET /ordem-servico). |
| `olist_ordem_servico_marcadores_create` | **Escrita** | Criar marcadores da ordem de serviço (POST /ordem-servico/{idOrdemServico}/marcadores). |
| `olist_ordem_servico_marcadores_delete` | **Escrita** | Excluir marcadores da ordem de serviço (DELETE /ordem-servico/{idOrdemServico}/marcadores). |
| `olist_ordem_servico_marcadores_list` | Leitura | Obter marcadores da ordem de serviço (GET /ordem-servico/{idOrdemServico}/marcadores). |
| `olist_ordem_servico_marcadores_update` | **Escrita** | Atualizar marcadores da ordem de serviço (PUT /ordem-servico/{idOrdemServico}/marcadores). |
| `olist_ordem_servico_situacao_update` | **Escrita** | Atualizar situação da ordem de serviço (PUT /ordem-servico/{idOrdemServico}/situacao). |
| `olist_ordem_servico_update` | **Escrita** | Atualizar ordem de serviço (PUT /ordem-servico/{idOrdemServico}). |

## Serviços

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_servicos_create` | **Escrita** | Criar serviço (POST /servicos). |
| `olist_servicos_delete` | **Escrita** | Excluir serviço (DELETE /servicos/{idServico}). |
| `olist_servicos_get` | Leitura | Obter serviço (GET /servicos/{idServico}). |
| `olist_servicos_list` | Leitura | Listar serviços (GET /servicos). |
| `olist_servicos_transformar_produto_create` | **Escrita** | Transformar serviço em produto (POST /servicos/{idServico}/transformar-produto). |
| `olist_servicos_update` | **Escrita** | Atualizar serviço (PUT /servicos/{idServico}). |

## Listas de preços

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_listas_precos_create` | **Escrita** | Criar lista de preços (POST /listas-precos). |
| `olist_listas_precos_get` | Leitura | Obter lista de preços (GET /listas-precos/{idListaDePreco}). |
| `olist_listas_precos_list` | Leitura | Listar listas de preços (GET /listas-precos). |
| `olist_listas_precos_produtos_delete` | **Escrita** | Excluir produto de lista de preços (DELETE /listas-precos/{idListaDePreco}/produtos/{idProduto}). |
| `olist_listas_precos_update` | **Escrita** | Atualizar lista de preços (PUT /listas-precos/{idListaDePreco}). |

## Categorias, marcas e tags

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_categorias_create` | **Escrita** | Criar categoria de produto (POST /categorias). |
| `olist_categorias_delete` | **Escrita** | Excluir categoria de produto (DELETE /categorias/{idCategoria}). |
| `olist_categorias_get` | Leitura | Obter categoria por identificador (GET /categorias/{idCategoria}). |
| `olist_categorias_receita_despesa_list` | Leitura | Listar categorias de receita e despesa (GET /categorias-receita-despesa). |
| `olist_categorias_todas_list` | Leitura | Listar árvore de categorias (GET /categorias/todas). |
| `olist_categorias_update` | **Escrita** | Editar categoria de produto (PUT /categorias/{idCategoria}). |
| `olist_grupos_tags_list` | Leitura | Listar grupos de tags (GET /grupos-tags). |
| `olist_marcas_create` | **Escrita** | Criar marca (POST /marcas). |
| `olist_marcas_list` | Leitura | Listar marcas (GET /marcas). |
| `olist_marcas_update` | **Escrita** | Atualizar marca (PUT /marcas/{idMarca}). |
| `olist_tags_create` | **Escrita** | Criar tags de produtos (POST /tags). |
| `olist_tags_list` | Leitura | Listar tags de produtos (GET /tags). |

## Formas de pagamento, recebimento e envio

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_formas_envio_get` | Leitura | Obter forma de envio (GET /formas-envio/{idFormaEnvio}). |
| `olist_formas_envio_list` | Leitura | Listar formas de envio (GET /formas-envio). |
| `olist_formas_pagamento_get` | Leitura | Obter forma de pagamento (GET /formas-pagamento/{idFormaPagamento}). |
| `olist_formas_pagamento_list` | Leitura | Listar formas de pagamento (GET /formas-pagamento). |
| `olist_formas_recebimento_get` | Leitura | Obter forma de recebimento (GET /formas-recebimento/{idFormaRecebimento}). |
| `olist_formas_recebimento_list` | Leitura | Listar formas de recebimento (GET /formas-recebimento). |
| `olist_intermediadores_get` | Leitura | Obter intermediador (GET /intermediadores/{idIntermediador}). |
| `olist_intermediadores_list` | Leitura | Listar intermediadores (GET /intermediadores). |

## Conta, usuários e vendedores

| Ferramenta | Tipo | Descrição |
|---|---|---|
| `olist_info_list` | Leitura | Obter informações da conta da empresa (GET /info). |
| `olist_list_accounts` | Leitura | Lista as conexões (empresas) Olist vinculadas a este install — company_id, label. |
| `olist_usuarios_list` | Leitura | Listar usuários (GET /usuarios). |
| `olist_vendedores_list` | Leitura | Listar vendedores (GET /vendedores). |

## Prompts de exemplo

```
Liste os pedidos de venda dos últimos 7 dias
Qual o estoque atual do produto X?
Quais contas a receber estão em aberto este mês?
```
