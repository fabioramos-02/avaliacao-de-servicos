# Modelos de Avaliação de Satisfação — Visão Geral

Documento de referência do PBI 1. Mapeia os principais modelos usados em serviços digitais e serviços públicos, com foco em aplicabilidade ao Portal de Serviços do MS.

Fontes consolidadas em `pesquisa/fontes.md`. Notas cruas em `pesquisa/notas/modelos.md`.

## Escopo

Foram investigados nove modelos, agrupados em três categorias:

- **Métricas de CX/loyalty:** NPS, CSAT, CES.
- **Instrumentos psicométricos:** Escala Likert (base), SUS (usabilidade), ACSI (macroíndice).
- **Formatos de coleta simples:** Estrelas, Emojis/Smileys, Thumbs up/down.

## Tabela-resumo

| Modelo | O que mede | Escala | Pergunta central |
|---|---|---|---|
| NPS | Lealdade / recomendação | 0–10 (11 pontos) | "O quanto você recomendaria este serviço?" |
| CSAT | Satisfação transacional | 1–5 (ou 1–7) | "Qual seu nível de satisfação?" |
| CES | Esforço percebido | 1–5 ou 1–7 | "Foi fácil resolver sua necessidade?" |
| Likert | Atitude/opinião (base) | 5 ou 7 pontos, agree-disagree | Múltiplos itens somados |
| SUS | Usabilidade percebida | 10 itens Likert 1–5 → 0–100 | Bateria fixa de 10 afirmações |
| ACSI | Satisfação (macro, governo) | 1–10 (3 perguntas) → índice 0–100 | Modelo econométrico multi-equações |
| Estrelas | Satisfação/qualidade | 1–5 estrelas | Implícita: "avalie" |
| Emojis/Smileys | Sentimento | 2–5 rostos | "Como foi sua experiência?" |
| Thumbs 👍/👎 | Aprovação binária | 2 pontos | "Foi útil? / Gostou?" |

## Como escolher

Três critérios governam a escolha em contexto de serviço público:

1. **Momento na jornada:** transacional (fim de fluxo) → CSAT/CES/estrelas. Relacional (percepção geral do órgão) → NPS/ACSI. Diagnóstico de usabilidade (não recorrente) → SUS.
2. **Público-alvo:** heterogêneo, com baixa escolaridade e idosos → emojis/smileys/estrelas com rótulos verbais. Público segmentado (ex.: servidores, empresas) → Likert/CES.
3. **Comparabilidade desejada:** benchmark internacional → NPS ou ACSI. Comparação interna entre serviços → CSAT padronizado (modelo gov.br).

## Referência brasileira

O governo federal padronizou a avaliação via **Portaria SGD/ME nº 548/2022** e a ferramenta do **LabQ (gov.br)**:

- Escala CSAT de 5 níveis com rótulos verbais: Péssima, Ruim, Mais ou menos, Boa, Excelente.
- Pergunta: *"Como foi sua experiência com o serviço?"*
- Após a nota, o usuário pode qualificar a avaliação em 6 dimensões: Privacidade, Transparência, Segurança, Resolutividade, Agilidade, Inclusão.
- Coleta voluntária e anônima.

Esse modelo é o principal candidato a referência para o MS por compatibilidade institucional e comparabilidade com outros portais estaduais/federais.

## Próximos passos (PBIs seguintes)

- **PBI 2 (Benchmark):** analisar como iFood, Uber, Amazon, Netflix operacionalizam a coleta (momento, UI, uso posterior).
- **PBI 3:** definir dimensões e perguntas alinhadas aos objetivos do MS.
- **PBI 4:** propor modelo híbrido (provável base CSAT gov.br + CES + campo aberto opcional).

## Arquivos relacionados

- `docs/02-modelos/nps.md`
- `docs/02-modelos/csat.md`
- `docs/02-modelos/ces.md`
- `docs/02-modelos/comparativo.md`
