# Agent Hijack + DeFi AI Defense (2026)

**Wave 6** do arsenal `maux339-cpu` — inventário de skills/ferramentas citadas no **X (Twitter)** + GitHub, focado em:

1. **Sequestro de agentes de IA** (goal hijacking / prompt injection / tool misuse)  
2. **Caça automática a vulnerabilidades DeFi** (agentes ofensivos em smart contracts)

> **Uso:** pesquisa autorizada, red team com permissão, defesa de produtos próprios e bug bounty legítimo.  
> **Não** é kit para exploração criminosa. Revisar cada `SKILL.md` / fork antes de instalar em agents.

---

## O que é (em português simples)

| Vetor | Analogia | Como monétiza o atacante |
|-------|----------|---------------------------|
| **Sequestro de agente** | Enganar o “estagiário-robô” com texto escondido | Bot de suporte/refund manda dinheiro; research agent vaza dados |
| **Caça DeFi com IA** | Farejador 24/7 de buraco em cofres on-chain | Exploit de contrato → drain de pool |

**Por que 2026:** todo mundo shipa agent com tools; surveys de security citam **agentic AI** como top attack vector; exploração autônoma de SC já é economicamente viável em simulação (CT/Anthropic SCONE).

---

## Inventário do X → GitHub (julho 2026)

### A) Defesa / red team de agentes (prioridade alta)

