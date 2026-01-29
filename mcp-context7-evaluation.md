# Avaliacao MCP Context7

## Data da Avaliacao
2026-01-29

## O que e o Context7?

O **Context7** e um servidor MCP (Model Context Protocol) desenvolvido pela Upstash que fornece documentacao atualizada e exemplos de codigo para LLMs e editores de codigo com IA.

### Problema que Resolve

LLMs possuem dados de treinamento desatualizados. Quando voce trabalha com bibliotecas modernas como Next.js 15, React 19, ou qualquer biblioteca que evoluiu apos a data de corte do modelo, voce pode receber APIs alucinadas e padroes obsoletos.

### Ferramentas Disponibilizadas pelo Context7

1. **resolve-library-id**: Recebe o nome de uma biblioteca (ex: "next.js") e retorna um ID do Context7 (ex: "/vercel/next.js/v15.0.0")

2. **get-library-docs**: Recebe um ID do Context7 e um filtro de topico opcional, retornando documentacao relevante e exemplos de codigo

## Status da Conexao

| Item | Status |
|------|--------|
| Ferramentas MCP do Context7 | **NAO DISPONIVEL** |
| resolve-library-id | Nao detectado |
| get-library-docs | Nao detectado |

## Diagnostico

O MCP Context7 **NAO esta configurado** neste ambiente. As ferramentas tipicas do Context7 (`resolve-library-id` e `get-library-docs`) nao estao disponiveis na lista de ferramentas MCP.

## Como Configurar o Context7

### Para Claude Code

```bash
claude mcp add context7 -- npx -y @upstash/context7-mcp --api-key YOUR_API_KEY
```

### Para Cursor

Adicionar ao arquivo `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "CONTEXT7_API_KEY": "YOUR_API_KEY"
      }
    }
  }
}
```

### Requisitos

- Node.js >= v18.0.0

## Como Usar (Apos Configuracao)

Basta dizer **"use context7"** no seu prompt para ativar a busca de documentacao atualizada.

Exemplo de uso especifico:
```
Use library /vercel/next.js/v15.4.0-canary.82 para implementar o app router
```

## Beneficios do Context7

- Documentacao atualizada e especifica por versao
- Exemplos de codigo funcionais
- Elimina APIs alucinadas e padroes obsoletos
- Especialmente util para frameworks que iteram rapidamente (Next.js, React, Vue, Astro)

## Recomendacao

Para utilizar o Context7 neste ambiente, e necessario:

1. Obter uma API key do Context7/Upstash
2. Configurar o servidor MCP usando o comando apropriado para seu ambiente
3. Reiniciar a sessao para que as ferramentas sejam carregadas

## Fontes

- [GitHub - Context7 MCP Server](https://github.com/upstash/context7)
- [Context7 no Smithery](https://smithery.ai/server/@upstash/context7-mcp)
- [Upstash Blog - Context7 MCP](https://upstash.com/blog/context7-mcp)
- [VS Code Marketplace - Context7](https://marketplace.visualstudio.com/items?itemName=Upstash.context7-mcp)
