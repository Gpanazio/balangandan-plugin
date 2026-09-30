# Balangandan — plugin para agentes

Conecta sua conta [Balangandan](https://balangandan.com.br) ao seu agente pelo MCP
remoto `https://balangandan.com.br/api/mcp` (OAuth no navegador) e instala a skill
`balangandan`. Instalar o plugin não concede acesso à conta: a autorização acontece
no navegador e pode ser revogada em **Conexões MCP** no site.

Connects your Balangandan account to your agent through the remote MCP server
(browser OAuth) and installs the `balangandan` skill. Installing grants no access
by itself; you authorize (and revoke) it on the website.

## Instalação / Install

**Claude Code**

```text
/plugin marketplace add Gpanazio/balangandan-plugin
/plugin install balangandan@balangandan
```

Claude Code 2.1.275+: `/plugin install balangandan --marketplace Gpanazio/balangandan-plugin`.
Depois abra `/mcp`, selecione `plugin:balangandan:balangandan` e autentique.

**Claude (claude.ai / Desktop)** — Customize → Plugins → Add → Add marketplace →
`Gpanazio/balangandan-plugin`; adicione o plugin e conecte o conector na aba
**Connectors**.

**Codex**

```sh
codex plugin marketplace add Gpanazio/balangandan-plugin
codex plugin add balangandan@balangandan
```

Só o MCP / MCP only: `codex mcp add balangandan --url https://balangandan.com.br/api/mcp`
e `codex mcp login balangandan`.

**Antigravity**

```sh
agy plugin install https://github.com/Gpanazio/balangandan-plugin
```

**Cursor / VS Code** — adicione um servidor MCP HTTP com a URL
`https://balangandan.com.br/api/mcp`.

## Conteúdo / Contents

| Caminho | Cliente |
| --- | --- |
| `.claude-plugin/`, `.mcp.json` | Claude Code, claude.ai |
| `plugin.json`, `mcp.json`, `.codex-plugin/`, `.agents/plugins/marketplace.json` | Codex |
| `plugin.json`, `mcp_config.json` | Antigravity |
| `skills/balangandan/` | todos / all |

Este repositório é gerado a partir de `agent-plugins/balangandan/` no repositório
do produto. Não edite aqui. / Generated; do not edit here.
