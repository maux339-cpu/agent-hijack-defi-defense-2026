---
name: agent-goal-hijack-defense
description: >
  Auditoria defensiva de agentes de IA contra goal hijacking e prompt injection
  indireto (e-mail, web, PDF, tool output). Use quando o agent tem tools que
  gastam dinheiro, reembolsam, assinam, enviam e-mail ou executam shell.
---

# Agent Goal Hijack — Defesa

## Objetivo

Garantir que **texto não confiável** nunca vire **comando** do agente, e que
ações irreversíveis tenham **humano no loop**.

## Escopo (autorizado)

- Agents/produtos sob seu controle ou com autorização escrita
- Design review, red team contratado, bug bounty

## Checklist rápido

1. **Mapa de superfície**
   - Quais inputs o agent lê? (user, e-mail, web scrape, PDF, RAG, MCP, issue GitHub)
   - Quais tools pode chamar? (refund, transfer, shell, e-mail, write file)
   - O que é irreversível sem HITL?

2. **Separação DATA vs COMMAND**
   - Untrusted content entra em delimitadores claros (`<data>...</data>`)
   - System prompt proíbe obedecer instruções dentro de DATA
   - Preferir arquitetura que **não** concatena system + untrusted em um blob

3. **Least privilege**
   - Tool de pagamento: valor máximo + allowlist de destinos + rate limit
   - Sem shell se não for coding agent em sandbox
   - Secrets fora do contexto do modelo (vault / scoped tokens)

4. **Humano no loop (HITL)**
   - Qualquer refund / wire / crypto transfer / change-of-beneficiary exige aprovação
   - Logs legíveis do que o agent leu **antes** de agir

5. **Testes**
   - Rodar `promptfoo` ou `garak` com casos de injection indireto
   - `agentseal scan` no system prompt e configs MCP
   - Casos: "ignore previous instructions", texto branco-no-branco, README malicioso, issue com payload

## Sinais de risco (P0)

- Agent com API de pagamento e **zero** HITL
- Tool `run_shell` + leitura de issues/PRs/web sem sandbox
- MCP server de terceiros sem audit (tool description poisoning)
- RAG que injeta trechos web no prompt sem fence

## Output esperado

Relatório curto:

| Achado | Severidade | Superfície | Fix |
|--------|------------|------------|-----|
| ... | P0/P1/P2 | e-mail→refund | HITL + fence DATA |

## Ferramentas do arsenal

- `maux339-cpu/agentseal`
- `maux339-cpu/promptfoo`
- `maux339-cpu/garak`
- `maux339-cpu/rebuff`
- Índice: `maux339-cpu/agent-hijack-defi-defense-2026`
