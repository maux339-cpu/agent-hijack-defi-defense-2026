---
name: defi-ai-audit-hunt
description: >
  Pipeline defensivo IA + estático + fuzz para smart contracts próprios ou
  bug bounty. Combina Slither, Foundry, Echidna e review com LLM. Nunca mainnet
  ofensiva sem autorização.
---

# DeFi AI Audit Hunt (autorizado)

## Quando usar

- Pré-deploy do **seu** protocolo  
- Retainer de audit  
- Bug bounty com regras claras  
- Lab (DV DeFi Foundry, testnet fork)

## Pipeline (ordem)

```
1. Recon código
   - README, deploy scripts, roles, oracles, bridges, upgradeability

2. Estático
   - slither . --filter-paths "lib|node_modules"
   - Classificar High/Medium; ignorar ruído documentado

3. Testes Foundry
   - forge test
   - Invariantes: forge test --match-test invariant
   - Fork local: anvil + forge script (NUNCA private key de prod no agent)

4. Fuzz
   - echidna . --contract <C> --config echidna.yaml
   - Foundry fuzz runs altos em funções de valor

5. Review assistido por LLM (defensivo)
   - Passar trechos com contexto de roles/invariantes
   - Pedir: access control, reentrancy, oracle, first depositor, bridge message trust
   - LLM sugere; humano valida; Foundry prova

6. Relatório
   - Impacto $ simulado em fork
   - Fix + test de regressão
```

## Foco de caça (2025–2026)

| Classe | Por quê |
|--------|---------|
| Bridge / message auth | Maiores drains recentes |
| Oracle / price manipulation | Flash loan + thin liquidity |
| Access control / roles | Admin solto, default admin |
| First depositor / inflation | Vaults ERC4626 |
| Callback / reentrancy | External calls |
| Signature / permit | Phishing + race |

## Regras de ouro

- Agent **nunca** recebe private key de mainnet  
- Explorar só fork local / testnet  
- PoC com Foundry; não “AI disse que é vulnerável” sem prova  
- Circuit breaker / pause nos contratos se você controla o deploy  

## Stack no arsenal

- `slither`, `echidna`, `foundry`, `damn-vulnerable-defi-foundry`  
- Opcional: skills em `hack-skills` (smart contract domain) **só** em alvo autorizado  
- Índice Wave 6: este repo  

## Saída

Tabela de findings + PoC path + severidade + remediação.
