# 2. Referência adotada

## A âncora — gov.br

`[FATO]` A referência principal deste estudo é o **modelo gov.br** de avaliação de serviços digitais, coordenado pela Secretaria de Governo Digital (SGD/MGI) e operado pela Central de Qualidade. O instrumento está normatizado pela **Portaria SGD/MGI nº 1.083, de 14/02/2025** (norma vigente; revisou a Portaria SGD/ME nº 548/2022).

`[FATO]` Indicador atual: **1.047 serviços integrados; nota média 4,39/5** (Central de Qualidade, ago/2026).

`[INTERPRETAÇÃO]` Adotar o modelo gov.br entrega três vantagens imediatas ao Portal MS: linguagem já reconhecida pelo cidadão, alinhamento ao marco normativo federal, e comparabilidade dos indicadores com o resto do país.

## Como o modelo gov.br se organiza

Duas peças complementares:

- **Central de Qualidade** — o guarda-chuva estratégico. Reúne boas práticas, padrões, autodiagnóstico do gestor e painel de gestão. Operada pelo LabQ (Laboratório de Qualidade de Serviços Públicos do Governo Digital Federal).
- **Ferramenta de Avaliação** — a peça operacional. É o formulário exibido ao cidadão + a interface (API) usada pelos órgãos para integrar + o painel do gestor.

Detalhamento técnico em `pesquisa/notas/deep-dives-benchmark.md` (repositório, fora do site).

## O que o cidadão vê no gov.br

`[FATO]` Estrutura do formulário federal em produção:

### Pergunta principal (obrigatória)

> **"Como foi a sua experiência com o serviço?"**

Escala de **5 estrelas com rótulos verbais fixos**:

| Estrelas | Rótulo |
|---|---|
| 1 | Péssima |
| 2 | Ruim |
| 3 | Mais ou menos |
| 4 | Boa |
| 5 | Excelente |

### Pergunta 2 (opcional)

> **"O que você mais gostou em nosso serviço? — Marque até 3 opções"**

Seis cards clicáveis, seleção múltipla até três:

1. Fácil de usar
2. Site/aplicativo funcionou bem
3. Informações claras
4. Consegui resolver
5. Foi rápido
6. Fácil de encontrar

### Comentário aberto (opcional)

> **"Deixe elogio, sugestão ou crítica"**

Placeholder: *"Para que possamos melhorar o serviço, conte-nos sobre sua experiência."* Limite de **2000 caracteres**, com contador visível.

### Bloco de acessibilidade (opcional)

> **"Você se considera uma pessoa com deficiência?"** — Sim / Não.

Bloco visualmente separado, com aviso: *"Para garantir que nossos serviços atendam todas as pessoas, gostaríamos de saber mais sobre você."*

### Envio

Botão único **"Enviar avaliação"** habilita assim que a nota é escolhida.

## Regra jurídica que atravessa todo o instrumento

`[FATO]` **A avaliação nunca pode ser etapa obrigatória da utilização do serviço** — art. 7º, §3º da Portaria SGD/ME nº 548/2022, mantido pela Portaria SGD/MGI nº 1.083/2025. Fechar, pular ou ignorar o convite deve estar sempre disponível, sem prejuízo ao serviço.

Este é o princípio mais importante do modelo. A avaliação é **convite**, não barreira.

## Não confundir dois planos do modelo gov.br

`[INTERPRETAÇÃO]` A Central de Qualidade organiza a qualidade em **7 dimensões que se desdobram em 5 atributos cada** — 35 padrões. Esse instrumento é o **Autodiagnóstico de Maturidade**, usado internamente pelo gestor para avaliar o próprio serviço. **Não são as perguntas apresentadas ao cidadão.**

O cidadão vê 1 pergunta obrigatória + 3 opcionais (nota, 6 cards, comentário, PcD). O gestor trabalha com um instrumento separado, mais estruturado, para plano de ação. Confundir os dois planos leva a formulários gigantes ao cidadão — erro comum e evitável.

## Modelos de escala considerados

Além do modelo gov.br, o estudo revisou os principais modelos de escala usados em serviços digitais para justificar a escolha do CSAT-5 rotulado. Deep-dives técnicos em `pesquisa/notas/deep-dives-modelos.md` (repositório, fora do site).

