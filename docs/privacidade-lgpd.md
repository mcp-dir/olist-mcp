# Privacidade & LGPD

Olist Tiny ERP segue a LGPD (Lei nº 13.709/2018).

## Princípios

1. **Escrita só quando você pede** — 73 ferramentas só consultam; 106 criam, alteram ou excluem dados no Olist (lista em [ferramentas.md](ferramentas.md)). Configure seu cliente pra pedir confirmação antes das de escrita.
2. **Mínimo necessário** — só os dados que a ferramenta pede.
3. **Você no controle** — desconectar / excluir conta a qualquer momento em `app.mcp.ai`.

## Sub-processadores

| Sub-processador | País | Papel |
|---|---|---|
| **Olist (Tiny)** | BR | ERP de e-commerce + API (provedor dos dados do usuário) |
| **LLM host escolhido por você** (Claude, ChatGPT, Cursor, agente próprio) | varia | Consumidor dos dados |

> ⚠️ O LLM host que você escolher é um sub-processador **fora do nosso controle**. Os dados retornados pelas tools são enviados pra ele a cada chamada. Recomendamos planos com opt-out de treinamento.

## Seus direitos (LGPD)

Acessar, corrigir, eliminar, portar, revogar consentimento. Contato: [olist@mcp.ai](mailto:olist@mcp.ai). Reclamações: [ANPD](https://www.gov.br/anpd/pt-br).

**Última atualização**: 2026-11-08.
