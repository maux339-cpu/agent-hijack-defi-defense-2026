---
name: agent-privilege-checklist
description: >
  Checklist de least privilege e HITL antes de colocar agent em produção
  (suporte, coding, research, trading). Use no go-live review.
---

# Agent Privilege + HITL Checklist

## Identidade do agent

- [ ] Nome / owner / ambiente (dev/stage/prod)
- [ ] Modelo(s) e provider
- [ ] Data do go-live

## Inputs (o que ele lê)

| Input | Confiável? | Fence DATA? |
|-------|------------|-------------|
| User chat | Parcial | sim |
| E-mail / ticket | Não | sim |
| Web scrape | Não | sim |
| PDF / upload | Não | sim |
| MCP tool result | Depende | sim |
| GitHub issue/PR | Não | sim |

## Tools (o que ele pode fazer)

| Tool | Irreversível? | HITL? | Limit |
|------|---------------|-------|-------|
| refund / pay | Sim | **Obrigatório** | max $ + rate |
| send_email | Médio | recomendado | allowlist |
| shell / code exec | Alto | sandbox | sem secrets |
| write DB | Médio | audit log | RBAC |
| browser | Médio | domain allowlist | — |

## Secrets

- [ ] Nenhuma API key no prompt  
- [ ] Tokens scoped + expiração  
- [ ] `.env` fora do workspace do agent se possível  
- [ ] MCP servers de terceiros auditados (AgentSeal)

## Go / No-go

**NO-GO se:**

- Tool de dinheiro sem HITL  
- Shell sem sandbox + untrusted input  
- MCP desconhecido com tools de rede/arquivo  

**GO se:**

- Fence DATA + least privilege + HITL em P0 + logs + testes promptfoo/garak  
