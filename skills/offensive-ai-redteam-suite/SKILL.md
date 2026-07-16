---
name: offensive-ai-redteam-suite
description: >
  Indice de packs ofensivos do arsenal maux339-cpu para red team de LLMs,
  agents, web e DeFi. Uso autorizado / CTF / bounty apenas.
---

# Offensive AI Red Team Suite — Indice

## Packs SKILL.md (forks)

| Pack | Path / repo | Foco ofensivo |
|------|-------------|----------------|
| **Claude-Red** | maux339-cpu/Claude-Red | 100+ skills red team (AI, web, AD, exploit, fuzz...) |
| → `Skills/ai/offensive-ai-security` | dentro Claude-Red | AI/LLM security ofensivo |
| **hack-skills** | maux339-cpu/hack-skills | 100+ topics incl. `ai-ml-security` + SC patterns |
| **src-hunter-skill** | maux339-cpu/src-hunter-skill | SRC/bounty playbooks + payloads estruturados |
| **recon-skills** | maux339-cpu/recon-skills | Recon massivo |
| **Claude-BugHunter** | maux339-cpu/Claude-BugHunter | BB recon/exploit skills |
| **pombocyber-skills-cybersec** | maux339-cpu/pombocyber-skills-cybersec | Mega pack cybersec |
| **web3-bug-bounty-hunting-ai-skills** | maux339-cpu/web3-bug-bounty-hunting-ai-skills | Web3 BB |
| **.context** | maux339-cpu/.context | Skills audit SC reports/PoCs |
| **quillshield_skills** / **pashov-skills** / **trailofbits-skills** | forks | Audit/tradecraft |

## Frameworks / scanners (nao sao SKILL.md, mas ofensivos)

| Tool | Repo | Uso |
|------|------|-----|
| deepteam | maux339-cpu/deepteam | Red team LLM/agents |
| agentic_security | maux339-cpu/agentic_security | Scanner agentic |
| garak | maux339-cpu/garak | LLM vuln scanner |
| promptfoo | maux339-cpu/promptfoo | Red team prompts/CI |
| hackagent | maux339-cpu/hackagent | Vulns em agents |
| strix | maux339-cpu/strix | Agents pentest web |
| SCONE-bench | maux339-cpu/SCONE-bench | Bench exploit SC+LLM |
| scone-bench-1 | maux339-cpu/scone-bench-1 | Anthropic SCONE |
| handbook | maux339-cpu/ai-llm-red-team-handbook | Manual metodologico |

## Skills locais deste repo (ofensivas)

1. `offensive-agent-prompt-injection`  
2. `offensive-mcp-tool-abuse`  
3. `offensive-defi-ai-exploit-hunt`  
4. `offensive-ai-redteam-suite` (este indice)

## Skills locais defensivas (par)

- agent-goal-hijack-defense  
- prompt-injection-authorized-test  
- defi-ai-audit-hunt  
- agent-privilege-checklist  

## Ordem de install (quando autorizar em maquina lab)

```text
1. Ler SKILL.md de cada pack (supply-chain risk)
2. Preferir copia seletiva: so AI + DeFi skills necessarias
3. Nao carregar EDR-evasion / malware skills em host com wallets
4. Rodar agentseal / scanner de skills se disponivel
5. Sandbox / VM dedicada
```

## Playbook rapido

| Missao | Skills / tools |
|--------|----------------|
| Quebrar support bot | offensive-agent-prompt-injection + deepteam + promptfoo |
| MCP host | offensive-mcp-tool-abuse + agentseal + pipelock |
| Audit SC ofensivo | offensive-defi-ai-exploit-hunt + foundry + slither + SCONE |
| Full red team LLM | Claude-Red offensive-ai + garak + agentic_security + handbook |
| BB web | src-hunter-skill + strix + recon-skills |

## Disclaimer

Material de **pentest autorizado, CTF, bug bounty e pesquisa**.  
Nao use para atividade ilegal.
