# Codex

Extraia a pasta `balangandan` inteira em `~/.agents/skills/balangandan/` para uso
pessoal ou `.agents/skills/balangandan/` no projeto. Preserve instalações existentes.
Abra uma nova sessão e mencione `$balangandan`.

Copie a URL exibida em Conexões MCP no site. Substitua `URL_DO_MCP` pelo endereço:

```sh
codex mcp add balangandan --url URL_DO_MCP
codex mcp login balangandan --scopes platform:read,generation:write
```

Conclua OAuth no navegador. Para consultas apenas, solicite `platform:read`.
O consentimento no site permite deixar a geração desmarcada. No app, também é
possível configurar o servidor HTTP nas configurações de MCP.

Confira `catalog` e `balance`. Nunca use uma geração paga como teste de conexão.
A instalação da skill e a autenticação MCP são etapas independentes.
Revogue o acesso em Conexões MCP no site.

Referências: `codex mcp add --help`, `codex mcp login --help` e
[documentação de skills](https://developers.openai.com/codex/skills).
