# 5. Indicadores

O que a gestão passa a acompanhar com a avaliação ativa no Portal.

## Indicador principal

**Nota média por serviço (1–5) + % Satisfeitos (nota 4 e 5).**

- **Nota média** = Σ(nota × frequência) ÷ N. Número público na página do serviço.
- **% Satisfeitos** = (n₄ + n₅) ÷ N × 100. Leitura executiva rápida.

Publicar **os dois**. A nota média conversa com o cidadão (comparável ao "4,3 estrelas" que ele conhece de aplicativos). O % Satisfeitos conversa com o gestor (meta clara: ≥ 80%).

`[HIPÓTESE]` **Meta orientativa inicial:** nota média ≥ 4,0 e % Satisfeitos ≥ 80%. Alinha com a referência gov.br (média 4,39/5 sobre 1.047 serviços em ago/2026).

## Indicadores mínimos — disponíveis no go-live

| # | Indicador | Fórmula | Uso |
|---|---|---|---|
| 1 | Nota média | Σ(nota) ÷ N | Número público na página do serviço |
| 2 | % Satisfeitos | (n₄ + n₅) ÷ N × 100 | Leitura executiva |
| 3 | Distribuição das notas | %n₁, %n₂, %n₃, %n₄, %n₅ | Diagnóstico (identifica cauda negativa) |
| 4 | Nº de avaliações no período | count() | Confiabilidade da amostra |

## Indicadores desejáveis — a partir do 3º mês

| # | Indicador | Fórmula | Uso |
|---|---|---|---|
| 5 | Taxa de resposta | avaliações ÷ conclusões de serviço no X-VIA × 100 | Saúde do instrumento |
| 6 | Top motivos positivos | ranking dos 6 cards nas notas 4 e 5 | O que preservar |
| 7 | Ranking de serviços | ordenação por nota média, com N mínimo de 30 | Priorização de melhoria |
| 8 | Variação mensal | média do mês − média do mês anterior | Alerta de queda |
| 9 | % de avaliações de PcD | n_pcd ÷ N × 100 | Recorte de acessibilidade |
| 10 | Nota média por município | agregada por `municipio_servico_ibge`, com N mínimo de 10 por município | Diferenças regionais |
| 11 | Efetividade do convite | avaliações por origem (tela vs. e-mail) ÷ convites emitidos × 100 | Ajuste do disparador e do link único |

## Indicadores propostos para o contrato de gestão

**Proposta a pactuar.** Os valores abaixo são recomendação do estudo e ainda não foram formalizados com as áreas responsáveis pelo contrato de gestão do Governo do Estado. Pendem de pactuação formal.

| # | Indicador proposto | Meta orientativa | Referência |
|---|---|---|---|
| CG1 | Nota média dos serviços do Portal | ≥ 4,0 de 5 | gov.br publicou 4,39/5 sobre 1.047 serviços (ago/2026) |
| CG2 | % de Satisfeitos (notas 4 e 5) | ≥ 80% | Padrão CSAT |
| CG3 | % de serviços com avaliação ativa | ≥ 80% do catálogo publicado | Cobertura do instrumento |
| CG4 | % de serviços com amostra válida (N ≥ 10 no trimestre) | ≥ 60% | Confiabilidade da medição |
| CG5 | % de serviços em alerta tratados no trimestre | ≥ 90% | Fechamento do ciclo de melhoria |

**Duas regras que sustentam estes indicadores:**

- Todo indicador de contrato de gestão precisa ser calculável a partir dos campos do modelo. Nenhum exige coleta adicional.
- Indicador pactuado **não pode depender de campo parametrizável**. Campo novo pode gerar indicador novo; não pode alterar a base de cálculo de um indicador já pactuado no meio de um ciclo.

## Alertas automáticos

- **Queda súbita de nota:** média mensal cai ≥ 0,5 vs. mês anterior → notifica gestor do serviço.
- **Nota baixa recorrente:** média < 3,0 por 2 meses seguidos → escalonamento para SETDIG.
- **Volume anômalo:** N mensal varia > 3× vs. média móvel → investigar (spam ou incidente).
- **Comentário crítico:** detecção de palavra-chave crítica (fraude, ilegal, discriminação) → alerta imediato à Ouvidoria.
- **Fila de triagem acumulada:** mais de 50 comentários novos há mais de 7 dias → notifica Ouvidoria.
- **Meta trimestral não atingida:** CG1 ou CG2 abaixo da meta no fechamento → notifica órgão e SETDIG.

## Painéis (especificação de conteúdo, não desenho)

### Público — página do serviço

- Nota média com contagem: *"★ 4,3 (1.247 avaliações)"*.
- Distribuição em barras (opcional, expansível).
- Corte mínimo N ≥ 10 no período; abaixo disso, *"Amostra ainda insuficiente"*.

### Órgão responsável — restrito ao próprio serviço

- Nota média + % Satisfeitos + N do mês e do mês anterior.
- Distribuição de notas.
- Ranking dos 6 motivos positivos.
- Últimos 50 comentários triados, com filtro por nota.
- Série temporal de 12 meses.
- Distribuição por município.
- Alertas ativos.
- *Identificador do cidadão não aparece no painel* — permanece na base para exercício de direitos do titular e envio do e-mail transacional.

### Ouvidoria Estadual

- Fila de triagem.
- Comentários críticos sinalizados.
- Encaminhamentos abertos por serviço.

### Direção SETDIG

- Ranking geral (10 melhores e 10 piores).
- % de serviços com meta atingida.
- Volume total de avaliações.
- Serviços em alerta.
- Comparativo por Secretaria.

## Cadência

| Ritmo | Ação |
|---|---|
| Tempo real | Coleta e recálculo da nota pública (cache curto) |
| Diário | Ouvidoria triaga comentários novos |
| Semanal | Painel do órgão gera relatório automático |
| Mensal | Reunião de qualidade por órgão |
| Trimestral | Revisão SETDIG do ranking geral; apuração dos indicadores de contrato de gestão |
| Anual | Publicação da série histórica em dados abertos |

## Publicação em dados abertos (fase 2)

Conjunto mensal em `dados.ms.gov.br` (quando maduro):

- Serviço (id, nome, órgão)
- Ano-mês
- Nota média
- N de avaliações
- Distribuição
- % Satisfeitos
- Top 3 motivos positivos
- Nota média por município

**Nunca** publicar dado bruto individual. Corte mínimo ≥ 10 avaliações por agregação. A avaliação é identificada internamente (decisão SGD 2026-08-25), mas painel público e dados abertos só saem em forma agregada, para evitar reidentificação em serviços de baixo volume.

## Referências

- Cadência inspirada em GOV.UK Service Manual (publicação mensal mínima).
- Base legal para publicação: Lei nº 13.460/2017, art. 23.
- Meta calibrada com referência pública do gov.br.
- [Modelo proposto](03-modelo-proposto.md)
- [Dados e privacidade](04-dados-e-privacidade.md)
