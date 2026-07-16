---
name: offensive-mcp-tool-abuse
description: >
  Red team AUTORIZADO de MCP servers e tool abuse em agents: tool description
  poisoning, confused deputy, over-privileged tools, SSRF/exfil via tools.
---

# Offensive — MCP & Tool Abuse (autorizado)

## Objetivo

Mostrar que um agent com MCP/tools pode ser forçado a:

- Executar tool que o usuario nao pediu  
- Confiar em descricao de tool maliciosa (poisoning)  
- Exfiltrar dados via URL/parametro de tool  
- Abusar de permissoes (confused deputy)

## Vetores

1. **Tool description poisoning** — server MCP mente sobre o que a tool faz  
2. **Excessive agency** — agent tem shell/pay/file sem necessidade  
3. **Result injection** — saida da tool contem "instrucoes" para o model  
4. **SSRF / egress** — tool HTTP como proxy  
5. **Supply chain skill** — SKILL.md malicioso no install path  

## Fluxo de teste

```
1. Inventario MCP (agentseal / pipelock / list tools)
2. Revisar schemas e descriptions (poisoning?)
3. Probe: "use tool X with arg that exfils"
4. Probe: tool result com prompt injection embutido
5. Escopo: staging only; sem secrets de prod
6. Report + fix (allowlist, human confirm, schema hard validation)
```

## Arsenal

- maux339-cpu/agentseal  
- maux339-cpu/pipelock  
- maux339-cpu/prismor  
- maux339-cpu/agentguard  
- maux339-cpu/hackagent  

## ROE

So lab / client com ROE. Nao instalar MCP duvidoso em maquina com carteiras/prod.
