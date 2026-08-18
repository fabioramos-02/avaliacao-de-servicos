# NPS — Net Promoter Score

## O que é

Métrica de lealdade e propensão a recomendar, criada por Fred Reichheld em 2003 (Bain & Company + Satmetrix), publicada no artigo "The One Number You Need to Grow" (Harvard Business Review, dez/2003). Marca registrada de Bain/Satmetrix/Reichheld.

## Pergunta padrão

- Original: *"How likely is it that you would recommend [company/product/service] to a friend or colleague?"*
- pt-BR: *"Em uma escala de 0 a 10, o quanto você recomendaria [serviço] a um amigo ou colega?"*

## Escala

11 pontos, de 0 ("de forma alguma") a 10 ("extremamente provável").

## Como calcular

1. Classificar respostas em três grupos:
   - **Detratores:** notas 0 a 6
   - **Neutros/Passivos:** notas 7 e 8
   - **Promotores:** notas 9 e 10
2. Calcular: **NPS = %Promotores − %Detratores**
3. Resultado varia de −100 a +100. Neutros não entram no cálculo, mas contam no denominador.

Exemplo: 100 respostas → 60 promotores, 20 neutros, 20 detratores → NPS = 60% − 20% = **+40**.

## Quando usar

- Avaliação **relacional** (percepção geral após múltiplas interações) mais do que transacional.
- Quando existe **comparabilidade externa** relevante (benchmarks públicos).
- Serviços com **alternativa/escolha** por parte do usuário.

## Vantagens

- Métrica única, fácil de comunicar para gestão.
- Benchmarks públicos por setor (Bain, Qualtrics, SurveyMonkey).
- Baixa fricção: 1 pergunta.
- Amplamente adotado → linguagem comum entre organizações.

## Limitações

- **Fragilidade estatística:** Keiningham et al. (2007, Journal of Marketing, premiado MSI/H. Paul Root Award) não replicou a alegada superioridade preditiva do NPS sobre o ACSI. Correlação com crescimento existe mas é dependente de setor.
- **Perda de informação:** notas 0 e 6 têm peso idêntico no cálculo (ambas detratoras), descartando granularidade.
- **Viés cultural:** brasileiros tendem a notas altas (cortesia); europeus/asiáticos ao meio da escala — comparabilidade internacional fica prejudicada.
- **A "linha zero":** score pode ser negativo mesmo com maioria satisfeita (ex.: 50% notas 7–8 e 50% notas 0–6 → NPS = −50), o que pode ser politicamente sensível em contexto público.

## Adequação para serviço público

**Baixa a média.** A pergunta "recomendaria" é conceitualmente estranha para serviços obrigatórios ou monopolistas (Receita Federal, DETRAN, expedição de documentos) — o cidadão não tem alternativa a quem recomendar.

Faz mais sentido em:

- Serviços onde há alternativa (público × privado, presencial × digital).
- Avaliação do **portal como um todo**, não de serviços individuais.
- Complemento a CSAT/CES, nunca como métrica única em gov.

Ministérios brasileiros predominantemente usam **CSAT** (padrão gov.br), não NPS.

## Fontes

- Reichheld (2003). "The One Number You Need to Grow." *Harvard Business Review*, dez/2003.
- Keiningham et al. (2007). "A Longitudinal Examination of Net Promoter and Firm Revenue Growth." *Journal of Marketing*, 71(3).
- Bain & Company — Net Promoter System.

Lista completa e URLs em `pesquisa/fontes.md`.