| Tool / skill | Upstream | Fork local | Uso | Stars (aprox.) |
|--------------|----------|------------|-----|----------------|
| **AgentSeal** | [getagentseal/agentseal](https://github.com/getagentseal/agentseal) | [maux339-cpu/agentseal](https://github.com/maux339-cpu/agentseal) | Scan MCP poisoning, prompt injection resistance, skills perigosas | ~327 |
| **promptfoo** | [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo) | [maux339-cpu/promptfoo](https://github.com/maux339-cpu/promptfoo) | Red team prompts/agents/RAG, CI | ~23k |
| **garak** | [NVIDIA/garak](https://github.com/NVIDIA/garak) | [maux339-cpu/garak](https://github.com/maux339-cpu/garak) | Scanner de vulnerabilidades LLM | ~8.4k |
| **rebuff** | [protectai/rebuff](https://github.com/protectai/rebuff) | [maux339-cpu/rebuff](https://github.com/protectai/rebuff) | Detector de prompt injection | ~1.5k |
| **Strix** | [usestrix/strix](https://github.com/usestrix/strix) | [maux339-cpu/strix](https://github.com/maux339-cpu/strix) | Agentes AI de pentest (web/app) | ~42k |
| **hack-skills** | [yaklang/hack-skills](https://github.com/yaklang/hack-skills) | [maux339-cpu/hack-skills](https://github.com/maux339-cpu/hack-skills) | Pack de `SKILL.md` (incl. AI/LLM + smart contract) | ~1.4k |

### B) DeFi / smart contracts (já no arsenal + Wave 6)

| Tool | Upstream / fork | Papel |
|------|-----------------|-------|
| **Slither** | [maux339-cpu/slither](https://github.com/maux339-cpu/slither) | Análise estática Solidity/Vyper |
| **Echidna** | [maux339-cpu/echidna](https://github.com/maux339-cpu/echidna) | Fuzzer property-based |
| **Foundry** | [maux339-cpu/foundry](https://github.com/maux339-cpu/foundry) | Forge/cast/anvil — test + PoC local |
| **DV DeFi Foundry** | [maux339-cpu/damn-vulnerable-defi-foundry](https://github.com/maux339-cpu/damn-vulnerable-defi-foundry) | Lab autorizado |

### C) Referências (não fork obrigatório)

| Recurso | Notas |
|---------|--------|
| OWASP Top 10 LLM / Agentic | Threat model: injection, tool misuse, goal hijack |
| Anthropic SCONE-bench (CT) | Benchmark de exploração SC com LLMs (pesquisa) |
| DeepMind “AI Agent Traps” | Taxonomia de traps web → agent |
| Giskard OSS | Eval/testing de LLM agents |

### D) Citados no X (avaliar caso a caso)

| Nome | Risco | Nota |
|------|-------|------|
| AgentGuard / Prismor / PipeLock | Médio | Firewall runtime / egress — validar manutenção antes de produção |
| cli-sandbox-guard | Médio | Isolamento de coding agents (sandbox) |
| Claude-Red / pombocyber packs | Alto se ofensivo cego | Skills ofensivas: **só ambiente autorizado** |
| “Solidity Auditor” AI multi-agent | Variável | Muitos clones; preferir stack Slither+Foundry+review humano |

---

## Skills deste repositório

### Defensivas

| Skill | Quando usar |
|-------|-------------|
| [`agent-goal-hijack-defense`](skills/agent-goal-hijack-defense/SKILL.md) | Auditar bot com tools (refund, e-mail, browser) |
| [`prompt-injection-authorized-test`](skills/prompt-injection-authorized-test/SKILL.md) | Red team autorizado de system prompt / agent |
| [`defi-ai-audit-hunt`](skills/defi-ai-audit-hunt/SKILL.md) | Pipeline IA+estático em **seu** contrato / bounty |
| [`agent-privilege-checklist`](skills/agent-privilege-checklist/SKILL.md) | Least privilege + HITL antes de ship |

### Ofensivas (só ROE / bounty / lab)

| Skill | Quando usar |
|-------|-------------|
| [`offensive-agent-prompt-injection`](skills/offensive-agent-prompt-injection/SKILL.md) | Quebrar agent com injection/goal hijack |
| [`offensive-mcp-tool-abuse`](skills/offensive-mcp-tool-abuse/SKILL.md) | MCP poisoning / tool coercion |
| [`offensive-defi-ai-exploit-hunt`](skills/offensive-defi-ai-exploit-hunt/SKILL.md) | Caça SC com IA + Foundry PoC |
| [`offensive-ai-redteam-suite`](skills/offensive-ai-redteam-suite/SKILL.md) | **Índice** de todos os packs ofensivos do arsenal |

---

## Wave 6.1 — packs ofensivos (X + GitHub)

### A) Frameworks / scanners ofensivos (forks novos)

| Fork | Upstream | Uso |
|------|----------|-----|
| [deepteam](https://github.com/maux339-cpu/deepteam) | confident-ai | Red team LLM/agents |
| [agentic_security](https://github.com/maux339-cpu/agentic_security) | msoedov | Scanner agentic / red team kit |
| [hackagent](https://github.com/maux339-cpu/hackagent) | AISecurityLab | Vulns em AI agents |
| [src-hunter-skill](https://github.com/maux339-cpu/src-hunter-skill) | MyuriKanao | Playbooks SRC/bounty + payloads |
| [ai-llm-red-team-handbook](https://github.com/maux339-cpu/ai-llm-red-team-handbook) | Shiva108 | Handbook metodológico |
| [SCONE-bench](https://github.com/maux339-cpu/SCONE-bench) | safety-research | Bench exploit SC + LLM |
| [scone-bench-1](https://github.com/maux339-cpu/scone-bench-1) | anthropics/scone-bench | Bench Anthropic SCONE |

### B) Firewalls (util ofensivo para testar bypass / defesa)

| Fork | Upstream | Uso |
|------|----------|-----|
| [pipelock](https://github.com/maux339-cpu/pipelock) | luckyPipewrench | Firewall MCP/egress |
| [prismor](https://github.com/maux339-cpu/prismor) | PrismorSec | Runtime firewall tool calls |
| [agentguard](https://github.com/maux339-cpu/agentguard) | GoPlusSecurity | Guard runtime agents |

### C) Packs ofensivos já no arsenal (cross-ref X)

| Fork | Papel |
|------|--------|
| [Claude-Red](https://github.com/maux339-cpu/Claude-Red) | 100+ skills red team (`Skills/ai/offensive-ai-security`) |
| [hack-skills](https://github.com/maux339-cpu/hack-skills) | `ai-ml-security` + SC domains |
| [strix](https://github.com/maux339-cpu/strix) | Agents pentest |
| [garak](https://github.com/maux339-cpu/garak) / [promptfoo](https://github.com/maux339-cpu/promptfoo) | LLM red team |
| [Claude-BugHunter](https://github.com/maux339-cpu/Claude-BugHunter) / [recon-skills](https://github.com/maux339-cpu/recon-skills) | BB recon |
| [pombocyber-skills-cybersec](https://github.com/maux339-cpu/pombocyber-skills-cybersec) | Mega pack |
| [web3-bug-bounty-hunting-ai-skills](https://github.com/maux339-cpu/web3-bug-bounty-hunting-ai-skills) / [.context](https://github.com/maux339-cpu/.context) | Web3/SC |

### Playbook ofensivo rápido

```text
Support bot:     offensive-agent-prompt-injection + deepteam + promptfoo
MCP host:        offensive-mcp-tool-abuse + agentseal + pipelock
DeFi SC:         offensive-defi-ai-exploit-hunt + foundry + slither + SCONE
Full LLM RT:     Claude-Red offensive-ai + garak + agentic_security + handbook
BB web:          src-hunter-skill + strix + recon-skills
```

---

## Pipeline recomendado (defesa)

```
1. Inventário de agents (onde rodam, quais tools, quem aprova $)
2. AgentSeal / promptfoo / garak  →  testes de injection + MCP
3. Arquitetura: untrusted = DATA  |  nunca = COMMAND
4. Humano no loop em qualquer gasto/refund/assinatura
5. DeFi: Slither → Foundry tests → Echidna → (opcional) agent review
6. Circuit breaker / pause / multi-sig / time-lock
7. Monitorar deploys novos + alertas Cielo/Arkham se for ops
```

---

## Integração no arsenal

Índice pai: **[arsenal-osint-defi-2026](https://github.com/maux339-cpu/arsenal-osint-defi-2026)** → **Wave 6**.

Forks Wave 6 + 6.1:

```text
# Wave 6
maux339-cpu/agentseal
maux339-cpu/strix
maux339-cpu/hack-skills
maux339-cpu/garak
maux339-cpu/rebuff
# Wave 6.1 ofensivo
maux339-cpu/deepteam
maux339-cpu/agentic_security
maux339-cpu/hackagent
maux339-cpu/src-hunter-skill
maux339-cpu/ai-llm-red-team-handbook
maux339-cpu/SCONE-bench
maux339-cpu/scone-bench-1
# Wave 6.1 firewall
maux339-cpu/pipelock
maux339-cpu/prismor
maux339-cpu/agentguard
# índice
maux339-cpu/agent-hijack-defi-defense-2026
```

Já existentes (cross-ref): `promptfoo`, `slither`, `echidna`, `foundry`, `Claude-Red`, packs web3.

---

## Fontes no X (amostra)

- AgentSeal toolkit (prompt injection + MCP) — posts CT/security  
- Strix AI pentest agents — trending GitHub  
- yaklang/hack-skills — arsenal de `SKILL.md` para agents  
- Zscaler / Threatlabz — agents enganados a processar pagamento  
- Surveys “agentic AI top attack vector 2026”  
- Anthropic SCONE / DeFi exploit agents — narrativa CT  

---

## Disclaimer

Material de **defesa e pesquisa autorizada**. Não use para atacar sistemas sem permissão escrita. Exploração de smart contracts só em ambiente próprio, fork local, testnet ou programa de bounty.

---

## Licença

Documentação deste índice: MIT.  
Cada fork/upstream mantém a licença original.
