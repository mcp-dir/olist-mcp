# Changelog

Segue [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) e [SemVer](https://semver.org/).

## [Unreleased]

### Corrigido
- Docs listavam 1 ferramenta (`search_tools`) somente leitura. O servidor expõe 179 ferramentas da API Olist v3 (73 de leitura, 106 de escrita) mais as da plataforma. `docs/ferramentas.md` agora lista todas por área, marcando as de escrita
- Removida a afirmação de "somente leitura" do README, README.en, LGPD e SECURITY; tag `read-only` do smithery trocada por `read-write`
- Descrição do `server.json` estava cortada no limite de 100 caracteres

## [0.1.0] — 2026-06-10

### Adicionado
- Lançamento público do repositório
- 1 ferramenta: `search_tools`
- Manifestos pra Claude Desktop, Cursor e VS Code (config única, auth em runtime)
- Skill geral pra agentes (`olist-mcp`)
- Documentação PT-BR + README EN
