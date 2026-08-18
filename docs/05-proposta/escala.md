# Escala — 5 estrelas rotuladas

## Decisão

**5 estrelas com rótulos verbais fixos:**

| Estrelas | Rótulo |
|---|---|
| 1 | Péssima |
| 2 | Ruim |
| 3 | Mais ou menos |
| 4 | Boa |
| 5 | Excelente |

## Por quê

1. **Padrão gov.br.** Portaria SGD/ME 548/2022 art. 7º §1º prevê "escala de cinco pontos". Replicar garante comparabilidade nacional.
2. **CSAT clássico.** Escala de 1–5 é o padrão internacional de Customer Satisfaction Score, com décadas de literatura e benchmark.
3. **Ímpar (ponto neutro).** Escala 5 permite ponto médio ("mais ou menos"), evitando forçar cidadão indeciso para lado positivo ou negativo.
4. **Rótulos verbais.** Reduzem ambiguidade cultural — "3 sem rótulo" pode ser interpretado como "mediano" por alguns e "insatisfeito" por outros.
5. **Estrelas + rótulos = melhor dos dois mundos.** Ícone visual comunica rapidamente (idoso, baixa alfabetização); texto elimina ambiguidade.

## Alternativas descartadas

| Alternativa | Motivo do descarte |
|---|---|
| 0–10 (NPS) | Pergunta "recomendaria" é estranha para serviço público monopolista. |
| 1–7 (Likert estendido) | Ganho analítico marginal, aumenta esforço cognitivo. |
| Binária (👍/👎) | Perde granularidade; não permite série histórica com sensibilidade a variação. |
| Emojis 5 rostos | Testado internacionalmente; funciona, mas rompe padrão gov.br sem ganho claro. |
| Slider 0–100 | Falso senso de precisão; drop-off maior no mobile. |

## Cálculo

- **Nota média** = Σ(nota × frequência) ÷ N.
- **% Satisfeitos (top-2-box)** = (n₄ + n₅) ÷ N × 100.
- Publicar as duas.

## Referência

Ver também: [CSAT](../02-modelos/csat.md), [Comparativo de modelos](../02-modelos/comparativo.md), [Ferramenta gov.br](../03-benchmark/ferramenta-de-avaliacao.md).
