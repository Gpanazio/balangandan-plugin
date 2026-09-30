# Claude

## Skill

Extraia a pasta `balangandan` inteira do ZIP. No Claude Code, coloque-a em
`~/.claude/skills/balangandan/` (pessoal) ou `.claude/skills/balangandan/` (projeto).
Abra uma nova sessão e invoque `/balangandan`. Não sobrescreva uma instalação
personalizada sem preservar suas alterações.

No Claude com interface web, use o carregamento de skills nas configurações
quando disponível para sua conta. O ZIP contém `balangandan/SKILL.md` e referências.
A disponibilidade de skills e conectores depende do produto e da conta.

## MCP

Copie a URL em Conexões MCP no Balangandan. No Claude Code, substitua `URL_DO_MCP`
pelo endereço copiado:

```sh
claude mcp add --transport http balangandan URL_DO_MCP
```

Abra `/mcp`, selecione Balangandan e conclua a autenticação no navegador.
No Claude web, adicione a URL como conector remoto personalizado quando disponível.
Leia as permissões; geração é opcional e utiliza seus créditos. Confira a conexão
com `catalog` e `balance`, sem criar mídia. Revogue o acesso em Conexões MCP no site.

Fontes: [Skills](https://code.claude.com/docs/en/skills),
[MCP](https://code.claude.com/docs/en/mcp).
