# Comparativo dos Modelos de Avaliação

Tabela para apoio à decisão do PBI 4 (proposta de modelo). Referências em `pesquisa/fontes.md`.

## Tabela comparativa

| Modelo | Pergunta central | Escala | Complexidade de implementação | Adequação para serviço público | Benchmark disponível | Melhor para |
|---|---|---|---|---|---|---|
| **NPS** | "Recomendaria a um amigo?" | 0–10 (11 pontos) | Baixa | Baixa/Média — pergunta estranha para serviço obrigatório | Alto (Bain, Qualtrics, setor) | Percepção relacional do portal como marca |
| **CSAT** | "Qual sua satisfação?" | 1–5 (rótulos) | Baixa | **Alta — padrão gov.br (Portaria 548/2022)** | Médio (interno gov.br) | Avaliação transacional pós-serviço |
| **CES** | "Foi fácil resolver?" | 1–5 ou 1–7 | Baixa | Alta — cidadão quer resolver com mínimo esforço | Baixo/Médio (Gartner, indústria) | Diagnosticar atrito em serviços digitais |
| **Likert (base)** | Múltiplas afirmações | 5 ou 7 pontos | Média (bateria de itens) | Média — usada como componente de outros | N/A (é escala, não métrica) | Compor instrumentos maiores (SUS, ACSI) |
| **SUS** | 10 afirmações fixas | Likert 1–5 → 0–100 | Média/Alta (10 perguntas) | Média — bom para diagnóstico periódico | **Alto** (score 68 = média; 80,3 = excelente) | Auditoria de usabilidade (não recorrente) |
| **ACSI** | 3 perguntas (satisfação, expectativa, ideal) | 1–10 → índice 0–100 | Alta (modelo econométrico) | Alta (padrão federal EUA) mas **licenciado (CFI Group)** | Alto (série histórica gov EUA) | Índice macro comparável entre agências |
| **Estrelas** | Implícita | 1–5 estrelas | Muito baixa | Média — sem rótulos vira ruído; com rótulos vira CSAT | Alto (e-commerce) | Avaliação leve de conteúdo/item |
| **Emojis/Smileys** | "Como foi sua experiência?" | 2–5 rostos | Muito baixa | Alta para público heterogêneo/baixa escolaridade | Baixo (proprietário HappyOrNot) | Coleta rápida em ponto de contato |
| **Thumbs 👍/👎** | "Foi útil?" | Binária | Muito baixa | Média — só para conteúdo, não para serviço transacional | Baixo | Feedback de FAQ/página de ajuda |

## Leitura resumida

- **NPS** é péssima escolha como métrica principal em serviços obrigatórios, mas pode servir para avaliar o **portal como marca**.
- **CSAT** (padrão gov.br) e **CES** são os mais indicados para avaliação **transacional** de cada serviço.
- **SUS** vale como **diagnóstico periódico** de usabilidade — não substitui métrica contínua.
- **ACSI** é referência conceitual, mas inviável adotar diretamente por licenciamento.
- **Estrelas/emojis/thumbs** são **formatos de apresentação** — a métrica por trás continua sendo CSAT ou binária.

## Recomendação preliminar para MS

Combinação candidata (a validar no PBI 4):

1. **CSAT-5 níveis com rótulos verbais** (compatível gov.br): pergunta principal em cada serviço.
2. **CES simplificado** (1 pergunta 1–5 sobre facilidade): complemento em serviços transacionais.
3. **Campo aberto opcional** para comentário livre.
4. **Dimensões qualificadoras** (privacidade, agilidade, resolutividade — modelo LabQ) após a nota.
5. **NPS aplicado ao portal** (não a cada serviço): coleta periódica separada.
6. **SUS** ou similar: auditoria trimestral/semestral, não avaliação contínua.
