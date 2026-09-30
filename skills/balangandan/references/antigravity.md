# Antigravity

Extraia a pasta `balangandan` inteira em `.agents/skills/balangandan/` no projeto.
Para instalação pessoal, o Antigravity 2.0/IDE usa
`~/.gemini/config/skills/balangandan/`; a CLI usa
`~/.gemini/antigravity-cli/skills/balangandan/`. Preserve alterações existentes.
Abra uma nova sessão e peça para usar a skill Balangandan.

No IDE, abra **MCP Servers → Manage MCP Servers → View raw config**.
Adicione uma entrada ao objeto `mcpServers` existente, preservando os demais
servidores. Substitua `URL_DO_MCP` pela URL copiada de Conexões MCP no site:

```json
{
  "mcpServers": {
    "balangandan": { "serverUrl": "URL_DO_MCP" }
  }
}
```

O arquivo global atual é `~/.gemini/config/mcp_config.json`; o de projeto é
`.agents/mcp_config.json`. Recarregue os servidores e conclua o OAuth solicitado
no navegador. Não cole cookies nem tokens no arquivo. Confira `catalog` e
`balance`; autorize geração somente se desejada. Revogue a conexão no site.

Fontes: [Skills](https://antigravity.google/docs/skills),
[MCP](https://antigravity.google/docs/mcp?tab=ide).
