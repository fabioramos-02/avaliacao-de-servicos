# Notas — Modelos de Avaliação (cruas)

Marcadores: `[FATO]` = confirmado por fonte primária/secundária citada. `[INTERPRETAÇÃO]` = leitura minha a partir de fatos. `[HIPÓTESE]` = ainda a validar.
Acesso das fontes: 2026-08-18. Referências completas em `pesquisa/fontes.md`.

---

## NPS (Net Promoter Score)

### Origem
- [FATO] Fred Reichheld, "The One Number You Need to Grow", HBR dez/2003 (Bain & Company + Satmetrix). Marca registrada Bain/Satmetrix/Reichheld.
- [FATO] Alicerçado em pesquisa que correlacionou intenção de recomendação com crescimento de receita em ~20 indústrias.

### Pergunta
- [FATO] "How likely is it that you would recommend [Company/Product/Service] to a friend or colleague?"
- Tradução usual pt-BR: "Em uma escala de 0 a 10, o quanto você recomendaria [X] a um amigo ou colega?"

### Escala
- [FATO] 11 pontos, 0 ("de forma alguma") a 10 ("extremamente provável").

### Cálculo
- [FATO] Segmentação: 0–6 Detratores; 7–8 Neutros/Passivos; 9–10 Promotores.
- [FATO] NPS = %Promotores − %Detratores. Varia de −100 a +100. Neutros são ignorados no cálculo, mas contam no denominador.

### Vantagens
- [FATO] Métrica única, fácil de comunicar.
- [FATO] Benchmarks públicos por setor (Bain, Qualtrics, SurveyMonkey).
- [INTERPRETAÇÃO] Baixo custo cognitivo para o respondente (1 pergunta) → melhor taxa de resposta.

### Limitações
- [FATO] Keiningham et al. (2007, Journal of Marketing) não replicou a alegada "clara superioridade" do NPS vs. ACSI como preditor de crescimento; correlação existe mas é dependente de setor. Paper ganhou o MSI/H. Paul Root Award 2007.
- [FATO] Descarta informação: a diferença entre nota 0 e 6 é 0 no cálculo (ambos detratores) — perde granularidade.
- [FATO/INTERPRETAÇÃO] Viés cultural: culturas latino-americanas tendem a notas altas por cortesia; culturas europeias/asiáticas tendem ao meio da escala — reduz comparabilidade internacional (documentado em literatura de survey research; Bain reconhece parcialmente em guias).
- [FATO] K21/comunidade PM brasileira: NPS falha em serviços obrigatórios/monopolistas (ex.: Receita Federal, DETRAN) — não faz sentido perguntar "recomendaria" para algo sem alternativa.

### Uso em serviços públicos
- [FATO] Adotado por algumas agências públicas (Reino Unido, EUA, Austrália) para serviços em que há alternativa ou comparação com privado.
- [INTERPRETAÇÃO] Uso limitado como métrica única em gov porque a pergunta de recomendação é conceitualmente estranha quando o serviço é único/obrigatório.

### Fontes
Reichheld 2003 HBR; Wikipedia NPS; MeasuringU replication; Keiningham 2007; K21 Brasil.

---

## CSAT (Customer Satisfaction Score)

### Origem
- [FATO] Métrica genérica pré-1990, sem inventor único. Popularizada com o crescimento de CX/call centers nos anos 1990–2000.
- [HIPÓTESE] Provavelmente derivada de práticas de pesquisa de mercado dos anos 1970 (ex.: SERVQUAL, Parasuraman/Zeithaml/Berry 1988) — não confirmado documentalmente aqui.

### Pergunta
- [FATO] "How satisfied were you with [product/service/experience]?"
- pt-BR: "Qual seu nível de satisfação com [serviço/atendimento]?"

### Escala
- [FATO] Mais comum: 1 a 5 (Muito Insatisfeito → Muito Satisfeito). Também 1 a 7 ou 1 a 10.
- [FATO] Variantes com rótulos apenas (sem números), estrelas ou smileys.

### Cálculo
- [FATO] CSAT (%) = (nº respostas "satisfeito" + "muito satisfeito") ÷ total de respostas × 100. Em escala 1–5, considera-se satisfeito quem marcou 4 ou 5 (top-2-box).

### Vantagens
- [FATO] Direto, transacional (mede um momento/interação específica).
- [INTERPRETAÇÃO] Fácil de entender por gestores não-técnicos.
- [FATO] Comparável entre serviços dentro da mesma organização.

### Limitações
- [FATO] Viés de resposta positiva (acquiescência) — pessoas satisfeitas respondem mais.
- [FATO/INTERPRETAÇÃO] Top-2-box descarta nuance da nota 3 (neutro).
- [FATO] Comparabilidade entre setores/países é fraca (falta padrão como ACSI).

