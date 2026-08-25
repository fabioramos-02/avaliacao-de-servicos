# Indicadores

O que a gestão passa a acompanhar com a avaliação ativa no Portal.

## Métrica principal

**Nota média por serviço (1–5) + % Satisfeitos (top-2-box)**

- **Nota média** = Σ(nota × frequência) ÷ N. Headline público na página do serviço.
- **% Satisfeitos** = (n₄ + n₅) ÷ N × 100. Leitura executiva rápida.

Publicar **os dois**. Nota média fala com o cidadão (comparável ao "4,3 estrelas" que ele conhece de apps). % Satisfeitos fala com o gestor (meta clara: ≥ 80%).

**Meta orientativa inicial:** nota média ≥ 4,0 e % Satisfeitos ≥ 80%. Alinha com o benchmark gov.br (média 4,39/5 em ago/2026 sobre 1.047 serviços).

## Indicadores mínimos (do dia 1)

| # | Indicador | Fórmula | Uso |
|---|---|---|---|
| 1 | Nota média | Σ(nota) ÷ N | Headline público |
| 2 | % Satisfeitos | (n₄+n₅) ÷ N × 100 | Meta executiva |
| 3 | Distribuição das notas | %n₁, %n₂, %n₃, %n₄, %n₅ | Diagnóstico (cauda ruim?) |
| 4 | Nº de avaliações no período | count() | Confiabilidade da amostra |

## Indicadores desejáveis (mês 3)

| # | Indicador | Fórmula | Uso |
|---|---|---|---|
| 5 | Taxa de resposta | avaliações ÷ conclusões × 100 | Saúde do instrumento |
| 6 | Top motivos positivos | ranking dos 6 cards nas notas 4+5 | O que preservar |
| 7 | Ranking de serviços | ordena por nota média (com N mínimo = 30) | Priorização de melhoria |

## Indicadores evolutivos (ano 1)

| # | Indicador | Fórmula | Uso |
|---|---|---|---|
| 8 | Variação mensal | (média mês − média mês-1) | Alerta de queda |
| 9 | % comentários críticos | regex simples em campo aberto | Sinal qualitativo |
| 10 | % avaliações de PcD | n_pcd ÷ N × 100 | Recorte de acessibilidade |

## Alertas automáticos

- **Queda súbita:** média mensal cai ≥ 0,5 vs. mês anterior → notifica gestor do serviço.
- **Nota baixa recorrente:** média < 3,0 por 2 meses seguidos → escalonamento para SETDIG.
- **Volume anômalo:** N mensal cresce ou cai > 3× vs. média móvel → investigar (spam ou incidente).
- **Comentário crítico:** regex de palavras-chave (fraude, ilegal, discriminação) → alerta imediato à Ouvidoria.

## Dashboard mínimo

### Público (página do serviço)

- Nota média com contagem: "★ 4,3 (1.247 avaliações)"
- Distribuição em barras (opcional)
- Link "Ver comentários públicos" (após moderação)

### Gestor do serviço (restrito)

- Nota média + % satisfeitos + N (mês atual e comparação mês anterior)
- Distribuição de notas
- Ranking dos 6 motivos positivos
- Últimos 50 comentários abertos com filtro por nota
- Série temporal 12 meses
- Alertas ativos

### Direção SETDIG (restrito)

- Ranking geral de serviços (top 10 melhores, top 10 piores)
- % de serviços com meta atingida
- Volume total de avaliações
- Serviços em alerta
- Comparativo por Secretaria

### Ouvidoria (restrito)

- Fila de comentários novos para triagem
- Comentários críticos flagados por regex
- Encaminhamentos abertos por serviço

## Publicação em dados abertos (fase 2)

Dataset mensal em `dados.ms.gov.br` (quando maduro):

- Serviço (id, nome, órgão)
- Ano-mês
- Nota média
- N avaliações
- Distribuição
- % Satisfeitos
- Top 3 motivos positivos

Nunca publicar dado bruto individual — apenas agregado ≥ 10 avaliações por corte. A avaliação é identificada internamente (decisão SGD 2026-08-25), mas painel público e dados abertos só saem em forma agregada, para evitar reidentificação em serviços de baixo volume.

## Referência

- Cadência inspirada em GOV.UK Service Manual (publicação mensal mínima).
- Base legal para publicação: Lei 13.460/2017 art. 23.
- Meta calibrada com benchmark público do gov.br.
