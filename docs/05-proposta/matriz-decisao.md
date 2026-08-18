# Matriz de decisão

Comparação estruturada entre as alternativas de modelo consideradas. Score 1 (ruim) a 5 (excelente) por critério.

## Alternativas avaliadas

- **A — Modelo gov.br idêntico** (mesma pergunta, escala, cards, campo aberto, PcD).
- **B — Modelo gov.br + adaptação MS leve** (idêntico ao A + cabeçalho institucional MS + integração com painel próprio).
- **C — Modelo próprio (CSAT + CES + campo aberto)** (2 perguntas quantitativas + texto).
- **D — Modelo enxuto (só estrelas)** (1 pergunta, sem qualificadores, sem campo aberto).

## Critérios e pesos

| Critério | Peso | Justificativa do peso |
|---|---|---|
| Simplicidade para o cidadão | 4 | Determinante da taxa de resposta |
| Taxa de resposta esperada | 4 | Sem resposta, não há dado |
| Qualidade do dado gerado | 4 | Sem dado útil, não há decisão |
| Capacidade analítica gerada | 3 | Habilita gestão baseada em evidência |
| Aderência à LGPD | 5 | Não negociável — risco jurídico |
| Custo operacional | 3 | Manutenção, moderação, painel |
| Aplicabilidade a serviços públicos | 4 | Cases privados nem sempre servem |
| Compatibilidade com gov.br | 5 | Comparabilidade nacional + Portaria 548 |
| Acessibilidade | 4 | Público heterogêneo, PcD |

## Matriz

| Critério (peso) | A (gov.br idêntico) | B (gov.br + MS) | C (próprio) | D (enxuto) |
|---|---|---|---|---|
| Simplicidade cidadão (4) | 5 | 5 | 3 | 5 |
| Taxa resposta esperada (4) | 4 | 4 | 3 | 5 |
| Qualidade do dado (4) | 4 | 5 | 4 | 2 |
| Capacidade analítica (3) | 4 | 5 | 4 | 2 |
| Aderência LGPD (5) | 5 | 5 | 4 | 5 |
| Custo operacional (3) | 4 | 4 | 2 | 5 |
| Aplicabilidade a gov (4) | 5 | 5 | 3 | 3 |
| Compatibilidade gov.br (5) | 5 | 5 | 2 | 3 |
| Acessibilidade (4) | 5 | 5 | 4 | 4 |
| **Score ponderado** | **158** | **163** | **117** | **131** |

## Cálculo detalhado da alternativa vencedora (B)

`5×4 + 4×4 + 5×4 + 5×3 + 5×5 + 4×3 + 5×4 + 5×5 + 5×4 = 20 + 16 + 20 + 15 + 25 + 12 + 20 + 25 + 20 = 163`

## Leitura

- **B vence** por combinar aderência total ao padrão gov.br com adaptação institucional mínima (cabeçalho MS, painel próprio, integração com catálogo de serviços do Portal).
- **A** é praticamente empatado; a diferença fica em `Qualidade do dado` e `Capacidade analítica`, onde ter painel próprio permite drill-down por município, canal, etapa — que a plataforma federal genérica não oferece ao estado.
- **C (modelo próprio)** perde pesado em `Compatibilidade gov.br` e `Aplicabilidade a gov`. Só faria sentido se o estado tivesse hipótese específica que o gov.br não cobre — não é o caso.
- **D (enxuto)** parece atraente pela simplicidade, mas mata a capacidade analítica: sem qualificadores, gestor sabe que serviço é ruim mas não sabe por quê.

## Recomendação

**Alternativa B — Modelo gov.br + adaptação MS leve**.

Ver [Modelo proposto](modelo-proposto.md) para o desenho completo.

## Riscos residuais da alternativa vencedora

- **Dependência do padrão federal.** Se SGD/MGI mudar a Portaria, o MS precisa acompanhar. Mitigação: monitorar publicações da SGD trimestralmente.
- **Painel próprio exige capacidade analítica.** Mitigação: schema conceitual já definido em [Indicadores](indicadores.md) reduz esforço de projeto.
- **Não integração automática com Painel Central de Qualidade federal.** Mitigação: fase 2 explora API `porOrgao` para envio opcional.