### Uso em serviços públicos
- [FATO] Amplamente adotado. Ex.: Portaria SGD/ME 548/2022 (Brasil) padroniza avaliação com escala de 5 níveis (Péssima → Excelente) — variação direta do CSAT com rótulos.
- [FATO] GOV.UK Service Manual usa satisfação como um dos 4 KPIs obrigatórios.

### Fontes
Qualtrics; SmartSurvey; WallStreetPrep; gov.br LabQ; GOV.UK Service Manual.

---

## CES (Customer Effort Score)

### Origem
- [FATO] Matthew Dixon, Karen Freeman, Nicholas Toman — "Stop Trying to Delight Your Customers", HBR jul-ago/2010 (CEB, hoje Gartner).
- [FATO] Base: 75.000+ interações analisadas; redução de esforço prediz lealdade melhor que "encantamento".

### Pergunta
- [FATO] Original (2010): "How much effort did you personally have to put forth to handle your request?" — escala 1–5.
- [FATO] Revisada (CES 2.0, ~2013): "[Empresa] made it easy for me to handle my issue." — escala 1–7 (Discordo Totalmente → Concordo Totalmente).
- pt-BR: "O quanto foi fácil resolver [necessidade] com o [serviço]?"

### Escala
- [FATO] Original: 1–5. Atual (CES 2.0): 1–7 concordância.

### Cálculo
- [FATO] CES = média aritmética das respostas. Alguns fornecedores calculam %top-2-box (concordo/concordo totalmente).

### Vantagens
- [FATO] Bom preditor de retenção/relealdade em contexto de suporte pós-venda.
- [INTERPRETAÇÃO] Aderente à realidade do serviço público, onde "encantar" raramente é o objetivo, mas "não travar" é.
- [FATO] Métrica acionável: aponta atrito operacional.

### Limitações
- [FATO] Foco em pós-atendimento/pós-transação; não mede percepção geral nem lealdade emocional.
- [INTERPRETAÇÃO] "Facilidade" é subjetiva e depende de expectativa do usuário (usuário novato vs. experiente diverge).

### Uso em serviços públicos
- [INTERPRETAÇÃO] Encaixe forte: cidadão quer resolver com mínimo esforço. Alinha com princípio "simples, ágil, resolutivo" da gov.br.
- [FATO] Dimensões "Agilidade" e "Resolutividade" do LabQ/gov.br correspondem conceitualmente a CES.

### Fontes
Dixon et al. 2010 HBR; Formbricks; CustomerSure; gov.br LabQ.

---

## Escala Likert

### Origem
- [FATO] Rensis Likert, 1932 — "A Technique for the Measurement of Attitudes", Archives of Psychology, 22(140).
- [FATO] Estudo original mediu atitudes sobre internacionalismo com escala 5 pontos: (1) Aprovo fortemente ... (5) Desaprovo fortemente.

### Pergunta
- Formato: afirmação + escala de concordância. Ex.: "O serviço atendeu minha necessidade."

### Escala
- [FATO] 5 ou 7 pontos são os mais comuns. Ímpar → inclui neutro; par (forced-choice) → obriga posicionamento.
- [FATO] Literatura debate 5 vs. 7 vs. mais pontos: 7 pontos oferece mais granularidade mas ganho marginal acima disso.

### Cálculo
- [FATO] Cada item é somado ou tirada a média. Não é escala de "opinião única" — é escala psicométrica formada por múltiplos itens (soma).
- [INTERPRETAÇÃO/FATO] Comum uso incorreto: 1 pergunta única "Likert-type" é chamada de "escala Likert", mas tecnicamente Likert = soma de múltiplos itens correlacionados.

### Vantagens
- [FATO] Padrão consolidado; imensa base de literatura psicométrica.
- [FATO] Aceita análise estatística tanto ordinal quanto (com cautela) intervalar.

### Limitações
- [FATO] Viés de acquiescência (tendência a concordar).
- [FATO] Viés de tendência central (evitar extremos), especialmente em culturas asiáticas.
- [FATO] Escalas ímpares dão "saída" via neutro.

### Uso em serviços públicos
- [FATO] Componente-base de vários instrumentos (SUS, ACSI, questionários gov). Não é métrica isolada, é escala de resposta.

### Fontes
Likert 1932; Simply Psychology; QuestionPro; NN/g.

---

## SUS (System Usability Scale)

### Origem
- [FATO] John Brooke, 1996 — "SUS: A quick and dirty usability scale". Digital Equipment Corp.
- [FATO] Domínio público. Uma das escalas de usabilidade mais usadas no mundo.

### Pergunta
- [FATO] 10 afirmações alternando polaridade positiva/negativa. Ex.: "Eu acho que gostaria de usar este sistema com frequência" / "Achei o sistema desnecessariamente complexo".

### Escala
- [FATO] Cada afirmação em Likert 5 pontos (Discordo Totalmente → Concordo Totalmente).