| Modelo | O que mede | Escala | Adequação a serviço público |
|---|---|---|---|
| **CSAT** (padrão gov.br) | Satisfação transacional | 1–5 rotulada | **Alta** — norma federal + comparabilidade nacional |
| NPS | Lealdade / recomendação | 0–10 | Baixa — cidadão não "escolhe" serviço monopolista |
| CES | Esforço percebido | 1–5 ou 1–7 | Alta como métrica complementar; sobrepõe ao CSAT em serviço simples |
| Likert (base) | Atitude | 5 ou 7 pontos | Média — usada como componente de outros |
| SUS | Usabilidade | 10 itens → 0–100 | Média — instrumento periódico, não contínuo |
| ACSI | Satisfação macro | 3 itens → 0–100 | Alta como benchmark, mas licenciado |
| Estrelas visuais | Sem métrica única | 1–5 | Formato de apresentação — a métrica por trás é CSAT |
| Emojis / Smileys | Sentimento | 2–5 rostos | Alta para público heterogêneo, mas fora do padrão gov.br |
| Thumbs 👍/👎 | Aprovação binária | 2 pontos | Baixa — sem granularidade para série histórica |

`[INTERPRETAÇÃO]` A escolha do gov.br pelo CSAT-5 rotulado é sustentada tecnicamente: ímpar (permite ponto neutro), rotulada (elimina ambiguidade cultural do "3 é bom ou ruim?"), visual (estrelas comunicam rapidamente) e comparável nacionalmente.

## Referências analisadas — cases secundários

Cases privados foram estudados para calibrar boas práticas de UX, momento de coleta e uso da avaliação. **Não substituem o gov.br** — servem como fonte de padrões consolidados na indústria digital.

| Case | Momento | Escala | Diferencial relevante |
|---|---|---|---|
| **gov.br** (âncora) | Ao concluir serviço, convite único não bloqueante | 5 estrelas rotuladas | Bloco de acessibilidade PcD; base legal explícita; anônimo por design no federal |
| GOV.UK | Widget permanente "Is this page useful?" + surveys | Sim / Não + Likert por serviço | Padrão Service Standard obriga medir e publicar mensalmente |
| iFood | Pós-entrega em janela de 7 dias | 5 estrelas + tags | Separa avaliação do restaurante, da entrega e do canal |
| Uber | Pós-viagem, tela bloqueante | 5 estrelas + tags condicionais | **Anti-padrão para serviço público** — bloquear enviesa a amostra |
| Airbnb | 14 dias após check-out | 5 estrelas + subcategorias | Double-blind — reduz retaliação |
| Google Play (In-App) | Card nativo padronizado | 5 estrelas + texto | Anti-fadiga por quota; proíbe pré-screening ("Está gostando?") |
| Amazon | E-mail 5–30 dias pós-entrega | 5 estrelas + texto + mídia | Ponderação por Verified Purchase e recência |

Detalhamento de cada case em `pesquisa/notas/deep-dives-benchmark.md` (repositório, fora do site).

### O que os cases secundários ensinam

1. **CSAT-5 é dominante.** Todos convergem em 1–5 estrelas como métrica principal — reforça a escolha do gov.br.
2. **Momento ancorado no evento.** Todos pedem depois que o cidadão terminou a interação. Padrão consolidado.
3. **Comentário aberto sempre opcional.** Nenhum força texto livre. gov.br segue o mesmo princípio.
4. **Nunca bloquear.** Só o Uber trava a próxima ação — e é criticado por isso. Para serviço público, a regra é lei (art. 7º §3º Portaria 548/2022).
5. **Anti-pré-screening.** Google Play proíbe explicitamente perguntar "Está gostando?" antes de mostrar o formulário. Boa prática ética a preservar.
6. **Publicar em dado aberto.** GOV.UK e gov.br publicam agregados; privados não. Vantagem estrutural do setor público.

### O que o gov.br tem que os cases privados não têm

`[INTERPRETAÇÃO]` Três diferenciais estruturais do modelo federal, essenciais para serviço público:

- **Bloco de acessibilidade (PcD).** Nenhum case privado analisado coleta essa informação.
- **Base legal explícita.** Ancora o formulário em política pública, não em métrica de negócio.
- **Anonimato por design** (no federal). O Portal MS diverge desse ponto por decisão SGD de 2026-08-25 — justificativa em [Dados e privacidade](04-dados-e-privacidade.md).

## Fontes

Consolidadas em [`pesquisa/fontes.md`](pesquisa/fontes.md).
