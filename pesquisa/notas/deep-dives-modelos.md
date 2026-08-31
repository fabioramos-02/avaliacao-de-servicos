# Deep-dives — modelos de avaliação

> Material técnico de pesquisa. Consolidação dos deep-dives originais em `docs/02-modelos/` (NPS, CSAT, CES), movidos para cá durante a consolidação de 2026-08-28. A síntese executiva vive em `docs/02-referencia.md` (seção "Modelos de escala").

---

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

---

# CSAT — Customer Satisfaction Score

## O que é

Métrica de satisfação transacional, usada para avaliar o quão satisfeito o usuário ficou com uma interação específica (um atendimento, o uso de um serviço, uma compra). Não tem inventor único; consolidou-se em práticas de CX/call centers desde os anos 1990.

## Pergunta padrão

- Original: *"How satisfied were you with [product/service/experience]?"*
- pt-BR: *"Qual seu nível de satisfação com [serviço/atendimento]?"*
- Variante gov.br (Portaria SGD/ME 548/2022): *"Como foi sua experiência com o serviço?"*

## Escala

Mais comum: **1 a 5** (Muito Insatisfeito → Muito Satisfeito). Também 1 a 7 ou 1 a 10.

Variantes de apresentação:
- Números com rótulos verbais.
- Estrelas (1–5).
- Smileys (2 a 5 rostos).
- Modelo gov.br: rótulos verbais — Péssima / Ruim / Mais ou menos / Boa / Excelente.

## Como calcular

**Top-2-box (padrão):**

CSAT (%) = (respostas "satisfeito" + "muito satisfeito") ÷ total de respostas × 100

Em escala 1–5, considera-se satisfeito quem marcou **4 ou 5**.

**Média (alternativo):** média aritmética das notas (ex.: 4,2 de 5).

## Quando usar

- Avaliação **transacional** (imediatamente após conclusão de um serviço).
- Quando se quer medir **um momento específico** da jornada (não a percepção geral).
- Como métrica **contínua** e de fácil comparação entre serviços da mesma organização.

## Vantagens

- Simples de entender e comunicar.
- Baixíssima fricção (1 pergunta).
- Comparável entre serviços dentro da mesma organização.
- Formato flexível (estrelas, smileys, rótulos) → adaptável ao público.
- **Padrão brasileiro:** compatível com Portaria SGD/ME 548/2022.

## Limitações

- **Viés de resposta positiva:** pessoas satisfeitas tendem a responder mais que insatisfeitas moderadas (auto-seleção).
- **Top-2-box descarta a nota 3** (neutra), gerando distorção quando muita gente está "razoavelmente satisfeita".
- **Comparabilidade externa fraca** (não há padrão internacional único como o ACSI).
- Não distingue **causa** da satisfação — precisa de perguntas complementares (dimensões, campo aberto).

## Adequação para serviço público

**Alta.** É o modelo dominante em gov digital no Brasil e amplamente usado internacionalmente:

- Portaria SGD/ME 548/2022 padroniza CSAT de 5 níveis com rótulos para todos os serviços federais.
- GOV.UK Service Manual exige satisfação como 1 dos 4 KPIs obrigatórios.
- ACSI (macro) é um refinamento estatístico do CSAT.

Adequações típicas para gov:
- Rótulos verbais em vez de números puros (reduz ambiguidade).
- Complementar com **dimensões qualificadoras** (privacidade, agilidade, resolutividade — modelo LabQ/gov.br).
- Aplicar **ao final do fluxo digital** e, quando possível, novamente ao final da jornada completa.

## Fontes

- Qualtrics — "What is CSAT and How Do You Measure It?"
- SmartSurvey — "How To Calculate CSAT."
- Gov.br / SGD — Ferramenta LabQ de Avaliação.
- Portaria SGD/ME nº 548, de 24/01/2022.

Lista completa e URLs em `pesquisa/fontes.md`.

---

# CES — Customer Effort Score

## O que é

Métrica de esforço percebido pelo usuário para resolver sua necessidade. Criada por Matthew Dixon, Karen Freeman e Nicholas Toman (CEB, hoje Gartner) e publicada no artigo *"Stop Trying to Delight Your Customers"* (Harvard Business Review, jul-ago/2010).

A pesquisa original, com 75.000+ interações, mostrou que **reduzir esforço** prediz lealdade melhor do que "encantar" o cliente.

## Pergunta padrão

- **CES 1.0 (2010):** *"How much effort did you personally have to put forth to handle your request?"* — escala 1–5 (esforço alto → baixo).
- **CES 2.0 (~2013, versão atual):** *"[Empresa] made it easy for me to handle my issue."* — escala 1–7 (Discordo Totalmente → Concordo Totalmente).
- pt-BR sugerido: *"Foi fácil resolver [necessidade] usando o [serviço]?"*

## Escala

- Versão atual (CES 2.0): **1 a 7**, formato de concordância.
- Versão original (CES 1.0): 1 a 5, formato de esforço direto.

## Como calcular

**Média aritmética:**

CES = soma das respostas ÷ nº de respostas

**Alternativa top-box:** % de respostas 6 ou 7 (concordo/concordo totalmente) na escala 1–7.

Não existe valor absoluto "bom" universal — deve ser acompanhado ao longo do tempo, comparando o mesmo serviço consigo mesmo.

## Quando usar

- Avaliação **imediatamente após** conclusão de um serviço ou interação com suporte.
- Quando o objetivo é reduzir atrito operacional (não medir encantamento).
- Como métrica **acionável**: baixa nota aponta diretamente para pontos de fricção.

## Vantagens

- Preditor forte de retenção e recompra em contexto de suporte pós-venda.
- **Alta aderência a serviço público:** cidadão quer resolver com mínimo esforço, raramente busca "encantamento".
- Aponta atrito operacional específico → orienta melhoria.
- Simples (1 pergunta).

## Limitações

- Foco em pós-atendimento/pós-transação; não mede lealdade emocional nem satisfação geral.
- "Facilidade" é subjetiva: usuário novato e experiente respondem diferente para o mesmo serviço.
- Menor base de benchmarks públicos que NPS/CSAT.
- Escala de 7 pontos pode ser confusa em populações de baixa escolaridade — versão 5 pontos ou emoji pode adaptar.

## Adequação para serviço público

**Alta**, especialmente para serviços transacionais. O modelo brasileiro (LabQ/gov.br) já reflete a lógica CES ao incluir **"Agilidade"** e **"Resolutividade"** como dimensões qualificadoras da avaliação — são traduções conceituais diretas do esforço percebido.

Recomendações para adoção:
- Usar como métrica **complementar ao CSAT**, não substituta.
- Escala 1–5 com rótulos verbais (ex.: "Muito difícil" → "Muito fácil") para acessibilidade.
- Aplicar imediatamente após o fim do fluxo digital.

## Fontes

- Dixon, Freeman, Toman (2010). "Stop Trying to Delight Your Customers." *Harvard Business Review*, jul-ago/2010.
- Formbricks — "Customer Effort Score: Questions, Formula & Benchmarks."
- CustomerSure — Guia CES.

Lista completa e URLs em `pesquisa/fontes.md`.