### Cálculo
- [FATO] Itens ímpares (1,3,5,7,9 — positivos): contribuição = posição escolhida − 1.
- [FATO] Itens pares (2,4,6,8,10 — negativos): contribuição = 5 − posição escolhida.
- [FATO] Soma × 2,5 → resultado 0 a 100 (não é percentil).
- [FATO] Score > 68 = acima da média; > 80,3 = "excelente" (Bangor/Sauro).

### Vantagens
- [FATO] Robustez psicométrica validada por décadas.
- [FATO] Benchmark bem estabelecido.
- [FATO] Curto (10 perguntas, ~2 min).

### Limitações
- [FATO] Mede usabilidade percebida, não satisfação com resultado.
- [INTERPRETAÇÃO] 10 perguntas é caro para colocar em fim de fluxo transacional público (drop-off).
- [FATO] Alternância positiva/negativa confunde usuários — variantes como UMUX/UMUX-Lite reduzem.

### Uso em serviços públicos
- [FATO] Usado em auditorias de usabilidade de portais (inclusive GOV.UK, USA.gov).
- [INTERPRETAÇÃO] Melhor como diagnóstico periódico do que como avaliação contínua em cada serviço.

### Fontes
Brooke 1996; ScienceDirect SUS overview.

---

## ACSI / ForeSee (E-Gov Satisfaction Index)

### Origem
- [FATO] ACSI criado em 1994 por Claes Fornell — University of Michigan + ASQ + CFI Group.
- [FATO] Adotado como padrão pelo governo federal dos EUA em 1999 para medir satisfação com serviços públicos.
- [FATO] ForeSee (adquirida pela Verint em 2018) foi parceira histórica no E-Gov Satisfaction Index.

### Pergunta
- [FATO] Três perguntas centrais em escala 1–10:
  1. Satisfação geral com o serviço.
  2. Comparação com expectativa.
  3. Comparação com serviço "ideal".
- [FATO] Modelo econométrico com variáveis-driver (qualidade percebida, expectativas, valor percebido) e outcomes (reclamações, lealdade).

### Escala
- [FATO] 1–10 nas perguntas base. Índice final reportado 0–100.

### Cálculo
- [FATO] Média ponderada das 3 perguntas, transformada em índice 0–100 via modelo econométrico multi-equações proprietário.
- [FATO] Não é simples média: usa equações estruturais.

### Vantagens
- [FATO] Rigor metodológico; benchmark comparável entre indústrias e agências.
- [FATO] Uso oficial no governo federal americano há 25+ anos → série histórica robusta.

### Limitações
- [FATO] Metodologia proprietária (licenciada por CFI Group) — custo.
- [INTERPRETAÇÃO] Complexidade estatística exige capacidade analítica; não é DIY.
- [FATO] Coleta amostral (não censitária), com N grandes para significância.

### Uso em serviços públicos
- [FATO] Padrão nos EUA. Mais de 100 serviços/sites federais medidos.
- [INTERPRETAÇÃO] Referência conceitual útil para MS, mas provavelmente inviável adotar por licenciamento.

### Fontes
ACSI Government; CFI Group Methodology; Wikipedia ACSI.

---

## Estrelas (5 estrelas)

### Origem
- [FATO] Não há inventor único. Herdada de guias/reviews (hotelaria, restaurantes) e popularizada em e-commerce (Amazon anos 1990, iTunes, Netflix pré-2017).

### Pergunta
- Implícita: "Avalie [item]" (sem enunciado formal).

### Escala
- [FATO] 1 a 5 estrelas, com ou sem meia-estrela. Alguns sistemas usam 1–10.

### Cálculo
- [FATO] Média aritmética das estrelas atribuídas + contagem de reviews.

### Vantagens
- [FATO] Universalmente reconhecido; zero fricção cognitiva.
- [FATO] Boa percepção visual (agregação fácil).
- [FATO] Pesquisa Northwestern/Spiegel: produtos com 4,2–4,5 estrelas convertem mais que 5,0 puros (5,0 percebido como suspeito).

### Limitações
- [FATO] Bimodalidade J-shaped: maioria vota 1 ou 5, poucos votos intermediários (viés de auto-seleção; só respondem quem está muito bom ou muito mal).
- [FATO] Ambiguidade semântica: "3 estrelas" significa "médio" ou "ruim"? Varia por cultura/plataforma.
- [INTERPRETAÇÃO] Sem contexto (o que exatamente está sendo avaliado?), a nota é ruído.

### Uso em serviços públicos
- [FATO] Gov.br adotou 5 níveis com rótulos verbais (Péssima → Excelente) — variante de estrelas com rótulos.
- [INTERPRETAÇÃO] Rótulos verbais reduzem ambiguidade da estrela pura.

