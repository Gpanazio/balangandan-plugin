---
name: balangandan
description: Use when the user wants to connect Balangandan, consult their models, credits, projects or history, or generate and retrieve images, videos or audio through its MCP.
---

# Balangandan

Use o MCP autenticado da conta do usuário. Instalar esta skill não conecta a conta.
Para configurar, leia a referência do cliente: [Claude](references/claude.md),
[Codex](references/codex.md) ou [Antigravity](references/antigravity.md).
A URL correta é a exibida em **Conexões MCP** no site que o usuário utiliza.

## Ferramentas

Descubra as ferramentas e leia seus schemas atuais antes de chamar; o cliente pode
acrescentar um prefixo aos nomes abaixo. Não invente IDs, preços ou parâmetros.

| Necessidade | Ferramenta |
| --- | --- |
| Modelos e parâmetros aceitos | `catalog` |
| Créditos da conta | `balance` |
| Projetos existentes | `projects` |
| Gerações anteriores | `history` |
| Custo antes de gerar | `quote_generation` |
| Criar imagem, vídeo ou áudio | `generate_image`, `generate_video`, `generate_audio` |
| Acompanhar e recuperar arquivos | `task_result` |

## Gerar e entregar

1. Consulte catálogo e projeto escolhido. Use o ID retornado por `projects` como
   `project_id`; se o destino estiver ambíguo, esclareça antes da geração.
2. Consulte `quote_generation` com o mesmo modelo e parâmetros da geração e confira
   `balance`. Respeite o orçamento autorizado. Se faltar autorização de gasto ou
   a estimativa ultrapassar o limite, peça a decisão do usuário. Uma autorização
   já dada dentro desse limite continua válida.
3. Para gerar é necessário o escopo `generation:write`, autorizado no navegador.
   Crie um `request_id` único antes do envio e mantenha-o junto dos parâmetros.
   Cada criação intencional usa um ID novo; a repetição da mesma criação reutiliza
   exatamente o ID e os parâmetros originais.
4. Use o identificador devolvido pela geração em `task_result`. Aguarde com
   intervalos moderados. HTTP 200 ou aceite da tarefa não significa conclusão.
5. Entregue apenas arquivos que `task_result` confirmou como concluídos e disponíveis.
   Use os links duráveis devolvidos pela plataforma, preservando todos os resultados
   e sua ordem. Se ainda pendente, informe o ID e o estado real.

## Timeout e reconexão

Um timeout pode ocorrer depois da criação. Consulte o ID conhecido ou `history`.
Para recuperar a resposta, repita somente com o MESMO `request_id` e parâmetros.
Se vier `submit_unconfirmed`, mantenha esse estado: não gere com outro ID para
contornar a incerteza. Não declare falha ou sucesso sem evidência.

Se a conexão expirar, refaça OAuth no cliente. Se faltar permissão para gerar,
autorize a geração em uma nova conexão no site. Tokens e cookies ficam no cliente;
não os peça no chat nem os inclua em arquivos compartilhados.

Exemplo: “Uma imagem no projeto X, até 8 OVC” pede descoberta do modelo/projeto,
cotação até 8 OVC, envio único com `request_id` e acompanhamento até arquivo pronto.