### Fontes
McKinsey Five-star growth; Northwestern/Spiegel; Appcues.

---

## Emojis / Smileys

### Origem
- [FATO] Emoticons em pesquisa datam dos anos 1970 (Andrews/Withey; escala facial de dor de Wong-Baker, 1988 — uso pediátrico).
- [FATO] Popularização em CX via terminais HappyOrNot (Finlândia, 2009) em aeroportos.

### Pergunta
- Implícita ou "Como foi sua experiência?". Resposta = escolher rosto.

### Escala
- [FATO] 2 a 5 rostos (feliz → triste; ou 5 gradações).

### Cálculo
- [FATO] Contagem/percentual por rosto ou média (se numerado 1–5).

### Vantagens
- [FATO] Universalidade (transcende barreiras de idioma/alfabetização) — validado em escalas de dor (correlação 0,91–0,95 com escalas de referência em cirurgia adulta).
- [FATO] Aumenta taxa de resposta (menor fricção).
- [INTERPRETAÇÃO] Adequado para populações heterogêneas (idosos, baixa escolaridade) — relevante para serviço público brasileiro.

### Limitações
- [FATO] Baixa granularidade → não serve para análise de causa-raiz sozinho.
- [FATO] Interpretação varia por cultura (emoji "sorriso leve" pode ser percebido como sarcasmo em algumas culturas — literatura de HCI).
- [INTERPRETAÇÃO] Percepção "infantil" pode reduzir credibilidade em contexto formal.

### Uso em serviços públicos
- [FATO] Portais europeus (França, Reino Unido, Finlândia) adotaram widgets de smiley em fim de página.
- [FATO] LabQ/gov.br não usa emoji direto (usa rótulos verbais).

### Fontes
QuestionPro; SurveySparrow; PMC/NIH Emoji Faces Pain Scale.

---

## Thumbs up/down (binário)

### Origem
- [FATO] Herança cultural (gestual romano). Digital: YouTube 2009 (substituiu 5 estrelas); Netflix abr/2017 (substituiu 5 estrelas por thumbs; em 2022 adicionou thumbs-up duplo).

### Pergunta
- "Isto foi útil?" / "Gostou?" — resposta binária.

### Escala
- [FATO] 2 pontos: 👍/👎. Ocasionalmente 3 (super-like).

### Cálculo
- [FATO] %positivos = 👍 ÷ (👍 + 👎).

### Vantagens
- [FATO] Menor fricção possível → maior taxa de resposta (Netflix reportou +200% em ratings após migração).
- [FATO] Ótimo para alimentar algoritmos de recomendação (sinal claro).
- [FATO] Útil em micro-feedback (helpful/not helpful em página de ajuda).

### Limitações
- [FATO] Zero granularidade — não distingue "aceitável" de "excelente" nem "ruim" de "péssimo".
- [FATO] Não serve para benchmark externo (não há padrão comparável).
- [INTERPRETAÇÃO] Pode mascarar problemas: 80% 👍 pode significar "ok" ou "excelente" — não sabemos.

### Uso em serviços públicos
- [FATO] Comum em widgets de "Esta página foi útil?" (GOV.UK, USA.gov, gov.br em páginas de conteúdo).
- [INTERPRETAÇÃO] Adequado para feedback de conteúdo (FAQ, manuais), inadequado como métrica principal de serviço transacional.

### Fontes
TechCrunch Netflix 2017; UX Collective; Prototypr; Appcues.

---

## Notas transversais

### GOV.UK Service Manual
- [FATO] Satisfação do usuário é 1 dos 4 KPIs obrigatórios (junto com custo por transação, taxa de conclusão, digital take-up).
- [FATO] Publicação mensal obrigatória.
- [FATO] Não prescreve pergunta única — equipes têm flexibilidade. Recomenda coleta ao fim do fluxo + fontes alternativas (helpdesk, redes sociais).

### Nielsen Norman Group
- [FATO] Recomenda pergunta única de satisfação em escala 1–7 aplicada APÓS uso real.
- [FATO] Diferencia satisfação (subjetiva, pós-uso) de métricas de performance (objetivas, task-completion).

### Portaria SGD/ME 548/2022 (Brasil)
- [FATO] Estabelece padrão de avaliação de satisfação para serviços digitais federais.
- [FATO] Ferramenta LabQ usa escala 5 níveis com rótulos (Péssima, Ruim, Mais ou menos, Boa, Excelente).
- [FATO] Pergunta: "Como foi sua experiência com o serviço?"
- [FATO] Após nota, oferece 6 dimensões para qualificar a avaliação: Privacidade, Transparência, Segurança, Resolutividade, Agilidade, Inclusão.
- [FATO] Voluntária e anônima.
- [INTERPRETAÇÃO] Modelo brasileiro é essencialmente CSAT de 5 níveis + qualificador de dimensão — simples e adequado ao contexto.
